# Security & Privacy

## Vor Veröffentlichung prüfen

Vor dem Upload auf GitHub oder Skool:

- keine API-Keys im JSON
- keine echten Credential-IDs veröffentlichen
- keine privaten Mailadressen veröffentlichen
- keine produktiven Gmail-Credential-Namen veröffentlichen
- keine internen URLs oder Domains veröffentlichen, wenn sie privat sind

Die Datei `gmail-ai-auto-labeling.public.json` wurde dafür bereinigt.

## OpenRouter

Der Workflow sendet nur Metadaten an OpenRouter:

```text
From
From email
From name
Sender domain
Subject
Snippet
Attachments
Bisherige Regel-Labels
```

Der vollständige Mailtext wird nicht übertragen.

## Gmail

Der Workflow setzt Labels auf Gmail-Threads.

Er löscht keine Mails, archiviert keine Mails und markiert keine Mails als gelesen.

## Empfehlung

Workflow erst mehrere Tage nur im Label-Modus laufen lassen und die Ergebnisse prüfen.
