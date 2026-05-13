# Anpassung der Regeln

## Neue Regel hinzufügen

Node:

```text
Classify Mail
```

Im Array `RULES` ergänzen:

```javascript
{
  group: "mygroup",
  label: "AUTO/MeinLabel",
  domains: ["example.com"],
  keywords: ["rechnung", "invoice", "account"],
  minScore: 70,
  trusted: true
}
```

## Bedeutung der Felder

| Feld | Bedeutung |
|---|---|
| `group` | pro Gruppe wird nur der beste Treffer genommen |
| `label` | Gmail-Labelname |
| `domains` | Absenderdomains |
| `keywords` | Suchbegriffe in Absender, Betreff, Snippet, Anhängen |
| `minScore` | Mindestscore für Treffer |
| `trusted` | true = harte, zuverlässige Regel |

## Wichtig-Label

Für kritische Mails wird zusätzlich gesetzt:

```text
AUTO/Wichtig
AUTO/Dringend
```

Die Logik liegt in `IMPORTANT_RULES`.

Typische Fälle:

```text
Anwalt
Polizei
Bank/Kredit
Versicherung
Arzttermin
```

## KI-Prompt anpassen

Wenn du neue Labels ergänzt, solltest du sie auch in der Node `AI Classify Mail` in die erlaubte Label-Liste aufnehmen.

## Merge AI Result

Wenn neue Labels auch von der KI zurückgegeben werden dürfen, müssen sie zusätzlich in `Merge AI Result` unter `ALLOWED_LABELS` stehen.
