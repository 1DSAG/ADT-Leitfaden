---
layout: page
title: Debugger
permalink: /troubleshooting/debugger/
parent: Troubleshooting-Werkzeuge in Eclipse
prev_page_link: /troubleshooting/
prev_page_title: Troubleshooting-Werkzeuge in Eclipse
next_page_link: /troubleshooting/checkpoint-logpoint/
next_page_title: Checkpoint IDs und dynamische Logpoints
nav_order: 1
has_toc: true
---

{: .no_toc}
# Der Debugger in den ABAP Development Tools

1. TOC
{:toc}

Im Eclipse steht für Analysezwecke ein [Debugger](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec30fb66e391014adc9fffe4e204223.html) zur Verfügung. Dieser wird über die Schaltfläche <span class="inline-img">![](../img/image14.png)</span> gestartet. Mit dem Starten wechselt die Perspektive in Eclipse automatisch auf die Perspektive des Debugger.

## Breakpoints und Soft-Breakpoints

Breakpoints in Eclipse sind ausschließlich externe Breakpoints. Die Breakpoints werden bei jedem Durchlauf der Software gezogen. Der Ablauf wird an der entsprechenden Stelle unterbrochen.

Breakpoints können in allen Perspektiven im Editor links neben der Zeilennummer gesetzt werden. Alternativ können Breakpoints über das Kontextmenü gesetzt werden. Gesetzte Breakpoints werden durch einen blauen Punkt neben der Codezeile gekennzeichnet.

Die ABAP Development Tools bieten neben den normalen Breakpoints die Möglichkeit von Soft Breakpoints. Diese werden über das Kontextmenü gesetzt und mit einem grünen Punkt gekennzeichnet. Im Gegensatz zu den Standard-Breakpoints wird der Programmablauf an der Stelle nur gestoppt, wenn die Software im Debugging-Kontext läuft. Ansonsten werden Soft-Breakpoints übersprungen.

## Debugging-Perspektive

![](../img/image24.jpg)  
<span class="img-caption" markdown=1>
*Abbildung: Debugging Perspektive in Eclipse*
</span>

Die Debugging-Perspektive in Eclipse bietet einen schnellen Überblick über den Programm-Code, Call-Stack, Variableninhalte und Inhalte von internen Tabellen. Die Variablen und interne Tabellen können mit Doppelklick im Programm-Code ausgewählt werden. Sie werden auf der rechten Seite angezeigt.

![](../img/image6.jpg)  
<span class="img-caption" markdown=1>
*Abbildung: Werte der Variablen in der Debugging Perspektive*
</span>

## Besonderes Verhalten im Debugger

Im Debugger der ABAP Development Tools ist es möglich, den Code direkt zu modifizieren und zu aktivieren. Im aktuellen Debugging-Kontext ist das Coding jedoch noch nicht aktiv. Der Programmlauf muss neu gestartet werden.

## Weitere Informationen

Weitere Besonderheiten über Debugging mit den ABAP Development Tools in Eclipse finden sich in den SAP-Blogs. Hervorzuheben sind dabei die folgenden beiden. Sie beschreiben Fälle und Lösungen, die beim Arbeiten mit dem Debugger auftreten können.

- [https://blogs.sap.com/2020/04/21/adt-abap-debugger-what-to-do-if-your-program-does-not-stop-at-breakpoints/](https://blogs.sap.com/2020/04/21/adt-abap-debugger-what-to-do-if-your-program-does-not-stop-at-breakpoints/)
- [https://blogs.sap.com/2015/11/02/breakpoint-validity-scope-and-activation-conflicts-in-abap-development-tools-adt/](https://blogs.sap.com/2015/11/02/breakpoint-validity-scope-and-activation-conflicts-in-abap-development-tools-adt/)
