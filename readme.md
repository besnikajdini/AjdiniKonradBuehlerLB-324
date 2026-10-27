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
Erklären Sie hier, wie Sie das Passwort aus Ihrer lokalen `.env` auf Azure übertragen.