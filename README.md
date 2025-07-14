# Git + GitHub Workflow: Beispielprojekt "climate-stripes"

Dies ist eine Schritt-für-Schritt-Anleitung zur Versionierung und Veröffentlichung dieses Projekts mit Git und GitHub. 


## 0. Neues GitHub-Repository erstellen

- Auf https://github.com ein neues Repository erstellen, z. B. `climate-stripes`
- Kein README anlegen (dies wird lokal erstellt)
- Repository-URL kopieren, z. B. `https://github.com/USERNAME/climate-stripes.git`

## 1. Lokales Projektverzeichnis vorbereiten

Einen entsprechenden Ordner erstellen.

## 2. Git initialisieren und erste Dateien hinzufügen

```bash
git init
git status
git add climate_stripes.ipynb climate_stripes.png
git commit -m "first commit: Add our climate stripes notebook and picture."
```
## 3. GitHub Personal Access Token (PAT) erstellen

Um über HTTPS pushen zu können, wird ein Personal Access Token (PAT) benötigt:

1. Aufrufen: https://github.com/settings/tokens
2. "Generate new token (classic)" auswählen
3. Mindestens `repo`-Berechtigungen aktivieren
4. Token generieren und sicher speichern (er wird nur einmal angezeigt)
5. Beim nächsten `git push` den GitHub-Benutzernamen eingeben und als Passwort den Token verwenden

Es gibt hier noch mehr, und vor allem komfortablere Möglichkeiten auf GitHub pushen zu können, ohne jedes mal das PAT eingeben zu müssen.
Das führt jetzt in diesem Rahmen zu weit und kann gut mit Hilfe von z.B. Youtube Videos oder ChatGPT/sonstigen Sprachmodellen durchgeführt werden.

## 4. Mit dem GitHub-Repository verbinden

```bash
git remote add origin https://github.com/kilberd/climate-stripes.git
git branch -M main
```

## 5. Eine .gitignore-Datei erstellen, um unerwünschte Dateien auszuschließen

```bash
touch .gitignore
nano .gitignore
```
Folgende Einträge hinzufügen, um .nc-Dateien auszuschließen:
```bash
*.nc
```
Dann: 
```bash
git add .
git commit -m "Add .gitignore to exclude *.nc files and checkpoints"
```

## 6. Eine README.md hinzufügen

```bash
touch README.md
nano README.md

git add README.md
git commit -m "Add README.md"
```
## 7. Letztlich einmal pushen (alle Commits auf GitHub hochladen)

```bash
git push -u origin main
```

Hier dann Benutzer und PAT eingeben, verbindet erstmals die beiden
branches origin ond main. Alle weiteren Pushs können mit 
```bash
git push
```
gemacht werden. Jetzt noch einmal
```bash
git status
```
 --> alles up to date!
