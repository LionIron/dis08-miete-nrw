# DIS08 – Datenanalyse von Mietpreisen und Studentenwohnheimen in NRW

Dieses Repository enthält die Prüfungsarbeit für das Modul **DIS08 **.  
Ziel des Projekts ist es, mithilfe von Datenanalyse-Verfahren Einblicke in den Wohnungsmarkt in Nordrhein-Westfalen (NRW) sowie in die Versorgung mit Studentenwohnheimen zu gewinnen.

Das Projekt besteht aus **zwei inhaltlich getrennten, aber miteinander verknüpften Projektteilen**, die jeweils nach dem **OSEMN-Framework** (Obtain, Scrub, Explore, Model, Interpret) umgesetzt wurden.

---

## Projektübersicht

### Projektteil 1: Mietpreise in NRW  
Analyse von Mietangeboten in NRW mit Fokus auf Preisunterschiede, Wohnungsmerkmale und Musterbildung.

### Projektteil 2: Studentenwohnheime in NRW  
Analyse der Wohnheimversorgung an Hochschulorten in NRW und Verknüpfung mit den Ergebnissen aus Projektteil 1.

---

## Datensätze

### Projektteil 1 – Mietdaten

- **Datei:** `data/raw/immo_data.csv`  
- **Quelle:** Kaggle  
  https://www.kaggle.com/datasets/corrieaar/apartment-rental-offers-in-germany/data  
- **Beschreibung:** Mietangebote für Wohnungen in Deutschland mit Angaben zu Preis, Wohnfläche, Ausstattung und Standort.

---

### Projektteil 2 – Studentenwohnheime

- **Datei:** `data/raw/student_housing/Studentenwohnheime_DE.xlsx`  
- **Quelle:** GovData  
  https://www.govdata.de/suche/daten/studierendenwohnheime-wohnheimplatze-studierende-sowie-wohnheimplatzrelationen-nach-hochschulor06b1a  
- **Beschreibung:** Studierendenwohnheime, Wohnheimplätze, Studierendenzahlen und Wohnheimplatzrelationen nach Hochschulorten in Deutschland.

- **Datei:** `data/raw/student_housing/Studentenwohnheime_BONN.json`  
- **Quelle:** Open.NRW  
  https://open.nrw/dataset/standorte-der-studentenwohnheime-bn  
- **Beschreibung:** Geografische Standorte der Studentenwohnheime in Bonn zur räumlichen Analyse.

---

## Forschungsfragen

### Projektteil 1 – Mietpreise in NRW

1. **Wie unterscheiden sich die Mietpreise pro Quadratmeter zwischen den Städten in NRW?**
2. **Sind kleinere Wohnungen pro Quadratmeter teurer als größere Wohnungen?**
3. **Haben Wohnungsmerkmale (z. B. Balkon, Küche, Baujahr) einen messbaren Einfluss auf die Mietpreise?**
4. **Lassen sich Mietangebote in NRW mithilfe von Datenanalyse-Methoden in unterschiedliche Muster gruppieren?**

---

### Projektteil 2 – Studentenwohnheime

**RQ-S1:**  
Wie unterscheiden sich Hochschulorte in NRW in der Wohnheimversorgung (Wohnheimplatzrelation)?

**RQ-S2:**  
Hängt die Wohnheimplatzrelation mit der Anzahl der Studierenden zusammen?

**RQ-S3:**  
Haben „teure“ Städte (basierend auf der Mietanalyse aus Projektteil 1) eine andere Wohnheimversorgung als „günstige“ Städte?

**RQ-S4:**  
Wie ist die räumliche Verteilung der Studentenwohnheime innerhalb der Stadt Bonn?

---

## Projektstruktur

--

<code>

dis08-miete-nrw/
│
├── data/
│ ├── raw/
│ │ ├── immo_data.csv
│ │ └── student_housing/
│ │ ├── Studentenwohnheime_DE.xlsx
│ │ └── Studentenwohnheime_BONN.json
│ └── processed/
│ ├── nrw_clean.csv
│ ├── city_price_groups.csv
│ └── student_housing_nrw_clean.csv
│
├── notebooks/
│ ├── 01_obtain.ipynb
│ ├── 02_scrub.ipynb
│ ├── 03_explore.ipynb
│ ├── 04_model_hypothesis_testing.ipynb
│ ├── 05_interpret.ipynb
│ │
│ └── student_housing/
│ ├── 01_obtain_student_housing.ipynb
│ ├── 02_scrub_student_housing.ipynb
│ ├── 03_explore_student_housing.ipynb
│ ├── 04_model_student_housing.ipynb
│ └── 05_interpret_student_housing.ipynb
│
├── docs/
│ └── (gespeicherte Grafiken und Abbildungen)
│
├── project_plan.md
└── README.md

</code>

--


---

## Methodisches Vorgehen (OSEMN)

### Obtain
- Laden der Rohdatensätze
- Erste Struktur- und Inhaltsprüfung

### Scrub
- Filtern auf NRW
- Entfernen oder Behandeln fehlender Werte
- Erzeugen abgeleiteter Variablen (z. B. Preis pro m²)
- Auswahl relevanter Merkmale

### Explore
- Deskriptive Statistiken
- Visualisierungen (Histogramme, Boxplots, Scatterplots)
- Vergleich von Städten und Gruppen

### Model
- Hypothesentests (z. B. Mann-Whitney-U-Test)
- Korrelationsanalysen (Spearman)
- Clustering (K-Means) zur Mustererkennung

### Interpret
- Zusammenfassung der Ergebnisse
- Beantwortung der Forschungsfragen
- Diskussion von Einschränkungen und Zusammenhängen zwischen beiden Projektteilen

---

## Verwendete Python-Bibliotheken

- pandas
- numpy
- matplotlib
- scipy
- scikit-learn
- pathlib
- json

---

## Verbindung beider Projektteile

Die Ergebnisse aus Projektteil 1 (Mietpreisniveau nach Stadt) werden genutzt, um Städte in **„teure“ und „günstige“ Gruppen** einzuteilen.  
Diese Einteilung dient als Grundlage für Projektteil 2, um zu untersuchen, ob ein Zusammenhang zwischen **Mietniveau** und **Wohnheimversorgung** besteht.

---

## Hinweise

- Die Notebooks sind **in der vorgesehenen Reihenfolge auszuführen**.
- Alle Analyseergebnisse werden ausschließlich aus den angegebenen Datensätzen abgeleitet.
- Die Interpretation orientiert sich an den in der Vorlesung vermittelten statistischen Grundlagen.

---

## Autor:in

Studiengang: Data & Information Science  
Modul: DIS08  
Prüfungsprojekt

