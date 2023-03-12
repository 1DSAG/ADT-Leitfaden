---
layout: page
title: Troubleshooting-Werkzeuge in Eclipse
permalink: /troubleshooting/
prev_page_link: /working-with-adt/features/cds/
prev_page_title: Arbeiten mit ADT
next_page_link: /troubleshooting/debugger/
next_page_title: Debugger
nav_order: 4
has_children: true
---

# Troubleshooting-Werkzeuge in Eclipse

Dieses Kapitel gibt einen Überblick über die Werkzeuge, die in den ABAP Development Tools zum [Troubleshooting](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ecc7d3a6e391014adc9fffe4e204223.html) zur Verfügung stehen. Dazu zählt u. a. Debuggen von Entwicklungsartefakten, Performance-Analyse und weitere Analyse- und Fehlerfindungsmethoden.

Neben der Beschreibung der Tools geben wir Hinweise für den sinnvollen Einsatz. Für detaillierte Funktionsbeschreibungen empfehlen wir die offizielle Dokumentation und geben, sofern vorhanden, hilfreiche Links an.

## Einführung

Wer den Einstieg in die ABAP Development Tools geschafft hat und die Vorzüge von ADT bei der Entwicklung zu schätzen weiß, möchte ungern weiter in SAP-GUI-basierter Umgebung entwickeln. Doch die ABAP Development Tools sind nicht nur eine Umgebung, um Code zu erstellen und zu ändern. In ADT finden sich zahlreiche Tools zur generellen Analyse von Code, dem Finden von Fehlern und der detaillierten Analyse der Performance der Funktionalitäten. Zusammenfassend können diese Aktivitäten als Troubleshooting bezeichnet werden.

Aber wie bereits beim Einstieg in die Entwicklung mit ADT, gibt es bei den Troubleshooting-Tools eine steile Lernkurve zu überwinden, deren Bezwingung mit zahlreichen Vorteilen belohnt wird. Beispielhaft sei hier erwähnt, dass es möglich ist, im Debugger den fehlerhaften Code direkt ändern zu können, statt umständlich parallel einen neuen Modus zu öffnen, die betreffende Stelle zu suchen und dann die Änderung durchzuführen. So gibt es in den Troubleshooting-Tools viele Vorteile zu entdecken, die hier in den einzelnen Abschnitten beschrieben werden.

Neben den direkten Vorteilen ist der Aspekt "Eclipse-ADT als gleiches Tool für alles" auch im Bereich des Troubleshootings nicht zu vernachlässigen.

Wenn man z. B. im SE80-Debugger sehr versiert ist, fällt einem der Umstieg schwerer, da die Vorteile des ADT-Debugger erst erarbeitet werden müssen. Für den Entwicklungsprozess in Summe ist es aber sinnvoll, ein Tool für alle Anwendungsfälle zu nutzen und das Hin- und Herwechseln zwischen den Umgebungen zu reduzieren bzw. gänzlich zu vermeiden.
