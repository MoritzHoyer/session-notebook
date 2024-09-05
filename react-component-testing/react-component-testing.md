# React Komponententests

## Lernziele

- [ ] Verständnis der Idee von Komponententests
- [ ] Wissen, wie man
  - eine React-Komponente in Tests rendert
  - Interaktionen mit einer gerenderten React-Komponente in Tests simuliert
  - nach erwarteten Elementen in der gerenderten React-Komponente sucht
  - erwartete Ergebnisse formuliert
- [ ] Ein allgemeines Verständnis für Mocks haben

---

## Warum es sinnvoll ist, Frontend zu testen

Beim Entwickeln von Apps müssen wir sie regelmäßig testen, um sicherzustellen, dass alles wie erwartet funktioniert und um Bugs zu finden, bevor es die Benutzer tun.

Manuelles Testen der App über die Benutzeroberfläche ist zeitaufwendig und unzuverlässig. Das Rendern eines Teils der Benutzeroberfläche und das Simulieren von Interaktionen kann in Komponententests automatisiert werden.

Dieser Ansatz versucht, mit der App auf die gleiche Weise zu interagieren wie ein echter Benutzer, indem er in der gerenderten App nach bestimmten Elementen sucht:

- Suche nach einer Überschrift mit bestimmtem Inhalt
- Suche nach Eingabefeldern mit bestimmten Labels und Einfügen von Text
- Suche nach einem Button mit einem bestimmten Label und Klicken zum Absenden eines Formulars
- Suche nach einem erwarteten Ergebnis, das nach dem Absenden angezeigt werden sollte

Wir können solche Tests für jede React-Komponente in unserem Code schreiben.

In einer früheren Sitzung haben wir uns Unit-Tests angesehen, die sich auf eine einzelne Funktion oder Einheit konzentrieren. Komponententests fallen in die Kategorie der Integrationstests, da sie testen, wie verschiedene einzelne Funktionen zusammenarbeiten, um ein Ergebnis auf den Bildschirmen der Benutzer zu erzeugen.

Anstatt die gesamte App oder eine vollständige Seite zu testen (dies wäre End-to-End-Testing), erstellen wir getrennte kleinere Tests für einzelne Komponenten.

Wir platzieren die Datei, die die Tests enthält, direkt neben der Komponentendatei mit der Endung `.test.js`.

```
MyComponent
├── MyComponent.styled.js
├── MyComponent.test.js
└── index.js
```

---

## Testing Library

Die [Testing Library](https://testing-library.com/docs/react-testing-library/intro) ermöglicht es uns, React-Komponenten in Jest-Tests zu rendern, Benutzerverhalten zu simulieren und die Ergebnisse nach dem erneuten Rendern der Komponente zu überprüfen.

### Beispiel

##### FahrenheitConverter.js

Die Komponente `FahrenheitConverter` rendert eine Überschrift, ein Formular und ein Ergebnisausgabe. Wenn das Formular noch nicht abgeschickt wurde, wird eine alternative Nachricht anstelle des Ergebnisses angezeigt. Nachdem das Formular abgeschickt wurde, wird die Berechnung durchgeführt und das Ergebnis im State gespeichert. Dies löst ein erneutes Rendern der Komponente aus, sodass das Ergebnis angezeigt wird.

```jsx
import { useState } from "react";

export default function FahrenheitConverter() {
  const [fahrenheit, setFahrenheit] = useState();

  function handleSubmit(event) {
    event.preventDefault();

    const form = event.target;
    const formElements = form.elements;
    const celsius = formElements.celsius.value;

    setFahrenheit((celsius * 9) / 5 + 32);
  }

  return (
    <div>
      <h1>Temperature Unit Converter</h1>
      <form onSubmit={handleSubmit}>
        <label htmlFor="celsius">°C</label>
        <input type="number" id="celsius" name="celsius" />
        <button>Convert to Fahrenheit</button>
      </form>
      {fahrenheit ? (
        <output>{fahrenheit} °F</output>
      ) : (
        <p>Please enter a Celsius value and submit</p>
      )}
    </div>
  );
}
```

##### FahrenheitConverter.test.js

Es gibt drei Tests für diese Komponente:

1. Test, dass die Überschrift angezeigt wird
2. Test, dass die alternative Nachricht angezeigt wird, bevor das Formular abgeschickt wurde
3. Test, dass die Formularinteraktion und das Abschicken funktionieren, das Ergebnis korrekt berechnet und anstelle der alternativen Nachricht angezeigt wird.

```jsx
import { render, screen } from "@testing-library/react";
import userEvent from "@testing-library/user-event";
import FahrenheitConverter from ".";

test("renders a heading", () => {
  render(<TemperatureUnitConverter />);
  const heading = screen.getByRole("heading", {
    name: /temperature unit converter/i,
  });
  expect(heading).toBeInTheDocument();
});

test("renders a fallback message if form is not yet submitted", () => {
  render(<FahrenheitConverter />);
  const message = screen.getByText(/please enter a celsius value and submit/i);
  expect(message).toBeInTheDocument();
});

test("converts Celsius to Fahrenheit and renders the result", async () => {
  const user = userEvent.setup();

  render(<FahrenheitConverter />);

  const input = screen.getByLabelText(/°C/i);
  expect(input).toBeInTheDocument();

  const button = screen.getByRole("button", { name: /convert to fahrenheit/i });
  expect(button).toBeInTheDocument();

  await user.type(input, "5");
  await user.click(button);

  const output = screen.getByText(/41 °F/i);
  expect(output).toBeInTheDocument();

  const message = screen.queryByText(
    /please enter a celsius value and submit/i
  );
  expect(message).not.toBeInTheDocument();
});
```

### Komponente rendern

Mit der [`render`](https://testing-library.com/docs/react-testing-library/api#render) Methode kannst du die `FahrenheitConverter` Komponente initial rendern. Danach kannst du die Methode [`screen`](https://testing-library.com/docs/queries/about/#screen) verwenden, um auf das von der Komponente generierte HTML zuzugreifen.

### Verwendung von Queries

Mit [`screen`](https://testing-library.com/docs/queries/about/#screen) kannst du Queries verwenden, um nach bestimmten Elementen zu suchen, die du im generierten HTML erwartest.

| Query                                                                 | Description                                                                                                                   |
| --------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [`ByRole`](https://testing-library.com/docs/queries/byrole)           | Search for an element based on their `role` / `aria-*` attribute (for example `button`, `textbox`, `heading`)                 |
| [`ByLabelText`](https://testing-library.com/docs/queries/bylabeltext) | Search for an element (like an input field) with a given label                                                                |
| [`ByText`](`https://testing-library.com/docs/queries/bytext`)         | Search for a given text                                                                                                       |
| [`ByTestId`](https://testing-library.com/docs/queries/bytestid)       | Last resort to search for an element you can't address with other queries. Mark the element with the attribute `data-testid`. |

In den meisten Fällen solltest du Queries mit `getBy` verwenden, um sofort zu scheitern, wenn das Element nicht gefunden wird. Manchmal möchtest du testen, ob etwas nicht angezeigt wird. Verwende in diesem Fall `queryBy`, da es den Test nicht sofort scheitern lässt, sondern `null` zurückgibt.

Du kannst einen String verwenden, um einen zu suchenden Text zu definieren, wie zum Beispiel: `getByText("Text hier")`.

Du kannst den Text auch in Schrägstriche setzen, gefolgt von einem `i`, _anstatt von_ Anführungszeichen für einen String, wie `getByText(/text hier/i)`.

Dies macht deine Tests widerstandsfähiger gegenüber Änderungen in der Implementierung: `getByText("Text hier")` würde beginnen zu scheitern, wenn sich die Groß-/Kleinschreibung in der Komponente ändern würde. Deshalb ist dies eine sehr übliche Konvention beim Schreiben von Tests. Auch wenn `/text hier/i` auf den ersten Blick seltsam aussieht, wirst du dich schnell daran gewöhnen.

Der Ausdruck, der in Schrägstriche eingeschlossen ist (`/hello world/`), wird als [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) bezeichnet. Der `i`-Modifikator am Ende sagt dem regulären Ausdruck, dass Unterschiede zwischen Groß- und Kleinschreibung ignoriert werden sollen. Reguläre Ausdrücke werden häufig verwendet, um Dinge in großen Strings zu suchen und sind sehr mächtig. Du musst sie jedoch nicht tiefer verstehen, als hier gezeigt, um deine Tests zu schreiben.

Die Verwendung des [Testing Playground](https://testing-playground.com/) hilft dir beim Schreiben von Queries.

### Benutzerereignisse simulieren

Du kannst [simulieren, wie Benutzer interagieren](https://testing-library.com/docs/user-event/intro) mit der Komponente. Zuerst musst du einen virtuellen Benutzer mit `userEvent.setup()` einrichten. Dann kannst du Ereignisse wie `type` oder `click` simulieren. Vergiss nicht, `await` mit Benutzereignissen zu verwenden.

### Verwendung von Matchern

Mit [`expect`](https://jestjs.io/docs/expect) kannst du [Matcher](https://jestjs.io/docs/using-matchers) verwenden, um ein erwartetes Ergebnis deines Tests zu formulieren: Es ist dasselbe Konzept wie beim Unit-Testing.

Da wir in Komponententests HTML generieren, kannst du einige [zusätzliche Matcher](https://github.com/testing-library/jest-dom#custom-matchers) verwenden, wie `toBeInTheDocument` oder `toBeVisible`.

---

## Mocks

[Ein Mock](https://jestjs.io/docs/mock-functions) ist ein Ersatz, der in Tests anstelle einer ursprünglichen Funktion verwendet wird. Häufige Anwendungsfälle sind:

- Event-Handler-Funktionen, die als Prop an eine Komponente übergeben werden
- Das Ersetzen eines importierten Pakets

Mocks werden verwendet, um Abhängigkeiten in einem Test zu reduzieren und eine testbare Umgebung für eine Komponente bereitzustellen.

### Mock-Funktion für Event-Handler

Betrachten wir eine `Counter` Komponente, die zwei Event-Handler-Funktionen als Prop akzeptiert:

```jsx
export default function Counter({ onDecrease, onIncrease }) {
  return (
    <>
      <button type="button" onClick={onDecrease}>
        decrease
      </button>
      <button type="button" onClick={onIncrease}>
        increase
      </button>
    </>
  );
}
```

In einem Test möchtest du möglicherweise testen, ob die übergebenen Event-Handler-Funktionen aufgerufen werden, wenn die Buttons geklickt werden. Da du in diesem Test keine vollständige App renderst, sondern nur diese Komponente, kannst du eine Mock-Funktion übergeben.

Mock-Funktionen können mit `jest.fn()` erstellt werden. Dies gibt dir eine Funktion, die du mit `expect` verwenden kannst.

```jsx
test("should call event-handler functions", async () => {
  // Erstellt Mock-Funktionen
  const handleDecrease = jest.fn();
  const handleIncrease = jest.fn();

  const user = userEvent.setup();

  render(<Counter onDecrease={handleDecrease} onIncrease={handleIncrease} />);

  const decreaseButton = screen.getByRole("button", {
    name: /decrease/i,
  });
  const increaseButton = screen.getByRole("button", {
    name: /increase/i,
  });

  await user.click(increaseButton);
  await user.click(decreaseButton);
  await user.click(increaseButton);

  expect(handleDecrease).toHaveBeenCalledTimes(1);
  expect(handleIncrease).toHaveBeenCalledTimes(2);
});
```

### Testing Next.js (`useRouter` Mock)

Beim Schreiben von Tests für Komponenten, die den `useRouter` Hook von Next.js verwenden, musst du auf einige Stolpersteine achten. Wenn Tests ausgeführt werden, laufen sie nicht in einem echten Browser. Daher gibt es keine [Browser Location API](https://developer.mozilla.org/en-US/docs/Web/API/Location), und der Kontext, den Next.js verwendet, um Routing-Informationen an alle Komponenten in der App bereitzustellen, ist nicht vorhanden.

Der `useRouter` Hook erfordert die Browser Location API, um zu funktionieren, daher wird er einen Fehler auslösen und die Tests werden fehlschlagen.

Um Komponenten zu testen, die den `useRouter` Hook verwenden, musst du einen Mock schreiben.

Ein Mock ist ein Ersatz, der in Tests anstelle der ursprünglichen Funktion verwendet wird. Du kannst den `useRouter` Hook von `next/router` durch einen Mock ersetzen, wie unten beschrieben. Füge die Funktionen/Eigenschaften des Routers hinzu, die die getestete Komponente verwendet. In einem Mock wird die einfachste mögliche Implementierung verwendet, die die Tests zum Laufen bringt. Im folgenden Beispiel nehmen wir an, dass die getesteten Komponenten auf `router.asPath` zugreifen und `router.push` aufrufen.

```jsx
import MyComponent from ".";
/* ... wahrscheinlich weitere Importe hier ... */

jest.mock("next/router", () => ({
  useRouter() {
    return {
      push: jest.fn(),
      asPath: "/",
    };
  },
}));

test("should render", () => {
  /* ... Test hier ... */
});

/* ... wahrscheinlich weitere Tests hier ... */
```

---

## Resources

- [Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
- [Testing Library: render](https://testing-library.com/docs/react-testing-library/api#render)
- [Testing Library: screen](https://testing-library.com/docs/queries/about/#screen)
- [Testing Library: Queries](https://testing-library.com/docs/queries/about/)
- [Testing Playground](https://testing-playground.com/)
- [Testing Library: UserEvents](https://testing-library.com/docs/user-event/intro)
- [jest-dom (additional matchers)](https://github.com/testing-library/jest-dom)
- [Jest: Mock functions](https://jestjs.io/docs/mock-functions)
