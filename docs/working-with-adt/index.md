---
layout: page
title: Kapitel 3 - Arbeiten mit ADT
permalink: /working-with-adt/
nav_order: 3
---

{: .no_toc}

# Kapitel 3 - Arbeiten mit ADT

1. TOC
{:toc}

Die ABAP Development Tools bieten sehr viele Funktionen, die auch entsprechend zahlreiche Möglichkeiten der Nutzung bieten. Dies kann für Entwickler, die noch nicht mit den ADT vertraut sind, verwirrend sein.

Der erste Schritt ist immer der schwerste. Zu Beginn dieses Kapitels möchten wir dem Einsteiger den Start in die ADT-Welt am Beispiel der Erstellung einer Klasse erleichtern. Die hier gezeigte Vorgehensweise lässt sich dann auf andere Entwicklungsobjekte übertragen, und der Einstieg ist geschafft.

Die weiteren Funktionalitäten werden im darauf folgenden Abschnitt übersichtsartig beschrieben, und es werden Hinweise gegeben und Best Practices erläutert, wie die zahlreichen Werkzeuge und auch Hilfen in der täglichen Arbeit eingesetzt werden und einen Mehrwert bieten können.

Neben den ADT-Einsteigern werden aber auch in ADT erfahrene Entwickler viele nützliche Hinweise und vielleicht auch Neues für die tägliche Arbeit mit den ABAP Development Tools finden.

Mit dem [SAP ABAP Development User Guide](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4b190c90ceba4d02a99e0a2286b89358.html), im Folgenden User-Guide genannt, stellt SAP die offizielle Dokumentation zu den ADT zur Verfügung. Für weitergehende Informationen zu einzelnen Funktionen sind die Links zu dem entsprechenden Abschnitt im User-Guide vermerkt.

# Einführung: Grundlagen der Arbeit mit ADT

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

Gewöhnungsbedürftig ist auch der Tausch der Tasten **F2** und **F3**. Während im SAP-GUI die F3-Taste als Zurück-Taste verwendet wird, dient die F3-Taste in den ADT zur Vorwärtsnavigation, die F2-Taste zur kontextsensitiven Hilfe.

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

## Verbinden des Entwicklungssystems -- Neues Projekt

Ein Entwicklungssystem wird in den ADT in Form eines Projekts dargestellt. Um ein Entwicklungssystem mit den ADT zu verknüpfen, müssen wir daher ein neues Projekt anlegen.

In einer neuen Installation von ADT wird ein neues Projekt über

File → New → ABAP Projekt

angelegt.

![](./img/image75.png)  
<span class="img-caption" markdown=1>
*Abbildung: Erstellung eines ABAP-Projekts in Eclipse*
</span>

Bei Anlage eines ABAP-Projekts für On-Premise-Systeme wird die Liste der im SAP-Logon verknüpften Systeme angezeigt. Die Login-Daten sind zu hinterlegen, sofern kein SSO verwendet wird und im letzten Schritt kann dem Projekt noch ein sprechender Name gegeben werden. Als Default ist die Sprache Englisch gewählt, diese muss ggf. angepasst werden.

Das neu erstellte Projekt und damit das verbundene Entwicklungssystem wird im sogenannten [[Project Explore](#project-explorer)r] dargestellt.

![](./img/image97.png)  
<span class="img-caption" markdown=1>
*Abbildung: Der Project Explorer*
</span>

Der Project Explorer ist der zentrale Einstiegspunkt und Objektkatalog, nachdem das entsprechende Entwicklungssystem geöffnet wurde. Die Objekte werden basierend auf den Paketen in hierarchischer Form dargestellt, wie man es bereits aus der SE80 kennt. In der täglichen Arbeit werden die zu bearbeitenden Objekte hieraus geöffnet.

Der Hauptarbeitsbereich ist der Knoten [Favorite Packages](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec55bf96e391014adc9fffe4e204223.html). Um das Paket zu den Favorite Packages hinzuzufügen, in das die zu erstellende Klasse eingefügt werden soll, führen Sie den Befehl "Add Package" mittels des Kontextmenüs aus.

![](./img/image35.png)  
<span class="img-caption" markdown=1>
*Abbildung: Hinzufügen von Packages zu den Favoriten*
</span>

## Das Erstellen einer Klasse im Textmodus

Zur [Erstellung einer neuen ABAP-Klasse](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec66fda6e391014adc9fffe4e204223.html) navigieren Sie im Project Explorer in das gewünschte Paket, erreichen das Kontextmenü mittels der rechten Maustaste und finden dort den Befehl

New → ABAP Class

![](./img/image74.png)  
<span class="img-caption" markdown=1>
*Abbildung: Erstellen einer neuen ABAP-Klasse im Projekt Explorer*
</span>

Es öffnet sich ein Fenster, in dem die Daten der Klasse angegeben werden können/müssen.

![](./img/image81.png)  
<span class="img-caption" markdown=1>
*Abbildung: Eigenschaftsdialog: Erstellung ABAP-Klasse*
</span>

Hier können bei Bedarf bereits die Super-Klasse und zu referenzierende Interfaces angegeben werden. Dies kann aber auch später textbasiert direkt im Quellcode erfolgen. Es öffnet sich nach Klick auf "Next" das Fenster zur Auswahl bzw. Anlage des Transportauftrages.

![](./img/image76.png)  
<span class="img-caption" markdown=1>
*Abbildung: Transportauftragsdialog*
</span>

Nach Klick auf "Finish" wird die Klasse angelegt, und diese findet sich sowohl im Project Explorer im Objektbaum als auch im Quellcode-Editor auf der rechten Seite der ADT.

![](./img/image78.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der neuen Klasse in den ADT*
</span>

Alle weiteren Operationen an der Klasse werden nun im Quellcode durchgeführt, d. h. alle Typen, Datendefinitionen und Methoden werden textbasiert als Quellcode in der Klasse geschrieben. Dies erscheint anfangs kompliziert und ungewohnt, die ADT bieten aber einige Funktionen an, die die Ausarbeitung der Klasse sehr effizient gestalten.

## Definition einer Methode in der Klasse

Nun möchten wir die erste Methode der Klasse erstellen, die Daten aus der Tabelle /DMO/FLIGHTS liest und die Anzahl der freien Plätze zu einem definierten Flug ausgibt.

Wir beschränken uns hier nur auf die Kernfunktionalitäten und werden keine zusätzlichen Funktionen für Output etc. bereitstellen.

Eine ABAP-Klasse ist in ADT in die Hauptbereiche "Definition" und "Implementierung" aufgeteilt. Dementsprechend werden wir für unsere erste Methode zuerst im Bereich "Definition" die Methode mit ihren Parametern definieren und anschließend die Implementierung mit dem Quellcode durchführen. Die sogenannte "Quick Fix"-Funktion wird uns dabei Tipparbeit ersparen.

Um eine Methode zu erstellen, navigiert man im Reiter/Tab "Global Class" in den Bereich

CLASS \<c*lassname\>* DEFINITION

und platziert den Cursor in den Sichtbarkeitsbereich der Klasse, in der die Methode zur Verfügung steht. In unserem Fall soll die Methode für andere Verwender sichtbar sein und daher im Bereich PUBLIC definiert werden. Die Definition der Methode wird mit dem Schlüsselwort METHODS eingeleitet.

![](./img/image98.png)  
<span class="img-caption" markdown=1>
*Abbildung: Bearbeiten der Klasse*
</span>

Bereits zu diesem Zeitpunkt zeigt sich einer der Hauptvorteile von ADT gegenüber der SE80. Sobald Code eingeben wurde, läuft automatisch der Syntax-Check und zeigt an, ob der Code syntaktisch korrekt ist.

Da der Abschlusspunkt nicht vorhanden ist, zeigt ADT sowohl im linken Balken einen Hinweis (als Hover-Message) als auch die View-Problems den Syntaxfehler an. Ein extra auszuführender Syntax-Check ist nicht erforderlich. Nur eine Kleinigkeit, die in der täglichen Arbeit eine signifikante Effizienzsteigerung bedeutet. Spätestens wenn man aus diversen Gründen eine Änderung in den GUI-basierten Tools vornimmt, wird man diese Funktion vermissen.

## Automatische Ergänzung und Formatierung des Codes

Wir schließen die Methodendefinition mit Erstellung der Parameter und des Abschlusspunkts ab. Durch die Nutzung der Code Completion wird uns die Arbeit dabei sehr erleichtert. Dazu geben wir jeweils nur die ersten zwei bis drei Buchstaben des gewünschten Schlüsselwortes an. Die Tastenkombination **STRG+LEERTASTE** zeigt uns die passenden Schlüsselworte an. Diese können daraufhin mittels **TAB+Pfeiltasten** aus der Vorschlagsliste ausgewählt werden. Zur weiteren Automatisierung der Code-Erstellung bietet sich die Nutzung von Templates an (s. Abschnitt [Code Template](#templates)).

![](./img/image80.png)  
<span class="img-caption" markdown=1>
*Abbildung: Beispiel Code Completion für den Import-Parameter*
</span>

Nachdem die Import-Parameter und der Return-Parameter definiert sind, wird der Cursor im Textbereich des Codes positioniert und die Formatierung des Codes mittels des Kontextmenüs\
Rechte Maustaste → Source Code → Format bzw. der Tastenkombination\
**Shift+F1**\
ausgeführt. Dies entspricht dem Pretty Printer in den GUI-Transaktionen. Anschließend wird der Code mittels\
**STRG+S**\
gespeichert.

Sollte ein Syntaxfehler vorliegen, zeigt das Problem-View und die farbliche Markierung im Code den Fehler an. Ist der Code syntaktisch korrekt, kann das Artefakt anschließend mittels **STRG+F3** aktiviert werden.

Nach Einübung der neuen, vor allem Tastatur-basierten, Arbeitsweise entsteht nach kurzer Zeit ein Automatismus, der nach dem Schreiben einiger Codezeilen und anschließender Abfolge der o.g. Tastenkombinationen einen formatierten, geprüften und gesicherten Code als Ergebnis hat. Zeitraubende Überraschungen in Form von Syntaxfehlern beim Aktivieren, wie es in den GUI-Tools vorkommen kann, bleiben dadurch erspart.

## Implementierung der Methode mittels Quick-Fix

Die Methode ist nun definiert, aufgrund der fehlenden Implementierung zeigt ADT im Problems-View folgenden Fehler an:\
`"Implementation missing for method \"CALC_FREE_SEATS_FOR_FLIGHT\"`.

Dieses "Problem" lässt sich sehr effizient mit Hilfe der Quick Fixes beheben.

Zur Methodenimplementierung nutzen Sie die [Quick-Fix](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec5668b6e391014adc9fffe4e204223.html)-Funktion, die sich über das Kontextmenü oder die Tastenkombination **STRG+1** aufrufen lässt.

![](./img/image87.png)  
<span class="img-caption" markdown=1>
*Abbildung: Nutzung des Quick Fix zur Methodenimplementierung*
</span>

Sie wählen "Add Implementation for ..." aus und bestätigen mit ENTER. Zum Ausführen der Quick-Fix-Befehle sollte der Code gespeichert und fehlerfrei sein, da manche Quick Fixes (automatische Code-Korrekturen/Refactorings) dies als Voraussetzungen haben.

Die Methodenimplementierung bedeutet hier, dass automatisiert die Sektion

```abap
METHOD

ENDMETHOD
```

im Bereich der "Class Implementation\" durch ADT erstellt wird und somit eine leere Methodenimplementierung vorhanden ist. Die Ausprägung der Methodenlogik innerhalb dieses Bereiches ist dann Ihre Aufgabe als Entwickler.

Zwischen Definition und Implementierung kann einfach durch Drücken der **F3**-Taste hin und her gesprungen werden.

Mit Platzierung des Cursors auf den Methodenname und **F2** kann man sich die Parameter der Methoden anzeigen lassen. Dies erleichtert das Schreiben des Codes und erspart umständliches Navigieren in den Definitionsbereich. Alternativ steht hierfür die View [ABAP Element Info](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/a8c361f8cc6040f79f52375fb6a9d333.html?q=abap%20element%20inf#loiof7c8d6d10279483ebb625e2e3e31c3d0) zur Verfügung.

In unserem Übungsbeispiel verwenden wir die Import-Parameter, um mittels eines SELECT-Befehls den gewünschten Datensatz zu lesen. Anschließend werden die Anzahl der freien Sitze kalkuliert und als Returning-Parameter an den Verwender zurückgegeben.

Auch hier hilft die Verwendung der Code Completion, die mit der Tastenkombination **STRG+LEERTASTE** aufgerufen wird, um den Code effizient und frei von Tippfehlern zu erstellen.

Um den Returning-Parameter "r_f_free_seats" nicht ausschreiben zu müssen und Typinformationen zu bekommen, schreiben wir die Struktur und den Komponentenseparator "-" und bekommen mittels der Tastenkombination **STRG+LEERTASTE** die Komponenten angezeigt, die dann ausgewählt und in den Code eingefügt werden können.

![](./img/image90.png)  
<span class="img-caption" markdown=1>
*Abbildung: Auswahl der Komponente mittels Code Completion*
</span>

Diese Möglichkeiten der Vorwärtsnavigation und Inline-Anzeige weitergehender Elementinformationen sind in dieser Form in SE80 nicht vorhanden und ein weiterer Baustein zur Steigerung der Entwicklereffizienz in ADT.

Wir haben damit die Klasse mit der ersten Methode in ADT definiert und implementiert.

## Umbenennung von Parametern -- Refactoring

Die laufende Optimierung von bestehenden Code ist eine wichtige Aufgabe jedes Entwicklers. Dies wird von ADT bestens unterstützt. Die verschiedenen Möglichkeiten des Refactoring werden im Abschnitt: [Refactoring von Code mit ADT](#refactoring-von-code-mit-adt) ausführlich erläutert. Weitere Informationen finden sich auch im [User-Guide](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec859406e391014adc9fffe4e204223.html).

Wir möchten die generelle Vorgehensweise des Refactoring anhand einer Umbenennung im Detail darstellen.

Gewohnheitsgemäß haben wir die ungarische Notation verwendet und möchten nun die Parameter der Methode umbenennen, um die Präfixe zu entfernen (vgl. ABAP Clean Code - [https://github.com/SAP/styleguides/blob/main/clean-abap/CleanABAP.md](https://github.com/SAP/styleguides/blob/main/clean-abap/CleanABAP.md)).

Während eine solche Aktion sich im SAP-GUI-Umfeld u. U. sehr aufwendig und fehleranfällig gestalten kann, bietet hier die Rename-Funktion in ADT eine sehr komfortable Möglichkeit, die Umbenennungen von Variablen, Parametern und Methodennamen über alle Verwendungen durchzuführen. Das bedeutet, dass in allen Entwicklungsobjekten, welche die Methode aufrufen, die Parameter automatisiert umbenannt werden. Eine aufwendige Suche nach Verwendern über den Verwendungsnachweis entfällt. Dies funktioniert aber natürlich nur, wenn keine dynamischen Methodenaufrufe verwendet werden. Solche Fälle kann ADT nicht erkennen.

Somit sind Code Cleaning und Refactoring mit ADT sehr effizient durchzuführen, und das Risiko von dadurch entstehenden Fehlern ist gegenüber der manuellen Methode deutlich reduziert.

Zur Umbenennung der Parameter wird die Rename-Funktion aus dem Kontextmenü über rechte Maustaste → Source-Code → Rename oder die Tastenkombination

**ALT+SHIFT+R** oder per Quickfix-Auswahl über

**STRG+1**

ausgeführt.

![](./img/image100.png)  
<span class="img-caption" markdown=1>
*Abbildung: Umbenennung von Methodenparametern*
</span>

Zuerst muss der Code gespeichert werden. Falls dies nicht erfolgt ist, erscheint eine Abfrage zum Speichern, die bestätigt werden muss.

![](./img/image84.png)  
<span class="img-caption" markdown=1>
*Abbildung: Abfragedialog zum Speichern des Code*
</span>

Es erscheint eine Dialog-Box zur Eingabe des Parameternamens.

![](./img/image85.png)  
<span class="img-caption" markdown=1>
*Abbildung: Eingabe neuer Parametername*
</span>

Sofern das Objekt bereits einem Transport zugeordnet ist, kann mit "Finish" die Umbenennung direkt durchgeführt werden.\
Mit "Next" können weitere optionale Einstellungen, wie der zu verwendende Transport und die Aktivierungsoption, vorgenommen werden.

![](./img/image86.png)  
<span class="img-caption" markdown=1>
*Abbildung: Auswahl des Transports und Optionen*
</span>

Vor der finalen Durchführung kann eine Vorschau auf die Änderung angezeigt werden.![](./img/image62.png)  
<span class="img-caption" markdown=1>
*Abbildung: Vorschau der Umbenennung*
</span>

Nach Klick auf "Finish" sind sowohl die Parameter in der Definition, die Verwendung in der Methode als auch die Parameternamen an den Stellen, an denen die Methode verwendet wird, passend abgeändert. Die hier gezeigte Umbenennung funktioniert analog in gleicher Weise für Variablen, Methoden und sogar Klassennamen.

Somit zeigt sich hier ein sehr starker Vorteil gegenüber den SAP-GUI-basierten Entwicklungswerkzeugen, in denen eine objektübergreifende Umbenennung nicht automatisiert möglich ist.

Damit sind die ersten Schritte gemacht, die grundlegenden Funktionen und Arbeitsweisen in ADT sind bekannt und können nun angewendet werden. Die erste Hürde ist genommen und die Basis für die Anwendung der zahlreichen Funktionen der ABAP Development Tools, die in den folgenden Abschnitten detailliert erläutert werden, geschaffen.

# Funktionen von ADT

Der vorige Abschnitt dient vor allem dem Einstieg in die Arbeitsweise und dem Entwickeln mit den ABAP Development Tools in Eclipse. Der Abschnitt Funktionen widmet sich vorrangig der Beschreibung der zahlreichen Features und der Vermittlung von Best Practices im Umgang mit ADT im täglichen Arbeiten.

Nachdem ADT erfolgreich eingerichtet und ein Projekt, d. h. eine Verbindung zu einem Netweaver On-Premise oder eine ABAP Cloud Environment in der SAP BTP hergestellt wurde, kann mit der Entwicklung begonnen werden. In den nachfolgenden Kapiteln bieten wir einen Überblick über die Möglichkeiten, welche die ADT bei der Entwicklung von neuen Objekten und auch bei der Erweiterung/Überarbeitung ("Refactoring") von bestehenden Objekten bietet.

## Übergreifende Features

### Workspaces

Als Hauptebene der Arbeitsstrukturierung und Ablage der Eclipse- und ADT-Konfiguration dienen die sogenannten Workspaces. Beim ersten Start von Eclipse erscheint die Abfrage, in welchem Verzeichnis der Workspaces abgelegt werden soll.

![](./img/image91.png)  
<span class="img-caption" markdown=1>
*Abbildung: Abfrage des Workspace-Verzeichnisses*
</span>

Eine Möglichkeit, wie die Verzeichnisstruktur gestaltet sein kann, findet sich in Kapitel 6 - Best Practices Eclipse Konfiguration.

In diesem Verzeichnis werden zahlreiche Konfigurationseinstellungen abgelegt. Dies sind u.a.

- die Projekte und damit zugreifbaren SAP-Systeme,
- welche Favorite-Packages in den Projekten verwendet werden,
- welche Perspektiven verwendet werden,
- welche Sichten und Objekte geöffnet sind.

Wer mit einem Workspace auskommt, kann den Haken bei "Use this as default ..." anklicken, damit zukünftig dieser Workspace ohne Nachfrage verwendet wird. Diese Einstellung ist in den Einstellungen jederzeit änderbar.

Für die meisten Fälle ist ein Workspace ausreichend. Arbeiten Sie in mehreren Projekten mit unterschiedlichen Systemlinien oder mit unterschiedlichen Kunden, können die Workspaces helfen, die jeweils genutzte Systemumgebung übersichtlich zu halten und für jede Situation die effizienteste Konfiguration zur Verfügung zu haben.

Falls Bedarf besteht, einen neuen Workspace zu erstellen oder zu wechseln, wird mittels

File → Switch Workspace

entweder ein vormals geöffneter Workspace aus der Liste ausgewählt oder mittels

File → Switch Workspace → Other

der Workspace-Dialog aufgerufen.

![](./img/image92.png)  
<span class="img-caption" markdown=1>
*Abbildung: Wechseln des Workspace*
</span>

![](./img/image93.png)  
<span class="img-caption" markdown=1>
*Abbildung: Der Workspace-Dialog*
</span>

Wenn Sie einen neuen Workspace anlegen möchten, geben Sie im Feld Workspace einen neuen Namen ein. Dadurch wird nach Klick auf Launch ein neuer Workspace mit den aktuellen Einstellungen angelegt. Welche Settings aus dem Quell-Workspace übernommen werden sollen, legen Sie mittels der Copy Settings fest. Alternativ können Sie hier einen der angezeigten Workspaces unter Recent Workspaces direkt über das Anklicken der blau hinterlegten Links aufrufen.

### Project Explorer

Der [Project Explorer](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/7135530f575b4f87bff9ae9f0fde4488.html) ist ein zentraler Bestandteil zur Navigation in den eingebundenen Systemen. Sobald Sie ein neues System als "ABAP Project" einbinden, taucht es in der Liste auf. Wenn Sie sich an einem System anmelden und aufklappen, erhalten Sie je nach System weitere Informationen zu freigegebenen Objekten, Favoriten, inaktiven Objekten etc. Diese [Repository Trees](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/c5660c7ea8ae4955bc565a6256ea061d.html) können frei definiert und angepasst werden. Auf Ebene des Pakets verhält sich der View wie die SE80 und bildet Objekt-Hierarchien ab, durch die Sie navigieren können.

### Favorite Packages

Für die tägliche Arbeit empfiehlt es sich, Pakete als Favoriten hinzuzufügen, in denen man regelmäßig tätig ist oder die in die persönliche Zuständigkeit fallen. Damit hat man eine gute Übersicht und findet schnell "seine" Objekte.

![](./img/image35.png)  
<span class="img-caption" markdown=1>
*Abbildung: Hinzufügen von Packages zu den Favoriten*
</span>

Für eine Ablage und Organisation von Favoriten auf Objektebene kann das Plug-in "ABAP Favorites" empfohlen werden, das über den Plug-in-Installationsmechanismus in Eclipse installiert werden kann, siehe Kapitel 7 - Plug-ins.

![](./img/image70.png)  
<span class="img-caption" markdown=1>
*Abbildung: Detailbild Project Explorer mit Buttonleiste*
</span>

In der Buttonleiste gibt es noch einige nützliche Funktionen, mit denen Sie Einstellungen an der View vornehmen können:

- Doppelpfeil (Link with Editor) - Objekte, die im Editor im Fokus sind, werden im Project Explorer angezeigt, es wird dazu die Hierarchie geladen.
- Drei Punkte (View Menü) - Weitere Einstellungen der Views, um zum Beispiel Working Sets anzulegen. Hierbei handelt es sich um Ordner, mit denen man Systeme gruppieren kann (siehe Screenshot oben).

### Working Sets

Wenn Sie als Entwickler mit mehreren Systemlinien arbeiten, empfehlen wir die Verwendung der Working Sets. Diese ermöglichen es, Projekte in Eclipse zu gruppieren und somit mehrere Systeme übersichtlich darzustellen.

Über das Drei-Punkte-Icon in der rechten oberen Ecke des Project Explorer finden sich diverse Einstellungsmöglichkeiten. Unter anderem können hier die Working Sets erstellt und konfiguriert werden.

![](./img/image95.png)  
<span class="img-caption" markdown=1>
*Abbildung: Working-Sets-Einstellungen*
</span>

Über den Dialog können nun Working Sets angelegt werden (New) und die Zuordnungen erfolgen (Edit).

![](./img/image55.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anlage und Bearbeitung der Working Sets*
</span>

Über den Edit-Button können im Folgedialog die gewünschten Projekte dem Working Set zugeordnet werden.

![](./img/image54.png)  
<span class="img-caption" markdown=1>
*Abbildung: Zuordnung Projekt zu Working Set*
</span>

Diese Funktion ermöglicht eine übersichtliche Strukturierung der Systeme nach Systemlandschaft oder ggf. nach Projekt bzw. Kunde. Abschließend muss noch die Anzeige der Top Level Elements auf Working Sets eingestellt werden.

![](./img/image56.png)  
<span class="img-caption" markdown=1>
*Abbildung: Einstellung der Projekt-Explorer-Anzeige*
</span>

![](./img/image57.png)  
<span class="img-caption" markdown=1>
*Abbildung: Darstellung Projekte in Working Sets*
</span>

## Suche und Navigation

Die Suche nach Objekten in Eclipse ist zentraler Bestandteil der täglichen Arbeit, ebenso wie die Navigation zwischen den Objekten oder auch die Vorwärtsnavigation. In diesem Abschnitt erfahren Sie mehr über die Suche und Navigation zwischen ABAP-Objekten.

### Objekte suchen

Um ein Objekt im System zu suchen bzw. zu öffnen, können Sie den Dialog\
"Open ABAP Development Object" nutzen (erreichbar über die Tastenkombination **STRG+SHIFT+A**).

![](./img/image101.png)  
<span class="img-caption" markdown=1>
*Abbildung: Dialog zur Objektsuche*
</span>

Im Dialog haben Sie die Möglichkeit, im oberen Teil das ABAP-Projekt zu ändern und damit zu entscheiden, auf welchem System Sie nach dem Objekt suchen möchten. Wurde im Suchfeld nichts eingegeben, erhalten Sie eine Historie der zuletzt geöffneten Objekte. Über das *Fragezeichen* im unteren Bereich erhalten Sie weitere Informationen, Tipps und Tricks zur Nutzung der Suche. Detaillierte Informationen zur Objektsuche finden Sie im [User-Guide](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec7eed86e391014adc9fffe4e204223.html).

### Objekte filtern

In der Objektsuche haben Sie nun die Möglichkeit, mit Such-Strings und Pattern zu arbeiten, um die Ergebnismenge weiter einzuschränken. Das Feld unterstützt den "Content Assist" (**STRG+LEERTASTE**), um weitere Einschränkungen und Filter zu verwenden. Eine einfache Suche könnte wie folgt aussehen:

![](./img/image63.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ergebnis der Suche*
</span>

Allerdings werden mehr als 50 Ergebnisse (Standardeinstellung) angezeigt und wahrscheinlich ist das gewünschte Ergebnis nicht mit in der Ergebnismenge erhalten. In diesem Fall können Sie den "Content Assist" aufrufen, um weitere Optionen zum Filtern zu erhalten.

![](./img/image58.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige weiterer Suchoptionen*
</span>

Wenn Sie zum Beispiel nun auf Tabellentypen einschränken möchten, dann würden Sie weiter nach dem Typ (TYPE) einschränken. Der "Content Assist" schlägt weiterhin auch die verschiedenen Typen von Objekten vor, sodass Sie auch den Tabellentyp (TTYP) finden.

![](./img/image65.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ergebnis mit Objekt- und Typfilter*
</span>

Die weiteren Filter und Typen können frei miteinander kombiniert werden, um die gewünschte Zielmenge oder das Zielobjekt zu finden. Mit einem Doppelklick auf den gewünschten Eintrag wird das Objekt dann im Editor angezeigt.

Um die Suche zu beschleunigen, empfiehlt es sich, den Typ des gewünschten Objektes vorzugeben, da sonst die Suche -- verglichen mit der gewohnten Geschwindigkeit in der SE80/SE11/etc. -- sehr lange dauert.

### Navigation

In der ABAP Workbench funktioniert die [Navigation](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/ec2da130ce43409fbb2f6a072f9ba07c.html) zum nächsten Objekt über einen Doppelklick auf den entsprechenden Ausdruck im Quellcode. In Eclipse wird hier lediglich der Quelltext markiert. Um die Vorwärtsnavigation auszulösen, gibt es drei Möglichkeiten:

- Cursor auf dem Objekt platzieren, F3 drücken
- Mit gedrückter **STRG**-Taste das Objekt anklicken
- In der Oberfläche wird ein klickbarer Link angeboten (z. B. Datenelement → Domäne)

Das Objekt wird in einem neuen Tab innerhalb des Editors geöffnet, das Quellobjekt bleibt weiterhin geöffnet und Sie können zwischen den zuletzt geänderten Objekten sehr einfach über die Tastenkombinationen navigieren:

- **ALT+Pfeil rechts**: vorwärts
- **ALT+Pfeil links**: rückwärts

Dies kann analog auch mit den Pfeiltasten im Bereich der Drucktastenleiste durchgeführt werden. Im Bereich der Drucktastenleiste gibt es dafür auch verschiedene Optionen, um zum letzten verwendeten Tab (**ALT+Pfeil links**) zu gelangen.

![](./img/image64.png)  
<span class="img-caption" markdown=1>
*Abbildung: Navigations-Ikonen*
</span>

### ABAP Repository Tree anzeigen

Nachdem Sie ein Objekt gefunden haben, möchten Sie in vielen Fällen in diesem Paket weiter arbeiten oder recherchieren. Dazu können Sie sich den Objektbaum laden lassen, indem Sie im Project Explorer den doppelten Pfeil ("Link with Editor") aktivieren.

![](./img/image88.png)  
<span class="img-caption" markdown=1>
*Abbildung: Aktionen für den Project Explorer*
</span>

In diesem Fall wird die Pakethierarchie zu dem im Editor fokussierten Objekt geladen. Im Anschluss können Sie im Project Explorer über die weiteren Objekte und Strukturen navigieren.

Die Arbeit mit dem Repository Tree ist detailliert im [[User-Guide] beschrieben](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/f831fc6e18984a8a864da4c0591e996b.html).

## ABAP Editor

Der [ABAP Editor](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/79d78f0268484b59a1f6a0e7994316d3.html) ist ein einfacher Texteditor, der die rein textuelle Erstellung von ABAP-Artefakten ermöglicht. Über die Kontext-Funktion können dort die wichtigsten Funktionen wie Quick Fixes, Refactoring-Funktionen und Formatierungsfunktionen aufgerufen werden. Der Einstieg in den ABAP Editor ist im Abschnitt [Das Erstellen einer Klasse im Textmodus](#das-erstellen-einer-klasse-im-textmodus) näher beschrieben.

![](./img/image45.png)  
<span class="img-caption" markdown=1>
*Abbildung: ABAP Editor - Hauptfenster*
</span>

### Element Info

Über die Positionierung des Cursors auf einem Objekt und dem Shortcut **F2** erscheint ein Pop-up mit Zusatzinformationen. Hier am Beispiel einer Methode und eines Datenelements:

![](./img/image7.png)  
<span class="img-caption" markdown=1>
*Abbildung: Element Info für eine Methode*
</span>

![](./img/image42.png)  
<span class="img-caption" markdown=1>
*Abbildung: Element Info für ein Datenelement*
</span>

In der [Element Info](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec724ce6e391014adc9fffe4e204223.html) sind somit direkt Details ersichtlich, für die man in der alten Welt noch im System navigieren musste. Zusätzlich lässt sich im Element Info weiter navigieren, um Details tieferer Ebenen zu sichten, z. B. die hinterlegte Domäne etc.

Die ABAP Element Info existiert auch als eigenständige View. Diese kann über das Menü Windows → Show View → ABAP Element Info aktiviert werden. Danach wird über "[Link with Selection](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec5bb496e391014adc9fffe4e204223.html)" ![](./img/image23.png) bei jedem Klick auf ein relevantes Entwicklungsobjekt automatisch dessen Element Info sowie die Dokumentation aus ABAP Doc angezeigt:

![](./img/image44.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Element Info nach Auswahl des Objekts*
</span>

Über "Pin this view" <span class="inline-img">![](./img/image17.png)</span> wird die Information dauerhaft angezeigt, auch wenn auf ein anderes Element geklickt oder die Element Info per **F2** für ein anderes Entwicklungsobjekt geöffnet wird.

### Quelltextformatierung mit dem ABAP Formatter

In der SAP GUI heißt das Werkzeug zum Formatieren des Quellcodes Pretty Printer. Das Pendant in ADT ist der [ABAP Formatter](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec799106e391014adc9fffe4e204223.html). Er wird entweder über die Tastenkombination

**SHIFT+F1**

oder über das Kontextmenü im Quelltext aufgerufen.

![](./img/image9.png)  
<span class="img-caption" markdown=1>
*Abbildung: Kontextmenü für die Formatierung*
</span>

Damit der ABAP Formatter seinen Dienst leisten kann, muss er vorab konfiguriert werden. Dabei legt man analog zu den Pretty-Printer-Einstellungen in der SAP GUI fest, ob Einrückungen gemacht werden sollen und wie die Groß-/Kleinschreibung formatiert wird. Dies geschieht für jedes ABAP-Projekt separat.

#### Einstellung des ABAP Formatters

Falls die Einstellungen noch nicht vorgenommen wurden, erscheint ein Pop-up-Fenster mit der Meldung, dass dies zuvor erledigt werden muss. In diesem Pop-up-Fenster ist auch ein Link zu den Einstellungen enthalten. Alternativ kann man diese auch direkt über den Kontextmenü-Eintrag *Properties* des entsprechenden Projektes aufrufen. In der folgenden Abbildung sehen Sie die Position in den Einstellungen.

![](./img/image11.png)  
<span class="img-caption" markdown=1>
*Abbildung: Einstellungen für den ABAP Formatter*
</span>

Die Einstellungen entsprechen denen in der SAP GUI. Wenn man die einzelnen Optionen durchprobiert, sieht man im Vorschaufenster das jeweilige Ergebnis. Neu ist die Möglichkeit, dass Camel-Case-Bezeichner beibehalten werden. Das ist gerade im Zusammenhang mit den CDS Views sehr praktisch, da diese im virtuellen Datenmodell von SAP (VDM) konsequent verwendet werden.

### Quick Fixes

Quick Fixes sind automatisierte Lösungen für gängige Probleme im Rahmen der Software-Entwicklung mit ABAP. Quick Fixes werden dabei nativ durch die ADT angeboten, können aber auch durch verschiedene Plug-ins erweitert werden. Die Verwendung durch die Vielzahl der verfügbaren Quick Fixes macht das Arbeiten mit den ADT wesentlich effizienter als mit der SE80. Zusätzlich wird das Risiko von Fehlern durch manuelle Anpassungen reduziert. Die ADT erledigen die Anpassungen automatisiert und immer identisch.

Quick Fixes liefern Funktionen für zwei Bereiche:

- Automatisches Anlegen von nicht vorhandenen Objekten (z. B. Methodenimplementierungen)
- Automatisches Verändern von bestehenden Objekten ohne Veränderung der Funktionalität (sog. Refactoring, z. B. "Methode extrahieren")

![](./img/image18.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Refactoring Optionen*
</span>

Aufgrund der Vielzahl an Quick Fixes und der ständigen Änderungen in diesem Bereich werden die einzelnen Quick Fixes hier nicht beschrieben. Ein Überblick ist in der [Dokumentation](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/ce178e5425364f51994f2c7f634cb56c.html) zu finden.

## Andere Objekttypen

### Programme und Funktionsgruppen

Programme und Funktionsgruppen werden in der Navigation des Project Explorers im Ordner *Source Code Library* angezeigt. Unter den entsprechenden Objekttypen werden alle Komponenten entsprechend der SAP GUI angezeigt.

![](./img/image77.png)  
<span class="img-caption" markdown=1>
*Abbildung: Vergleich Funktionsgruppen im Project Explorer der ADT und in der SE80*
</span>

Es wird der gleiche Quelltexteditor wie für ABAP-Klassen verwendet. Damit sind alle Features vom ABAP Formatter bis zur Language-Help weitgehend identisch.

## ABAP Views

### Outline

Die [Outline](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/706db06c6bf41014b5040bee4e204223.html) View liefert Informationen zum aktuell fokussierten Entwicklungsobjekt und löst Variablen, lokale Klassen, Typen etc. auf. Die View kann mit der SE80 verglichen werden, zeigt Ihnen aber immer nur den aktuellen Kontext des Objekts an. Im Screenshot sehen Sie eine Klasse, darunter die entsprechenden Methoden und zwei private Attribute der Klasse. Mit einem Klick auf einen Eintrag navigieren Sie an die entsprechende Stelle im Quellcode.

![](./img/image38.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Eigenschaften in den Outlines*
</span>

In der Button-Leiste gibt es weitere verschiedene Funktionen für den View:

- "Sort" -- Sortierung der Einträge nach Alphabet oder nach Typ und Alphabet
- "Hide Non-Public Members" -- Es werden nur Attribute und Methoden angezeigt, die auch von außen verwendbar sind (Thema Sichtbarkeit)

Hinweis: Im Kapitel 7 - Plug-ins finden Sie weitere Informationen zum Plug-in "Classic Outlines", welches die Outlines erweitert.

### Problems

Die [Problems View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/10bd0d0fdb9c42a8a78933d270f2c41b.html) ist wahrscheinlich eine der wichtigsten Views. Sie zeigt Informationen zu Fehlern innerhalb von Entwicklungsobjekten in Form einer Liste. Die View aktualisiert sich automatisch, wenn neue Fehler hinzukommen oder bestehende korrigiert werden. Ein andauerndes "Prüfen" des Source-Codes ist nicht notwendig.

Dargestellt werden in der Standardkonfiguration dabei systemübergreifend alle Fehler in den eigenen geöffneten Objekten, nicht nur des aktuell in Bearbeitung befindlichen Objekts.

![](./img/image2.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Meldungen im Problems View*
</span>

Durch Doppelklick kann an die entsprechende Stelle im Source-Code navigiert werden.

Über den Button <span class="inline-img">![](./img/image31.png)</span> kann der View weiter konfiguriert werden:

![](./img/image59.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Optionen des Views*
</span>

- Unter "Show" kann konfiguriert werden, welche Fehler/Warnungen in der Problems View angezeigt werden, z. B. nur die des aktuell in Bearbeitung befindlichen Entwicklungsobjekts oder alle.
- "Group by" ermöglicht eine Gruppierung nach verschiedenen Kriterien, üblicherweise wird hier nach "Severity", d. h. Fehler/Warnung/Info gruppiert.
- Über "Sort By" kann die Reihenfolge der Darstellung verändert werden.
- "New Problems View" dupliziert die View.
- "Filters" ermöglicht, die Ergebnisliste noch einmal im Detail bis hinunter auf den Entwicklungsobjekttyp zu filtern.
- "Configure Columns" ermöglicht es, Spalten ein- und auszublenden sowie die Reihenfolge der Spalten zu ändern.

![](./img/image99.png)  
<span class="img-caption" markdown=1>
*Abbildung: Konfiguration der angezeigten Punkte*
</span>

### Properties

Die [Properties View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec739dd6e391014adc9fffe4e204223.html) sammelt Informationen, die in der klassischen SAP GUI unter "Eigenschaften" dargestellt werden. Dazu zählen beispielsweise:

- Zustand Entwicklungsobjekt (aktiv/inaktiv)
- Erstellungs- und Änderungsinformationen
- Paketzuordnung

![](./img/image36.png)  
<span class="img-caption" markdown=1>
*Abbildung: Properties View*
</span>

Im Bereich "Specific" werden objektspezifische Eigenschaften angezeigt und können dort teilweise geändert werden. Für Klassen ist hier beispielsweise die Festpunktarithmetik einstellbar.

Im Bereich Transport ist eine Historie der Transportaufträge gelistet, in denen das Objekt enthalten ist.

![](./img/image47.png)  
<span class="img-caption" markdown=1>
*Abbildung: Historie der Transporte*
</span>

Über das Kontextmenü kann wiederum in den Transportauftrag zur weiteren Analyse verzweigt werden.

![](./img/image66.png)  
<span class="img-caption" markdown=1>
*Abbildung: Transport View*
</span>

Abhängig vom Typ des geöffneten Entwicklungsobjektes existieren weitere Bereiche, die spezifische Informationen zum jeweiligen Objekt enthalten.

Um mehrere Objekte parallel zu sichten, lassen sich über den Button <span class="inline-img">![](./img/image31.png)</span> auch mehrere Properties Views erzeugen.

Der Properties View hat im Vergleich zur klassischen SAP-GUI-Entwicklung mehrere Vorteile:

- Er ist (in der Regel) ständig eingeblendet und verfügbar, so dass nicht aufwendig navigiert werden muss.
- Er aggregiert Informationen, die zuvor nur über mehrere Transaktionen/Tabs/Reiter identifizierbar waren.

### Templates

[Code Templates](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec116596e391014adc9fffe4e204223.html) sind vorgefertigte Muster an Quellcode, die beliebig in eine Anwendung implementiert werden können. Diese Muster geben statischen Quellcode wieder und besitzen dynamische Elemente in Form von Variablen. In der Standardauslieferung der ADT werden einige Templates ausgeliefert.

#### Template View

Templates werden über einen eigenen View zur Verfügung gestellt (Window → Show View → Templates) und können auch über die Einstellungen angepasst werden (General → ABAP Development → Editors → Source Code Editors → ABAP Templates).

![](./img/image69.png)  
<span class="img-caption" markdown=1>
*Abbildung: Template View Browser*
</span>

Der View besteht im oberen Bereich aus einer Button-Leiste, einer Liste der Code Templates und im unteren Teil aus einem Preview des Templates.

#### Template verwenden

Das [Template](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ecd257e6e391014adc9fffe4e204223.html) kann direkt im Quellcode verwendet werden. Beginnen Sie, den Namen zu tippen, und wählen Sie mit Hilfe des "Content Assist" das passende Template aus (hier die ersten beiden Einträge).

![](./img/image52.png)  
<span class="img-caption" markdown=1>
*Abbildung: Auswahl der Templates im Content Assist*
</span>

Das gesamte Template wird eingefügt, und Sie können damit beginnen, die Platzhalter (Variablen) zu befüllen. Mit dem Tabulator springen Sie zwischen den einzelnen Platzhaltern hin und her.

Häufig verwendete Templates zur Nutzung sind beispielsweise:

- **lcl** - Anlage einer lokalen Klasse
- **testClass** - Anlage einer Testklasse
- **functionModuleParameter** - Beispielschnittstelle für Funktionsbausteine

Die Anlage von eigenen Templates eignet sich sehr gut zur Einsparung von Entwicklungsaufwand bei wiederholenden Aufgaben oder ähnlichen Code-Abschnitten. Weiterhin können sie in Schulungen hilfreich sein, wenn Sie größere Code-Abschnitte einfügen möchten, ohne per Copy-and-paste zu arbeiten.

#### Template anlegen

Ein Template kann grundsätzlich mit allen in ABAP verwendeten Sprachbefehlen definiert werden (Quellcode, Kommentare). Variable Teile des Templates können Sie mit Platzhaltern versehen ("\${placeholder}"). Zur Ableitung von kontextspezifischen Informationen stehen auch Variablen zur Verfügung. Diese gibt es für die folgenden Szenarien:

- Name des Objekts
- Name des Pakets
- ID des Systems
- User, Datum und Uhrzeit
- Aktuelles Jahr
- Cursor-Position nach dem Einfügen

Gleichnamige Platzhalter werden nach dem Einfügen immer einheitlich angepasst (z. B. der Name der Klasse).

#### Verfügbarkeit von Templates

Templates stehen innerhalb eines Eclipse-Workspace zur Verfügung, sind im Gegensatz zu eigenen Mustern aber über Systeme hinweg verfügbar. Templates können über die Einstellungen importiert und exportiert werden, um sie unter Kollegen/Mitarbeitern auszutauschen. Eine zentrale An- und Ablage von Templates für alle Entwickler ist nicht möglich.

### Verwendungsnachweis/Where-Used-List

Der [Verwendungsnachweis](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ecc9bf86e391014adc9fffe4e204223.html) findet alle statischen Verwendungen eines Entwicklungsobjektes im Source-Code des aktuellen Projektes. Der Verwendungsnachweis ist über die Tastenkombination

**STRG+SHIFT+G** (Get-Where-Used-List)

erreichbar. Das Ergebnis wird im Reiter "Search" dargestellt:

![](./img/image43.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ergebnis des Verwendungsnachweises/Where-Used-List*
</span>

Durch die Verwendung der Filterfunktion mit Hilfe des Filter-Icons kann hierbei auf Pakete, Objekttypen und Benutzer eingeschränkt werden. Auch hier kann per **STRG+SPACE** die automatische Vervollständigung genutzt werden, um Objekte schneller zu finden.

![](./img/image67.png)  
<span class="img-caption" markdown=1>
*Abbildung: Filter für Where-Used-Search*
</span>

Über **STRG+.** und **STRG+,** lassen sich die Fundstellen komfortabel browsen, d. h. die jeweils nächste oder vorherige Fundstelle anzeigen.

### Bookmarks

[Bookmarks](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ecd34b46e391014adc9fffe4e204223.html) sind "Lesezeichen" zu im System definierten Entwicklungsobjekten. Oft ergeben sich Schlüsselstellen, an denen des Öfteren Anpassungen notwendig sind. Das kann verschiedene Gründe haben, beispielsweise:

- Ein großer historisch gewachsener Include, an dem immer wieder Erweiterungen stattfinden.
- Eine Klasse mit komplexer Logik, die sich als fehleranfällig herausstellt.
- Objekte, an denen regelmäßig gearbeitet wird.

Bookmarks können durch Rechtsklick auf die Liste neben dem Source-Code erstellt werden:

![](./img/image60.png)  
<span class="img-caption" markdown=1>
*Abbildung: Menü zur Erstellung des Bookmarks*
</span>

Als Name wird per Standard das Coding der selektierten Zeile angegeben. Es bietet sich an, einen sprechenden und fachlich sinnvollen Namen zu vergeben, über den das Bookmark dann auch einfach wiedergefunden wird.

![](./img/image8.png)  
<span class="img-caption" markdown=1>
*Abbildung: Eingabe eines Namens (Bookmark)*
</span>

Innerhalb des Source-Code-Editors erscheint nun eine kleine blaue Fahne neben der selektierten Zeilennummer:

![](./img/image51.png)  
<span class="img-caption" markdown=1>
*Abbildung: Darstellung eines Bookmarks im Quellcode*
</span>

Das Bookmark ist dann in der Liste verfügbar und kann durch Doppelklick aufgerufen werden. Über <span class="inline-img">![](./img/image31.png)</span> lassen sich zudem die Ansicht anpassen und Filterungen durchführen. Über das Kontextmenü ist ein Löschen des Bookmarks sowie das Editieren der Beschreibung möglich.

![](./img/image32.png)  
<span class="img-caption" markdown=1>
*Abbildung: Bookmarks View*
</span>

### Teilen von ADT-Links

Im Entwickler-Alltag kommt es oft vor, dass gemeinsam über Code gesprochen werden muss (z. B. bei Reviews) oder ein Problem in einem Stück Coding gefunden wird, welches in der Verantwortung einer anderen entwickelnden Person liegt (kein Shared-Code-Ownership). Oft heißt es dann "Kannst du mal bitte in der Klasse *XYZ Methode ABC Zeile 1203* schauen... Ich glaube, da ist ein Bug?". Der andere Entwickler muss aufwändig durch die IDE navigieren, bis er die erwähnte Stelle findet.

ADT bietet die Möglichkeit, einen Link zu versenden, der den Empfänger direkt an die passende Code-Stelle führt, wenn er auf diesen klickt. Hierzu muss ein Bereich im Source-Code markiert und dann im Kontextmenü "Share Link" ausgewählt werden.

![](./img/image82.png)  
<span class="img-caption" markdown=1>
*Abbildung: Teilen des Quellcodes als Link (Kontextmenü)*
</span>

![](./img/image49.png)  
<span class="img-caption" markdown=1>
*Abbildung: Dialog zum Teilen des Links*
</span>

Der entsprechend generierte Link kann dann an den Kollegen per Mail versendet oder in die Zwischenablage kopiert und beispielsweise über ein Chat-Programm versendet werden. Man hat die Auswahl zwischen HTTP-Link und ADT-Link. HTTP-Links werden direkt im Browser geöffnet, ADT-Links verzweigen in die ADT (Eclipse).

Aufbau eines ADT-Links (URI):

*adt://\<System\>/sap/bc/adt/oo/classes/\<Klasse\>/source/\<Methode\>#start=18,0*

Mehr Details sind im [User-Guide](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec63adf6e391014adc9fffe4e204223.html) zu finden.

### ABAP Type Hierarchy

Die View [Type Hierarchy](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4eccd9066e391014adc9fffe4e204223.html) dient dazu, die Vererbungshierarchie von Klassen und Interfaces darzustellen. Um die View zu nutzen, braucht man nur den Cursor auf die Klasse oder das Interface zu setzen und den Shortcut **F4** zu drücken. Alternativ kann man über das Kontextmenü die ABAP Type Hierarchy öffnen.

![](./img/image22.png)  
<span class="img-caption" markdown=1>
*Abbildung: Öffnen der ABAP Type Hierarchie*
</span>

Die View zeigt die Hierarchie in einer Baumstruktur an.

![](./img/image3.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Type Hierarchy im View*
</span>

Per Doppelklick kann man das markierte Objekt im ABAP Editor öffnen. Über **STRG+T** lässt sich auch inline im Code die [Quick Type Hierarchy](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/aafadb177a1a4cac8117b7b079c2596b.html) öffnen.

### Transport Organizer

Der [Transport Organizer](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ecc6dd96e391014adc9fffe4e204223.html) zeigt eine Übersicht der geöffneten ABAP-Projekte. Unter den Systemen finden Sie die aktuellen Transporte im System. In der Standardeinstellung sehen Sie alle eigenen Transporte. Über einen Rechtsklick auf ein System und den Punkt "Configure Tree ..." können diese Einstellungen überschrieben und auch Transporte von anderen Entwicklern eingesehen werden.

![](./img/image68.png)  
<span class="img-caption" markdown=1>
*Abbildung: Transport Organizer View*
</span>

Es stehen alle Funktionen des Transport Organizer (SE09/SE10) aus der SAP GUI zur Verfügung:

- Doppelklick - Details zu Auftrag/Aufgabe in eigenem View anzeigen
- Rechtsklick - Verschiedene Funktionen wie zum Beispiel: Benutzer ändern, Konsistenzprüfung, Freigeben

### Feed Reader

Der [Feed Reader](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec3b0cd6e391014adc9fffe4e204223.html) kann im Zusammenhang mit ADT genutzt werden, um bestimmte Benachrichtigungen vom SAP-System zu erhalten. Standardmäßig werden bei einem ABAP-Projekt folgende Benachrichtigungen konsumiert:

- Laufzeitfehler (Dump) verursacht durch den eigenen User
- Laufzeitfehler für Objekte, für die der eigene User verantwortlich ist
- Systemmeldungen

![](./img/image6.png)  
<span class="img-caption" markdown=1>
*Abbildung: Darstellung eines Laufzeitfehlers*
</span>

![](./img/image12.png)  
<span class="img-caption" markdown=1>
*Abbildung: Beispiel für Systemmeldung*
</span>

Über den Button "Add feed..." kann man weitere Benachrichtigungen konsumieren. Welche Art von Benachrichtigung zur Verfügung steht, hängt vom Release-Stand des verknüpften SAP-Systems ab. Bei den meisten Benachrichtigungen kann man verschiedene Filterkriterien angeben. Zusätzlich kann man auch einen normalen Atom- oder RSS-Feed per URL hinzufügen und somit konsumieren.

Details dazu findet man im User-Guide in den Hilfefunktionen von Eclipse. Der Artikel Getting Feeds ist dabei ein guter Einstiegspunkt.

### ABAP Unit

Die View [ABAP Unit](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/08c60b52cb85444ea3069779274b43db.html) öffnet sich nach dem Ausführen von ABAP Unit Tests und listet die ausgeführten Testmethoden sowie deren Status auf. Die ABAP Unit Tests können per Shortcut **STRG+SHIFT+F10** oder über das Kontextmenü im ABAP Editor mit dem Menüpunkt *"Run As"* gestartet werden.

![](./img/image40.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ausführung des ABAP Unit Test über das Kontextmenü*
</span>

Innerhalb der View kann man die Liste nach Status filtern, Testfälle erneut ausführen und sich Details zu fehlerhaften Läufen anzeigen lassen. Letzteres erscheint durch Anklicken der betroffenen Testmethode.

![](./img/image37.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ergebnisanzeige des ABAP Unit Test*
</span>

Den Umfang der auszuführenden Testmethoden kann man über verschiedene Möglichkeiten bestimmen. Zum einen hängt dies vom Kontext ab. Hat man zum Beispiel den Fokus auf einer einzelnen Testmethode, so wird auch nur diese Methode ausgeführt. Sitzt der Fokus auf der zu testenden Klasse, dann werden alle Testklassen (und Testmethoden) dazu ausgeführt. Man kann das Ganze sogar auf ein komplettes Paket ausweiten, indem man das Paket im Projekt Explorer markiert und die Unit Tests ausführt. Außerdem kann man in der View per Kontextmenü einzelne oder alle Tests erneut ausführen - je nachdem, welche Ebene man wählt. Zum Beispiel könnte man alle Testmethoden nur einer Testklasse ausführen. Diese Möglichkeit ist besonders hilfreich, wenn ein Testfall nicht erfolgreich ist und man das Verhalten analysieren muss.

![](./img/image89.png)  
<span class="img-caption" markdown=1>
*Abbildung: Neustart der Ausführung*
</span>

Zum anderen kann man über "ABAP Unit Test With..." festlegen, welche Art von Tests durchgeführt werden sollen.

![](./img/image15.png)  
<span class="img-caption" markdown=1>
*Abbildung: Dialog zur Einstellung der Ausführung von ABAP Unit Tests*
</span>

Somit könnte man zum Beispiel nur die Testmethoden in einem Paket ausführen, die das Risk-Level "Dangerous" und die Duration "Medium" haben.

### ABAP Coverage

Die View [ABAP Coverage](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec487046e391014adc9fffe4e204223.html) erscheint, wenn man ABAP Unit Tests mit Coverage (Testabdeckung) ausführt. Die Test-Coverage bietet einen Hinweis darauf, welcher Code nicht durch automatisierte Tests abgedeckt ist. Die dortige Testabdeckung kann eine bewusste Entscheidung sein, da eine Testabdeckung von hundert Prozent auf Dauer sehr viel Aufwand in der Entwicklung macht. Coverage kann auch Hinweise darauf liefern, wo mehr Testabdeckung nötig sein könnte. Eine pauschale Empfehlung für eine Testabdeckung kann nicht gegeben werden und ist gegebenenfalls auch abhängig von der Kritikalität der Anwendung.\
\
Diese Art der Ausführung kann per Shortcut **STRG+Shift+F11** oder über das Kontextmenü mit dem Menüpunkt "Coverage As" gestartet werden.

![](./img/image71.png)  
<span class="img-caption" markdown=1>
*Abbildung: Durchführung der Abdeckungsmessung*
</span>

Die View stellt den durchlaufenen Code in einer Baumstruktur dar und gibt Auskunft darüber, wie viele Statements absolut und relativ durch die ausgeführten Testmethoden ausgeführt wurden. Zusätzlich wird im ABAP Editor farblich markiert, welche Statements genau ausgeführt wurden (mit grün) und welche nicht (mit rot).

![](./img/image72.png)  
<span class="img-caption" markdown=1>
*Abbildung: Farbliche Hervorhebung von Quellcode nach Unit Test*
</span>

Ist die farbliche Ansicht im Source-Code nicht sichtbar, so kann diese über das Icon <span class="inline-img">![](./img/image34.png)</span> aktiviert werden.

### ATC und Exemption

Das [ABAP Test Cockpit](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec5711c6e391014adc9fffe4e204223.html) kann in ADT ebenso wie in der SAP GUI ausgeführt werden. Dabei haben Sie verschiedene Möglichkeiten, wie Sie die Prüfung starten können:

- Über die Tastenkombination **STRG+SHIFT+F2**
- Rechtsklick im Projekt Explorer unter dem Punkt "Run As"
- Im Menüband oben, unter dem Button zum Starten des Objekts

Nach Ausführung der Prüfungen erhalten Sie die View für die "ATC Problems", also die Rückmeldungen über die gefundenen Meldungen durch die eingestellten Prüfungen.

![](./img/image20.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige der Ergebnisse des ATC-Laufs*
</span>

Auf der linken Seite werden die Meldungen sortiert nach der Schwere des Fehlers angezeigt. Rechts erhalten Sie Informationen zum gewählten Eintrag. Hier wird für Sie noch einmal erklärt, was geprüft wurde und wie eine Korrektur aussehen kann. In der Button-Leiste im oberen Bereich der View kann das Ergebnis auch wieder gelöscht werden. Auf diese Weise verschwinden die Markierungen im Quellcode.

Mit einem Rechtsklick auf die Meldung kann über den Menü-Eintrag "Request Exemption" auch eine Ausnahme beantragt werden.

![](./img/image19.png)  
<span class="img-caption" markdown=1>
*Abbildung: Beantragung von Ausnahmen über den ATC View*
</span>

Das Formular entspricht von den Informationen her der SAP GUI und leitet Sie durch den Freigabeprozess. Am Ende kann die Anfrage wie gewohnt über das ATC Cockpit bearbeitet werden.

![](./img/image24.png)  
<span class="img-caption" markdown=1>
*Abbildung: Dialog zur Klassifizierung der Ausnahme*
</span>

### ABAP Language Help

In jedem Quelltexteditor, beispielsweise für ABAP, CDS oder BDL, kann für das Schlüsselwort, auf dem der Cursor ist, mit der Taste F1 direkt die jeweilige [Sprachhilfe](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/640a9cf3278e45b49076370f092cdd1f.html) (nicht nur ABAP!) aufgerufen werden. Alternativ kann man diese auch über das Kontextmenü per Rechtsklick auf die entsprechende Anweisung bekommen:

*Source Code → Show ABAP Language Help*

Damit kann man jederzeit Unterstützung bekommen, falls man sich der exakten Syntax einer Anweisung nicht sicher ist.

![](./img/image48.png)  
<span class="img-caption" markdown=1>
*Abbildung: Aufruf der ABAP-Sprachhilfe über das Kontextmenü*
</span>

### Der ABAP Language Help View

Die entsprechende Dokumentation wird im ABAP Language Help View als HTML-Dokument angezeigt. Damit ist eine Vorwärtsnavigation über Hyperlinks möglich.

![](./img/image4.png)  
<span class="img-caption" markdown=1>
*Abbildung: ABAP Language Help View*
</span>

Wie in vielen Views in Eclipse sind hier einige nützliche Standard-Buttons vorhanden.

![](./img/image102.png)  
<span class="img-caption" markdown=1>
*Abbildung: Button-Leiste des Views*
</span>

- Der gelbe Doppelpfeil koppelt die View mit dem aktiven Editor. Damit zeigt die View stets die passende Hilfe für eine Anweisung an, auf der der Cursor momentan steht.
- Der grüne Pin hält den Inhalt des Views fest. Wenn ein weiteres Mal mit F1 eine Hilfe angefordert wird, öffnet sich eine neue View für die ABAP Language Help.
- Die gelben Pfeile nach rechts und links dienen der Navigation (analog eines Web-Browsers).
- Mit Hilfe des Drucker-Symbols kann man mit entsprechender Hardware eine papierhafte Kopie der ABAP-Hilfe anfertigen.
- Die beiden Symbole A mit den Pfeilen nach oben und unten sind für die Änderung der Schriftgröße zuständig.
- Mit dem Suchfeld kann die komplette ABAP-Hilfe, einschließlich der anderen Sprachen wie CDS oder BDL, durchsucht werden.

### Application Help

Neben der ABAP Keyword Documentation (bzw. ABAP Language Help) stellt SAP für jedes Entwicklungsszenario sogenannte Eclipse Help Plug-ins zur Verfügung. Klicken Sie hierfür

**Help → Help Contents**

in der Menüleiste, um den Hilfe-Browser zu öffnen.

![](./img/image41.png)  
<span class="img-caption" markdown=1>
*Abbildung: Navigation zum Help Content*
</span>

Sie erkennen die Help Plug-ins von SAP an dem gelben Buch-Icon. Momentan gibt es die folgenden Help Plug-ins:

![](./img/image96.png)  
<span class="img-caption" markdown=1>
*Abbildung: Übersicht der verfügbaren Hilfen und Dokumentationen*
</span>

Mit Hilfe der Suche (Search) können Sie nach Stichworten suchen. Mittels Scope können Sie die Suche auf ein oder mehrere Help Plug-ins eingrenzen.

![](./img/image25.png)  
<span class="img-caption" markdown=1>
*Abbildung: Suche in der Hilfe*
</span>

In Wizards, die die ?-Ikone anbieten, können sie die kontextsensitive Hilfe öffnen. Diese führt Sie direkt zu dem jeweiligen Hilfeinhalt, den es für den Wizard gibt.

![](./img/image10.png)  
<span class="img-caption" markdown=1>
*Abbildung: Weiterführende Hilfen und Dokumentationen*
</span>

Sie können so genannte Active Links in einer Hilfeseite klicken, um aus der Hilfe heraus ein Eclipse-UI zu öffnen. Sie erkennen Active Links an der grünen Ikone mit dem weißen Pfeil.

![](./img/image29.png)  
<span class="img-caption" markdown=1>
*Abbildung: Darstellung der Navigationspfade*
</span>

Der identische Hilfeinhalt, wie er Ihnen im ADT Client zur Verfügung steht, ist auch online auf dem [SAP Help Portal](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4b190c90ceba4d02a99e0a2286b89358.html) verfügbar.

## Refactoring von Code mit ADT

Wie bereits im Kapitel 2 - Motivation für ADT kurz erwähnt, ermöglichen die zahlreichen Funktionen in ADT auch das Refactoring von Code. Doch was ist [Refactoring](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/b2ffd9b6ac5c41d2b0cda4858d4a6c9b.html), welche Vorteile bietet es und welche Funktionen werden hierfür von ADT bereitgestellt? Diese Fragen sollen im folgenden Abschnitt detailliert beantwortet werden.

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

Die ADT bieten über die Quick Assists (**STRG+1**) folgende Refactorings an:

1. Rename Identifier -- Umbenennung innerhalb eines Codeblocks oder global
2. Extract Method -- Extrahieren einer Methode aus dem Source-Code oder aus einem Ausdruck
3. Extract Constants -- Textliterale in Konstanten umwandeln
4. Extract Variables -- Variablen extrahieren und konvertieren
5. Move Member -- Attribute von Klassen verändern und bewegen
6. Exception Handling -- Automatisiertes Anlegen/Transformieren von Exception-Blöcken

Insbesondere die Rename- und die Extract-Method-Funktion unterstützen den Entwickler dabei, den Code sauber zu halten und Code-Redundanzen zu vermeiden bzw. zu reduzieren.

Da z. B. die Rename-Funktion Identifier nicht nur innerhalb der Einheit, sondern über alle Verwender hinweg behandelt, ist es nun ein Leichtes, einen unpassend gewählten Namen in einen besser zum Gesamtkontext passenden Namen zu ändern. Dabei wird nicht das Risiko eingegangen, dass Verwender vergessen und so Fehler im Code eingebaut werden.

Die Extract-Funktion analysiert den markierten Code, bietet Hilfestellung bei der Parametervergabe und ersetzt die Stelle des Codes mit dem Aufruf der neu erstellten Methode. Wenn die zu extrahierende Methode mit einem Kommentar versehen ist, wird dieser als Vorschlag für die Benennung der Methode herangezogen.

Weiterhin empfehlen die Autoren die Verwendung des Plug-ins [ABAP Quick Fix](https://marketplace.eclipse.org/content/abap-quick-fix) von Lukasz Pegiel, welches im Kapitel 7 - Plug-ins beschrieben wird. Generell bieten die mittels Quick Fixes bereitgestellten Refactoring Tools in ADT sowohl bei der Erstellung als auch bei der Überarbeitung von bestehendem Code eine enorme Hilfe. Die Nutzung dieses hilfreichen Plug-ins verbessert auf diese Weise einerseits den aktuell bearbeiteten Code, hilft aber auch bei der Erstellung von neuem Code, die neueren Sprachkonstrukte selbst anzuwenden, falls man darin noch wenig geübt ist.

## Versionsverwaltung und Vergleichen

Hinter dem Kontextmenüpunkt "[Compare with](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/3fbf95542e784e4d9e01ce75386b642b.html)" verstecken sich einige der wichtigsten Features für die tägliche Arbeit. Diese funktionieren bei allen Quelltexteditoren in den ADT, nicht nur bei der Entwicklung von ABAP-Code.

![](./img/image27.png)  
<span class="img-caption" markdown=1>
*Abbildung: Kontextmenü zum Vergleichen von Versionen*
</span>

### Local History -- Die lokale Versionsverwaltung

Die Local History ermöglicht den Zugriff auf ältere Versionen des aktuellen Quelltextdokuments aus dem Eclipse Workspace, mit dem der Benutzer gerade arbeitet. Mit jedem Speichern des Objektes wird eine Version gezogen. Das bedeutet, dass man sehr komfortabel seine eigene Arbeit im Laufe der Stunden und Tage nachverfolgen und ohne Weiteres auch wieder auf ältere Versionen zurückwechseln kann.

Da sich die lokale Versionshistorie nur auf den eigenen Eclipse Workspace bezieht, kann es passieren, dass man Änderungen auch auf einem anderen Gerät hat oder ein Kollege zuletzt Änderungen durchgeführt hat.

### Revision History -- Die Versionsverwaltung des ABAP

Unter dem Menüpunkt Revision History erreicht man die "normale" Quelltextverwaltung des ABAP-Servers, die auch schon in der SAP GUI zur Verfügung stand. Hier werden standardmäßig Versionen gezogen, wenn ein Transportauftrag freigegeben wird.

Die Versionen der Revision History sind entsprechend global für alle User zugänglich, unabhängig vom Workspace der Eclipse-Installation.

### Anderer Projektname -- Systemübergreifend vergleichen

Wenn man sich ein Projekt aus der Liste rauspickt, kann man systemübergreifend vergleichen. Das kann ein System aus der gleichen Systemlandschaft sein, z. B. das Produktivsystem oder auch ein ganz anderes System. Somit kann aus ADT heraus Code von unterschiedlichen Systemen miteinander verglichen werden, die keine RFC-Verbindung zueinander haben. Dies bietet in komplexen Systemlandschaften einen großen Vorteil gegenüber den GUI-basierten Vergleichsmöglichkeiten.

### Comparison View

In der Comparsion View kann man links den aktuellen Stand des Quelltextes sehen und rechts die zum Vergleich ausgewählte Version. Die Abweichungen werden hervorgehoben:

- Grün sind die Dinge, die in der aktuellen Version neu sind
- Rot sind die Dinge, die gelöscht wurden und in
- Grau sind die Änderungen hinterlegt

Mit den Buttons <span class="inline-img">![](./img/image103.png)</span> kann der alte Zustand durch Kopieren von rechts nach links wiederhergestellt werden. Es ist aber auch möglich, dass man direkt in dieser Vergleichs-View auf der linken Seite Änderungen durchführt. Nach dem Speichern wird der Vergleich wiederholt.

![](./img/image14.png)  
<span class="img-caption" markdown=1>
*Abbildung: Comparison View* -- *Vergleich von zwei Versionen*
</span>

Wenn man eine alte Version vollständig übernehmen will, kann man aus dem Kontextmenü mittels *Replace With → Local History* direkt die passende Version auswählen.

![](./img/image50.png)  
<span class="img-caption" markdown=1>
*Abbildung: Kontextmenü zum kompletten Übernehmen einer Version aus der lokalen Versionsverwaltung*
</span>

## Dokumentation mit den ABAP Doc

### Was sind ABAP Doc?

[ABAP Doc](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/a7b235922f6944bbaf3b36949e500b12.html) ermöglicht die Code-basierte Dokumentation wie z. B. von Methoden und deren Parametern.

![](./img/image73.png)  
<span class="img-caption" markdown=1>
*Abbildung: ABAP-Doc Dokumentation der Methode*
</span>

ABAP Doc ist ein Feature, das nur in den ADT unterstützt wird. Anstatt des formularbasierten Editors mit der Möglichkeit der Kurzbeschreibung von Methoden, der in den ADT nicht mehr verfügbar ist, wurde mit den ABAP Docs ein deutlich mächtigerer Ersatz etabliert, der in ähnlicher Form auch in anderen Programmiersprachen verfügbar ist (z. B. JavaDoc).

Im Folgenden wird für die bessere Lesbarkeit des Texts detailliert auf den Einsatz der ABAP Docs im Kontext von Klassen/Methoden eingegangen. Die ABAP Docs sind aber auch auf andere Entwicklungartefakte wie z. B. Funktionsbausteine anwendbar (s. SAP-Hilfe).

Mit Hilfe der ABAP-Doc-Funktion können für Klassen und deren Methoden textuelle Beschreibungen erfasst werden. Des Weiteren können auch für die einzelnen Parameter und Ausnahmen Beschreibungen in ABAP Doc hinterlegt werden.

Die mit ABAP Doc zu erstellenden Hinweise werden im Bereich der Definition angelegt. Der Mehrwert entsteht aber vor allem durch den einfachen Aufruf dieser Dokumentation durch den Verwender. Dies ist sowohl an der Aufrufstelle als auch im Bereich der Implementierung von Entwicklungsartefakten mittels der Taste F2 möglich. Zusätzlich können die in ABAP Docs erstellten Texte sogar mittels HTML-Tags formatiert werden. So können die Dokumentationen mit Überschriften oder Textformatierungen angereichert und somit noch ansprechender und strukturierter dargestellt werden.

Um in ABAP Doc erstellte Beschreibungen in die SAP-GUI-angezeigten Kurztexte zu übernehmen, wird das "[Syncronized](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/8327c3ff3fcb424584636bbc33211d53.html)" Tag verwendet, so dass auch bei Betrachtung mittels SE24/SE80 die Überschriften sichtbar sind.

Dies kann sinnvoll sein, falls Objekte Enhancements enthalten, die nicht direkt in ADT editiert

werden können und darum die Modifikation noch in den GUI-basierten Tools erfolgen muss.

Eine Mischung von ABAP Doc und GUI-Kurztexten empfehlen wir nicht. Die Nutzung von ABAP Doc ist das Mittel der Wahl, um den funktionalen Code von Kommentaren zu entlasten und dem Verwender hilfreiche Hinweise zu den Entwicklungsartefakten zu geben.

### Nutzung der Quick Fixes zur Erstellung von ABAP Doc

Die Erstellung der ABAP Doc ist über den Aufruf der Quick Fixes einfach. Dazu markiert man die Methodendefinition, ruft die Quick Fixes auf und wählt "Add ABAP Doc" aus. Wurde eine Methodendefinition geändert, z. B. indem ein Parameter ergänzt wurde, und es ist eine Aktualisierung der Dokumentation erforderlich, kann die ABAP Doc aktualisiert werden, indem hier nicht die Methodensignatur, sondern der ABAP-Doc-Bereich direkt markiert wird und damit die Quick Fixes aufgerufen werden.

### Weitergehende Informationen zu ABAP Doc

Weitergehende Informationen zu ABAP Doc finden sich in der offiziellen SAP-Hilfe (z. B.)

unter [ABAP Doc - ABAP-Schlüsselwortdokumentation (sap.com)](https://help.sap.com/doc/abapdocu_750_index_htm/7.50/de-de/abendoccomment.htm) (7.50), in der Beispielklasse CL_DEMO_ABAP_DOC und im [User-Guide](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/a7b235922f6944bbaf3b36949e500b12.html).

## Ausführen von Source-Code

Auch in den ADT kann geöffneter Source-Code weiterhin komfortabel ausgeführt werden. Über F8 wird eine SAP-GUI-Instanz des jeweiligen Systems initialisiert und das geöffnete Entwicklungsobjekt ausgeführt. Bei Klassen entspricht dies beispielsweise der Funktion "Testen Klasse X", bei Reports wird normal der Report ausgeführt.

![In Eclipse ausgeführte Klasse](./img/image46.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ausführung einer Klasse in SAP GUI*
</span>

![](./img/image1.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ergebnis der Ausführung*
</span>

Soll ein beliebiges Entwicklungsobjekt ausgeführt werden, so kann mit **ALT+F8** ein Objekt über den Object Finder gesucht werden. Dabei kann ein beliebiges Projekt ausgewählt werden, d. h. ein an ADT angebundenes SAP-System. Dies muss nicht das System sein, in dem gerade entwickelt wird -- es kann auch ein Qualitätssicherungssystem sein. Wichtig ist hierbei, dass die ADT-Funktionen für dieses System freigeschaltet sind bzw. die entsprechenden Berechtigungen existieren.

![](./img/image21.png)  
<span class="img-caption" markdown=1>
*Abbildung: Auswahl des Projekts*
</span>

Über den Menüpunkt "Run → Run History" stehen zusätzlich Informationen über bereits ausgeführte Objekte zur Verfügung, so dass deren Ausführung komfortabel wiederholt werden kann.

Klassen, die das Interface if_oo_adt_classrun implementieren, können ebenfalls direkt über F9 als [Konsolen-Applikation](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/520a4e84024b4a96b3793775bf9e6844.html) ausgeführt werden und erzeugen somit Output in der Konsole.

Reports, die eine Write-Ausgabe erzeugen, können über F9 ausgeführt werden. Die WRITE-Ausgabe wird dann ebenfalls in die Konsole umgeleitet.

![](./img/image16.png)  
<span class="img-caption" markdown=1>
*Abbildung: Ausgabe in die Console*
</span>

## Data Preview

Die View [Data Preview](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/2fd1241b187b4d6c989e1ff8b1f00ba1.html) kann man nutzen, um sich Daten von Datenbanktabellen und (CDS-)Views anzeigen zu lassen. Die View öffnet sich, indem man entweder im Project Explorer ein entsprechendes Objekt markiert und den Shortcut **F8** drückt, oder das Kontextmenü nutzt.

![](./img/image61.png)  
<span class="img-caption" markdown=1>
*Abbildung: Starten des Data Preview über die Tabelle*
</span>

Der Shortcut **F8** funktioniert auch, wenn man ein entsprechendes Objekt geöffnet hat und der Fokus auf dem Objekt liegt.

Die View führt beim Öffnen unverzüglich die Datenselektion aus und listet dann die selektierten Daten in Tabellenform auf. Zusätzlich zeigt sie die Anzahl der selektierten Zeilen und die benötigte Zeit dafür an.

![](./img/image33.png)  
<span class="img-caption" markdown=1>
*Abbildung: Anzeige des Data Preview*
</span>

Man hat in der View diverse Möglichkeiten, die Selektion anzupassen. Dazu zählen:

- Anzahl der selektierten Zeilen
- Selektierte Spalten
- Filterkriterien
- Sortierung (Anklicken der Spaltenüberschrift)

Außerdem kann man nach einem Muster in den angezeigten Daten suchen (inkl. ? und \* als Joker-Zeichen). Passende Daten werden dann farbig und fett hervorgehoben. Darüber hinaus können die Gesamtanzahl der betroffenen Einträge und ein Log über ausgeführte Aktionen eingesehen werden. Über den Speichern-Button kann man die angezeigten Werte in unterschiedlichen Formaten innerhalb einer Datei speichern. Es ist sogar möglich, ein ABAP Value Statement dadurch zu generieren, was sehr nützlich zur Erstellung von Testdaten sein kann.

Bei [CDS-Views mit Associations](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/d70c7d8e6e81438e836c96f1aa61a259.html) ist es möglich, den Associations zu folgen und somit die verknüpften Daten anzuzeigen. Dazu markiert man einen der Datensätze und wählt oben über den Pfeil die gewünschte Association aus.

![](./img/image28.png)  
<span class="img-caption" markdown=1>
*Abbildung: Navigation über Assoziationen*
</span>

Ein Highlight des Data Preview Views ist die [SQL Console](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/c672ec1c94964bb8837075f4f4ecea66.html). Anhand der selektierten Spalten, angegebenen Filtern und der Sortierung wird ein SQL Select Statement generiert, welches dann zur Selektion der Daten verwendet wird.

![](./img/image26.png)  
<span class="img-caption" markdown=1>
*Abbildung: SQL Console*
</span>

Dieses SQL Statement kann man individuell anpassen, prüfen und ausführen. Dabei gelten folgende Regeln und Einschränkungen:

- Es sind nur SELECT Statements gemäß ABAP Open SQL Syntax erlaubt.
- Es ist möglich, Aggregationen und komplexe Selektionen, wie z. B. mit JOIN und UNION, zu erstellen.
- Es sind nur lesende Zugriffe möglich (keine SQL Statements mit Datenänderung)
- Schlüsselwörter mit Bezug zu internen Tabellen können nicht verwendet werden

Man kann die SQL Console auch direkt aufrufen, indem man im Project Explorer das Kontextmenü für das ABAP Projekt öffnet und den Menüpunkt SQL Console auswählt. Der View zeigt das zuletzt verwendete SQL Statement an und führt es unverzüglich aus.

Alles in allem ist die SQL Console ein mächtiges Tool, mit dem man unkompliziert Selektionen ausführen, Daten auswerten oder Anpassungen an Selects testen kann.

Details zum Data Preview sind in der Eclipse-Hilfe für ADT zu finden.

## Core Data Services

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

![](./img/image79.png)  
<span class="img-caption" markdown=1>
*Abbildung: Objekttypen der CDS in der Navigation*
</span>

Die Quelltext Editoren für die unterschiedlichen Dateitypen der Core Data Services verhalten sich weitgehend wie der Quelltexteditor für ABAP-Code. Unter anderem sind folgende Features enthalten:

- Code Completion (**STRG+SPACE**) - Vorschlagswerte, die im Kontext passen.
- Element Info (**F2**) - Informationen über das Element, auf dem der Cursor steht.
- Pretty Printer (**SHIFT+F1**)

Ein Unterschied sind die Farben, die im Editor verwendet werden.

Ein Grundproblem bei den Core Data Services ist, dass die Eigenschaften eines Objektes (z. B. einer CDS View Entity) aus mehreren Dateien und den Eigenschaften der Datenquellen zusammengesetzt sind.. Diese Dateien erklären jeweils ihre Zugehörigkeit, und die Datenquellen propagieren ihre Feldeigenschaften (Annotationen). Das ist für das Erweiterungskonzept sehr praktisch. Aber die Transparenz leidet darunter, denn die Dateien liegen nicht notwendigerweise im gleichen Entwicklungspaket.

![](./img/image83.png)  
<span class="img-caption" markdown=1>
*Abbildung: Unterschiedliche Dateien legen die Eigenschaften einer CDS View Entity fest*
</span>

Um ein vollständiges Bild eines CDS-Objektes unter Berücksichtigung aller Dateien und Propagationen zu bekommen, sind darum Hilfsmittel notwendig. Dazu gehören:

- Element Info
- Dependency Analyzer
- Active Annotations

### Element Info für CDS

Mit **F2**oder der separaten [Element Info View](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/c2ffbc2fee0c4ceda3bb89bd843ee419.html) bekommen Sie für einen CDS View eine gute Übersicht über die Datenstruktur und Assoziationen, unabhängig davon, wo diese definiert wurden. Außerdem werden alle relevanten Erweiterungsdateien angezeigt.

![](./img/image94.png)  
<span class="img-caption" markdown=1>
*Abbildung: Übersicht über ein CDS View Entity mit Hilfe von Element Info*
</span>

### Dependency Analyzer

Der [Dependency Analyzer](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/bedc1723e35244e188c5a44a5f4f8340.html) bietet eine gute Übersicht über die Herkunft der Daten. Er wird über das Kontextmenü aufgerufen..

![](./img/image30.png)  
<span class="img-caption" markdown=1>
*Abbildung: Aufruf des Dependency Analyzers über das Kontextmenü*
</span>

Der Dependency Analyzer hat drei Tab-Reiter, die Informationen über eine View anzeigen:

- Der **SQL Dependency Tree** zeigt die hierarchische Struktur in Tabellenform an

![](./img/image53.png)  
<span class="img-caption" markdown=1>
*Abbildung: SQL Dependency Tree*
</span>

- Der **SQL Dependency Graph** zeigt die gleichen Informationen grafisch an.

![](./img/image13.png)  
<span class="img-caption" markdown=1>
*Abbildung: SQL Dependency Graph*
</span>

- Der Tab-Reiter **Complexity Metrics** zeigt zusätzliche Informationen zur Gesamtkomplexität des CDS Views an, inklusive aller Quell-Views.\
    > Gerade bei Performance-Problemen lohnt hier ein Blick.

![](./img/image5.png)  
<span class="img-caption" markdown=1>
*Abbildung: Complexity Metrics*
</span>

### Active Annotations

Die [View Active Annotations](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/45ba68d3b4924a97ad2dc598e756968e.html) wird ebenfalls über das Kontextmenü in der Navigation aufgerufen. In ihr werden die Werte sämtlicher aktiven Annotationen der Views angezeigt:

- Auf **View-Ebene** sind nur genau die Annotationen sichtbar, die in dem View definiert wurden.
- Auf **Feld-Ebene** sind alle gültigen Annotationen sichtbar. Ihre Herkunft, wie beispielsweise Datenelement, Metadata-Extension oder Datenquelle, wird ebenfalls mit angezeigt.
- Auf **Parameter-Ebene**

Manche Eigenschaften, z. B. Feldtexte, können schon durch die Datenelemente festgelegt und diese dann in die View propagiert werden. Dies ist in folgender Abbildung beispielhaft dargestellt:

![](./img/image39.png)  
<span class="img-caption" markdown=1>
*Abbildung: Aktive Annotationen eines Views*
</span>
