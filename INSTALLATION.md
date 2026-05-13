# Installation

## 1. Workflow importieren

1. n8n öffnen.
2. Neuen Workflow erstellen oder bestehende Workflows öffnen.
3. Menü oben rechts öffnen.
4. `Import from File` auswählen.
5. Datei `workflows/gmail-ai-auto-labeling.public.json` importieren.

## 2. Gmail Credentials setzen

In diesen Nodes das eigene Gmail OAuth2 Credential setzen:

```text
Gmail Trigger
Get many messages
Apply Labels to Gmail Thread
```

## 3. OpenRouter Credential setzen

In der Node `AI Classify Mail`:

```text
Authentication: Generic Credential Type
Generic Auth Type: Bearer Auth
Credential: eigenes OpenRouter Bearer Credential
```

Tokenformat:

```text
sk-or-...
```

Nicht direkt in den JSON-Body schreiben.

## 4. Gmail Labels anlegen

Lege die Labels in Gmail an, z. B.:

```text
AUTO
AUTO/Review
AUTO/Fehler
AUTO/Wichtig
AUTO/Amazon
AUTO/Bank/Haspa
AUTO/Server/Hetzner
```

## 5. Label-IDs mappen

In n8n einmal testweise ein Label setzen oder Gmail Labels abfragen und die internen IDs in `Map Gmail Label IDs` eintragen.

## 6. Testlauf

Workflow manuell starten und prüfen:

```text
Get many messages → 20 Items
Loop Over Items → einzelne Verarbeitung
Apply Labels → gewünschte Label IDs
```

## 7. Aktivieren

Erst aktivieren, wenn mindestens 2 bis 3 Testläufe korrekt waren.
