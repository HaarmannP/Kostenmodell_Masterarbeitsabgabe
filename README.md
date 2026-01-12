# Kostenmodell_Masterarbeitsabgabe
Kostenmodell und Gruppierungsalgorithmen sowie Ergebnisse der Masterarbeit "Kostenoptimierte Ressourcenzuweisung für RPA im  Shared Service Center - Eine modellbasierte Analyse struktureller Kostenwirkung der Prozessgruppenbildung"

## Wissenschaftlicher Kontext

Dieses Repository entstand im Rahmen einer **Masterarbeit** an der **Universität Leipzig** und ist Teil des Anhangs.

**Institutioneller Rahmen:**

- Universität Leipzig  
- Wirtschaftswissenschaftliche Fakultät  
- Institut für Wirtschaftsinformatik  
- Professur WINF / Informationssysteme in der Logistik  

**Thema der Masterarbeit:**

*Kostenoptimierte Ressourcenzuweisung für RPA-Prozesse*  
*Eine modellbasierte Analyse struktureller Kostenwirkungen der Prozessgruppenbildung im Shared Service Center*

Autor: Paolo Herrmann
---

# Kostenmodell für VDI- und Prozesskonfigurationen

Dieses Repository enthält ein simulationsbasiertes Kostenmodell zur Analyse und Bewertung
verschiedener VDI- und Prozesskonfigurationen. Ziel ist es, die Auswirkungen unterschiedlicher
Laufzeiten, Prozessmengen und Gruppenzuweisungsstrategien auf die Gesamtkosten transparent
darzustellen und vergleichbar zu machen.

Das Projekt basiert auf Python-Notebooks, ergänzenden Excel-Konfigurationsdateien sowie
automatisch erzeugten Grafiken und JSON-Ergebnisdateien.

---

## Inhalte und Zielsetzung

Untersucht werden mehrere Varianten eines Kostenmodells, die sich hinsichtlich Laufzeiten,
Skalierung und Prozessanzahl unterscheiden. Neben der reinen Kostenberechnung werden
unterschiedliche Verfahren zur Gruppenzuweisung von Prozessen zu VDI-Pools analysiert.

Die Ergebnisse werden in Form von:
- Tabellen (Excel),
- Konfigurations- und Ergebnisdateien (JSON),
- sowie grafischen Auswertungen (PNG)

bereitgestellt.

---

## Modellkonfigurationen

Im Repository sind folgende Konfigurationen des Kostenmodells enthalten:

- **Standardmodell**
  - VDI-Laufzeit: 20 Stunden pro Tag
  - Referenzkonfiguration für alle Vergleiche

- **Reduzierte VDI-Laufzeit**
  - Reduktion von 20 h auf **2 h pro Tag**
  - Analyse der Kosteneffekte stark verkürzter Laufzeiten

- **Erweiterte VDI-Laufzeit**
  - Erweiterung von 20 h auf **200 h pro Tag**
  - Simulation stark erhöhter Nutzungsintensität

- **Skalierung der Prozesse**
  - **Duplizierung der Prozesse um den Faktor 10**
  - Untersuchung der Kostenentwicklung bei hoher Last

---

## Gruppenzuweisungs- und Optimierungsverfahren

Für jede Modellkonfiguration werden verschiedene Verfahren zur Gruppenzuweisung eingesetzt,
unter anderem:

- Greedy-Verfahren
- Pairing (Top-90 %)
- Preseeding mit Best-Fit
- Score-basierte Greedy-Verfahren mit variablen Gewichtungsparametern

Die Ergebnisse der einzelnen Verfahren werden getrennt gespeichert und ausgewertet.

---

## Verzeichnisstruktur (Auszug)

python for github
├── README.md
├── Kostenmodell v9
│ ├── *.ipynb
│ ├── Prozesslaufzeiten und Konfig *.xlsx
│ ├── Grafiken
│ ├── Grafiken 2h je VDI
│ ├── Grafiken 200h je VDI
│ ├── JSON
│ ├── JSON2h
│ └── JSON200h
├── Kostenmodell x10
│ ├── Kostenmodell x10.ipynb
│ ├── JSONx10
│ └── Grafiken x10
└── Prozesszuweisung
└── *.ipynb


---

## Grafiken und Auswertungen

Zu jeder Modellvariante werden automatisch Grafiken erzeugt, unter anderem:

- Gesamtkosten vs. Anzahl VDIs
- Gesamtkosten vs. Anzahl User-Instanzen
- Gesamtkosten vs. Anzahl Pools
- Kostenstruktur (absolut und anteilig)
- Verteilung der Gesamtkosten über alle Konstellationen
- Korrelationsmatrizen

Die Grafiken sind jeweils in den zugehörigen Unterordnern (`Grafiken`, `Grafiken 2h`,  
`Grafiken 200h`, `Grafiken x10`) abgelegt.

---

## Ergebnisdaten

Die detaillierten Konstellationen der Gruppenzuweisungen werden als JSON-Dateien gespeichert.
Jede Datei repräsentiert eine konkrete Konstellation aus:

- Gruppierungsverfahren
- Poolgröße
- ggf. Gewichtungsparameter (Score-basierte Verfahren)

Diese Dateien bilden die Grundlage für die grafische und tabellarische Auswertung.

---

## Voraussetzungen

Zur Nutzung und Reproduktion der Ergebnisse werden benötigt:

- Python (empfohlen: ≥ 3.9)
- Jupyter Notebook / JupyterLab
- Gängige Python-Bibliotheken für Datenanalyse und Visualisierung  
  (z. B. pandas, numpy, matplotlib, seaborn)

---

## Nutzung

1. Öffnen der gewünschten Notebook-Datei (`.ipynb`)
2. Anpassen der Konfigurationsparameter (etwa Pfade)
3. Ausführen der Zellen zur Neuberechnung der Kostenmodelle
4. Analyse der erzeugten Grafiken und Ergebnisdateien

---

## Hinweise

- Die Ordner `.ipynb_checkpoints` sind automatisch von Jupyter erzeugt und nicht relevant
  für die fachliche Auswertung.
- Excel-Dateien dienen sowohl als Eingabekonfiguration als auch zur Ergebnissicherung.
- Die README beschreibt bewusst die Struktur und Zielsetzung, nicht die interne
  Implementierungslogik der Algorithmen.

---

## Grafiken

In den Ordnern "Grafiken" sind stehts die verschiedenen Ergebnisse und Grafiken der Berechnungen zu finden inklusive eine excel, die alle Ergebnisse der Jahresberechnung auflistet.

---

## Modellvarianten und Versionslogik

Zur besseren Nachvollziehbarkeit der Simulationen und Ergebnisse werden im Repository
mehrere Modellvarianten verwendet, die sich systematisch aus einem gemeinsamen
Basismodell ableiten.

### Kostenmodell v9 (Basismodell)

Das **Kostenmodell v9** stellt das **klassische Referenzmodell** der Arbeit dar.
Es bildet den Ausgangspunkt für alle weiteren Varianten und entspricht dem
Standardfall der Modellierung.

Charakteristika:
- Standardisierte Prozessmengen
- VDI-Laufzeit von **20 Stunden pro Tag**
- Referenz für Kostenvergleiche und Sensitivitätsanalysen

Alle Abweichungen werden ausschließlich relativ zu diesem Modell interpretiert.

---

### Modellvariante: Reduzierte VDI-Laufzeit (2h)

Die Modellvariante **2h** basiert vollständig auf dem Kostenmodell v9,
unterscheidet sich jedoch durch eine **reduzierte tägliche VDI-Laufzeit**.

Charakteristika:
- Identische Prozess- und Kostenstruktur wie v9
- Reduzierung der VDI-Laufzeit von **20 h auf 2 h pro Tag**
- Analyse der Kosteneffekte stark verkürzter Nutzungszeiten

Die Ergebnisse sind in separaten Notebook-, Grafik- und JSON-Verzeichnissen abgelegt.

---

### Modellvariante: Erweiterte VDI-Laufzeit (200h)

Die Modellvariante **200h** stellt eine Erweiterung des Basismodells v9 dar
und simuliert eine stark erhöhte VDI-Nutzungsintensität.

Charakteristika:
- Identische Prozess- und Kostenstruktur wie v9
- Erhöhung der VDI-Laufzeit von **20 h auf 200 h pro Tag**
- Untersuchung nichtlinearer Kostenwirkungen bei hoher Auslastung

---

### Modellvariante: Skalierung der Prozessmenge (x10)

Die Modellvariante **x10** erweitert das Basismodell v9 durch eine
**Verzehnfachung der Prozessmenge**.

Charakteristika:
- Faktor **10** auf die Anzahl der Prozesse
- Unveränderte Laufzeitannahmen gegenüber dem Basismodell
- Analyse von Skaleneffekten und strukturellen Kostenverschiebungen

Diese Variante ist in einem eigenen Verzeichnis (`Kostenmodell x10`) abgelegt
und verwendet separate Konfigurations-, JSON- und Grafikdateien.

-> Die Ausführung des Codes kann deutlich länger dauern als bei den anderen Varianten.
