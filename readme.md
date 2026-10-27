# LB 324

## Aufgabe 2
Erklären Sie hier, wie man `pre-commit` installiert.

## Aufgabe 4
**Laufende Applikation:** https://ajdinikonradbuehler-lb324-cdenatcuase9erct.germanywestcentral-01.azurewebsites.net

### Passwort aus der `.env` auf Azure übertragen
1. Im Azure Portal unter **App Services** die Applikation `ajdinikonradbuehler-lb324` öffnen.
2. Links unter **Einstellungen → Umgebungsvariablen** → Reiter **App-Einstellungen** → **+ Hinzufügen**.
3. Name `PASSWORD`, Wert = GitHub-Benutzername `besnikajdini` (ohne Anführungszeichen) → **Übernehmen** → **Übernehmen** → **Bestätigen**. Die App startet neu.
4. Die App liest den Wert mit `os.getenv("PASSWORD")`. Auf Azure gibt es keine `.env`-Datei: Azure stellt die App-Einstellung als Umgebungsvariable bereit. Die `.env` steht in der `.gitignore` und kommt nie auf GitHub.
5. Unter **Konfiguration → Allgemeine Einstellungen** ist als Startbefehl `gunicorn --bind=0.0.0.0 --timeout 600 app:app` eingetragen.
6. Kontrolle: URL öffnen und mit dem GitHub-Benutzernamen einloggen.

### Automatische Auslieferung
Im **Bereitstellungscenter** ist GitHub mit dem Branch `main` verbunden. Der Workflow `.github/workflows/main_ajdinikonradbuehler-lb324.yml` läuft bei jedem Push auf `main`, also bei jedem gemergten PR von `dev` nach `main`, und liefert die App neu auf Azure aus.