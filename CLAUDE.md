# CLAUDE.md — Portfolio Christian Epping

## Projekt
Persönliches Portfolio (christian-epping.com) von Christian Epping, Senior UX/UI
Designer mit Schwerpunkt auf komplexen eCommerce-Lösungen und Produkt-Konfiguratoren.
Quelle liegt in diesem GitHub-Repo, Deployment läuft automatisch über Vercel bei
jedem Push auf `main`.

## Sprachen (zweisprachig: DE + EN)
Die Seite ist vollständig zweisprachig — Deutsch und Englisch sind gleichwertig.
- Inhaltsparität: Jede Seite existiert in beiden Sprachen mit gleichem Informationsgehalt.
- Struktur: Sprachpfade `/de/…` und `/en/…`; die Wurzel `/` leitet sinnvoll weiter
  (z. B. anhand der Browsersprache) oder zeigt eine neutrale Sprachauswahl.
- Sprachumschalter: auf jeder Seite sichtbar und persistent; er wechselt auf die
  entsprechende Seite in der anderen Sprache, nicht zurück zur Startseite.
- Korrektes `lang`-Attribut im `<html>` und `hreflang`-Verweise zwischen den
  Sprachversionen (SEO).
- EN ist eigenständig formuliert, keine wörtliche Übersetzung des DE-Texts.

## Positionierung (wichtigste Regel)
Die Seite ist **outcome- und KPI-getrieben**, nicht prozess- oder passion-getrieben.
- Jede Case Study folgt dem Muster: Ausgangsproblem → Eingriff → messbares Ergebnis
  (z. B. Conversion, Time-to-Configure, Fehlerrate im Konfigurator, Umsatz, Support-Last).
- Selbstbewusst und konkret formulieren. Vage Design-Prosa vermeiden
  ("mit viel Leidenschaft gestaltet", "user-centric journey" o. Ä.).
- Wo eine Zahl fehlt, lieber eine ehrliche Wirkungs-Aussage als eine Floskel.

## Design-System
- **Typografie:** Fraunces für Headlines/Display, Inter für Fließtext und UI.
  Keine weiteren Schriftfamilien ohne Rückfrage.
- **Akzentfarbe:** `#FF002E` als durchgängiges Signature-Motiv — bewusst und
  sparsam als Signatur eingesetzt (Akzente, Hover-States, Marker, Detail-Linien),
  nicht flächig als Hintergrund.
- **Look:** reduziert, editorial, großzügiger Weißraum, klare typografische Hierarchie.

## Technik — Tailwind CSS v4
- Styling-Framework ist Tailwind CSS v4 über die Standalone-CLI (kein Bundler nötig).
- Zwei Pakete installieren: `tailwindcss` + `@tailwindcss/cli`. Der alte v3-Befehl
  `npx tailwindcss` funktioniert nicht — der CLI liegt jetzt in `@tailwindcss/cli`.
- Eine Eingabedatei (`src/input.css`) mit `@import "tailwindcss";` als Basis.
- Markenwerte CSS-first im `@theme`-Block definieren (keine JS-Config):
  Fraunces/Inter als Font-Variablen, `#FF002E` als Brand-Farbe. So sind sie überall
  als Utilities verfügbar (z. B. `font-display`, `text-brand`).
- Build: `npx @tailwindcss/cli -i ./src/input.css -o ./dist/output.css`
  (`--watch` für lokale Entwicklung, `--minify` für Produktion).
- Auf Vercel den Build-Command entsprechend setzen, damit `output.css` beim
  Deploy erzeugt wird.
- Ansonsten statisches HTML/JS. Semantisches, barrierearmes Markup; Kontrast von
  `#FF002E` auf Text prüfen. Responsive, Mobile-first.
- Weitere Abhängigkeiten nur nach Rückfrage aufnehmen.

## Arbeitsweise
- Kleine, nachvollziehbare Änderungen mit sprechenden Commit-Messages.
- Vor größeren Umbauten kurz den Plan skizzieren und abstimmen.
- Beide Sprachfassungen konsistent halten: eine Änderung an einer Seite immer auch
  in der anderen Sprache nachziehen.
- Nichts committen oder pushen, ohne dass ich es vorher gesehen habe.
