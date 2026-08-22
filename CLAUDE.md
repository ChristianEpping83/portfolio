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

## Technik — schlankes, modernes CSS
- Kein Framework, kein Build-Schritt, kein npm. Statisches HTML/CSS/JS, das Vercel
  direkt ausliefert. Die bestehende Pipeline bleibt unverändert (auf Vercel ist
  weiterhin kein Build-Command nötig).
- Ein zentrales Stylesheet (z. B. `css/style.css`), das von allen Seiten eingebunden
  wird — keine verstreuten Inline-Styles.
- Design-Tokens einmal zentral als CSS-Variablen im `:root` definieren und überall
  darüber nutzen (nicht jeden Wert einzeln hart codieren):
    :root {
      --brand: #FF002E;
      --font-display: "Fraunces", serif;
      --font-body: "Inter", sans-serif;
    }
- Fraunces und Inter als Webfonts einbinden (Google Fonts oder selbst gehostet).
- `#FF002E` bewusst und sparsam als Signature einsetzen. Für Fließtext ist der Ton
  meist zu grell — Kontrast prüfen und die Farbe eher für Akzente als für Textfarbe
  verwenden.
- Semantisches, barrierearmes Markup. Responsive, Mobile-first.
- Bestehende Grafiken weiterverwenden: referenzieren, nicht neu erzeugen.
  Bild-Optimierung (WebP/AVIF, lazy loading, responsive Größen) ist ein späterer
  Feinschliff, kein Neuaufbau.
- Zusätzliche Abhängigkeiten oder ein Build-Schritt nur nach ausdrücklicher Rückfrage.

## Arbeitsweise
- Kleine, nachvollziehbare Änderungen mit sprechenden Commit-Messages.
- Vor größeren Umbauten kurz den Plan skizzieren und abstimmen.
- Beide Sprachfassungen konsistent halten: eine Änderung an einer Seite immer auch
  in der anderen Sprache nachziehen.
- Nichts committen oder pushen, ohne dass ich es vorher gesehen habe.
