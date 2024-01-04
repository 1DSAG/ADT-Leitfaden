---
layout: page
title: Refactoring
parent: Funktionen von ADT
grand_parent: Arbeiten mit ADT
permalink: /working-with-adt/features/refactoring/
prev_page_link: /working-with-adt/features/abap-views/
prev_page_title: ABAP Views
next_page_link: /working-with-adt/features/vcs-and-compare/
next_page_title: Versionsverwaltung und Vergleichen
nav_order: 6
---

{: .no_toc}
# Refactoring

1. TOC
{:toc}

Wie bereits im Kapitel [Motivation für ADT](/ADT-Leitfaden/motivation-for-adt) kurz erwähnt, ermöglichen die zahlreichen Funktionen in ADT auch das Refactoring von Code. Doch was ist [Refactoring](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/b2ffd9b6ac5c41d2b0cda4858d4a6c9b.html), welche Vorteile bietet es und welche Funktionen werden hierfür von ADT bereitgestellt? Diese Fragen sollen im folgenden Abschnitt detailliert beantwortet werden.

Refactoring bezeichnet die Veränderung von Source-Code, um dessen Struktur und Lesbarkeit zu verbessern, ohne dabei die Funktionen zu ändern. Dies bedeutet, es kommen keine neuen Funktionalitäten hinzu, es fallen keine Funktionalitäten weg und es bleibt die Korrektheit der Lösung erhalten, d. h. sie liefert weiterhin das korrekte Ergebnis. Es werden keine neuen Bugs eingeführt.

Die Erhaltung der Korrektheit ist hierbei sicherlich der wichtigste und auch in der SAP-Welt am schwersten zu erreichende Aspekt. Korrektheit kann am einfachsten über automatisierte Tests bewiesen werden. Leider sind diese im SAP-Kosmos kaum verbreitet, wurden in der Vergangenheit nur wenig unterstützt und sind oft schwierig zu implementieren, da die Strukturen von historischem ABAP-Code dafür schwer geeignet sind. Somit stellt allerdings das Herstellen einer automatisierten Testbarkeit ein primäres Ziel von Refactorings dar.

Darüber hinaus gibt es noch weitere Gründe für ein Refactoring:

- Erhöhung der Verständlichkeit des Codes ("Clean Code")
- Verbesserung der Anpassbarkeit des Codes für Erweiterungen
- Abbau von technischen Schulden
- Aktualisierungen von veralteten Befehlen/Modulen

Refactoring ist ein integraler Bestandteil der Software-Entwicklung und sollte beim täglichen Entwickeln durchgeführt werden, um einen gewissen Qualitätsstandard zu halten. Es ist davon abzuraten, spezielle "Refactoring Sprints" o. ä. durchzuführen, da diese oft von Geldgebern skeptisch betrachtet oder gar nicht genehmigt werden. Die Autoren empfehlen daher die Boy-Scout-Rule zu beachten: "Always leave the code better than you found it."

In der Vergangenheit war dies mit der SE80 meist mit hohem Aufwand verbunden. Durch die mangelnde Unterstützung der IDE mussten die Refactorings zu großen Teilen händisch durchgeführt werden. Dieser hohe manuelle Aufwand und deren Fehleranfälligkeit führten zu einer geringen Akzeptanz dieses Prozesses und von Clean Code im Allgemeinen.

Mit den ADT hat sich diese Situation nun verändert. Existieren keine automatisierten Tests als doppelter Boden, so ist es immer noch möglich, sogenannte Save Refactorings durchzuführen, die wir an dieser Stelle beschreiben möchten. Ein Save Refactoring kennzeichnet sich dadurch, dass es Tool-gestützt, d. h. durch Funktionen der IDE oder auch mit zusätzlichen Plug-ins, durchgeführt wird. Dadurch entfällt das Risiko, durch manuelle Änderungen neue Fehler in den Code einzubauen. Durch die Automatisierung können Refactorings leicht durchgeführt werden und damit zum Bestandteil der täglichen Arbeit werden.

## Refactoring mit Quick Assists

Die ADT bieten über die Quick Assists (<kbd>Strg</kbd>+<kbd>1</kbd>) folgende Refactorings an:

1. Rename Identifier -- Umbenennung innerhalb eines Codeblocks oder global
2. Extract Method -- Extrahieren einer Methode aus dem Source-Code oder aus einem Ausdruck
3. Extract Constants -- Textliterale in Konstanten umwandeln
4. Extract Variables -- Variablen extrahieren und konvertieren
5. Move Member -- Attribute von Klassen verändern und bewegen
6. Exception Handling -- Automatisiertes Anlegen/Transformieren von Exception-Blöcken

Insbesondere die Rename- und die Extract-Method-Funktion unterstützen den Entwickler dabei, den Code sauber zu halten und Code-Redundanzen zu vermeiden bzw. zu reduzieren.

Da z. B. die Rename-Funktion Identifier nicht nur innerhalb der Einheit, sondern über alle Verwender hinweg behandelt, ist es nun ein Leichtes, einen unpassend gewählten Namen in einen besser zum Gesamtkontext passenden Namen zu ändern. Dabei wird nicht das Risiko eingegangen, dass Verwender vergessen und so Fehler im Code eingebaut werden.

Die Extract-Funktion analysiert den markierten Code, bietet Hilfestellung bei der Parametervergabe und ersetzt die Stelle des Codes mit dem Aufruf der neu erstellten Methode. Wenn die zu extrahierende Methode mit einem Kommentar versehen ist, wird dieser als Vorschlag für die Benennung der Methode herangezogen.

## Refactoring Plugins
### ABAP Cleaner Plug-in
Eine noch recht neue Möglichkeit besteht in der Nutzung des Plug-ins [ABAP Cleaner](/ADT-Leitfaden//plug-ins/open-source-adt-plugins/#ABAPCleaner). <br>
Dieses Plugin bietet verschiedene Möglichkeiten den Code gemäß des Clean-ABAP Styleguides zu optimieren. Der ABAP Cleaner wendet mehr als 60 Regeln des Clean-ABAP Styleguides an und automatisiert, was automatisierbar ist. Während die ADT Refactoring Funktionen vorrangig für Strukturänderung des Codes verwendet werden, wendet der ABAP Cleaner Regeln an,
die die Lesbarkeit des Codes verbessern, z.B. durch Ersetzung von Call Method durch funktionale Aufrufe, 
die Anwendung einheitlicher Formatierung bzgl. Leerzeichen und Leerzeilen und die Ersetzung von Datendefinitionen durch Inline-Deklarationen.

Als weitere und wichtige Unterscheidung zum Formatter, kann die Anwendung des ABAP Cleaner auch selektiv nur auf einzelne Methoden oder gar Selektionen beschränkt werden. Dies ist wichtig wenn vorhandener Code überarbeitet werden muss, aber nicht die ganze Klasse vom ABAP-Cleaner geändert werden soll.<br>
Die Funktionen des ABAP Cleaners finden sich im Bereich Source-Code des Kontextmenues (**ALT+SHIFT+S**). 
Es kann dabei eine vollautomatisierte Variante, eine Interaktive Variante oder die Read-Only Option verwendet werden.

Der ABAP Cleaner bringt die meisten Vorteile, wenn dieser bereits bei der Erstellung von Code verwendet wird und damit neu erstellte Artefakte automatisch den Clean-Code Regeln entsprechen.<br>
Als Nebeneffekt dieser Verwendung werden die Clean-ABAP Regeln in der Praxis sichtbar und ein Entwickler wird die von ABAP-Cleaner angewandten Regeln kurz- bis mittelfristig automatisch bei neuen Entwicklungen selbst anwenden.<br>
Wird der ABAP Cleaner konsequent im gesamten Entwicklungsteam eingesetzt, fördert es die Verständlichkeit und Lesbarkeit von Code im gesamten Team, da die selben Regeln einheitlich angewendet werden. Weitere Informationen zum ABAP Cleaner finden sie im Abschnitt [Plug-ins](/ADT-Leitfaden//plug-ins/open-source-adt-plugins/).


### ABAP-Quick-Fix Plug-in
Weiterhin empfehlen die Autoren die Verwendung des Plug-ins [ABAP Quick Fix](https://marketplace.eclipse.org/content/abap-quick-fix) von Lukasz Pegiel, welches im Kapitel [Plug-ins](/ADT-Leitfaden/plug-ins) beschrieben wird. Generell bieten die mittels Quick Fixes bereitgestellten Refactoring Tools in ADT sowohl bei der Erstellung als auch bei der Überarbeitung von bestehendem Code eine enorme Hilfe. Die Nutzung dieses hilfreichen Plug-ins verbessert auf diese Weise einerseits den aktuell bearbeiteten Code, hilft aber auch bei der Erstellung von neuem Code, die neueren Sprachkonstrukte selbst anzuwenden, falls man darin noch wenig geübt ist.
