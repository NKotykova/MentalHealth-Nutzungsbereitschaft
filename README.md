# Vorhersage der Nutzungsbereitschaft von Mental-Health-Angeboten

Dieses Projekt untersucht, welche Faktoren die Bereitschaft beeinflussen, ein vom Arbeitgeber finanziertes Mental-Health-Angebot zu nutzen. Auf Basis einer Umfrage mit 567 Teilnehmenden aus Deutschland wurde ein Klassifikationsmodell entwickelt und ein interaktives Dashboard erstellt.

## Projektziel

Vorhersage, ob eine Person ein Mental-Health-Angebot nutzen würde (binäre Klassifikation: Ja / Nein) sowie Erstellung eines Zielgruppenprofils auf Basis demografischer und psychologischer Merkmale.

## Datenbasis

- 567 Personen, Deutschland
- Zielvariable: Frage 18 (Ja: 64 %, Nein: 36 %) — unbalancierter Datensatz
- Fehlende Werte in F6, F12, F13 wurden durch den Modus ersetzt
- Datenteilung: 80 % Training / 20 % Test (Stratified Sampling)

## Hypothesen

- H1: Frauen sind eher nutzungsbereit als Männer — bestaetigt (68 % vs. 60 %)
- H2: Personen mit mittlerem Einkommen (2.000-3.000 EUR) zeigen hoehere Nutzungsbereitschaft — bestaetigt (25,4 %)
- H3: Ein ML-Modell erreicht >= 75-80 % Genauigkeit — bestaetigt (Random Forest: 83 %)

## Ergebnisse

Bestes Modell: Random Forest

| Metrik      | Wert |
|-------------|------|
| Accuracy    | 0,83 |
| Cohen Kappa | 0,63 |
| Precision   | 0,81 |
| Recall      | 0,71 |
| Specificity | 0,90 |
| F-Measure   | 0,75 |

Staerkste Einflussfaktoren: F9 Online MH (3,60x), F7 Therapiebereitschaft (3,35x), F6 Reden hilft.

Demografische Merkmale ermoeglichen einfaches Vor-Targeting. Psychologische Faktoren sind staerkere Praediktoren, aber nur per Umfrage erfassbar. Empfehlung: Kombination beider Ansaetze.

## Technologien

- **KNIME 5.8.0** — Datenvorbereitung, EDA, Modellierung (Decision Tree, Random Forest, Logistic Regression, Naive Bayes, K-Nearest Neighbors)
- **Power BI** — Interaktives Dashboard mit Bookmark-Navigation (5 Ansichten), DAX-Kennzahlen, Zielklassen-Slicer
- **Microsoft Excel** — Datensatz, Modellmetriken, Kodierungsschema

## Projektstruktur

```
/
README.md
KNIME_MentalHealth_Workflow.knwf
Dashboard.pbix
Datensatz_MH_bereinigt.xlsx
Modellergebnisse.xlsx
LogRegrFactoren.xlsx
Praesentation.pdf
Projektbeschreibung.pdf
```

## Hinweis

Der Datensatz und alle projektbezogenen Materialien wurden anonymisiert. Alle Verweise auf den Auftraggeber wurden durch den Begriff "Mental-Health-Dienstleister" ersetzt.