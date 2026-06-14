# StudySmart 🎓

KI-Prüfungstrainer: Lade ein PDF hoch, lass die KI daraus eine Multiple-Choice-Prüfung
erstellen, beantworte sie interaktiv und verfolge deinen Fortschritt. Läuft **komplett im
Browser** (kein Backend, kein Build) – ideal für **GitHub Pages**.

## Online stellen (kein npm, kein Build)

1. Neues Repository auf GitHub anlegen (z. B. `studysmart`).
2. Die Dateien `index.html` und `.nojekyll` ins Repo hochladen
   (auf github.com: **Add file → Upload files**, reinziehen, **Commit**).
3. **Settings → Pages → Source:** Branch `main`, Ordner `/ (root)` → **Save**.
4. Nach ~1 Minute läuft die App unter `https://<dein-name>.github.io/studysmart/`.

## Eigener API-Schlüssel (BYOK)

Jede Person, die die Seite nutzt, trägt oben rechts über das **Zahnrad** ihren **eigenen**
API-Schlüssel ein. Der Schlüssel wird nur lokal im Browser gespeichert (localStorage) und
direkt an den Anbieter gesendet – alle Kosten laufen über das **eigene Token-Guthaben**.

- **Anthropic (Claude):** Schlüssel unter <https://console.anthropic.com/settings/keys>
- **OpenAI (GPT):** Schlüssel unter <https://platform.openai.com/api-keys>

> ⚠️ **API-Schlüssel ≠ Chat-Abo.** Du brauchst einen API-Schlüssel mit Pay-as-you-go-Abrechnung
> (pro Token). Ein **ChatGPT-Plus**- oder **Claude-Pro**-Abo allein funktioniert **nicht** für
> die API. Mit dem Button **„Verbindung testen"** in den Einstellungen kann jeder prüfen, ob
> sein Schlüssel klappt.

> 🔒 Weil dies eine reine Frontend-App ist, liegt der Schlüssel im Browser und ist in den
> Netzwerk-Anfragen sichtbar. Nutze die App nur auf Geräten, denen du vertraust, und teile die
> Seite nicht mit eingetragenem Schlüssel.

## Hinweise

- Beim **ersten Laden** dauert es ein paar Sekunden (React/pdf.js werden per CDN geladen,
  JSX wird im Browser umgewandelt). Internetverbindung nötig.
- **Modell ändern:** in `index.html` oben die Zeilen `ANTHROPIC_MODEL` / `OPENAI_MODEL` anpassen
  (z. B. `claude-haiku-4-5` für geringere Kosten).
- **Gescannte PDFs** (reine Bilder ohne Textebene) enthalten keinen auslesbaren Text.
- Bestanden-Schwelle (Standard 60 %) änderbar über `PASS_THRESHOLD` in `index.html`.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette App in einer Datei |
| `.nojekyll` | Verhindert, dass GitHub Pages Dateien wegfiltert |
| `studysmart-github-pages.zip` | Alle Deploy-Dateien gebündelt zum Hochladen |
