---
layout: page
title: Ausführen von Source-Code
parent: Funktionen von ADT
grand_parent: Arbeiten mit ADT
permalink: /working-with-adt/features/running-code/
prev_page_link: /working-with-adt/features/abap-doc/
prev_page_title: Dokumentation mit ABAP Doc
next_page_link: /working-with-adt/features/data-preview/
next_page_title: Data Preview
nav_order: 9
---

{: .no_toc}
# Ausführen von Source-Code

1. TOC
{:toc}

Auch in den ADT kann geöffneter Source-Code weiterhin komfortabel ausgeführt werden. Über F8 wird eine SAP-GUI-Instanz des jeweiligen Systems initialisiert und das geöffnete Entwicklungsobjekt ausgeführt. Bei Klassen entspricht dies beispielsweise der Funktion "Testen Klasse X", bei Reports wird normal der Report ausgeführt.

![In Eclipse ausgeführte Klasse](../../img/image46.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ausführung einer Klasse in SAP GUI*
</span>

![](../../img/image1.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ergebnis der Ausführung*
</span>

Soll ein beliebiges Entwicklungsobjekt ausgeführt werden, so kann mit **ALT+F8** ein Objekt über den Object Finder gesucht werden. Dabei kann ein beliebiges Projekt ausgewählt werden, d. h. ein an ADT angebundenes SAP-System. Dies muss nicht das System sein, in dem gerade entwickelt wird -- es kann auch ein Qualitätssicherungssystem sein. Wichtig ist hierbei, dass die ADT-Funktionen für dieses System freigeschaltet sind bzw. die entsprechenden Berechtigungen existieren.

![](../../img/image21.png)  
<span class="img-caption" markdown=1>
*Abbildung: Auswahl des Projekts*
</span>

Über den Menüpunkt "Run → Run History" stehen zusätzlich Informationen über bereits ausgeführte Objekte zur Verfügung, so dass deren Ausführung komfortabel wiederholt werden kann.

Klassen, die das Interface if_oo_adt_classrun implementieren, können ebenfalls direkt über F9 als [Konsolen-Applikation](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/520a4e84024b4a96b3793775bf9e6844.html) ausgeführt werden und erzeugen somit Output in der Konsole.

Reports, die eine Write-Ausgabe erzeugen, können über F9 ausgeführt werden. Die WRITE-Ausgabe wird dann ebenfalls in die Konsole umgeleitet.

![](../../img/image16.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ausgabe in die Console*
</span>