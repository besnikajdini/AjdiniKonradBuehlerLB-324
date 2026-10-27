# LB 324

## Aufgabe 2
Die Datei .pre-commit-config.yaml definiert zwei Automatisierungen:

- *Bei jedem Commit* (Stage pre-commit): black formatiert die Python-Dateien automatisch. Hat black etwas geändert, bricht der Commit ab. Dann die Dateien mit git add . erneut hinzufügen und nochmals committen.
- *Bei jedem Push* (Stage pre-push): pytest führt alle Tests aus. Schlägt ein Test fehl, wird der Push abgebrochen.

### Installation (einmalig nach dem Klonen)

    pip install -r requirements.txt
    pip install pre-commit
    pre-commit install

pre-commit install installiert dank default_install_hook_types beide Hooks (pre-commit und pre-push). Gleichwertig, aber ausführlich:

    pre-commit install --hook-type pre-commit --hook-type pre-push

### Manuell ausführen

    pre-commit run --all-files                          # black auf alle Dateien
    pre-commit run --hook-stage pre-push --all-files    # Tests wie beim Push

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