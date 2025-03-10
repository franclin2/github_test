### Vergleich: GitHub Actions YAML vs. Jenkinsfile

| **Aspekt**                  | **GitHub Actions (YAML)**                                                                                     | **Jenkinsfile (Groovy)**                                                                                   |
|-----------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Sprache**                 | YAML                                                                                                          | Groovy                                                                                                    |
| **Pipeline-Struktur**       | Jobs und Steps (`jobs.<job_id>.steps`)                                                                        | Stages und Steps (`pipeline { stages { stage { steps } } }`)                                              |
| **Trigger**                 | Definiert in `on:` (z. B. `push`, `pull_request`)                                                             | Trigger werden außerhalb des Jenkinsfiles konfiguriert (z. B. in der Jenkins UI oder Multibranch Pipelines). |
| **Agent/Runner**            | `runs-on` gibt die Umgebung an (z. B. `ubuntu-latest`).                                                      | `agent` definiert die Umgebung (z. B. `label 'ubuntu-latest'`).                                           |
| **Schrittdefinition**       | Schritte werden als Liste unter `steps:` definiert, z. B. `run: npm install`.                                | Schritte werden mit `sh` oder anderen Groovy-Befehlen definiert, z. B. `sh 'npm install'`.               |
| **Abhängigkeiten zwischen Jobs** | Jobs können explizit voneinander abhängen (`needs:`).                                                     | Abhängigkeiten zwischen Stages sind implizit und folgen der Reihenfolge im Jenkinsfile.                  |
| **Hosting**                 | Läuft auf GitHub-gehosteten oder selbst-gehosteten Runnern.                                                  | Läuft auf vom Nutzer selbst verwalteten Jenkins-Servern oder Build-Agenten.                              |
| **Installation von Node.js**| Fertige Action (`actions/setup-node@v2`) mit einfacher Konfiguration (`node-version`).                        | Manuelle Installation über Shell-Befehle (`curl` und `apt-get`).                                         |

---

### Wichtige Unterschiede

1. **Sprache und Syntax**:
   - GitHub Actions verwendet YAML, das einfacher zu lesen und zu schreiben ist, besonders für Einsteiger.
   - Jenkins verwendet Groovy, das flexibler, aber komplexer ist.

2. **Pipeline-Struktur**:
   - GitHub Actions organisiert Workflows in Jobs und Steps, während Jenkins Pipelines in Stages und Steps unterteilt.
   - In GitHub Actions können Jobs parallel ausgeführt werden, während in Jenkins die Reihenfolge der Stages linear ist.

3. **Trigger-Konfiguration**:
   - In GitHub Actions wird die Trigger-Logik direkt im YAML definiert (`on: push`).
   - In Jenkins erfolgt die Trigger-Konfiguration oft außerhalb des Jenkinsfiles (z. B. in der UI).

4. **Node.js-Setup**:
   - GitHub Actions nutzt vorgefertigte Actions wie `actions/setup-node@v2`, was den Prozess vereinfacht.
   - In Jenkins erfolgt das Setup manuell über Shell-Befehle.

5. **Hosting und Wartung**:
   - GitHub Actions bietet gehostete Runner, während Jenkins eine eigene Serverinfrastruktur benötigt.

---

### Fazit

GitHub Actions ist einfacher einzurichten und zu warten, da es YAML verwendet und viele vorgefertigte Aktionen bereitstellt. Jenkins bietet mehr Flexibilität und Kontrolle, erfordert aber mehr Aufwand bei der Konfiguration und Wartung.
