# React-Projekt Setup

## Lernziele

- Ein allgemeines Verständnis für Projekt-Strukturierung entwickeln
- Lernen, wie man mit Vite ein React-Projekt erstellt
- Den Zweck eines Bundlers verstehen
- Häufige `npm`-Skripte verstehen
- Den Unterschied zwischen `public` und `src` Ordner kennen

---

## Projekt-Strukturierung

Projekt-Strukturierung ist der Prozess der Erstellung eines neuen Projekts. Du wirst
[Vite](https://vitejs.dev/guide/#getting-started) verwenden, um automatisch ein neues React-Projekt zu erstellen.

> 💡 Grundsätzlich könntest du ein neues React-Projekt von Grund auf erstellen. Das würde jedoch viel Arbeit erfordern und wir müssten viele Dinge selbst einrichten. Zum Beispiel müsstest du einen Entwicklungsserver, einen Build-Prozess und einen Test-Runner einrichten. Außerdem müsstest du einen Modul-Bundler und einen Transpiler konfigurieren. Das ist viel Arbeit und du müsstest es jedes Mal tun, wenn du ein neues Projekt erstellen möchtest.

> 💡 Übrigens, Vite funktioniert sehr ähnlich wie das `ghcd`-Tool, das du wahrscheinlich schon verwendet hast.

## Vite

Vite ist ein lokaler Entwicklungsserver für Webanwendungen. Es enthält auch ein Tool, das es dir ermöglicht, mit einem einzigen Befehl ein React-Projekt zu erstellen. Es ist ein großartiges Werkzeug, um mit React zu beginnen.

> 📙 Lies
> [**Scaffolding Your First Vite Project** in der Vite-Dokumentation](https://vitejs.dev/guide/#scaffolding-your-first-vite-project)
> um zu erfahren, wie man mit `npm` ein neues Projekt erstellt.

### Ordnerstruktur

Vite erstellt für dich eine Ordnerstruktur mit vielen Dateien und Ordnern.

Am wichtigsten sind `src`, `src/components` und `public`, die wir besprechen werden.

### Verfügbare Skripte

Vite bietet ein paar mehr npm-Skripte als die, die du bisher gesehen hast. Neben dem Starten eines Entwicklungsservers und dem Ausführen von Tests kannst du sie auch verwenden, um deine App zu bauen.

Die wichtigsten Skripte für uns sind `dev`, `lint` und `preview`. `build` wird in der Regel nur für Produktionsumgebungen verwendet.

> 📙 Lies mehr über
> [das Bauen und Vorschauen einer Vite+React Seite](https://vitejs.dev/guide/static-deploy.html#deploying-a-static-site)

### Hinzufügen eines Stylesheets

Du kannst CSS-Dateien direkt in deinen JavaScript-Dateien importieren.

Es ist üblich, dein CSS zusammen mit deinen Komponenten zu speichern. Das bedeutet, dass du eine CSS-Datei mit dem gleichen Namen wie die Komponente hast, die in der JavaScript-Datei der Komponente importiert wird. Es ist eine gute Praxis, die BEM-Namenskonvention für deine CSS-Klassen zu verwenden, um Namenskonflikte zwischen Komponenten zu vermeiden.

> 📙 Lies mehr über
> [**Hinzufügen eines Stylesheets** in der Vite-Dokumentation](https://vitejs.dev/guide/features.html#css).

### Hinzufügen von Bildern, Schriftarten und Dateien

Du kannst Bilddateien oder Schriftarten direkt in deinen JavaScript-Dateien importieren.

> 📙 Lies mehr über
> [**Hinzufügen von Bildern, Schriftarten und Dateien** in der Vite-Dokumentation](https://vitejs.dev/guide/assets.html#static-asset-handling).

## Ressourcen

- [Scaffolding Your First Vite Project in der Vite-Dokumentation](https://vitejs.dev/guide/#scaffolding-your-first-vite-project)
- [Das Bauen und Vorschauen einer Vite+React Seite](https://vitejs.dev/guide/static-deploy.html#deploying-a-static-site)
- [Hinzufügen eines Stylesheets in der Vite-Dokumentation](https://vitejs.dev/guide/features.html#css)
- [Hinzufügen von Bildern, Schriftarten und Dateien in der Vite-Dokumentation](https://vitejs.dev/guide/assets.html#static-asset-handling)
