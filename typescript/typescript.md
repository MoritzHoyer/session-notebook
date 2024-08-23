# typescript

## Lernziele

- Verstehen des statischen Typsystems von TypeScript und wie es JavaScript-Code verbessern kann.
- Erlernen der Anwendung von TypeScript-Funktionen wie Typen, Interfaces und Generics zur besseren Codeorganisation und Fehlerreduktion.
- Entwicklung der Fähigkeit, TypeScript in praktischen Codierungsszenarien zu implementieren.

---

## Einführung in TypeScript

TypeScript ist eine Open-Source-Programmiersprache, die von Microsoft entwickelt und gepflegt wird. Sie ist eine Obermenge von JavaScript, was bedeutet, dass jeder gültige JavaScript-Code auch gültiger TypeScript-Code ist. TypeScript fügt jedoch statische Typisierungsfähigkeiten zu JavaScript hinzu, was zu robusterem Code, frühzeitiger Fehlererkennung und erhöhter Entwicklerproduktivität führt. TypeScript ist für die Entwicklung großer Anwendungen konzipiert und wird zu JavaScript transkompiliert, wodurch es mit jedem Browser, Host oder Betriebssystem kompatibel ist.

### Warum TypeScript?

JavaScript, die Lingua Franca des Webs, ist dynamisch typisiert. Diese Flexibilität ist mächtig, kann aber in großen Anwendungen zu schwer zu behebenden Laufzeitfehlern führen. TypeScript löst dieses Problem durch die Einführung einer optionalen statischen Typisierung. Das Typsystem überprüft den Code auf Typkorrektheit, bevor er ausgeführt wird, und erkennt Fehler frühzeitig im Entwicklungsprozess. Diese Fähigkeit ist besonders wertvoll, wenn Anwendungen wachsen und Teams größer werden.

### Wichtige Features von TypeScript

- **Statische Typisierung:** Variablentypen festlegen und Typfehler vor der Laufzeit abfangen.
- **Klassenbasierte Objektorientierte Programmierung:** Klassen, Interfaces und Vererbung nutzen, um organisierten und wiederverwendbaren Code zu schreiben.
- **Generics:** Wiederverwendbare und typsichere Funktionen, Klassen, Interfaces und mehr erstellen.
- **Zugriffsmodifikatoren:** `public`, `private` und `protected` verwenden, um den Zugriff auf Klassenmitglieder zu steuern.
- **Erweiterte Typen:** Union, Intersection und Tuple-Typen für präzisere Typenkontrolle nutzen.
- **Tooling-Unterstützung:** Hervorragende Tooling-Unterstützung in den meisten IDEs mit Funktionen wie Codevervollständigung, Refactoring und IntelliSense.

### Installation von TypeScript

TypeScript kann einfach über den Paketmanager von Node.js, npm, installiert werden. Um TypeScript global auf Ihrem Rechner zu installieren, führen Sie folgenden Befehl im Terminal aus:

```bash
npm install -g typescript
```

Nach der Installation können Sie die installierte TypeScript-Version mit `tsc --version` überprüfen.

### Kompilieren von TypeScript

TypeScript-Code muss kompiliert (oder "transpiliert") werden, um in einer JavaScript-Umgebung ausgeführt werden zu können. Der TypeScript-Compiler, `tsc`, übernimmt diesen Prozess. Um eine TypeScript-Datei zu kompilieren, führen Sie folgenden Befehl aus:

```bash
tsc myfile.ts
```

Dies erzeugt eine `myfile.js`-Datei im gleichen Verzeichnis, die in jeder JavaScript-Umgebung ausgeführt werden kann.

### Ihr erstes TypeScript-Programm

Erstellen Sie eine Datei namens `hello.ts` und fügen Sie den folgenden TypeScript-Code hinzu:

```typescript
let message: string = "Hello, TypeScript!";
console.log(message);
```

Kompilieren Sie die TypeScript-Datei zu JavaScript mit dem `tsc`-Befehl:

```bash
tsc hello.ts
```

Führen Sie die kompilierte JavaScript-Datei mit Node.js aus:

```bash
node hello.js
```

Sie sollten "Hello, TypeScript!" auf der Konsole sehen.

### Warum TypeScript verwenden?

- **Fehlererkennung:** Fehler frühzeitig in der Entwicklung erkennen und dadurch Bugs in der Produktion reduzieren.
- **Lesbarkeit und Wartbarkeit:** Die Lesbarkeit und Wartbarkeit des Codes mit expliziten Typen und objektorientierten Programmierprinzipien verbessern.
- **Produktivität:** Die Entwicklerproduktivität durch bessere Tooling-Unterstützung steigern.
- **Community und Ökosystem:** Von einem großen und wachsenden Ökosystem von Typdefinitionen für bestehende JavaScript-Bibliotheken profitieren.

### Fazit

TypeScript erweitert JavaScript um statische Typen. Obwohl es eine zusätzliche Komplexität hinzufügt, sind die Vorteile in Bezug auf Fehlerreduktion, Code-Lesbarkeit und Entwicklerproduktivität enorm, insbesondere bei großen oder komplexen Projekten. Während Sie TypeScript weiter erkunden, werden Sie mehr über seine leistungsstarken Funktionen erfahren und wie diese genutzt werden können, um robuste, skalierbare Webanwendungen zu erstellen.

## Typannotationen in TypeScript

TypeScript verbessert JavaScript, indem es Entwicklern ermöglicht, Typinformationen explizit anzugeben. Diese Funktion, bekannt als "Typannotationen", ermöglicht es dem TypeScript-Compiler, die Typen von Variablen, Parametern und Rückgabewerten zu überprüfen und Fehler zu erkennen, bevor sie im Browser oder auf einem Server ausgeführt werden. Diese Einführung wird die Grundlagen von Typannotationen in TypeScript erforschen und deren Syntax und Vorteile aufzeigen.

### Was sind Typannotationen?

Typannotationen in TypeScript sind eine Möglichkeit für Programmierer, den Typ der Werte anzugeben, die Variablen halten können, sowie den Typ der Daten, die Funktionen als Argumente akzeptieren und zurückgeben. Durch diese Spezifikation können Entwickler das leistungsstarke Typsystem von TypeScript nutzen, um typspezifische Fehler während der Kompilierungszeit zu erkennen, was zu robusterem Code führt.

### Syntax von Typannotationen

Typannotationen in TypeScript folgen einer einfachen Syntax: Nach der Deklaration einer Variablen wird ein Doppelpunkt (:) gefolgt vom Typ hinzugefügt. Dies gibt TypeScript an, welcher Datentyp von der Variablen erwartet wird. Hier ist ein einfaches Beispiel:

```typescript
let username: string = "JohnDoe";
let age: number = 30;
let isActive: boolean = true;
```

Im obigen Beispiel wird `username` als `string`, `age` als `number` und `isActive` als `boolean` annotiert. TypeScript erzwingt diese Typen, wann immer diese Variablen verwendet werden, und stellt sicher, dass z.B. keine Zahl versehentlich `username` zugewiesen wird.

### Funktionsparameter und Rückgabewert-Annotationen

Typannotationen sind auch in Funktionen äußerst nützlich, um die Typen von Parametern und den Rückgabetyp der Funktion zu spezifizieren. Dies klärt den Vertrag der Funktion und stellt sicher, dass sie korrekt in Ihrer Anwendung verwendet wird.

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

In der `add`-Funktion wird erwartet, dass `a` und `b` Zahlen sind, und es wird auch erwartet, dass eine Zahl zurückgegeben wird. Der Versuch, einen Wert eines anderen Typs als Argument zu übergeben oder einen anderen Typ zurückzugeben, führt zu einem TypeScript-Kompilierungsfehler.

### Warum Typannotationen verwenden?

Typannotationen bieten mehrere Vorteile:

- **Frühe Fehlererkennung:** Durch das Abfangen von Fehlern zur Kompilierungszeit statt zur Laufzeit können Entwickler typspezifische Probleme frühzeitig im Entwicklungsprozess erkennen und beheben.
- **Code-Lesbarkeit:** Typannotationen dienen als Dokumentation für Ihren Code, wodurch klarer wird, mit welcher Art von Daten gearbeitet wird.
- **Tooling-Unterstützung:** Verbesserte Editor-Unterstützung mit Funktionen wie Autovervollständigung, IntelliSense und Refactoring-Tools, die den Code genauer verstehen können.

### Fazit

Typannotationen sind ein grundlegendes Feature von TypeScript, das einen robusten Mechanismus bietet, um die JavaScript-Entwicklung typsicherer und effizienter zu gestalten. Durch das explizite Definieren der Typen von Variablen und Funktionsparametern können Entwickler vorhersehbareren Code schreiben, Laufzeitfehler reduzieren und die allgemeine Wartbarkeit ihrer Anwendungen verbessern. Ob Sie an einem kleinen Projekt oder einer großen Unternehmensanwendung arbeiten, die Nutzung von Typannotationen kann Ihren Entwicklungsworkflow erheblich verbessern.

## Typinferenz in TypeScript

Die Typinferenz von TypeScript bedeutet, dass Sie Ihren Code nicht explizit mit Typinformationen annotieren müssen; TypeScript kann dies für Sie erledigen. Diese Funktion macht TypeScript zu einem leistungsstarken Werkzeug zur Verbesserung Ihres JavaScript-Codes, ohne dass eine steile Lernkurve erforderlich ist. Hier werden wir untersuchen, was Typinferenz ist, wie sie funktioniert und warum sie nützlich ist.

### Was ist Typinferenz?

Typinferenz in TypeScript ermöglicht es der Sprache, die Typen von Variablen und Ausdrücken automatisch abzuleiten, wenn Sie sie nicht explizit angeben. Dieser Prozess findet zur Kompilierungszeit statt und hilft dabei, typspezifische Fehler zu erkennen, bevor der Code ausgeführt wird.

### Wie funktioniert Typinferenz?

TypeScript verwendet mehrere Strategien, um Typen abzuleiten. Schauen wir uns einige häufige Szenarien an:

1. **Variableninitialisierung:**
   TypeScript betrachtet die rechte Seite von Variablendeklarationen, um den Typ der Variablen auf der linken Seite abzuleiten.

   ```typescript
   let x = 10; // x wird als Typ number abgeleitet
   ```

2. **Rückgabewerte von Funktionen**:
   Wenn Sie eine Funktion erstellen, untersucht TypeScript die Rückgabeanweisungen, um den Rückgabetyp der Funktion abzuleiten.

```typescript
function add(a: number, b: number) {
  return a + b;
}
// Der Rückgabewert von add wird als number abgeleitet
```

3. **Array-Literal-Typen**:
   Wenn Sie ein Array-Literal verwenden, leitet TypeScript den Typ für das Array basierend auf den Typen der Elemente im Array ab.

```typescript
let arr = [0, 1, null]; // arr wird als (number | null)[] abgeleitet
```

4. **Objekt-Literal-Typen**:
   Für Objektliterale leitet TypeScript den Typ basierend auf den von Ihnen bereitgestellten Eigenschaften und Werten ab.

```typescript
let user = { name: "Alice", age: 30 };
// user wird als { name: string; age: number; } abgeleitet
```

### Best Practices und Einschränkungen

Obwohl die Typinferenz mächtig ist, ist es nicht immer die beste Praxis, sich ausschließlich auf sie zu verlassen. Hier einige Tipps:

- **Explizite Typen für öffentliche API:** Für Funktionsparameter und Rückgabetypen, insbesondere bei Bibliotheken oder Frameworks, definieren Sie Typen explizit, um die Klarheit und Stabilität Ihrer API sicherzustellen.
- **Verwenden Sie Typannotationen, wenn nötig:** In komplexen Szenarien oder wenn der abgeleitete Typ nicht dem entspricht, was Sie beabsichtigen, verwenden Sie Typannotationen, um TypeScript zu leiten.
- **Achten Sie auf `any`:** Wenn TypeScript keinen Typ ableiten kann, wird möglicherweise `any` verwendet, was die Typprüfung umgeht. Versuchen Sie, implizite `any`-Typen zu vermeiden, indem Sie spezifischere Typen angeben.

### Fazit

Die Typinferenz ist ein Markenzeichen von TypeScript und bietet eine Mischung aus Flexibilität und Sicherheit. Durch das Verständnis und die Nutzung der Typinferenz können Sie robusteren Code mit weniger Aufwand schreiben. Denken Sie jedoch daran, dass explizite Typen manchmal die Intentionen klären und Fehler verhindern können, daher sollten Sie Typinferenz mit Bedacht einsetzen, um das Beste aus beiden Welten zu erhalten.

## Primitive Typen

In TypeScript, wie auch in JavaScript, stellen primitive Typen die grundlegenden Datentypen dar, die die Bausteine der Programmierlogik bilden. TypeScript erweitert diese Typen um statische Typisierung, die eine bessere Validierung und Dokumentation des Codes ermöglicht. Die wichtigsten primitiven Typen in TypeScript sind `string`, `number`, `boolean`, `null`, `undefined`, `symbol` und `bigint`.

### 1. String

Der `string`-Typ wird verwendet, um Textdaten darzustellen. Es ist einer der häufigsten primitiven Typen und kann jede Zeichenfolge enthalten, die in einfache (`'`), doppelte (`"`) oder Backticks (`` ` ``) eingeschlossen ist.

```typescript
let username: string = "JohnDoe";
let greeting: string = `Hello, ${username}`;
```

### 2. Number

TypeScript, wie JavaScript, unterscheidet nicht zwischen Ganzzahlen und Gleitkommawerten; alle Zahlen werden durch den `number`-Typ dargestellt. Dies umfasst Ganzzahlen, Brüche und Werte wie `Infinity` und `NaN`.

```typescript
let age: number = 30;
let price: number = 99.99;
```

### 3. Boolean

Der `boolean`-Typ repräsentiert eine logische Entität und kann nur zwei Werte haben: `true` und `false`. Es wird häufig in bedingten Anweisungen und logischen Operationen verwendet.

```typescript
let isActive: boolean = true;
let isVerified: boolean = false;
```

### 4. Null und Undefined

`null` und `undefined` in TypeScript sind ähnlich wie in JavaScript. `null` wird einer Variablen zugewiesen, von der bekannt ist, dass sie keinen Wert hat, während `undefined` eine Variable darstellt, die deklariert, aber noch nicht zugewiesen wurde. TypeScript behandelt sie als eigene Typen.

```typescript
let emptyValue: null = null;
let uninitializedValue: undefined = undefined;
```

### 5. Symbol

Eingeführt in ECMAScript 2015 und von TypeScript übernommen, wird der `symbol`-Typ verwendet, um eindeutige Bezeichner für Objekteigenschaften zu erstellen. Symbole sind unveränderlich und einzigartig.

```typescript
let key: symbol = Symbol("uniqueKey");
```

### 6. BigInt

`bigint` ist eine neuere Ergänzung, die die Darstellung von Ganzzahlen mit beliebiger Präzision ermöglicht. Es ist besonders nützlich, um mit großen Ganzzahlen zu arbeiten, die über das sichere Limit für den `number`-Typ hinausgehen.

```typescript
let largeNumber: bigint = 9007199254740991n;
```

### Verwendung und Best Practices

Das Verständnis, wann und wie diese Typen verwendet werden, ist entscheidend für eine effektive TypeScript-Entwicklung. Hier einige Tipps:

- Verwenden Sie `string`, `number` und `boolean` für die meisten grundlegenden Datenrepräsentationen.
- Verwenden Sie explizit `null` und `undefined`, um leere oder nicht initialisierte Werte zu kennzeichnen und die Lesbarkeit und Wartbarkeit des Codes zu verbessern.
- Nutzen Sie `symbol` für eindeutige Eigenschaftsschlüssel, insbesondere bei der Erstellung von Bibliotheken oder komplexen Objekten.
- Verwenden Sie `bigint`, wenn Sie mit Zahlen außerhalb des sicheren Ganzzahlbereichs des `number`-Typs arbeiten.

### Fazit

Primitive Typen in TypeScript bieten eine starke Grundlage für den Aufbau typensicherer Anwendungen. Durch die Durchsetzung der Typkonsistenz können Entwickler Laufzeitfehler reduzieren und die Codequalität verbessern. Dieses Kapitel hat die wesentlichen primitiven Typen behandelt und den Grundstein für eine tiefere Erforschung des Typsystems von TypeScript in den folgenden Kapiteln gelegt.

## Union-Typen in TypeScript

Union-Typen sind ein mächtiges Feature in TypeScript, das es ermöglicht, dass Variablen mehr als einen Typ von Werten enthalten können. Diese Flexibilität kann die Funktionalität und Zuverlässigkeit Ihres TypeScript-Codes erheblich verbessern. Dieses Kapitel untersucht das Konzept der Union-Typen, ihre Syntax und praktische Anwendungen, damit Sie sie effektiv in Ihren Projekten nutzen können.

### Einführung in Union-Typen

Im Kern ist ein Union-Typ eine Möglichkeit zu deklarieren, dass eine Variable oder ein Funktionsparameter einer von mehreren Typen sein kann. Union-Typen sind besonders nützlich in Szenarien, in denen die strikte Typisierung von Variablen die Flexibilität Ihrer Funktionen oder Datenstrukturen einschränken würde.

### Syntax von Union-Typen

Die Syntax für Union-Typen ist einfach: Die Typen werden mit dem Pipe-Zeichen (`|`) kombiniert. Dies zeigt an, dass eine Variable oder ein Parameter einen Wert halten kann, der einem der angegebenen Typen entspricht.

```typescript
let mixedType: number | string;
mixedType = 20; // Gültig
mixedType = "Twenty"; // Auch gültig
```

Im obigen Beispiel kann `mixedType` entweder einen `number`- oder einen `string`-Wert enthalten, und TypeScript stellt sicher, dass jeder zugewiesene Wert einem dieser Typen entspricht.

### Verwendung von Union-Typen mit Funktionen

Union-Typen sind unglaublich nützlich für Funktionsparameter, da sie es Funktionen ermöglichen, unterschiedliche Typen von Argumenten anzunehmen und bedingt innerhalb des Funktionskörpers mit ihnen zu arbeiten.

```typescript
function printId(id: number | string) {
  if (typeof id === "number") {
    console.log(`Ihre ID-Nummer ist: ${id}.`);
  } else {
    console.log(`Ihre ID-Zeichenfolge ist: ${id}.`);
  }
}
```

In diesem Beispiel kann `printId` sowohl `number` als auch `string`-Typen für seinen `id`-Parameter akzeptieren, und es verwendet Typprüfungen (`typeof` in diesem Fall), um den Typ von `id` zur Laufzeit zu bestimmen.

### Arbeiten mit Arrays und Union-Typen

Union-Typen können auch verwendet werden, um Arrays zu definieren, die mehrere Typen von Werten enthalten, was besonders nützlich für Daten ist, die nicht einem einzigen Typ entsprechen.

```typescript
let mixedArray: (number | string)[];
mixedArray = [1, "two", 3, "four"];
```

### Unionstypen und Schnittstellen

Unionstypen können mit Schnittstellen kombiniert werden, um komplexe Typstrukturen zu erstellen, die sich an verschiedene Datenformen anpassen können.

```typescript
interface Car {
  drive(): void;
}

interface Boat {
  sail(): void;
}

let vehicle: Car | Boat;

function operate(vehicle: Car | Boat) {
  if ("drive" in vehicle) {
    vehicle.drive();
  } else {
    vehicle.sail();
  }
}
```

### Verengen von Unionstypen

TypeScript ermöglicht das Verengen von Unionstypen durch verschiedene Typwächter (type guards). Dieser Prozess beinhaltet die Bestimmung des spezifischen Subtyps eines Unionstyps innerhalb eines Codeblocks.

- **Verwendung von `typeof` für primitive Typen**
- **Verwendung von `instanceof` für Klasseninstanzen**
- **Verwendung benutzerdefinierter Typwächter wie `in`-Operator oder benutzerdefinierter Typwächterfunktionen**

### Best Practices für die Verwendung von Unionstypen

- **Verwenden Sie Typwächter, um Unionstypen zu verengen:** Stellen Sie sicher, dass Sie den Typ Ihrer Variablen ordnungsgemäß überprüfen, bevor Sie Operationen an ihnen durchführen.
- **Halten Sie Unionstypen einfach:** Auch wenn Unionstypen mächtig sind, können übermäßig komplexe Unionen schwer zu warten sein. Streben Sie nach Einfachheit, wo immer möglich.
- **Nutzen Sie Schnittstellen mit Unionstypen:** Verwenden Sie für Objekttypen Schnittstellen oder Typ-Aliasse, um Ihren Code organisiert und lesbar zu halten.

### Fazit

Unionstypen in TypeScript bieten eine vielseitige Möglichkeit, mit Variablen und Funktionen zu arbeiten, die mehrere Typen unterstützen müssen. Indem Sie verstehen, wie man Unionstypen definiert, verengt und mit ihnen arbeitet, können Sie flexibleren und robusteren TypeScript-Code schreiben. Dieses Kapitel hat ein grundlegendes Verständnis von Unionstypen vermittelt und befähigt Sie, diese effektiv in Ihren TypeScript-Projekten zu nutzen.

## Arrays in TypeScript

Arrays in TypeScript werden wie in JavaScript verwendet, um mehrere Werte in einer einzelnen Variablen zu speichern. TypeScript erweitert jedoch Arrays, indem es Entwicklern ermöglicht, den Typ der Elemente anzugeben, die gespeichert werden können, was leistungsstarke Funktionen wie statische Typprüfung und Codevervollständigung bietet. Dieses Kapitel führt in Arrays in TypeScript ein, wobei der Schwerpunkt auf Syntax, Typannotationen und einigen gängigen Operationen liegt.

Eine Array-Deklaration in TypeScript kann auf zwei Hauptarten erfolgen: mit der `type[]`-Syntax oder dem generischen Array-Typ `Array<type>`. Beide Ansätze bieten die gleiche Funktionalität, und die Wahl zwischen ihnen hängt oft von persönlichen oder teambezogenen Vorlieben ab.

### Syntax und Typannotationen

1. **Verwendung der `type[]`-Syntax**

Dies ist die gebräuchlichste Methode, um Arrays in TypeScript zu definieren. Sie ist prägnant und leicht lesbar, insbesondere für diejenigen, die mit JavaScript vertraut sind.

```typescript
let numbers: number[] = [1, 2, 3, 4, 5];
let names: string[] = ["Alice", "Bob", "Charlie"];
```

2. **Verwendung der `Array<type>`-Syntax**

Alternativ können Arrays unter Verwendung des generischen Array-Typs `Array<type>` definiert werden. Diese Syntax ist ausführlicher, aber genauso leistungsfähig.

```typescript
let numbers: Array<number> = [1, 2, 3, 4, 5];
let names: Array<string> = ["Alice", "Bob", "Charlie"];
```

### Gemischte Typ-Arrays (Tupels)

TypeScript unterstützt Arrays mit gemischten Typen, die als Tupel bekannt sind. Tupel sind Arrays mit fester Länge, bei denen jedes Element einen bekannten und spezifischen Typ hat. Sie sind besonders nützlich, wenn Sie einen Wert als Paar oder Triplet von Elementen mit unterschiedlichen Typen darstellen müssen.

```typescript
let person: [string, number] = ["Alice", 30]; // Tupel aus string und number
let rgb: [number, number, number] = [255, 0, 0]; // Tupel für RGB-Farben
```

### Gängige Operationen auf Arrays

Arrays in TypeScript können mit JavaScript-Array-Methoden manipuliert werden. TypeScripts statische Typisierung verbessert diese Operationen, indem während der Kompilierungszeit Typensicherheit gewährleistet wird.

- **Elemente hinzufügen/entfernen:** Verwenden Sie die Methoden `push`, `pop`, `shift`, `unshift`, um Arrays zu manipulieren.

```typescript
numbers.push(6); // Fügt 6 am Ende hinzu
let lastNumber = numbers.pop(); // Entfernt das letzte Element
```

- **Über Arrays iterieren:** Schleifen Sie durch Arrays mit `for`, `forEach`, `for...of` Schleifen.

```typescript
numbers.forEach((number) => {
  console.log(number);
});
```

- **Mapping und Filtern:** Transformieren oder filtern Sie Arrays mit `map` und `filter`.

```typescript
let squaredNumbers = numbers.map((number) => number * number);
let evenNumbers = numbers.filter((number) => number % 2 === 0);
```

### Arrays mit Unionstypen

TypeScript-Arrays können Elemente von Unionstypen speichern, was eine größere Flexibilität ermöglicht. Diese Funktion ist nützlich, wenn ein Array Elemente von mehr als einem Typ enthalten muss.

```typescript
let arr: (number | string)[] = [1, "two", 3, "four"];
// Oder gleichwertig
let arr: Array<number | string> = [1, "two", 3, "four"];
```

### Schreibgeschützte Arrays

TypeScript bietet den Typ `ReadonlyArray<type>` an, um sicherzustellen, dass Arrays nach der Erstellung nicht mehr geändert werden können. Dies ist besonders nützlich, um die Unveränderlichkeit eines Arrays sicherzustellen.

```typescript
let readonlyNumbers: ReadonlyArray<number> = [1, 2, 3];
// readonlyNumbers.push(4); // Fehler: push existiert nicht auf ReadonlyArray<number>
```

### Fazit

Arrays in TypeScript sind eine vielseitige Möglichkeit, mit Sammlungen von Daten zu arbeiten. Durch die Nutzung des Typsystems von TypeScript können Entwickler zuverlässigere und wartbarere Anwendungen erstellen. Dieses Kapitel behandelte die Grundlagen der Definition und Manipulation von Arrays und legte eine solide Grundlage für die weitere Erkundung der erweiterten Funktionen von TypeScript.

## Funktionen in TypeScript

Funktionen sind das Rückgrat jeder JavaScript-Anwendung, und TypeScript erweitert diese mit zusätzlichen Funktionen und Typsicherheit. Dieses Kapitel taucht in die Welt der Funktionen in TypeScript ein und untersucht, wie man Funktionen definiert, verwendet und die Kraft der Typen nutzt, um robusteren und wartbareren Code zu erstellen.

### Einführung in Funktionen in TypeScript

In TypeScript werden Funktionen ähnlich behandelt wie in JavaScript, mit dem zusätzlichen Vorteil von Typannotationen. Diese Annotationen bieten eine Möglichkeit, die Typen von Parametern und den Rückgabewert von Funktionen anzugeben, wodurch die Lesbarkeit und Wartbarkeit des Codes verbessert und die Wahrscheinlichkeit von Laufzeitfehlern reduziert wird.

### Grundlagen von Funktionen

Das Definieren einer Funktion in TypeScript ist ähnlich wie das Definieren einer in JavaScript, mit der Ergänzung von Typannotationen für Parameter und Rückgabewerte:

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

In diesem Beispiel nimmt die Funktion `add` zwei Parameter vom Typ `number` entgegen und gibt einen Wert vom Typ `number` zurück.

### Optionale und Standardparameter

TypeScript führt optionale Parameter ein, die vom Aufrufer nicht bereitgestellt werden müssen, sowie Standardparameter, die einen Standardwert haben, falls sie nicht bereitgestellt werden:

```typescript
function greet(name: string, greeting: string = "Hello"): void {
  console.log(`${greeting}, ${name}!`);
}

greet("Alice"); // Ausgabe: "Hello, Alice!"
greet("Alice", "Good morning"); // Ausgabe: "Good morning, Alice!"
```

Optionale Parameter werden mit einem `?` markiert und müssen nach den erforderlichen Parametern kommen. Standardparameter können für optionales Verhalten mit einem definierten Wert verwendet werden.

### Rest Parameters und Tuple Types

TypeScript erlaubt es Funktionen, eine unbestimmte Anzahl von Argumenten als Array zu behandeln, indem Restparameter verwendet werden. Sie können auch Tupeltypen mit Restparametern verwenden, um Typen für alle erwarteten Argumente anzugeben:

```typescript
function buildName(firstName: string, ...restOfName: string[]): string {
  return firstName + " " + restOfName.join(" ");
}

const employeeName = buildName("Joseph", "Samuel", "Lucas", "MacKinzie");
```

### Funktionsüberladungen

TypeScript unterstützt Funktionsüberladungen, die es ermöglichen, mehrere Funktionen mit demselben Namen, aber unterschiedlichen Parametertypen oder -anzahlen zu definieren:

```typescript
function getInfo(name: string): string;
function getInfo(age: number): string;
function getInfo(single: boolean): string;
function getInfo(value: string | number | boolean): string {
  switch (typeof value) {
    case "string":
      return `Name: ${value}`;
    case "number":
      return `Age: ${value}`;
    case "boolean":
      return `Single: ${value}`;
    default:
      return "Invalid type";
  }
}
```

Funktionsüberladungen bieten eine Möglichkeit, unterschiedliche Eingabetypen mit einer einzigen Funktion zu behandeln, was die Flexibilität erhöht.

### Arrow-Funktionen

TypeScript unterstützt ES6 Arrow-Funktionen, die eine prägnante Möglichkeit bieten, Funktionen zu schreiben. Arrow-Funktionen sind besonders nützlich für Inline-Funktionen und Callbacks:

```typescript
const names = ["Alice", "Bob", "Charlie"];
const lengths = names.map((name) => name.length);
```

### Höhere Funktionen

Das Typsystem von TypeScript glänzt bei der Arbeit mit höheren Funktionen – Funktionen, die Funktionen als Parameter akzeptieren oder als Ausgabe zurückgeben. Typannotationen können auf Funktionsparameter und Rückgabetypen angewendet werden, um die Typensicherheit zu gewährleisten:

```typescript
function times(n: number, action: (index: number) => void): void {
  for (let i = 0; i < n; i++) {
    action(i);
  }
}

times(3, (index) => console.log(`Hello ${index}`));
```

### Fazit

Funktionen in TypeScript erweitern JavaScript-Funktionen um die Kraft der Typen. Durch die Anwendung von Typannotationen, die Nutzung von Funktionsüberladungen und das Ausnutzen höherer Funktionen können Entwickler zuverlässigeren und verständlicheren Code schreiben. Dieses Kapitel hat die Grundlagen der Arbeit mit Funktionen in TypeScript eingeführt und die Grundlage für die Erkundung komplexerer Typen und Muster in den folgenden Kapiteln gelegt.

--

## Objekte in TypeScript

In TypeScript, wie auch in JavaScript, sind Objekte Sammlungen von Schlüssel-Wert-Paaren, wobei die Schlüssel Strings sind und die Werte alles Mögliche sein können. TypeScript verbessert Objekte, indem es Entwicklern ermöglicht, die Form und den Typ der Daten zu definieren, die Objekte halten können. Dieses Kapitel taucht in die Grundlagen der Arbeit mit Objekten in TypeScript ein und behandelt Typannotationen für Objekte, optionale Eigenschaften, readonly-Eigenschaften und mehr.

Objekte spielen eine entscheidende Rolle in TypeScript-Anwendungen, da sie die Grundlage für komplexere Datenstrukturen und Typen bilden. Das statische Typsystem von TypeScript bietet mehrere Möglichkeiten zur Definition und Durchsetzung der Struktur von Objekten, um Konsistenz und Vorhersehbarkeit des Codes zu gewährleisten.

### Definition von Objekttypen

Die einfachste Möglichkeit, einen Objekttyp in TypeScript zu definieren, besteht darin, eine Inline-Typannotierung mit den Eigenschaften und ihren Typen zu verwenden.

```typescript
let user: { name: string; age: number } = {
  name: "John Doe",
  age: 30,
};
```

Dieses `user`-Objekt hat eine strenge Struktur: Es muss eine `name`-Eigenschaft vom Typ `string` und eine `age`-Eigenschaft vom Typ `number` haben. Der Versuch, Werte falscher Typen diesen Eigenschaften zuzuweisen, führt zu einem TypeScript-Fehler.

### Optionale Eigenschaften

TypeScript erlaubt es, Objekt-Eigenschaften als optional zu kennzeichnen, was bedeutet, dass sie möglicherweise auf einem Objekt vorhanden sind oder nicht. Optionale Eigenschaften werden durch ein `?` nach dem Eigenschaftsnamen angezeigt.

```typescript
let employee: { name: string; age?: number } = {
  name: "Jane Doe",
  // age ist optional
};
```

Im `employee`-Objekt ist `age` optional, daher ist es vollkommen gültig, es wegzulassen.

### Readonly-Eigenschaften

TypeScript bietet eine Möglichkeit, Objekt-Eigenschaften schreibgeschützt zu machen. Dies erfolgt durch den `readonly`-Modifier vor dem Eigenschaftstyp. Sobald eine Eigenschaft als readonly gekennzeichnet ist, kann sie nach der Erstellung des Objekts nicht mehr neu zugewiesen werden.

```typescript
let config: { readonly url: string } = {
  url: "http://example.com",
};
// config.url = "http://anotherurl.com"; // Fehler: Cannot assign to 'url' because it is a read-only property.
```

### Überprüfung von zusätzlichen Eigenschaften

Beim Zuweisen von Objekten an Variablen oder beim Übergeben von Objekten als Argumente an Funktionen führt TypeScript Überprüfungen zusätzlicher Eigenschaften durch. Das bedeutet, dass, wenn ein Objektliteral zusätzliche Eigenschaften enthält, die der "Zieltyp" nicht hat, ein Fehler auftritt.

Um diese Überprüfungen zu umgehen, können Sie Typassertionen verwenden oder eine String-Index-Signatur zum Objekttyp hinzufügen, wenn Sie nicht alle Eigenschaftsnamen im Voraus kennen.

### Index-Signaturen

Für Objekte, die als Dictionaries mit Schlüsseln eines bestimmten Typs dienen, unterstützt TypeScript Index-Signaturen. Dies ermöglicht es Ihnen, den Typ der Schlüssel und Werte in einem Objekt zu definieren.

```typescript
let scores: { [key: string]: number } = {
  Alice: 90,
  Bob: 85,
  // Beliebige Anzahl von String-Number-Paaren kann hinzugefügt werden
};
```

### Schnittstellen für Objekte

Für komplexe Objekttypen oder wenn dieselbe Objektstruktur an mehreren Stellen verwendet wird, ist es besser, eine Schnittstelle zu verwenden. Schnittstellen bieten eine leistungsstarke Möglichkeit, Verträge innerhalb Ihres Codes sowie Verträge mit Code außerhalb Ihres Projekts zu definieren.

```typescript
interface User {
  name: string;
  age?: number;
}

let user: User = {
  name: "John Doe",
  // age ist optional
};
```

Schnittstellen können andere Schnittstellen erweitern, was die Komposition und Wiederverwendung von Typdefinitionen ermöglicht.

### Fazit

Objekte in TypeScript sind vielseitig und leistungsstark, da sie Entwicklern ermöglichen, die Form von Daten auf eine Weise zu definieren, die die Zuverlässigkeit des Codes und die Produktivität der Entwickler erhöht. Durch das Verständnis und die Nutzung der Objekttypen von TypeScript, optionale und readonly-Eigenschaften, Index-Signaturen und Schnittstellen können Entwickler robuste, typsichere Anwendungen erstellen. Dieses Kapitel hat die Grundlage für die Arbeit mit Objekten in TypeScript gelegt und den Weg für fortgeschrittenere Themen und Muster geebnet.

--

## Typ-Alias in TypeScript

Das statische Typsystem von TypeScript hilft nicht nur, Fehler zur Kompilierzeit zu erkennen, sondern verbessert auch den Entwicklungsworkflow, indem es ausdrucksstärkere Code-Definitionen ermöglicht. Eine der leistungsstarken Funktionen, die TypeScript in dieser Hinsicht bietet, sind "Typ-Alias". Typ-Alias ermöglichen es Ihnen, neue Namen für Typen zu erstellen, sei es einfach oder komplex, wodurch Ihr Code lesbarer und wartbarer wird. Dieses Kapitel beschäftigt sich mit dem Konzept der Typ-Alias und veranschaulicht ihre Syntax, Verwendung und Vorteile in der TypeScript-Programmierung.

Typ-Alias in TypeScript sind benutzerdefinierte Namen für Typdefinitionen. Diese können von primitiven Typen bis hin zu komplexeren Objektstrukturen reichen. Durch die Verwendung von Typ-Alias können Sie Ihren Code vereinfachen, sodass er leichter zu verstehen und zu refaktorisieren ist.

### Syntax von Typ-Alias

Typ-Alias werden durch das Schlüsselwort `type`, gefolgt vom Alias-Namen, einem Gleichheitszeichen `=` und der Typdefinition definiert. Hier ein einfaches Beispiel:

```typescript
type UserID = string | number;
```

In diesem Beispiel ist `UserID` ein Typ-Alias, der entweder eine Zeichenkette oder eine Zahl sein kann, was die Verwendung von Union-Typen mit Typ-Alias demonstriert.

### Verwendung von Typ-Alias

Typ-Alias können überall dort verwendet werden, wo Typen verwendet werden. Dies schließt Variablendeklarationen, Funktionsparameter, Rückgabetypen und mehr ein. So können Sie den oben definierten Typ-Alias `UserID` verwenden:

```typescript
function getUser(id: UserID) {
  // Funktionsimplementierung
}
```

### Typ-Alias mit Objekten

Typ-Alias sind besonders nützlich für die Benennung von Objekttypen, was den Code beschreibender und leichter zu verwalten macht.

```typescript
type User = {
  id: UserID;
  name: string;
  age?: number; // Optionale Eigenschaft
};

let user: User = {
  id: "user123",
  name: "John Doe",
};
```

### Generics mit Typ-Alias

Typ-Alias können auch generisch sein, indem sie Typ-Parameter akzeptieren, um flexible und wiederverwendbare Typdefinitionen zu erstellen.

```typescript
type Response<T> = {
  status: number;
  data: T;
};

let userResponse: Response<User> = {
  status: 200,
  data: {
    id: 1,
    name: "Alice",
  },
};
```

In diesem Beispiel ist `Response<T>` ein generischer Typ-Alias, der eine Antwortstruktur kapselt, wobei `T` der Typ des `data`-Feldes ist.

### Vorteile von Typ-Alias

1. **Klarheit:** Typ-Alias machen komplexe Typdefinitionen klarer und ausdrucksstärker.
2. **Wiederverwendbarkeit:** Definieren Sie einen Typ einmal und verwenden Sie ihn in Ihrem gesamten Codebase wieder, um Konsistenz zu gewährleisten und Redundanz zu reduzieren.
3. **Flexibilität:** Erweitern oder ändern Sie Ihre Typen problemlos, wenn sich die Anforderungen Ihrer Anwendung ändern.

### Union-Typen und Typ-Alias

Typ-Alias glänzen bei der Verwendung mit Union-Typen, da Sie Typen definieren können, die mehrere Werttypen enthalten können.

```typescript
type Padding = number | string;
```

Hier kann `Padding` überall verwendet werden, wo entweder eine Zahl oder eine Zeichenkette akzeptiert wird, nützlich zum Beispiel für CSS-Eigenschaften.

### Intersection-Typen und Typ-Alias

Ähnlich können Typ-Alias auch Intersection-Typen darstellen, die mehrere Typen zu einem kombinieren.

```typescript
type Employee = User & { department: string };
```

`Employee` kombiniert `User` mit einer zusätzlichen `department`-Eigenschaft und zeigt, wie Typ-Alias komplexe Typen aus bestehenden Typen erstellen können.

### Fazit

Typ-Alias in TypeScript bieten einen leistungsstarken Mechanismus zum Benennen von Typen, von den einfachsten bis zu den komplexesten. Sie verbessern die Lesbarkeit, Wartbarkeit und Flexibilität des Codes und machen sie zu einem wesentlichen Bestandteil des TypeScript-Werkzeugkastens. Ob Sie einen Typ für einen Funktionsparameter, eine komplexe Objektstruktur oder einen Union/Intersection-Typ definieren, Typ-Alias vereinfachen die Aufgabe und helfen Entwicklern, klare und prägnante Typdefinitionen zu schreiben. Nutzen Sie Typ-Alias, um Ihre Typdefinitionen organisiert und verständlich zu halten, während Sie weiterhin TypeScript erkunden.

## Klassen in TypeScript

Klassen sind ein Kernthema der objektorientierten Programmierung (OOP), und TypeScript bringt dieses Konzept mit eigenen Erweiterungen in das JavaScript-Ökosystem. Eine Klasse in TypeScript ist eine Vorlage für die Erstellung von Objekten, die dieselbe Struktur und dieselben Verhaltensweisen teilen. Klassen kapseln Daten für das Objekt und Methoden, um mit diesen Daten zu arbeiten. Dieser Ansatz zur Programmierung ermöglicht es Ihnen, wiederverwendbaren, skalierbaren und wartbaren Code zu erstellen.

### Wichtige Merkmale von TypeScript-Klassen

- **Encapsulation:** Klassen bündeln Daten (Eigenschaften) und Methoden, um auf diese Daten zuzugreifen, in einer Einheit und kontrollieren die Zugänglichkeit ihrer Komponenten durch Zugriffsmodifikatoren wie public, private und protected.
- **Inheritance:** TypeScript-Klassen unterstützen Vererbung, sodass eine Klasse eine andere erweitern kann. Diese Funktion ermöglicht es Ihnen, eine neue Klasse zu erstellen, die Attribute und Verhaltensweisen von einer bestehenden Klasse erbt, was die Wiederverwendbarkeit des Codes fördert.
- **Static Properties and Methods:** Diese gehören zur Klasse selbst und nicht zu einer bestimmten Objektinstanz. Statische Mitglieder können ohne Erstellen einer Instanz der Klasse aufgerufen werden.
- **Constructors:** Eine spezielle Methode zur Initialisierung neuer Objekte. Der Konstruktor wird aufgerufen, wenn eine neue Instanz der Klasse erstellt wird und ermöglicht die Initialisierung von Eigenschaften.
- **Abstract Classes:** Dies sind Basisklassen, von denen andere Klassen abgeleitet werden können. Sie können nicht direkt instanziiert werden, können jedoch Implementierungsdetails für ihre Mitglieder enthalten. Abstrakte Klassen sind eine leistungsstarke Möglichkeit, ein bestimmtes Set von Verhaltensweisen in abgeleiteten Klassen zu erzwingen.

### Erstellen einer einfachen TypeScript-Klasse

Hier ist ein einfaches Beispiel für eine TypeScript-Klasse, die ein einfaches `Book` modelliert:

```typescript
class Book {
  // Eigenschaften
  title: string;
  author: string;
  pages: number;

  // Konstruktor
  constructor(title: string, author: string, pages: number) {
    this.title = title;
    this.author = author;
    this.pages = pages;
  }

  // Methode
  describe(): string {
    return `${this.title} von ${this.author}, ${this.pages} Seiten lang.`;
  }
}

// Erstellen einer Instanz der Book-Klasse
const myBook = new Book("The TypeScript Way", "Jane Doe", 300);
console.log(myBook.describe());
```

In diesem Beispiel kapselt die `Book`-Klasse Eigenschaften (`title`, `author` und `pages`) und eine Methode (`describe`), die auf diesen Eigenschaften arbeitet. Der Konstruktor initialisiert die Eigenschaften, wenn ein neues `Book`-Objekt erstellt wird.

### Fazit

TypeScript-Klassen bieten einen strukturierten Ansatz zur Erstellung von JavaScript-Code, der die Verwaltung und Erweiterung erleichtert. Denken Sie daran, dass Übung der Schlüssel zur Beherrschung dieser Konzepte ist. Zögern Sie daher nicht, eigene Klassen zu erstellen und die von TypeScript angebotenen Funktionen zu erkunden.

Nächste Woche bauen wir auf dem Wissen über Klassen auf, indem wir in fortgeschrittenere objektorientierte Programmierkonzepte eintauchen, einschließlich Schnittstellen und Generics in TypeScript. Viel Spaß beim Programmieren!

## Schnittstellen in TypeScript

Schnittstellen in TypeScript dienen als grundlegendes Fundament für das Schreiben von robustem, gut dokumentiertem Code. Sie ermöglichen Entwicklern, Verträge innerhalb ihres Codes sowie Verträge mit Code außerhalb ihres Projekts zu definieren. Dieses Kapitel erkundet die Kraft von Schnittstellen in TypeScript und zeigt, wie sie verwendet werden können, um die Struktur von Objekten zu definieren, Klassenstrukturen durchzusetzen und mit Drittanbieter-Code zu integrieren.

## Einführung in Schnittstellen

Eine Schnittstelle in TypeScript ist eine Möglichkeit, einen Vertrag in Ihrer Anwendung zu definieren. Sie erklärt die Form eines Objekts oder die Struktur einer Klasse, einschließlich der Typen von Eigenschaften, Methoden und deren jeweiligen Argumenten und Rückgabewerten. Schnittstellen dienen dazu, Daten und Funktionalität zu formen und sind unerlässlich für die Aufrechterhaltung einer klaren und konsistenten Codierung.

### Definition von Schnittstellen

Um eine Schnittstelle zu deklarieren, verwenden Sie das Schlüsselwort `interface`, gefolgt vom Namen der Schnittstelle. Eine Schnittstelle kann Eigenschaften und Methodendeklarationen enthalten, jedoch keine Implementierungen.

```typescript
interface User {
  id: number;
  name: string;
  age?: number; // Optionale Eigenschaft
}
```

Diese `User`-Schnittstelle spezifiziert, dass jedes Objekt, das ihr entspricht, `id`- und `name`-Eigenschaften vom Typ `number` und `string` haben sollte. Die `age`-Eigenschaft ist optional.

### Implementieren von Schnittstellen in Klassen

Eine der Hauptverwendungen von Schnittstellen besteht darin, einen Vertrag für Klassen zu definieren. Eine Klasse, die eine Schnittstelle implementiert, muss eine Implementierung für alle Eigenschaften und Methoden der Schnittstelle bereitstellen.

```typescript
class Person implements User {
  id: number;
  name: string;
  age: number;

  constructor(id: number, name: string, age: number) {
    this.id = id;
    this.name = name;
    this.age = age;
  }
}
```

### Schnittstellen mit Funktionstypen

Schnittstellen können auch Funktionstypen beschreiben. Dabei spezifizieren Sie die Signatur der Funktion, einschließlich der Typen ihrer Parameter und ihres Rückgabetyps.

```typescript
interface SearchFunc {
  (source: string, subString: string): boolean;
}

let mySearch: SearchFunc;
mySearch = function (source: string, subString: string) {
  return source.search(subString) > -1;
};
```

### Erweiterung von Schnittstellen

Schnittstellen können eine oder mehrere andere Schnittstellen erweitern, was es Ihnen ermöglicht, komplexe Typen aus einfacheren zu kombinieren.

```typescript
interface Shape {
  color: string;
}

interface Square extends Shape {
  sideLength: number;
}

let square = <Square>{};
square.color = "blau";
square.sideLength = 10;
```

### Implementieren von Schnittstellen für Objektliterale

Die Verwendung von Schnittstellen für Objektliterale kann eine bestimmte Struktur für Daten in Ihrer Anwendung durchsetzen, um Konsistenz und Vorhersehbarkeit bei der Datenverarbeitung sicherzustellen.

```typescript
function greet(user: User) {
  console.log("Hallo, " + user.name);
}

greet({ id: 1, name: "John Doe" }); // Korrekte Verwendung
// greet({ username: "JohnDoe" }); // Fehler: Property 'name' fehlt im Typ '{ username: string; }'
```

### Schnittstellen vs. Typ-Alias

Während Schnittstellen und Typ-Alias oft austauschbar verwendet werden können, gibt es einige Unterschiede. Schnittstellen schaffen einen neuen Namen, der überall verwendet wird, verbessern Fehlermeldungen und ermöglichen es, dass die Schnittstelle von Klassen erweitert oder implementiert wird. Typ-Alias hingegen können Union- und Tupel-Typen definieren, was bei Schnittstellen nicht möglich ist.

Im Folgenden finden Sie eine Tabelle, die die Unterschiede zwischen „Typ-Alias“ und „Schnittstellen“ in TypeScript veranschaulicht:

| Merkmal                        | Typ-Alias                                                                                                                                                                | Schnittstellen                                                                                                                                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Deklaration                    | Verwenden Sie das Schlüsselwort `type`.<br>`typescript<br>type Point = { x: number; y: number; };<br>`                                                                   | Verwenden Sie das Schlüsselwort `interface`.<br>`typescript<br>interface Point { x: number; y: number; }<br>`                                                                                                          |
| Erweiterung                    | Erweiterung über Schnittmengen mit `&`.<br>`typescript<br>type Animal = { name: string; };<br>type Bear = Animal & { honey: boolean; };<br>`                             | Erweiterung mit dem Schlüsselwort `extends`.<br>`typescript<br>interface Animal { name: string; }<br>interface Bear extends Animal { honey: boolean; }<br>`                                                            |
| Wiedereröffnung/Erweiterung    | Kann nicht wiedereröffnet werden, um neue Eigenschaften hinzuzufügen.<br>`typescript<br>// Nicht anwendbar auf Typ-Alias<br>`                                            | Kann wiedereröffnet werden, um neue Eigenschaften hinzuzufügen.<br>`typescript<br>interface Window { title: string; }<br>interface Window { ts: TypeScriptAPI; }<br>// Jetzt hat Window sowohl title als auch ts.<br>` |
| Zusammenführung                | Unterstützt keine automatische Zusammenführung.<br>`typescript<br>// Nicht anwendbar auf Typ-Alias<br>`                                                                  | Unterstützt automatische Zusammenführung.<br>`typescript<br>interface Box { height: number; width: number; }<br>interface Box { scale: number; }<br>// Box hat jetzt height, width und scale.<br>`                     |
| Verwendung mit Primitiven      | Kann zur Aliasierung von primitiven Typen verwendet werden.<br>`typescript<br>type ID = string;<br>`                                                                     | Kann keine primitiven Typen aliasieren.<br>`typescript<br>// Direkt nicht anwendbar für Schnittstellen<br>`                                                                                                            |
| Berechnete Eigenschaften       | Kann berechnete Eigenschaften verwenden.<br>```typescript<br>type Keys = 'option1'                                                                                       | 'option2';<br>type Flags = { [K in Keys]: boolean };<br>```                                                                                                                                                            | Kann berechnete Eigenschaften nicht direkt verwenden.<br>`typescript<br>// Schnittstellen können keine berechneten Eigenschaften direkt verwenden<br>`                                              |
| Union- und Schnittmengen-Typen | Unterstützt sowohl Union- als auch Schnittmengen-Typen.<br>```typescript<br>type Shape = Circle                                                                          | Square;<br>```                                                                                                                                                                                                         | Unterstützt Union-Typen direkt nicht; verwendet Schnittmengen.<br>`typescript<br>// Union-Typen werden nicht direkt unterstützt<br>`                                                                |
| Implementierung in Klassen     | Kann nicht in einer Klasse implementiert werden.<br>`typescript<br>// Typ-Alias können nicht implementiert werden, nur erweitert.<br>`                                   | Kann von einer Klasse implementiert werden.<br>`typescript<br>interface ClockInterface { currentTime: Date; }<br>class Clock implements ClockInterface { currentTime: Date = new Date(); }<br>`                        |
| Tupel- und Array-Syntax        | Unterstützt sowohl Tupel- als auch Array-Typen explizit.<br>`typescript<br>type StringNumberPair = [string, number];<br>`                                                | Hat keine spezielle Syntax für Tupel.<br>`typescript<br>// Schnittstellen definieren hauptsächlich Objektstrukturen<br>`                                                                                               |
| Komplexität                    | Besser geeignet für komplexe Typdefinitionen mit Unionen oder Schnittmengen.<br>`typescript<br>// Beispiel siehe oben<br>`                                               | Bevorzugt zum Definieren von Objektstrukturen mit Erweiterungsmöglichkeiten.<br>`typescript<br>// Beispiel siehe oben<br>`                                                                                             |
| Anwendungsfall                 | Verwenden Sie, wenn Sie spezifische Typstrukturen benötigen oder wenn Typen nicht ausschließlich Objektstrukturen darstellen.<br>```typescript<br>type Command = 'start' | 'stop';<br>```                                                                                                                                                                                                         | Verwenden Sie für objektorientierte Muster, insbesondere bei der Definition von Verträgen für Objektstrukturen.<br>`typescript<br>interface User {<br>  name: string;<br>  login(): void;<br>}<br>` |

Diese Beispiele verdeutlichen die Flexibilität und spezifischen Verwendungszwecke von Typ-Alias und Schnittstellen in TypeScript und helfen bei der Auswahl des richtigen Werkzeugs basierend auf den Anforderungen Ihres Codes.

### Fazit

Schnittstellen in TypeScript sind ein leistungsstarkes Werkzeug zur Definition und Durchsetzung von Strukturen in Ihrem Code. Sie bieten eine Möglichkeit, Objektstrukturen zu beschreiben, Klassenverträge durchzusetzen und durch Erweiterungen aufzubauen. Durch die Verwendung von Schnittstellen können TypeScript-Entwickler sicherstellen, dass ihr Code spezifischen Mustern und Strukturen entspricht, was zu zuverlässigeren und wartbareren Anwendungen führt. Wenn Sie weiterhin TypeScript erkunden, denken Sie daran, wie Schnittstellen zur Verbesserung der Klarheit und Robustheit Ihres Codes beitragen können.

## Typ-Aussagen in TypeScript

Das statische Typsystem von TypeScript bietet eine umfassende Möglichkeit, die Typen von Variablen in Ihrem Code anzugeben und so die Typsicherheit zur Compile-Zeit zu gewährleisten. Es gibt jedoch Szenarien, in denen Sie möglicherweise mehr über den Typ eines bestimmten Wertes wissen als das Typsystem von TypeScript. Für diese Fälle bietet TypeScript „Typ-Aussagen“ als Möglichkeit, dem Compiler zu sagen: „Vertrau mir, ich weiß, was ich tue.“ Dieses Kapitel behandelt Typ-Aussagen, erklärt deren Syntax, Anwendungsfälle und bewährte Verfahren.

### Verständnis von Typ-Aussagen

Typ-Aussagen sind eine Möglichkeit, die von TypeScript abgeleiteten Typen zu überschreiben, indem Sie manuell einen spezifischeren oder anderen Typ für einen Wert angeben. Es ist wichtig zu beachten, dass Typ-Aussagen den Typ der Variablen zur Laufzeit nicht ändern; sie werden ausschließlich vom TypeScript-Compiler für die Typüberprüfung verwendet.

### Syntax von Typ-Aussagen

TypeScript bietet zwei Syntaxen für Typ-Aussagen:

1. **Spitzwinkel-Syntax**

```typescript
let someValue: any = "this is a string";
let strLength: number = (<string>someValue).length;
As-Syntax
typescript
Code kopieren
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

Beide Syntaxen erreichen dasselbe Ziel; die Wahl zwischen ihnen ist hauptsächlich stilistisch. Wenn Sie jedoch TypeScript mit JSX verwenden, ist nur die `as`-Syntax erlaubt, um Verwirrung mit der Spitzwinkel-Syntax von JSX zu vermeiden.

### Anwendungsfälle für Typ-Aussagen

1. **Arbeiten mit `any`**

Beim Arbeiten mit Variablen vom Typ `any` müssen Sie möglicherweise den spezifischen Typ angeben, um auf bestimmte Eigenschaften oder Methoden zuzugreifen.

```typescript
let input: any = document.getElementById("myInput");
// TypeScript kennt den spezifischen Typ von input nicht, daher wird es als HTMLInputElement angenommen
(input as HTMLInputElement).focus();
```

2. **Überschreiben eines weniger spezifischen Typs**

Manchmal müssen Sie einen Typ überschreiben, den TypeScript für eine Variable abgeleitet hat, um ihn spezifischer zu machen, basierend auf dem Wissen, das Sie über den Wert haben.

```typescript
let pet: Animal = getPet();
// Wir wissen genauer, dass pet ein Dog ist, nicht nur ein Animal
(pet as Dog).bark();
```

3. **Verarbeiten von Union-Typen**

Typ-Aussagen können nützlich sein, wenn Sie einen Wert von einem Union-Typ auf einen spezifischeren Typ eingrenzen.

```typescript
function handleEvent(event: MouseEvent | KeyboardEvent) {
  if ((event as MouseEvent).clientX) {
    console.log("Mouse event:", event.clientX, event.clientY);
  } else {
    console.log("Keyboard event:", (event as KeyboardEvent).key);
  }
}
```

### Best Practices und Vorsichtsmaßnahmen

- **Vermeiden Sie übermäßige Nutzung:** Verlassen Sie sich so weit wie möglich auf die Typerkennung von TypeScript. Übermäßiger Einsatz von Typ-Aussagen könnte ein Zeichen für ein Designproblem in Ihren Typdefinitionen sein.
- **Laufzeitsicherheit:** Denken Sie daran, dass Typ-Aussagen ein Feature zur Compile-Zeit sind. Sie führen keine Typprüfung oder -konvertierung zur Laufzeit durch, stellen Sie daher sicher, dass Ihre Aussagen korrekt sind, um Laufzeitfehler zu vermeiden.
- **Mit Vorsicht verwenden:** Falsche Verwendung von Typ-Aussagen kann zu schwer zu findenden Fehlern führen. Stellen Sie sicher, dass Sie keine falschen Typen nur verwenden, um das Typsystem von TypeScript zu umgehen.

### Fazit

Typ-Aussagen in TypeScript sind ein leistungsfähiges Feature, das Entwicklern die Flexibilität gibt, das Typsystem zu überschreiben, wenn sie zusätzliche Informationen über die Typen in ihrem Code haben. Sie sollten sparsam und verantwortungsvoll verwendet werden, um die Typsicherheit von TypeScript zu respektieren. Zu verstehen, wann und wie man Typ-Aussagen verwendet, ist der Schlüssel zur Beherrschung von TypeScript und zur Entwicklung robuster, typsicherer Anwendungen.

## Literaltypen in TypeScript

Literaltypen in TypeScript stellen eine leistungsstarke und nuancierte Funktion dar, die es Entwicklern ermöglicht, Variablen zu definieren, die auf einen bestimmten Wert oder eine bestimmte Menge von Werten beschränkt sind. Im Gegensatz zu allgemeineren Typen (wie `string`, `number` oder `boolean`), die jeden Wert dieses Typs zulassen, schränken Literaltypen die Möglichkeiten auf exakte Werte ein, was die Ausdruckskraft und Sicherheit des Typsystems erhöht. Dieses Kapitel führt in Literaltypen ein, erkundet ihre Syntax und Nützlichkeit und zeigt, wie man sie effektiv in TypeScript-Anwendungen nutzen kann.

### Einführung in Literaltypen

Literaltypen sind exakte, spezifische Typen, die einen einzelnen Wert darstellen. Anstatt beispielsweise den allgemeinen Typ `string` zu verwenden, können Sie `"admin"` oder `"user"` als Literal-String-Typen für eine Variable angeben, die Benutzerrollen bestimmt. Literaltypen können Zeichenfolgen, Zahlen und Booleans sein und sind entscheidend, um Typen zu erstellen, die die realen Einschränkungen Ihrer Domäne genauer modellieren.

### Syntax von Literaltypen

Das Definieren einer Variable mit einem Literaltyp ist einfach – weisen Sie einfach den spezifischen Wert zu, den die Variable halten soll.

```typescript
let trueFlag: true = true;
let zero: 0 = 0;
let helloWorld: "Hello, world!" = "Hello, world!";
```

In diesen Beispielen sind die Variablen nicht nur mit allgemeinen Typen (`boolean`, `number`, `string`) annotiert, sondern mit Literaltypen, die ihre genauen Werte repräsentieren.

### Kombinieren von Literaltypen mit Union-Typen

Literaltypen zeigen ihre wahre Kraft, wenn sie mit Union-Typen kombiniert werden, wodurch eine Variable einen von einer begrenzten Menge spezifischer Werte annehmen kann.

```typescript
type UserRole = "admin" | "user" | "guest";

let role: UserRole = "admin"; // Gültig
role = "user"; // Auch gültig
// role = "moderator"; // Fehler: Typ '"moderator"' ist nicht dem Typ 'UserRole' zuweisbar.
```

Dieser Ansatz ist besonders nützlich, um Entitäten und Operationen zu modellieren, die nur einen bestimmten Wertebereich annehmen können.

### Literaltypen für Funktionsparameter und Rückgabewerte

Literaltypen können auch Funktionsdeklarationen verbessern, indem sie exakte Werte für Parameter und Rückgabewerte festlegen, was die beabsichtigte Verwendung und das Verhalten der Funktion klarer macht.

```typescript
function setAlignment(alignment: "left" | "right" | "center"): void {
  // Funktionsimplementierung
}

setAlignment("center"); // Gültiger Aufruf
// setAlignment("justify"); // Fehler: Argument des Typs '"justify"' ist nicht dem Parameter des Typs '"left" | "right" | "center"' zuweisbar.
```

### Typableitung mit Literaltypen

TypeScript leitet Literaltypen in bestimmten Kontexten ab, wie z.B. bei `const`-Deklarationen. Wenn Literale jedoch Variablen zugewiesen werden, die mit `let` oder `var` deklariert wurden, wählt TypeScript den allgemeineren Typ (`string`, `number` oder `boolean`), es sei denn, er wird ausdrücklich annotiert.

```typescript
const greeting = "Hello, world!"; // Abgeleiteter Typ: "Hello, world!"
let farewell = "Goodbye, world!"; // Abgeleiteter Typ: string
```

### Eingrenzung mit Literaltypen

Literaltypen sind entscheidend bei Typwächtern und der Kontrollflussanalyse, da sie es TypeScript ermöglichen, den Typ von Variablen innerhalb von bedingten Blöcken einzugrenzen.

```typescript
function processEvent(type: "click" | "scroll", event: Event): void {
  if (type === "click") {
    // TypeScript weiß hier, dass `type` "click" ist
  } else {
    // Hier muss `type` "scroll" sein
  }
}
```

### Best Practices und Überlegungen

- **Wo angemessen verwenden:** Verwenden Sie Literaltypen, um gültige Werte zu erzwingen, wenn eine Variable oder ein Parameter eine gut definierte Menge möglicher Werte hat.
- **Bevorzugen Sie `const`-Aussagen für komplexe Objekte:** Wenn Sie mit Objekten mit festen Formen und Werten arbeiten, ziehen Sie const-Aussagen in Betracht, um Literaltypen automatisch abzuleiten.
- **Kombinieren Sie mit Schnittstellen für reichhaltigeres Modellieren:** Verwenden Sie Literaltypen innerhalb von Schnittstellen, um Eigenschaften mit einem bestimmten Wertebereich zu definieren, was die Typsicherheit und Lesbarkeit des Codes verbessert.

### Fazit

Literaltypen sind ein Beweis für die Flexibilität und Tiefe von TypeScript und bieten Entwicklern präzise Werkzeuge, um die Form und das Verhalten von Daten innerhalb ihrer Anwendungen zu beschreiben. Durch die Integration von Literaltypen, insbesondere in Kombination mit Union-Typen und Schnittstellen, können TypeScript-Praktiker beschreibenderen, sichereren und wartbareren Code erstellen. Das Verstehen und Anwenden von Literaltypen ist ein wichtiger Schritt, um die gesamte Leistungsfähigkeit des TypeScript-Typsystems zu nutzen.

## Generics in TypeScript: Ermöglichung typsicherer Wiederverwendbarkeit

Generics sind eines der leistungsstärksten Features von TypeScript und bieten eine Möglichkeit, wiederverwendbare Komponenten bei gleichzeitiger Wahrung der Typsicherheit zu erstellen. Dieses Konzept, das von anderen statisch typisierten Sprachen übernommen wurde, ermöglicht es Entwicklern, flexible, generische Codeblöcke zu erstellen, die über eine Vielzahl von Typen hinweg funktionieren, anstatt über nur einen einzigen Typ. Dieses Kapitel behandelt die Grundlagen von Generics in TypeScript, zeigt deren Syntax, Anwendungsfälle und wie sie die Wiederverwendbarkeit und Wartbarkeit des Codes verbessern.

### Einführung in Generics

Generics beinhalten im Kern die Verwendung von Typvariablen, die es Ihnen ermöglichen, Klassen, Schnittstellen und Funktionen zu erstellen, die keine genauen Typen für bestimmte Eigenschaften oder Rückgabewerte im Voraus festlegen. Stattdessen werden diese Typen bestimmt, wenn die Komponente verwendet wird. Dieser Ansatz bewahrt die strengen Typüberprüfungsvorteile von TypeScript, während er unvergleichliche Flexibilität bietet, wie Funktionen, Klassen und Schnittstellen implementiert und aufgerufen werden.

### Grundlegende Syntax von Generics

Generics werden typischerweise durch spitze Klammern (`< >`) dargestellt, die eine oder mehrere Typvariablen enthalten. Hier ist ein einfaches Beispiel für eine generische Funktion:

```typescript
function identity<T>(arg: T): T {
  return arg;
}
```

In dieser `identity`-Funktion ist `T` eine Typvariable, die einen Typ repräsentiert, der bestimmt wird, wenn die Funktion aufgerufen wird. Sie können `identity` mit verschiedenen Typen verwenden, und TypeScript stellt sicher, dass Eingabe und Ausgabe denselben Typ haben:

```typescript
let output1 = identity<string>("myString");
let output2 = identity<number>(100);
```

### Generics in Schnittstellen und Klassen

Generics sind nicht auf Funktionen beschränkt; sie können auch auf Schnittstellen und Klassen angewendet werden, um generische Datenstrukturen zu definieren:

```typescript
interface GenericIdentityFn<T> {
  (arg: T): T;
}

class GenericNumber<T> {
  zeroValue: T;
  add: (x: T, y: T) => T;
}
```

### Verwendung mehrerer Typvariablen

Generics können mehrere Typvariablen verwenden, was komplexere Interaktionen zwischen den Typen ermöglicht:

```typescript
function merge<U, V>(obj1: U, obj2: V): U & V {
  return { ...obj1, ...obj2 };
}

let result = merge({ name: "John" }, { age: 30 });
// result ist vom Typ { name: string, age: number }
```

### Generische Einschränkungen

Manchmal müssen Sie möglicherweise die Typen einschränken, die mit Generics verwendet werden können. TypeScript ermöglicht es Ihnen, Einschränkungen mit dem Schlüsselwort `extends` festzulegen:

```typescript
function loggingIdentity<T extends { length: number }>(arg: T): T {
  console.log(arg.length); // Jetzt wissen wir, dass es eine .length-Eigenschaft hat
  return arg;
}
```

### Standard-Generics-Typen

TypeScript unterstützt Standardtypen für Generics, sodass Sie Standardtypen angeben können, wenn keine bereitgestellt werden:

```typescript
function createArray<T = string>(length: number, value: T): T[] {
  return new Array(length).fill(value);
}
```

### Generics mit Typableitung

Bei der Verwendung von Generics versucht TypeScript, die Typen, wenn möglich, abzuleiten, wodurch die Notwendigkeit expliziter Typannotationen reduziert wird:

```typescript
let myIdentity: GenericIdentityFn<number> = identity;
```

### Anwendungsfälle für Generics

- **Datenstrukturen:** Implementieren Sie generische Datenstrukturen wie Stacks, Queues und verkettete Listen, die mit jedem Typ arbeiten können.
- **Utilities:** Erstellen Sie Hilfsfunktionen und -klassen, die mit jedem Typ arbeiten können, wie z.B. Promise-Wrapper, Ereignis-Handler und mehr.
- **Higher-Order Functions:** Erstellen Sie Funktionen, die andere Funktionen zurückgeben oder Funktionen als Argumente annehmen, ohne die Typinformation zu verlieren.

### Fazit

Generics sind ein Eckpfeiler des Typsystems von TypeScript und ermöglichen es Entwicklern, flexible, wiederverwendbare Komponenten zu schreiben, ohne die Typsicherheit zu opfern. Durch das Verständnis und die Anwendung von Generics können Sie die Ausdruckskraft und Wartbarkeit Ihres TypeScript-Codes erheblich verbessern. Generics fördern eine abstraktere Denkweise über Typen, was zu saubereren und anpassungsfähigeren Codebasen führt. Ob Sie Hilfsfunktionen, Datenstrukturen oder komplexe Anwendungslogik erstellen, Generics bieten die Werkzeuge, um spezifische Typenabstraktionen zu erstellen und Ihren Code wiederverwendbar zu machen.

---

## Prozess: Herausforderungen

- Setzen Sie sich mit praktischen Codierungsübungen auseinander, um TypeScript-Konzepte anzuwenden.
- Fördern Sie die Zusammenarbeit und die Nutzung der TypeScript-Dokumentation als Referenz.

---

## Bewertung: Zusammenfassung der Aufgabe / Diskussion des MVP / Lösung

- Diskutieren Sie Lösungen zu Übungen und betonen Sie wichtige Konzepte und Lernergebnisse.
- Klären Sie Zweifel und festigen Sie das Verständnis der TypeScript-Funktionen.

## Abschluss

- Fassen Sie die wichtigsten Erkenntnisse zusammen und ermutigen Sie zur praktischen Anwendung von TypeScript in Projekten.
- Heben Sie die Bedeutung der Typsicherheit hervor und wie TypeScript die Entwicklung unterstützt.

## Schlüsselwörter für die Zusammenfassung:

- Statische Typisierung
- Typannotationen
- Union-Typen
- Generics
- Schnittstellen
- Typ-Aliase
- Literaltypen
