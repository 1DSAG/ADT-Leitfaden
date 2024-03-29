---
layout: page
title: Grundlagen
parent: Arbeiten mit ADT
permalink: /working-with-adt/basics/
prev_page_link: /working-with-adt/
prev_page_title: Arbeiten mit ADT
next_page_link: /working-with-adt/features/
next_page_title: Funktionen von ADT
nav_order: 1
---

{: .no_toc}
# Einführung: Grundlagen der Arbeit mit ADT

1. TOC
{:toc}

## Der Einstieg in das Arbeiten mit den ABAP Development Tools

Dieser Abschnitt richtet sich an Entwickler, die bisher noch nicht mit den ADT gearbeitet haben und die ersten Schritte gehen möchten. Im User-Guide befindet sich im Abschnitt "[Getting Started](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/12bdb73f7f6a4bfe95540b31af29ac10.html)" ein Abschnitt zum Einstieg in ADT, in dem alle Funktionen ausführlich erläutert werden. In diesem Leitfaden möchten wir mittels einer Schritt-für-Schritt-Beschreibung zur Erstellung einer ABAP-Klasse den Einstieg so leicht wie möglich gestalten und die Vorteile der Nutzung der ABAP Development Tools aufzeigen.

Folgende Arbeitsschritte werden hierbei Schritt für Schritt beschrieben:

- Einrichtung des Projekts
- Einrichtung der Favoritenpakete
- Erstellung einer Klasse mit einer Methode
- Arbeiten am Code und Refactoring

Zum Zweck der generellen Nachvollziehbarkeit werden die hier gezeigten Beispiele in einer Instanz des BTP Trial Accounts dargestellt, diese können aber in gängigen On-Premise-Systemen problemlos angewendet werden.

Entwickler, die bereits den Einstieg geschafft haben und sich einen Überblick über die einzelnen Funktionen verschaffen möchten oder detaillierte Arbeitshinweise suchen, können diesen Abschnitt überspringen.

## Der Umstieg von der formularbasierten zur textorientierten Code-Erstellung

Im Gegensatz zu den SAP-GUI-basierten Transaktionen wie SE80 oder SE24 findet sich in ADT kein formularbasierter Editor. Die Erstellung von Klassen (und auch Funktionsbausteinen etc.) erfolgt in ADT rein textbasiert. Für Entwicklungswerkzeuge, die abhängig von ADT und Backend-Version noch nicht in Eclipse zur Verfügung stehen, kann aus Eclipse auf diese Transaktionen integriert zugegriffen werden.

Gewöhnungsbedürftig ist auch der Tausch der Tasten <kbd>F2</kbd> und <kbd>F3</kbd>. Während im SAP-GUI die <kbd>F3</kbd>-Taste als Zurück-Taste verwendet wird, dient die <kbd>F3</kbd>-Taste in den ADT zur Vorwärtsnavigation, die <kbd>F2</kbd>-Taste zur kontextsensitiven Hilfe.

Dies stellt für den Einstieg mitunter auch die größte Hürde dar, da lang eingeübte Praxis und gewohnte Arbeitsprozesse sich mit dem Umstieg auf ADT ändern. Und wenn es schnell gehen soll, greift man gerne auf gewohnte und bestens vertraute Arbeitsweisen zurück.

Der Einstieg und die Umstellung erfordert also erstmal Zeit und Bedarf der Einübung. Doch der anfängliche Mehraufwand zahlt sich bereits nach kurzer Zeit wieder aus. Denn nach etwas Eingewöhnung und Übung stellen die beschriebenen Punkte kein Problem mehr dar. Die zahlreichen Funktionen, die die ABAP Development Tools bieten, erleichtern das Schreiben und Überarbeiten von ABAP Code und erhöhen damit die Effizienz beim Entwickeln. Daher sollte der Umstieg von SE80 & Co. auf ADT in Eclipse als ein persönliches Investment in eine effiziente und zukunftsfähige Arbeitsweise betrachtet werden.

## Kontext des hier gezeigten Übungsbeispiels

Das hier gezeigte Beispiel ist bewusst einfach gewählt, da vorrangig die grundlegenden Funktionen und Arbeitsweisen der ADT dargestellt werden sollen.

Wir möchten eine kleine Klasse anlegen, die folgende Funktionen anbietet:

1. Ermittlung von Flügen aus der Tabelle ***/DMO/FLIGHT*** gemäß Eingabe.
2. Berechnung der verfügbaren Plätze des Fluges.
3. Berechnung des Flugpreises auf Basis einer zusätzlichen prozentualen Gebühr.

Die Klasse dient als interne Service-Klasse und bietet keine UI bzw. Ausgabe von Daten an.

Dabei werden die grundlegenden Arbeitsweisen und meistgenutzten Funktionen gezeigt, die zum Effizienzgewinn während der Code-Erstellung und Änderung führen.

## Verbinden des Entwicklungssystems - Neues Projekt

Ein Entwicklungssystem wird in den ADT in Form eines Projekts dargestellt. Um ein Entwicklungssystem mit den ADT zu verknüpfen, müssen wir daher ein neues Projekt anlegen.

In einer neuen Installation von ADT wird ein neues Projekt über

File → New → ABAP Projekt

angelegt.

![Erstellung eines ABAP-Projekts in Eclipse](./img/image75.png)

Erstellung eines ABAP-Projekts in Eclipse
{: .img-caption}

Bei Anlage eines ABAP-Projekts für On-Premise-Systeme wird die Liste der im SAP-Logon verknüpften Systeme angezeigt. Die Login-Daten sind zu hinterlegen, sofern kein SSO verwendet wird und im letzten Schritt kann dem Projekt noch ein sprechender Name gegeben werden. Als Default ist die Sprache Englisch gewählt, diese muss ggf. angepasst werden.

Das neu erstellte Projekt und damit das verbundene Entwicklungssystem wird im sogenannten [Project Explorer](/ADT-Leitfaden/working-with-adt/features/general-features#project-explorer) dargestellt.

![Der Project Explorer](./img/image97.png)

Der Project Explorer
{: .img-caption}

Der Project Explorer ist der zentrale Einstiegspunkt und Objektkatalog, nachdem das entsprechende Entwicklungssystem geöffnet wurde. Die Objekte werden basierend auf den Paketen in hierarchischer Form dargestellt, wie man es bereits aus der SE80 kennt. In der täglichen Arbeit werden die zu bearbeitenden Objekte hieraus geöffnet.

Der Hauptarbeitsbereich ist der Knoten [Favorite Packages](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec55bf96e391014adc9fffe4e204223.html). Um das Paket zu den Favorite Packages hinzuzufügen, in das die zu erstellende Klasse eingefügt werden soll, führen Sie den Befehl "Add Package" mittels des Kontextmenüs aus.

![Hinzufügen von Packages zu den Favoriten](./img/image35.png)

Hinzufügen von Packages zu den Favoriten
{: .img-caption}

## Das Erstellen einer Klasse im Textmodus

Zur [Erstellung einer neuen ABAP-Klasse](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec66fda6e391014adc9fffe4e204223.html) navigieren Sie im Project Explorer in das gewünschte Paket, erreichen das Kontextmenü mittels der rechten Maustaste und finden dort den Befehl

New → ABAP Class

![Erstellen einer neuen ABAP-Klasse im Projekt Explorer](./img/image74.png)

Erstellen einer neuen ABAP-Klasse im Projekt Explorer
{: .img-caption}

Es öffnet sich ein Fenster, in dem die Daten der Klasse angegeben werden können/müssen.

![Eigenschaftsdialog: Erstellung ABAP-Klasse](./img/image81.png)

Eigenschaftsdialog: Erstellung ABAP-Klasse
{: .img-caption}

Hier können bei Bedarf bereits die Super-Klasse und zu referenzierende Interfaces angegeben werden. Dies kann aber auch später textbasiert direkt im Quellcode erfolgen. Es öffnet sich nach Klick auf "Next" das Fenster zur Auswahl bzw. Anlage des Transportauftrages.

![Transportauftragsdialog](./img/image76.png)

Transportauftragsdialog
{: .img-caption}

Nach Klick auf "Finish" wird die Klasse angelegt, und diese findet sich sowohl im Project Explorer im Objektbaum als auch im Quellcode-Editor auf der rechten Seite der ADT.

![Anzeige der neuen Klasse in den ADT](./img/image78.png)

Anzeige der neuen Klasse in den ADT
{: .img-caption}

Alle weiteren Operationen an der Klasse werden nun im Quellcode durchgeführt, d. h. alle Typen, Datendefinitionen und Methoden werden textbasiert als Quellcode in der Klasse geschrieben. Dies erscheint anfangs kompliziert und ungewohnt, die ADT bieten aber einige Funktionen an, die die Ausarbeitung der Klasse sehr effizient gestalten.

## Definition einer Methode in der Klasse

Nun möchten wir die erste Methode der Klasse erstellen, die Daten aus der Tabelle /DMO/FLIGHTS liest und die Anzahl der freien Plätze zu einem definierten Flug ausgibt.

Wir beschränken uns hier nur auf die Kernfunktionalitäten und werden keine zusätzlichen Funktionen für Output etc. bereitstellen.

Eine ABAP-Klasse ist in ADT in die Hauptbereiche "Definition" und "Implementierung" aufgeteilt. Dementsprechend werden wir für unsere erste Methode zuerst im Bereich "Definition" die Methode mit ihren Parametern definieren und anschließend die Implementierung mit dem Quellcode durchführen. Die sogenannte "Quick Fix"-Funktion wird uns dabei Tipparbeit ersparen.

Um eine Methode zu erstellen, navigiert man im Reiter/Tab "Global Class" in den Bereich

CLASS \<c*lassname\>* DEFINITION

und platziert den Cursor in den Sichtbarkeitsbereich der Klasse, in der die Methode zur Verfügung steht. In unserem Fall soll die Methode für andere Verwender sichtbar sein und daher im Bereich PUBLIC definiert werden. Die Definition der Methode wird mit dem Schlüsselwort METHODS eingeleitet.

![Bearbeiten der Klasse](./img/image98.png)

Bearbeiten der Klasse
{: .img-caption}

Bereits zu diesem Zeitpunkt zeigt sich einer der Hauptvorteile von ADT gegenüber der SE80. Sobald Code eingeben wurde, läuft automatisch der Syntax-Check und zeigt an, ob der Code syntaktisch korrekt ist.

Da der Abschlusspunkt nicht vorhanden ist, zeigt ADT sowohl im linken Balken einen Hinweis (als Hover-Message) als auch die View-Problems den Syntaxfehler an. Ein extra auszuführender Syntax-Check ist nicht erforderlich. Nur eine Kleinigkeit, die in der täglichen Arbeit eine signifikante Effizienzsteigerung bedeutet. Spätestens wenn man aus diversen Gründen eine Änderung in den GUI-basierten Tools vornimmt, wird man diese Funktion vermissen.

## Automatische Ergänzung und Formatierung des Codes

Wir schließen die Methodendefinition mit Erstellung der Parameter und des Abschlusspunkts ab. Durch die Nutzung der Code Completion wird uns die Arbeit dabei sehr erleichtert. Dazu geben wir jeweils nur die ersten zwei bis drei Buchstaben des gewünschten Schlüsselwortes an. Die Tastenkombination <kbd>Strg</kbd>+<kbd>Space</kbd> zeigt uns die passenden Schlüsselworte an. Diese können daraufhin mittels <kbd>TAB</kbd>+<kbd>Pfeiltasten</kbd> aus der Vorschlagsliste ausgewählt werden. Zur weiteren Automatisierung der Code-Erstellung bietet sich die Nutzung von Templates an (s. Abschnitt [Code Template](/ADT-Leitfaden/working-with-adt/features/abap-views#templates)).

![Beispiel Code Completion für den Import-Parameter](./img/image80.png)

Beispiel Code Completion für den Import-Parameter
{: .img-caption}

Nachdem die Import-Parameter und der Return-Parameter definiert sind, wird der Cursor im Textbereich des Codes positioniert und die Formatierung des Codes mittels des Kontextmenüs\
Rechte Maustaste → Source Code → Format bzw. der Tastenkombination <kbd>Shift</kbd>+<kbd>F1</kbd> ausgeführt. Dies entspricht dem Pretty Printer in den GUI-Transaktionen. Anschließend wird der Code mittels <kbd>Strg</kbd>+<kbd>S</kbd> gespeichert.

Sollte ein Syntaxfehler vorliegen, zeigt das Problem-View und die farbliche Markierung im Code den Fehler an. Ist der Code syntaktisch korrekt, kann das Artefakt anschließend mittels <kbd>Strg</kbd>+<kbd>F3</kbd> aktiviert werden.

Nach Einübung der neuen, vor allem Tastatur-basierten, Arbeitsweise entsteht nach kurzer Zeit ein Automatismus, der nach dem Schreiben einiger Codezeilen und anschließender Abfolge der o.g. Tastenkombinationen einen formatierten, geprüften und gesicherten Code als Ergebnis hat. Zeitraubende Überraschungen in Form von Syntaxfehlern beim Aktivieren, wie es in den GUI-Tools vorkommen kann, bleiben dadurch erspart.

## Implementierung der Methode mittels Quick-Fix

Die Methode ist nun definiert, aufgrund der fehlenden Implementierung zeigt ADT im Problems-View folgenden Fehler an:\
`"Implementation missing for method \"CALC_FREE_SEATS_FOR_FLIGHT\"`.

Dieses "Problem" lässt sich sehr effizient mit Hilfe der Quick Fixes beheben.

Zur Methodenimplementierung nutzen Sie die [Quick-Fix](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec5668b6e391014adc9fffe4e204223.html)-Funktion, die sich über das Kontextmenü oder die Tastenkombination <kbd>Strg</kbd>+<kbd>1</kbd> aufrufen lässt.

![Nutzung des Quick Fix zur Methodenimplementierung](./img/image87.png)

Nutzung des Quick Fix zur Methodenimplementierung
{: .img-caption}

Sie wählen "Add Implementation for ..." aus und bestätigen mit <kbd>Enter</kbd>. Zum Ausführen der Quick-Fix-Befehle sollte der Code gespeichert und fehlerfrei sein, da manche Quick Fixes (automatische Code-Korrekturen/Refactorings) dies als Voraussetzungen haben.

Die Methodenimplementierung bedeutet hier, dass automatisiert die Sektion

```abap
METHOD

ENDMETHOD
```

im Bereich der "Class Implementation\" durch ADT erstellt wird und somit eine leere Methodenimplementierung vorhanden ist. Die Ausprägung der Methodenlogik innerhalb dieses Bereiches ist dann Ihre Aufgabe als Entwickler.

Zwischen Definition und Implementierung kann einfach durch Drücken der <kbd>F3</kbd>-Taste hin und her gesprungen werden.

Mit Platzierung des Cursors auf den Methodenname und <kbd>F2</kbd> kann man sich die Parameter der Methoden anzeigen lassen. Dies erleichtert das Schreiben des Codes und erspart umständliches Navigieren in den Definitionsbereich. Alternativ steht hierfür die View [ABAP Element Info](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/a8c361f8cc6040f79f52375fb6a9d333.html?q=abap%20element%20inf#loiof7c8d6d10279483ebb625e2e3e31c3d0) zur Verfügung.

In unserem Übungsbeispiel verwenden wir die Import-Parameter, um mittels eines SELECT-Befehls den gewünschten Datensatz zu lesen. Anschließend werden die Anzahl der freien Sitze kalkuliert und als Returning-Parameter an den Verwender zurückgegeben.

Auch hier hilft die Verwendung der Code Completion, die mit der Tastenkombination <kbd>Strg</kbd>+<kbd>Space</kbd> aufgerufen wird, um den Code effizient und frei von Tippfehlern zu erstellen.

Um den Returning-Parameter "r_f_free_seats" nicht ausschreiben zu müssen und Typinformationen zu bekommen, schreiben wir die Struktur und den Komponentenseparator "-" und bekommen mittels der Tastenkombination <kbd>Strg</kbd>+<kbd>Space</kbd> die Komponenten angezeigt, die dann ausgewählt und in den Code eingefügt werden können.

![Auswahl der Komponente mittels Code Completion](./img/image90.png)

Auswahl der Komponente mittels Code Completion
{: .img-caption}

Diese Möglichkeiten der Vorwärtsnavigation und Inline-Anzeige weitergehender Elementinformationen sind in dieser Form in SE80 nicht vorhanden und ein weiterer Baustein zur Steigerung der Entwicklereffizienz in ADT.

Wir haben damit die Klasse mit der ersten Methode in ADT definiert und implementiert.

## Umbenennung von Parametern - Refactoring

Die laufende Optimierung von bestehenden Code ist eine wichtige Aufgabe jedes Entwicklers. Dies wird von ADT bestens unterstützt. Die verschiedenen Möglichkeiten des Refactoring werden im Abschnitt: [Refactoring von Code mit ADT](/ADT-Leitfaden/working-with-adt/features/refactoring) ausführlich erläutert. Weitere Informationen finden sich auch im [User-Guide](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec859406e391014adc9fffe4e204223.html).

Wir möchten die generelle Vorgehensweise des Refactoring anhand einer Umbenennung im Detail darstellen.

Gewohnheitsgemäß haben wir die ungarische Notation verwendet und möchten nun die Parameter der Methode umbenennen, um die Präfixe zu entfernen (vgl. [ABAP Clean Code](https://github.com/SAP/styleguides/blob/37c1413c6e3b2665f9bab7b6edc53b2417934224/clean-abap/CleanABAP.md)).

Während eine solche Aktion sich im SAP-GUI-Umfeld u. U. sehr aufwendig und fehleranfällig gestalten kann, bietet hier die Rename-Funktion in ADT eine sehr komfortable Möglichkeit, die Umbenennungen von Variablen, Parametern und Methodennamen über alle Verwendungen durchzuführen. Das bedeutet, dass in allen Entwicklungsobjekten, welche die Methode aufrufen, die Parameter automatisiert umbenannt werden. Eine aufwendige Suche nach Verwendern über den Verwendungsnachweis entfällt. Dies funktioniert aber natürlich nur, wenn keine dynamischen Methodenaufrufe verwendet werden. Solche Fälle kann ADT nicht erkennen.

Somit sind Code Cleaning und Refactoring mit ADT sehr effizient durchzuführen, und das Risiko von dadurch entstehenden Fehlern ist gegenüber der manuellen Methode deutlich reduziert.

Zur Umbenennung der Parameter wird die Rename-Funktion aus dem Kontextmenü über rechte Maustaste → Source-Code → Rename oder die Tastenkombination <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd> oder per Quickfix-Auswahl über
<kbd>Strg</kbd>+<kbd>1</kbd> ausgeführt.

![Umbenennung von Methodenparametern](./img/image100.png)

Umbenennung von Methodenparametern
{: .img-caption}

Zuerst muss der Code gespeichert werden. Falls dies nicht erfolgt ist, erscheint eine Abfrage zum Speichern, die bestätigt werden muss.

![Abfragedialog zum Speichern des Code](./img/image84.png)

Abfragedialog zum Speichern des Code
{: .img-caption}

Es erscheint eine Dialog-Box zur Eingabe des Parameternamens.

![Eingabe neuer Parametername](./img/image85.png)

Eingabe neuer Parametername
{: .img-caption}

Sofern das Objekt bereits einem Transport zugeordnet ist, kann mit "Finish" die Umbenennung direkt durchgeführt werden.  
Mit "Next" können weitere optionale Einstellungen, wie der zu verwendende Transport und die Aktivierungsoption, vorgenommen werden.

![Auswahl des Transports und Optionen](./img/image86.png)

Auswahl des Transports und Optionen
{: .img-caption}

Vor der finalen Durchführung kann eine Vorschau auf die Änderung angezeigt werden:

![Vorschau der Umbenennung](./img/image62.png)

Vorschau der Umbenennung
{: .img-caption}

Nach Klick auf "Finish" sind sowohl die Parameter in der Definition, die Verwendung in der Methode als auch die Parameternamen an den Stellen, an denen die Methode verwendet wird, passend abgeändert. Die hier gezeigte Umbenennung funktioniert in gleicher Weise für Variablen, Methoden und sogar Klassennamen.

Somit zeigt sich hier ein sehr starker Vorteil gegenüber den SAP-GUI-basierten Entwicklungswerkzeugen, in denen eine objektübergreifende Umbenennung nicht automatisiert möglich ist.

Damit sind die ersten Schritte gemacht, die grundlegenden Funktionen und Arbeitsweisen in ADT sind bekannt und können nun angewendet werden. Die erste Hürde ist genommen und die Basis für die Anwendung der zahlreichen Funktionen der ABAP Development Tools, die in den folgenden Abschnitten detailliert erläutert werden, geschaffen.
