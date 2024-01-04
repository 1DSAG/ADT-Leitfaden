---
layout: page
title: Core Data Services (CDS) 
parent: Funktionen von ADT
grand_parent: Arbeiten mit ADT
permalink: /working-with-adt/features/cds/
prev_page_link: /working-with-adt/features/data-preview/
prev_page_title: Data Preview
next_page_link: /troubleshooting/
next_page_title: Troubleshooting-Werkzeuge in Eclipse
nav_order: 11
---

{: .no_toc}
# Core Data Services (CDS)

1. TOC
{:toc}

## CDS Dateitypen

Im Bereich der Core Data Services (CDS) gibt es unterschiedliche [Dateitypen](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/4ed280596e391014adc9fffe4e204223.html), die in den ADT angelegt werden können:

- Data Definitions (DDLS) - Quelltextdateien für Datenmodelle in den folgenden Varianten:
  - DDIC Based CDS Views
  - CDS View Entities
  - Abstrakte CDS-Entitäten
  - Hierarchien
  - Erweiterungen der Views
  - CDS Table Functions
- Access-Control-Dateien (DCLS) - Zugriffs-Definitionen
- Metadata Extensions (DDLX) - Auslagerung von Annotationen aus der CDS-Definition
- Behavior Definitions (BDEF) - Verhaltens-Definitionen für RAP-Business-Objekte

![CDS Objekttypen](../img/image79.png)

Objekttypen der CDS in der Navigation
{: .img-caption}

Die Quelltext Editoren für die unterschiedlichen Dateitypen der Core Data Services verhalten sich weitgehend wie der Quelltexteditor für ABAP-Code. Unter anderem sind folgende Features enthalten:

- Code Completion (<kbd>Strg</kbd>+<kbd>Space</kbd>) - Vorschlagswerte, die im Kontext passen.
- Element Info (<kbd>F2</kbd>) - Informationen über das Element, auf dem der Cursor steht.
- Pretty Printer (<kbd>Shift</kbd>+<kbd>F1</kbd>)

Ein Unterschied sind die Farben, die im Editor verwendet werden.

## Ermittlung der Eigenschaften von Core Data Services

Bei den Core Data Services befinden sich die Eigenschaften eines Objekts nicht an einer zentralen Stelle, sondern sind aus mehreren Dateien und den Eigenschaften der Datenquellen zusammengesetzt (s. Abbildung).
Diese Dateien erklären jeweils ihre Zugehörigkeit und die Datenquellen propagieren ihre Feldeigenschaften (Annotationen). Das ist für das Erweiterungskonzept sehr praktisch. Darunter kann aber die Transparenz leiden, da die Dateien nicht im selben Entwicklungspaket liegen müssen, sondern sich in verschiedenen Paketen befinden können. 

![CDS Eigenschaften](../img/image83.png)

Unterschiedliche Dateien legen die Eigenschaften einer CDS View Entity fest
{: .img-caption}

Um ein vollständiges Bild eines CDS-Objektes unter Berücksichtigung aller Dateien und Propagationen zu bekommen, können folgende Views in ADT verwendet werden:

- [Element Info View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/c2ffbc2fee0c4ceda3bb89bd843ee419.html)
- [Dependency Analyzer](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/bedc1723e35244e188c5a44a5f4f8340.html)
- [Active Annotations View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/45ba68d3b4924a97ad2dc598e756968e.html)

## Element Info für CDS

Mit <kbd>F2</kbd> oder der separaten [Element Info View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/c2ffbc2fee0c4ceda3bb89bd843ee419.html) bekommen Sie für einen CDS View eine gute Übersicht über die Datenstruktur und Assoziationen, unabhängig davon, wo diese definiert wurden. Außerdem werden alle relevanten Erweiterungsdateien angezeigt.

![Element Info für CDS](../img/image94.png)

Übersicht über ein CDS View Entity mit Hilfe von Element Info
{: .img-caption}

## Dependency Analyzer

Der [Dependency Analyzer](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/bedc1723e35244e188c5a44a5f4f8340.html) bietet eine gute Übersicht über die Herkunft der Daten. Er wird über das Kontextmenü aufgerufen..

![Dependency Analyzer](../img/image30.png)

Aufruf des Dependency Analyzers über das Kontextmenü
{: .img-caption}

Der Dependency Analyzer hat drei Tab-Reiter, die Informationen über eine View anzeigen:

- Der **SQL Dependency Tree** zeigt die hierarchische Struktur in Tabellenform an

![SQL Dependency Tree](../img/image53.png)

SQL Dependency Tree
{: .img-caption}

- Der **SQL Dependency Graph** zeigt die gleichen Informationen grafisch an.

![SQL Dependency Graph](../img/image13.png)

SQL Dependency Graph
{: .img-caption}

- Der Tab-Reiter **Complexity Metrics** zeigt zusätzliche Informationen zur Gesamtkomplexität des CDS Views an, inklusive aller Quell-Views.
  
  {: .note}
  > Gerade bei Performance-Problemen lohnt hier ein Blick.

![Complexity Metrics](../img/image5.png)

Complexity Metrics
{: .img-caption}

## Active Annotations View

Die [Active Annotations View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/45ba68d3b4924a97ad2dc598e756968e.html) wird ebenfalls über das Kontextmenü in der Navigation aufgerufen. In ihr werden die Werte sämtlicher aktiven Annotationen der Views angezeigt:

- Auf **View-Ebene** sind nur genau die Annotationen sichtbar, die in dem View definiert wurden.
- Auf **Feld-Ebene** sind alle gültigen Annotationen sichtbar. Ihre Herkunft, wie beispielsweise Datenelement, Metadata-Extension oder Datenquelle, wird ebenfalls mit angezeigt.
- Auf **Parameter-Ebene**

Manche Eigenschaften, z. B. Feldtexte, können schon durch die Datenelemente festgelegt und diese dann in die View propagiert werden. Dies ist in folgender Abbildung beispielhaft dargestellt:

![Aktive Annotationen eines Views](../img/image39.png)

Aktive Annotationen eines Views
{: .img-caption}
