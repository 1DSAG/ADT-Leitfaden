---
layout: page
title: Kapitel 1 - Einführung Eclipse und ADT
permalink: /kapitel1/
nav_order: 1
---

Autoren: Florian Henninger, (Jörg Brandeis), Paul Peitz, (Jens Zähringer), Sören Schlegel

**Kapitelstatus:** "In Arbeit" (initial von Sebastian gesetzt, gerne ändern)

*Fertig zum Review aus Sicht Florian (Info zur offenen Schnittstelle für IDEs noch ergänzt)*

*Erstes Review von Sebastian am 19.09.22 (kleinere sprachliche Anpassungen, 1 Kommentar erfasst)*

Review von Sebastian am 11.01.23 auf alle Kapitel

*(zum Beispiel "Nicht gestartet" \| "In Arbeit" \| "Fertig zum Review" \| "Review durchgeführt von x am y" \| "Review eingearbeitet am y" \| "Finaler Zustand" \|*

*\<was aus eurer Sicht sinnvoll erscheint, evtl. Unterkapitel nennen, falls ihr die Arbeit verteilt\> )*

## Warum eigentlich Eclipse?

Warum ist Eclipse die richtige Plattform für die ADT-Tools und nicht VSCode, NetBeans oder irgendeine andere Entwicklungsumgebung?

Eine vollumfassende Antwort wird hier nicht möglich sein. Fakt ist jedoch, dass SAP sich strategisch für den Einsatz von Eclipse als Grundlage für die zukünftige ABAP-Entwicklungsumgebung (als Nachfolger der klassischen ABAP Workbench) entschieden hat und plant diesen Ansatz auch weiter zu verfolgen.

Das ist so auch aus den Roadmaps der ABAP-Plattform ersichtlich und kann dort nachgelesen werden.

Es muss aber erwähnt werdenn, dass mit der Anbindung an Eclipse eine offene Schnittstelle (zwischen der Entwicklungsumgebung und dem SAP-Backend) entstanden ist, die von anderen Umgebungen genutzt werden kann. Für VSCode gibt es beispielsweise bereits Erweiterungen, die auf diesen Schnittstellen basieren. Über die Vollständigkeit und Nutzbarkeit wird jedoch im Leitfaden nicht eingegangen. Wenn Sie hierzu mehr Informationen benötigen, über die üblichen Suchmaschinen schnell wird man schnell passende Ergebnisse finden.

## Ein kurzer Blick auf die Entstehungsgeschichte

Ursprung von Eclipse ist bei IBM und wurde im Jahr 2004 mit der Eclipse Foundation eigenständig. Eclipse wird in der Programmiersprache Java implementiert und steht unter einer Open Source-Lizenz offen zur Verfügung. Zunächst wurden die neuen Eclipse-Versionen nach Objekten aus dem Weltall benannt (u.a. Jupiter-Monde).

Der Einfachheit halber hat man sich aber auch bei der Eclipse-Foundation 2018 für eine nachvollziehbare Namenskonvention für die Eclipse-Versionen entschieden: \< (Jahr)-(Monat) \>. Zeitgleich wurde auf deutlich schnellere (3-monatige) Releasezyklen umgestellt.

## Das Prinzip von Erweiterungen

Die Basisinstallation von Eclipse wird bereits mit einem Grundstock an Funktionen und Erweiterungen ausgeliefert. Der Umfang dieser Funktionen und Erweiterungen hängt maßgeblich davon ab, welche Version Sie auf der Webseite zum Download auswählen. Technisch betrachtet ist der Kern der Anwendung immer identisch. Alle zusätzlichen Funktionalitäten werden mittels Erweiterungen geliefert - das gilt auch für die ABAP Development Tools.

Das heißt also, dass Sie jederzeit alle Erweiterungen im Nachhinein ihrer Installation hinzufügen bzw. wieder entfernen können.

Typischerweise beziehen Sie die Erweiterungen über den Eclipse-Marketplace, den Sie auch direkt aus dem Tool heraus erreichen.

## Unterschied zwischen Perspektive und Sicht

Ein wichtiges Merkmal von Eclipse besteht in der Anpassbarkeit. Hierauf wird in den folgenden Kapiteln noch im Detail eingegangen. Essentiell ist hierbei, die grundlegenden Begrifflichkeiten zu verstehen.

Eine Sicht (oft auch View genannt) ist ein eigenständiger Programmteil, der entweder bereits in der Basis-Installation enthalten ist oder per Erweiterung Eclipse nachträglich hinzugefügt wurde. Diese Sicht kann vom Benutzer an verschiedenen Positionen innerhalb der Entwicklungsumgebung angeordnet werden.

Eine Perspektive beinhaltet ein spezifisches Layout von Eclipse, also alle angezeigten Sichten und deren Position.. Perspektiven geben Ihnen damit den Fokus für eine Tätigkeit mit allen Sichten, die Sie hierfür benötigen.

Details hierzu finden Sie t im Leitfaden [[Kapitel 4 - Arbeiten mit ADT]{.underline}](https://docs.google.com/document/u/0/d/16emZEtUlOHQpYIIreZMAnsDXAdIas9H36MMugzDdQPw/edit).

Die Kenntnis der Begrifflichkeiten ist essentiell, um effizient mit Eclipse arbeiten zu können. Dokumentationen aller Art nutzen diese Terminologie, um Funktionen zu erklären. Das gilt auch für diesen ADT-Leitfaden.

## Die Macht der Tastenkürzel

Ein prägnantes Merkmal von Eclipse liegt in der Verwendung von Tastenkürzeln. Sie werden am Anfang viel Zeit damit verbringen, die Funktionalitäten, die Sie von der klassischen ABAP-Worbench (Transaktion: SE80) gewohnt sind, wiederzufinden und sich einzuprägen. Im Gegensatz zur SE80 ist Eclipse jedoch dahingehend optimiert, mit Tastenkürzeln bedient zu werden. Behalten Sie das im Hinterkopf und nutzen Sie die Möglichkeiten, sich die Tastenkürzel zu verinnerlichen. Weitere Informationen hierzu finden Sie auch in [[Kapitel 4.]{.underline}](https://docs.google.com/document/u/0/d/16emZEtUlOHQpYIIreZMAnsDXAdIas9H36MMugzDdQPw/edit)

## Ab wann ist welche Funktion mit Eclipse verfügbar?

Da der Funktionsumfang der ABAP Development Tools fortlaufend durch SAP erweitert wird, ist es wichtig zu prüfen, welche Funktionen in der von Ihnen verwendeten ADT-Version zur Verfügung stehen. Dabei ist zu beachten, dass einige der bereitgestellten Funktionen auch vom Release des verwendeten SAP-Systems abhängen. Um den aktuellen Stand über die letzten Updates der ADT zu erfahren, sind die offiziellen Quellen der SAP hier das Mittel der Wahl, da diese entsprechend laufend gepflegt werden.

Für Cloud:

[[https://help.sap.com/docs/BTP/5371047f1273405bb46725a417f95433/ab03dcd9072f4a2d85c945d05929d3fb.html]{.underline}](https://help.sap.com/docs/BTP/5371047f1273405bb46725a417f95433/ab03dcd9072f4a2d85c945d05929d3fb.html)

[OPTIONAL -- ABER WOHL NICHT NOTWENDIG]{.mark}

Für On-Premise:

[[https://help.sap.com/doc/2e9cf4a457d84c7a81f33d8c3fdd9694/Cloud/en-US/inst_guide_abap_development_tools.pdf]{.underline}](https://help.sap.com/doc/2e9cf4a457d84c7a81f33d8c3fdd9694/Cloud/en-US/inst_guide_abap_development_tools.pdf)
