Hausaufgabenblatt: Einführung in GitHub Actions 

Ziel: 
Dieses Hausaufgabenblatt führt dich in GitHub Actions ein, ein weiteres beliebtes CI/CD-Tool, das besonders für GitHub-basierte Projekte genutzt wird. Du wirst einfache Pipelines in GitHub Actions erstellen, die Unterschiede zwischen Jenkins und GitHub Actions verstehen und einige YAML-basierte Übungen machen. Erstelle dafür auch ein neues Github Repo  

 

 

1. Erstelle eine einfache GitHub Actions Pipeline 

Erstelle in deinem GitHub-Repository eine neue Datei im Ordner .github/workflows mit dem Namen ci-pipeline.yml. Diese Datei beschreibt die Schritte für deine CI-Pipeline. 

Die Pipeline soll bei jedem Push auf den main-Branch ausgeführt werden. 

Erstelle drei Schritte:  

Checkout des Repositories – Verwende actions/checkout@v2. 

Installiere Node.js – Verwende actions/setup-node@v2. 

Führe Tests mit npm aus – Verwende den Befehl npm test (du kannst die Installation von Abhängigkeiten überspringen, wenn keine vorhanden sind). 

Erwartung: 
Eine einfache CI-Pipeline, die bei jedem Push auf den main-Branch Tests ausführt. 

2. GitHub Actions und Jenkins: Unterschiede 

Konfigurationsdateien: 
Vergleiche, wie eine Pipeline in GitHub Actions und Jenkins konfiguriert wird. Erstelle eine einfache Jenkinsfile-Pipeline und beschreibe die Unterschiede in der Syntax und Struktur im Vergleich zu einer GitHub Actions YAML-Datei. 

CI/CD-Pipelines: 
Welche der folgenden Konzepte sind in beiden Tools vorhanden und wie werden sie implementiert? 

Trigger (z. B. bei einem Push) 

Jobs und Steps 

Artefakte speichern 

Parallelisierung von Aufgaben 

 

3. YAML-Übung 

GitHub Actions verwendet YAML-Dateien zur Konfiguration von Workflows. Mach dir mit der YAML-Syntax vertraut, indem du folgende Übungen machst: 

Erstelle eine YAML-Datei: 
Erstelle eine YAML-Datei mit den folgenden Eigenschaften: 

Ein Key-Value-Paar für den Namen des Workflows. 

Ein Array von Branches, bei denen der Workflow ausgelöst wird. 

Eine einfache If-Bedingung für das Ausführen eines Schrittes, abhängig von einem Eingabewert (z. B. nur ausführen, wenn eine Umgebungsvariable gesetzt ist). 

Fehlerbehebung in einer YAML-Datei: 
Gegeben ist eine fehlerhafte YAML-Datei, die nicht korrekt funktioniert: 

name: Simple Workflow 

on: 

  push: 

    branches: 

      - main 

jobs: 

  build: 

    runs-on: ubuntu-latest 

    steps: 

      - name: Checkout Repository 

        uses: actions/checkout@v2 

      - name: Run Command 

        run: echo "Hello, World!" 

      - name: Create File 

        run: touch newfile.txt 

        if: success 

      - name: Print Message 

        run: echo "The workflow completed successfully." 

 

Identifiziere drei Fehler in der YAML-Datei. 

Erkläre, warum diese Fehler entstehen und wie du sie beheben würdest. 

Hinweise: 

Achte auf die Struktur und die korrekte Verwendung von YAML-Syntax. 

Prüfe, ob alle verwendeten Schlüssel korrekt sind und die Logik sinnvoll ist. 

 

Erwartung: 
Die Schüler sollten in der Lage sein, Fehler zu erkennen, zu erklären und zu beheben, um eine funktionierende GitHub Actions-Pipeline zu erstellen. 

 

4. Jenkinsfile mit YAML vergleichen 

Erstelle ein einfaches Jenkinsfile, das dieselben Schritte ausführt wie die GitHub Actions-Pipeline aus der ersten Übung. Achte darauf, wie du den Workflow definierst, die Schritte beschreibst und Abhängigkeiten zwischen den Jobs angibst. 

Vergleiche beide Dateien (Jenkinsfile und GitHub Actions YAML) und beschreibe die wichtigsten Unterschiede in der Syntax und Struktur. 

 

Abgabe 

Reiche dein GitHub-Repository mit der .github/workflows/ci-pipeline.yml Datei ein. 

Reiche die Jenkinsfile-Datei und die Vergleiche zwischen Jenkins und GitHub Actions als Text oder in einem Dokument ein. 

Schicke die YAML-Übungen als separate Dateien oder Screenshots zur Kontrolle ein. 

 

Bonus-Aufgabe (optional) 

Erstelle eine GitHub Actions-Pipeline, die bei einem Push auf den main-Branch eine zusätzliche Nachricht ausgibt, z. B. echo "This is a simple CI pipeline!". 

 