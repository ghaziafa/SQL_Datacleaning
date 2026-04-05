# SQL Data Cleaning — National Housing Dataset
### SQL-Datenbereinigung — Nationaler Immobiliendatensatz

---

## English

### Project Overview
A structured SQL data cleaning project applied to a real-world **National Housing dataset**. The project demonstrates professional-level data cleaning techniques using **Microsoft SQL Server (T-SQL)**, transforming a raw, inconsistent housing dataset into a clean, analysis-ready table through a series of well-documented SQL operations.

---

### Dataset
**Name:** National Housing Data (`national_housing`)
**Database:** `Avacado_Proj.dbo.national_housing`
**Tool:** Microsoft SQL Server (T-SQL)
**Domain:** Real Estate / Property Sales

---

### What the SQL Script Covers

#### Cleaning Steps — In Order

| Step | Operation | SQL Technique Used |
|------|-----------|-------------------|
| 1 | Standardise sale date format | `ALTER TABLE`, `ADD`, `CONVERT(date)`, `UPDATE` |
| 2 | Populate missing property addresses using matching Parcel IDs | `SELF JOIN`, `ISNULL()`, `UPDATE` |
| 3 | Split property address into separate columns (street + city) | `SUBSTRING()`, `CHARINDEX()`, `ALTER TABLE`, `UPDATE` |
| 4 | Split owner address into house number, city and state | `PARSENAME()`, `REPLACE()`, `ALTER TABLE`, `UPDATE` |
| 5 | Standardise "Sold as Vacant" field (Y/N → Yes/No) | `CASE WHEN`, `UPDATE`, `DISTINCT`, `COUNT` |
| 6 | Drop redundant and original columns after splitting | `ALTER TABLE DROP COLUMN` |
| 7 | Remove duplicate records | CTE with `ROW_NUMBER()` |

---

### Key SQL Techniques Demonstrated

- **Self Join** — used to fill missing `PropertyAddress` values by matching rows with the same `ParcelID` but different `UniqueID`
- **ISNULL()** — replaces null address values with a matched non-null address from the same parcel
- **SUBSTRING() + CHARINDEX()** — splits a combined address string into individual street and city columns
- **PARSENAME() + REPLACE()** — parses the owner address into three separate components: house number, city and state
- **CASE WHEN** — standardises inconsistent flag values (`Y` → `Yes`, `N` → `No`)
- **ALTER TABLE ADD / DROP COLUMN** — adds new structured columns and removes original raw columns after splitting
- **ROW_NUMBER() with CTE** — identifies and removes exact duplicate rows

---

### Tools & Technologies
| Tool | Purpose |
|------|---------|
| Microsoft SQL Server | Database engine |
| T-SQL | Query language for all cleaning operations |
| SQL Server Management Studio (SSMS) | Development environment |

---

### Key Skills Demonstrated
- Real-world SQL data cleaning on a property dataset
- Advanced T-SQL: self joins, window functions, string manipulation
- Systematic column engineering from raw combined fields
- Duplicate detection and removal using CTEs
- Schema modification using `ALTER TABLE`

---

### Project Structure
```
SQL_Datacleaning/
│
├── Housing_Society_Proj    ← Main SQL cleaning script (T-SQL)
└── README.md
```

---

### How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/ghaziafa/SQL_Datacleaning.git
   ```
2. Open **SQL Server Management Studio (SSMS)**
3. Create a database called `Avacado_Proj` and import the `national_housing` dataset
4. Open `Housing_Society_Proj` and run the queries section by section

---

## Deutsch

### Projektübersicht
Ein strukturiertes SQL-Datenbereinigungsprojekt, das auf einem echten **nationalen Immobiliendatensatz** angewendet wird. Das Projekt demonstriert professionelle Datenbereinigungstechniken mit **Microsoft SQL Server (T-SQL)** und transformiert einen rohen, inkonsistenten Immobiliendatensatz durch eine Reihe dokumentierter SQL-Operationen in eine saubere, analysebereit e Tabelle.

---

### Datensatz
**Name:** Nationaler Immobiliendatensatz (`national_housing`)
**Datenbank:** `Avacado_Proj.dbo.national_housing`
**Tool:** Microsoft SQL Server (T-SQL)
**Bereich:** Immobilien / Eigentumsverkäufe

---

### Inhalt des SQL-Skripts

#### Bereinigungsschritte — In Reihenfolge

| Schritt | Operation | Verwendete SQL-Technik |
|---------|-----------|----------------------|
| 1 | Standardisierung des Verkaufsdatumsformats | `ALTER TABLE`, `ADD`, `CONVERT(date)`, `UPDATE` |
| 2 | Fehlende Immobilienadressen über übereinstimmende Parcel-IDs befüllen | `SELF JOIN`, `ISNULL()`, `UPDATE` |
| 3 | Immobilienadresse in separate Spalten aufteilen (Straße + Stadt) | `SUBSTRING()`, `CHARINDEX()`, `ALTER TABLE`, `UPDATE` |
| 4 | Eigentümeradresse in Hausnummer, Stadt und Bundesstaat aufteilen | `PARSENAME()`, `REPLACE()`, `ALTER TABLE`, `UPDATE` |
| 5 | Feld "Als leer verkauft" standardisieren (J/N → Ja/Nein) | `CASE WHEN`, `UPDATE`, `DISTINCT`, `COUNT` |
| 6 | Redundante und originale Spalten nach der Aufteilung entfernen | `ALTER TABLE DROP COLUMN` |
| 7 | Doppelte Datensätze entfernen | CTE mit `ROW_NUMBER()` |

---

### Gezeigte SQL-Kernkompetenzen

- **Self Join** — Befüllung fehlender `PropertyAddress`-Werte durch Abgleich von Zeilen mit gleicher `ParcelID` aber unterschiedlicher `UniqueID`
- **ISNULL()** — Ersetzt NULL-Adresswerte durch einen übereinstimmenden Nicht-NULL-Wert desselben Grundstücks
- **SUBSTRING() + CHARINDEX()** — Teilt eine kombinierte Adresszeichenkette in einzelne Straßen- und Stadtspalten auf
- **PARSENAME() + REPLACE()** — Analysiert die Eigentümeradresse in drei separate Komponenten: Hausnummer, Stadt und Bundesstaat
- **CASE WHEN** — Standardisiert inkonsistente Flagwerte (`Y` → `Yes`, `N` → `No`)
- **ALTER TABLE ADD / DROP COLUMN** — Fügt neue strukturierte Spalten hinzu und entfernt ursprüngliche Rohdatenspalten nach der Aufteilung
- **ROW_NUMBER() mit CTE** — Identifiziert und entfernt exakte doppelte Zeilen

---

### Verwendete Tools
| Tool | Zweck |
|------|-------|
| Microsoft SQL Server | Datenbank-Engine |
| T-SQL | Abfragesprache für alle Bereinigungsoperationen |
| SQL Server Management Studio (SSMS) | Entwicklungsumgebung |

---

### Gezeigte Kernkompetenzen
- Echte SQL-Datenbereinigung an einem Immobiliendatensatz
- Fortgeschrittenes T-SQL: Self Joins, Fensterfunktionen, String-Manipulation
- Systematisches Column Engineering aus rohen kombinierten Feldern
- Duplikaterkennung und -entfernung mit CTEs
- Schema-Modifikation mit `ALTER TABLE`

---

### Projektstruktur
```
SQL_Datacleaning/
│
├── Housing_Society_Proj    ← Haupt-SQL-Bereinigungsskript (T-SQL)
└── README.md
```

---

### Ausführung
1. Repository klonen:
   ```bash
   git clone https://github.com/ghaziafa/SQL_Datacleaning.git
   ```
2. **SQL Server Management Studio (SSMS)** öffnen
3. Datenbank `Avacado_Proj` erstellen und den `national_housing`-Datensatz importieren
4. `Housing_Society_Proj` öffnen und die Abfragen Schritt für Schritt ausführen
