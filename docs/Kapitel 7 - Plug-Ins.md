---
layout: page
title: Kapitel 7 - Plug-ins
permalink: /kapitel7/
nav_order: 7
---

# Kapitel 7 - Plug-ins


1. TOC
{:toc} 

# Einführung

Eclipse ist eine integrierte Entwicklungsumgebung (IDE), die im Kern aus vielen kleinen Einheiten -- sog. Plug-ins -- besteht. Wenn man beispielhaft die Eclipse-Varianten Eclipse IDE for Java Developers oder Eclipse IDE for C/C++ Developers betrachtet, dann sind diese vorkonfigurierten Pakete nur Sammlungen von Plug-ins, die für einen bestimmten Zweck entwickelt worden sind.

Die ABAP Development Tools (ADT) sind kategorisch genau das Gleiche, also eine Sammlung von Plug-ins, und stellen somit ABAP-Entwicklern ein modernes Entwicklungswerkzeug zur Verfügung. Eben genau dieser modulare Aufbau ermöglicht es jetzt jedem Entwickler, eigene Plug-ins zu erstellen, um Eclipse und/oder ADT weiter anzupassen und dadurch z. B. wiederkehrende Aufgaben zu vereinfachen oder Funktionen bereitzustellen, die durch die ADT nicht angeboten werden und nur in der ABAP Workbench zu finden sind.

Solche Plug-ins können aus reinem UI-Code bestehen, wie z. B. das ABAP Favorites Plug-in, welches Funktionen des Easy-Access-Menü (SAP GUI) nach Eclipse bringt. Sie können jedoch auch umfangreicher sein und extra ABAP-Code auf dem SAP-System benötigen. Ein Beispiel dafür ist das ABAP Code Search Plug-in, das vergleichbar ist mit der SAP-GUI-Transaktion CODE_SCANNER.

# Nützliche Open-Source-Plug-ins

## Open Editors 

Bietet eine neue View, die alle geöffneten Editoren in Eclipse anzeigt. Diese View bietet auch die Möglichkeit, die Sortierreihenfolge der Editoren anzupassen.

![](./Kapitel 7 - Plug-ins/media/image1.png)

*Abbildung: Dialog zur Anpassung der Sortierreihenfolge von geöffneten Editoren*

Voraussetzungen Eclipse:

-   Eclipse IDE for Java Developers

Links:

-   Source-Code auf [GitHub](https://github.com/dbickley/OpenEditors)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/open-editors)

## AnyEdit Tools

Bietet viele Möglichkeiten zum Editieren von Text/Quellcode:

-   Umwandlung von Text in Klein-/Großbuchstaben

-   Umwandlung von Text von Pascal- zu Camel-Schreibweise

-   Sortierung der selektierten Zeilen (alphabetisch, numerisch, nach Zeilenlänge)

-   ...

Zusätzlich bietet das Plug-in auch viele Möglichkeiten zum Vergleichen von Text.

-   Vergleich eines Editors mit Text in der Zwischenablage

-   Vergleich eines Editors mit einem beliebigen anderen Editor

-   Vergleich eines Editors mit einer externen Datei

Alle möglichen Operationen stehen über das Kontextmenü eines Editors zur Verfügung.

![](./Kapitel 7 - Plug-ins/media/image4.png)

*Abbildung: Beispiele für verfügbare Operationen im Kontextmenü*

Voraussetzungen Eclipse:

-   Eclipse IDE for Java Developers

Links

-   Source-Code auf [GitHub](https://github.com/iloveeclipse/anyedittools)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/anyedit-tools)

## PDE Tools 

Dieses Plug-in erweitert Eclipse um nützliche Tools für Plug-in-Entwickler:

-   Vorschau von Icon-Dateien direkt im Project Explorer

-   Generierung von Java-Konstanten für Icon-Ordner

-   Screenshot-Tool für UI-Elemente im Eclipse Workbench

Es gibt jedoch Features, die auch außerhalb der Plug-in-Entwicklung hilfreich sind:

-   Erweiterte Historie der Zwischenablage

-   Direkter Start eines neuen Eclipse-Fensters mit einem bestimmten Workspace

![](./Kapitel 7 - Plug-ins/media/image7.png)

*Abbildung: Historie für Zwischenablage (Tastenkürzel Strg+Shift+V)*

Links:

-   Source-Code auf [GitHub](https://github.com/jeeeyul/pde-tools)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/pde-tools)

# Nützliche Open Source ADT Plugins

## ABAP Favorites

Das ABAP Favorites Plug-in wurde entwickelt, um die Funktionalität des SAP GUI User Menu abzubilden. In diesem Menü kann jeder Benutzer Transaktionen, Reports oder URLs seinen Favoriten hinzufügen und diese nach seinen persönlichen Vorlieben strukturieren.

Die Plug-in-Installation bringt mit Favorites und Favorite DevObjects zwei neue Views, verfügbar über Windows → Show View → Others. Beide Views bieten eine gefilterte Baumansicht, in der die favorisierten Objekte verwaltet werden können.

Der Unterschied der beiden Views liegt in den Möglichkeiten zur Erstellung der Ordner (Container). Die Favorites View ermöglicht zwei Arten dieser Ordner: "Standard" für Transaktionen, Reports und URL und "DevObject" zur Verwaltung von Entwicklungsobjekten wie Klassen, Funktionsbausteinen, CDS Views usw. Im Falle der Favorite DevObjects können ausschließlich "DevObject"-Ordner erstellt werden. Die Aufteilung dieser Views ermöglicht dem Verwender zu wählen, ob er alle Ordner vermischt oder gemäß der beschriebenen Trennung verwalten möchte.

Vergleicht man den "Standard"- mit dem "DevObject"-Ordner liegt neben den auswählbaren Objekttypen der größte Unterschied darin, dass bei "Standard" durch einen Doppelklick die Objekte ausgeführt werden. Ein Doppelklick in einem "DevObject"-Ordner bewirkt das Öffnen des ausgewählten Objekts.

![](./Kapitel 7 - Plug-ins/media/image5.png)

*Abbildung: ABAP Favorites View*

Um neue Objekte den Favoriten hinzuzufügen, können die Kontextmenüs der Favorites View, des ABAP Editors oder des Project Explorers genutzt werden.

![](./Kapitel 7 - Plug-ins/media/image8.png)

*Abbildung: Kontextmenü eines Ordners im ABAP Favorites View*

Voraussetzungen:

-   Eclipse IDE for Java Developers

-   ADT

Links:

-   Source-Code auf [GitHub](https://github.com/fidley/ABAPFavorites)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-favorites)

## ABAP Continuous Integration

AbapCI ist ein Open Source Eclipse Plug-in, das verschiedene Continuous Integration (CI) Tools für die ABAP-Entwicklung mit Eclipse bereitstellt. Das Plug-in basiert auf den CI-Funktionen von ADT.

Das Plug-in stellt folgende Funktionen bereit:

-   Automatische Unit-Testläufe

-   Automatische ATC-Läufe

-   Visualisierung des Quellcode-Status auf der Benutzeroberfläche

-   Unterschiedliche Farbgebung für jedes ABAP-Projekt

-   Automatische Quellcode-Formatierung

-   Shortcut für abapGit

-   Auslösen von Jenkins aus Eclipse (experimentell)

![](./Kapitel 7 - Plug-ins/media/image10.png)

*Abbildung: Farbige Hervorhebung der Statusleiste pro Projekt + Teststatus*

![](./Kapitel 7 - Plug-ins/media/image29.png)

*Abbildung: Verwaltung von Paketen, für die Unittests und/oder ATC-Prüfläufe eingeplant sind*

Weitere Informationen können im GitHub Repository nachgelesen werden.

Voraussetzungen:

-   Eclipse IDE for Java Developers ( \<= 2022-06, Installation mit neueren Versionen aktuell nur mit Workaround möglich; siehe [Issue](https://github.com/andau/abapCI/issues/34) auf GitHub)

-   ADT

Links:

-   Source-Code auf [GitHub](https://github.com/andau/abapCI)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-continuous-integration)

## 

## ABAP ADT Extensions

Dieses Plug-in erweitert die ADT um mehrere zusätzliche Funktionalitäten.

### Automatisches Einloggen in SAP-Systeme

Die Funktionalität "Automatisches Einloggen" ermöglicht dem Entwickler, seine Benutzer/Passwort-Kombinationen innerhalb des Secure Storage von Java zu verwalten. Sicherheitstechnisch sollten diese verschlüsselt werden.

![](./Kapitel 7 - Plug-ins/media/image9.png)

*Abbildung: View zur Verwaltung der hinterlegten Zugangsdaten von ABAP Systemen*

Abhängig von den Einstellungen des Plug-in kann man sich in jedes der ausgewählten On-Premise-SAP-Systeme, die mittels ABAP/BW-Projekten abgebildet sind, automatisch einloggen lassen. Die Passwörter können bei der Erstellung des Projekts oder erst später über die Passwort-View gepflegt werden.

### Verändern von ABAP-Projekt-Attributen

Durch das Kontextmenü des Project Explorers können für ABAP/BW-Projekte die Projektattribute (Client, User, Sprache) geändert werden. Zudem können die Breakpoint-User gesetzt werden.

![](./Kapitel 7 - Plug-ins/media/image27.png)

*Abbildung: Kontextmenü auf Projekt im Project Explorer*

### Eingabefeld zur Ausführung von Transaktions-Codes

Nach der Installation erscheint in Eclipse im unteren rechten Bereich eine Toolbar mit einem Eingabefeld für Transaktions-Codes. Das Feld kann per Maus oder über den Shortcut **Shift+F8** bedient werden. Nach der Eingabe des Codes und dem Bestätigen per Enter wird die Transaktion im momentan aktiven Projekt ausgeführt.

![](./Kapitel 7 - Plug-ins/media/image20.png)

*Abbildung: Statusleiste im Eclipse-Fenster*

Voraussetzungen:

-   Eclipse IDE for Java Developers

-   ADT

Links:

-   Source-Code auf [GitHub](https://github.com/fidley/ABAP-Project-Extensions)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-adt-extensions)

## ADT Classic Outline

Dieses Plug-in fügt Ihrer Oberfläche eine neue View namens "Classic Outline" hinzu, die gewissermaßen die SE80-Objektliste abbildet. In den meisten Fällen kann diese Ansicht die eingebaute ADT Outline ersetzen. Die angezeigte Objektliste kann gefiltert werden und erlaubt die Ansicht der Objektattribute, ähnlich der eingebauten ADT Outline. Durch einen Doppelklick (bzw. einfachen Klick abhängig von den Einstellungen) kann in das selektierte Objekt navigiert werden.

![](./Kapitel 7 - Plug-ins/media/image13.png)

*Abbildung: Classic Outline View*

Voraussetzungen:

-   Eclipse IDE for Java Developers

-   ADT

Voraussetzungen ABAP:

-   SAP NetWeaver 7.40 SP08 oder neuer

-   abapGit repository [ADT Classic Outline Backend](https://github.com/fidley/ADT-Classic-Outline-Backend.git) muss installiert sein

Links:

-   Source-Code auf GitHub: [Frontend](https://github.com/fidley/ADT-Classic-Outline-Frontend) und [Backend](https://github.com/fidley/ADT-Classic-Outline-Backend)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/adt-classic-outline)

## 

## ABAP Quick Fix 

Quick Fixes sind Teil der Eclipse IDE. Im ADT-Standard werden sie im Backend-System verarbeitet und können vom Nutzer bei Bedarf mittels Shortcut **CTRL+1** verwendet werden. Das ABAP Quick Fix Plug-in bietet zusätzliche Quick Fixes, die direkt von der Eclipse-Umgebung prozessiert werden.

![](./Kapitel 7 - Plug-ins/media/image17.png)

*Abbildung: ABAP Code vor Quick-Fix-Ausführung*

![](./Kapitel 7 - Plug-ins/media/image21.png)

*Abbildung: ABAP Code nach Quick-Fix-Ausführung*

Einen Auszug der verfügbaren Features finden Sie in der folgenden Liste:

-   Ersetze READ TABLE durch ASSIGN, REF#, Table Expression oder line_exists.

-   Ersetze CALL METHOD durch den direkten Aufruf.

-   Ersetze MOVE durch die direkte Zuweisung.

-   Ändere APPEND TO in APPEND VALUE#( ) TO.

-   Ersetze CREATE OBJECT durch NEW.

-   Entferne "full line comments" vom Statement.

-   Unterlasse die Selbstreferenz ME-\>.

-   Ersetze die Operatoren EQ, NE, GT, GE, LT, LE mit =, \<\>, \>, \>=, \<, \<=

-   Rücke Operatoren im markierten Bereich entsprechend ein.

-   Rücke TYPE und LIKE im Deklarationsblock der Variablen entsprechen ein.

Voraussetzungen:

-   Eclipse IDE for Java Developers

-   ADT

Links:

-   Source-Code auf [GitHub](https://github.com/fidley/ABAPQuickFix)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-quick-fix)

## 

## ABAPQuickFixS4Conversion

Dieses Plug-in ist ein sehr schönes Beispiel für die Zusammenarbeit von Entwicklern innerhalb der Community. ABAPQuickFixS4Conversion ist eine Erweiterung des ABAP Quick Fix Plug-in von SAP und ergänzt dieses um folgende Funktionalitäten:

-   Konvertiere SELECT SINGLE nach SELECT ... UP TO 1 ROWS ... ORDER BY

-   Passe für jede beliebige Tabelle die custom ORDER BY-Liste an

-   Ändere SELECT SINGLE auf den modernen SQL-Stil

-   Konvertiere SELECT/ENDSELECT in den modernen SQL-Stil

-   Transformiere MOVE_CORRESPONDING nach CORRESPONDING #( )

![](./Kapitel 7 - Plug-ins/media/image25.png)

*Abbildung: Beispiel für Quick-Fix-Verfügbarkeit bei einer SELECT-Anweisung*

![](./Kapitel 7 - Plug-ins/media/image24.png)

*Abbildung: SELECT-Anweisung nach Anwendung des Quick Fix*

Voraussetzungen:

-   Eclipse IDE for Java Developers

-   ADT

-   ABAP Quick Fixes plugin

Links:

-   Source-Code auf [GitHub](https://github.com/lc-leuc/ABAPQuickFixS4Conversion)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-quickfix-s4-conversion)

## 

## ABAP Tags

Das ABAP Tags Plug-in ermöglicht es, Tags zu erstellen, welche dann zu beliebigen Entwicklungsobjekten hinzugefügt werden können. Die Tags und deren zugeordneten Objekte werden dabei auf dem jeweiligen ABAP-System persistiert. Dies erleichtert den Zugriff auf getaggte Objekte durch andere Benutzer. Generell erlaubt das Plug-in, Tags entweder im globalen oder im benutzerspezifischen Geltungsbereich anzulegen. Benutzerspezifische Tags können dabei auch mit anderen geteilt werden und dadurch die Zusammenarbeit erleichtern.

![](./Kapitel 7 - Plug-ins/media/image28.png)

*Abbildung: View "Tag Manager"*

Das Taggen von Objekten ist intuitiv über das Kontextmenü aus dem Editor oder dem Project Explorer heraus möglich. Die getaggten Objekte können dann entweder aus dem View "Tag Manager" mittels Kontextmenü-Aktion, oder über die in den "Search"-Dialog integrierten "ABAP Tagged Object Search" gesucht und angezeigt werden.

![](./Kapitel 7 - Plug-ins/media/image32.png)

*Abbildung: Search-Dialog mit Seite "ABAP Object Search"*

Voraussetzungen Eclipse:

-   Eclipse Platform Runtime oder Eclipse IDE for Java Developers

-   ADT

Voraussetzungen ABAP:

-   SAP NetWeaver 7.40 SP08 oder neuer

-   abapGit repository [abap-tags-backend](https://github.com/stockbal/abap-tags-backend) muss installiert sein

Links:

-   Source-Code auf [GitHub](https://github.com/stockbal/abap-tags-ui)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-tags) (Marketplace Client muss installiert sein)

## 

## ABAP Search and Analysis Tools

Dieses Plug-in erweitert die ADT um weitere Such- und Analysefunktionen für die folgenden Objekttypen:

-   Klasse/Interface

-   Datenbanktabelle/-view

-   CDS View

Die Suchfunktionen sind in den Eclipse-Search-Dialog integriert (**Strg+H**). Die Bedienung ist dabei ähnlich wie beim Dialog "Open ABAP Development Object" (**Strg+Shift+A**). Den Objekttyp kann man mittels Dropdown ändern. Dieser steuert unter anderem die verfügbaren Filter im Feld "Search Filters".

![](./Kapitel 7 - Plug-ins/media/image31.png)

*Abbildung: Search-Dialog auf Seite "ABAP Object Search"*

Zusätzlich zu den Suchfunktionen stellt das Plug-in noch den View "CDS Analyzer" zur Verfügung, der die folgenden Analysen auf CDS Views erlaubt:

-   Top-Down

-   Auswertung auf alle verwendeten Entitäten eines CDS View

-   Verwendungsnachweis von Datenbankentitäten als Datenquelle ("*select from"* oder "*association"*)

-   Analyse auf Feldebene

    -   Top-Down (Herkunftsermittlung)

    -   Bottom-up (Verwendung eines Feldes in Feldern anderer CDS Views)

![](./Kapitel 7 - Plug-ins/media/image26.png)

*Abbildung: View "CDS Analyzer" - Top-Down-Analyse*

Voraussetzungen Eclipse:

-   Eclipse Platform Runtime oder Eclipse IDE for Java Developers

-   ADT

Voraussetzungen ABAP:

-   SAP NetWeaver 7.40 SP08 oder neuer

-   abapGit repository [abap-search-tools](https://github.com/stockbal/abap-search-tools) muss installiert sein

Links:

-   Source-Code auf [GitHub](https://github.com/stockbal/abap-search-tools-ui)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-search-and-analysis-tools) (Marketplace Client muss installiert sein)

## 

## ABAP Code Search

Dieses Plug-in bringt die bekannte SAP-GUI-Transaktion CODE_SCANNER nach Eclipse. Wie der Name schon vermuten lässt, ist die "ABAP Code Search" auch im Eclipse-Search-Dialog integriert. Neben der Verwendung von regulären Ausdrücken gibt es auch spezielle Suchmodi wie z. B. *Single Pattern mode* oder *Sequential Matching*. Weitere Merkmale der Suche sind:

-   Parallele Ausführung (optional pro Benutzer steuerbar)

-   Suche kann jederzeit gestoppt werden

-   Komplette Systemsuche möglich, da auf dem Anwendungs-Server immer nur kleine Pakete verarbeitet werden

-   Tags können zur Objektauswahl verwendet werden → erfordert Installation des ABAP Tags Plug-in

![](./Kapitel 7 - Plug-ins/media/image22.png)

*Abbildung: Search-Dialog mit "ABAP Code Search"-Seite*

Voraussetzungen Eclipse:

-   Eclipse Platform Runtime oder Eclipse IDE for Java Developers

-   ADT

Voraussetzungen ABAP:

-   SAP NetWeaver 7.40 SP08 oder neuer

-   abapGit repository [abap-code-search-tools](https://github.com/stockbal/abap-code-search-tools) muss installiert sein

Links:

-   Source-Code auf [GitHub](https://github.com/stockbal/abap-code-search-tools)

-   [Eclipse Marketplace](https://marketplace.eclipse.org/content/abap-code-search) (Marketplace Client muss installiert sein)

## 

## abapGit Eclipse Plug-in

Stellt die Funktionen der abapGit-SAP-GUI-Transaktion als Eclipse Plug-in bereit. Der volle Funktionsumfang ist aktuell (2022) jedoch nur über die SAP-GUI-Transaktion gewährleistet.

Voraussetzungen Eclipse:

-   Eclipse IDE for Java Developers

-   ADT

Voraussetzungen ABAP:

-   SAP NetWeaver 7.50 oder neuer

-   Vollständige [abapGit](https://github.com/abapGit/abapGit) Installation

-   abapGit repository [ADT_Backend](https://github.com/abapGit/ADT_Backend) muss installiert sein

Links:

-   Source-Code auf [GitHub](https://github.com/abapGit/ADT_Frontend)

-   Installation über Update-Site [https://eclipse.abapgit.org/updatesite/](https://eclipse.abapgit.org/updatesite/)

# Eigene ADT Plug-ins entwickeln

## Voraussetzungen

Da Plug-ins für Eclipse in Java zu entwickeln sind, empfiehlt es sich, dort schon einige Kenntnisse zu haben. Der notwendige Kenntnisgrad richtet sich dabei nach dem Plug-in, das man entwickeln will.

## Einrichtung der Entwicklungsumgebung

### Installation Eclipse for RCP/RAP Development

Um Plug-ins für Eclipse zu entwickeln, benötigt man eine bestimmte Variante der Eclipse-Plattform: *Eclipse IDE for RCP and RAP Developers* (RAP = Remote Application Platform). Diese Variante bietet ein vollständiges Toolset, um sowohl Plug-ins für Eclipse als auch Rich-Client-Anwendungen (RCP) auf Basis von Eclipse zu entwickeln. Sie kann direkt von [eclipse.org](https://www.eclipse.org/downloads/packages/) bezogen werden.

![](./Kapitel 7 - Plug-ins/media/image2.png)

*Abbildung: Eclipse Bundle "Eclipse IDE for RCP and RAP Developers"*

Des Weiteren wird eine Installation des Java Development Kits (JDK) benötigt. Dieses kann z. B. von den folgenden Quellen bezogen werden:

-   [https://adoptium.net/de/](https://adoptium.net/de/)

-   [https://openjdk.org/](https://openjdk.org/)

-   [https://sap.github.io/SapMachine/](https://sap.github.io/SapMachine/)

**Hinweis**: In den aktuelleren Eclipse-Versionen wird dieses bereits mitgeliefert.

#### Welche Java-Version?

Seit Eclipse v2020-09 bzw. ADT v3.16 ist Java 11 die Mindestvoraussetzung, und somit sollte auch das JDK in mindestens dieser Version installiert werden.

### Installation von ADT

Als nächsten Schritt muss ADT in Eclipse installiert werden, da sonst nicht gegen das ADT SDK entwickelt werden kann.

Um die bestmögliche Kompatibilität zu haben, empfiehlt es sich, ADT immer in der gleichen Version wie Eclipse zu installieren. Die neueste ADT-Version kann hierbei über [https://tools.hana.ondemand.com/latest](https://tools.hana.ondemand.com/latest) bezogen werden. Für ältere Versionen von ADT muss einfach das *latest* im Pfad gegen die gewünschte Eclipse-Version ausgetauscht werden (für Eclipse 2020-09 wäre es z. B.: [https://tools.hana.ondemand.com/2020-09](https://tools.hana.ondemand.com/2020-09)).

### Installation nützlicher Plug-ins (optional)

Neben der Eclipse-Installation empfiehlt es sich, noch folgende Plug-ins zu installieren:

#### Enhanced Class Decompiler 

Marketplace Link: [https://marketplace.eclipse.org/content/enhanced-class-decompiler](https://marketplace.eclipse.org/content/enhanced-class-decompiler).

Dieses Plug-in erlaubt es, kompilierten Source-Code lesbar anzuzeigen. Es ist sogar möglich, in solchen de-kompilierten Klassen Haltepunkte zu setzen und den Code zur Laufzeit zu analysieren.

#### Web Developer Tools

Marketplace Link: [https://marketplace.eclipse.org/content/eclipse-web-developer-tools-0/promo](https://marketplace.eclipse.org/content/eclipse-web-developer-tools-0/promo).

Wenn man für sein Plug-in auch eine Hilfe anbieten möchte, erweitert dieses Plug-in Eclipse um Editoren mit Syntax-Highlighting für die typischen Web-Dateiendungen (css, html etc.).

#### WindowBuilder

Marketplace Link: [https://www.eclipse.org/windowbuilder/](https://www.eclipse.org/windowbuilder/)

Das Erstellen von GUI-Elementen, wie z. B. Dialoge oder eigene Sichten, kann zeitweise sehr aufwendig sein. Der WindowBuilder kann dabei Abhilfe schaffen und erlaubt es, GUI-Elemente mit Hilfe eines grafischen Editors zu erstellen.

## Wichtige Konzepte/Artefakte

### Plug-in

Ein Plug-in wird verwendet, um Code zu einer modularen, erweiterbaren und gemeinsam nutzbaren Einheit zusammenzufassen. Die gesamte Eclipse-Anwendung besteht aus vielen solcher Plug-ins.

### Feature

Ein Feature dient zur Gruppierung von einem oder mehreren Plug-ins zu einer einzigen installierbaren und aktualisierbaren Einheit.

### Update-Site

Update-Sites werden verwendet, um Features zu organisieren und zu exportieren, damit sie in Eclipse-Anwendungen installiert werden können.

## Erstellung eines Plug-in-Projektes

Ein neues Plug-in-Projekt kann über File → New → Plug-in Project erstellt werden. Daraufhin öffnet sich der Plug-in Project Wizard:

![](./Kapitel 7 - Plug-ins/media/image6.png)

*Abbildung: Plug-in Project Wizard - Einstieg*

Hier muss zunächst ein Name für das Projekt vergeben werden. Beim Namen wird die sog. *Reverse-Naming-Domain-Notation* empfohlen (z. B. com.company.myplugin), jedoch kann hier auch jede beliebige andere Namenskonvention gewählt werden.

Standardmäßig wird ein Plug-in Projekt immer als Java-Projekt angelegt weil die meisten Plug-ins Code beisteuern. Diese Option kann jedoch auch abgewählt werden, z. B. für Plug-ins, welche nur Dokumentation bereitstellen.

Da in diesem Guide explizit auf die Plug-in-Entwicklung für Eclipse eingegangen wird, ist die *Zielplattform* immer Eclipse.

Durch den Klick auf *Next* geht es auf die nächste Seite des Wizards.

![](./Kapitel 7 - Plug-ins/media/image11.png)

*Abbildung: Plug-in Project Wizard - Inhalt*

Hier werden die Plug-in-spezifischen Eigenschaften erfasst. Für die ID wird empfohlen, den Projektnamen zu verwenden, verpflichtend ist dies jedoch nicht. Die Version muss dem Muster *major.minor.micro.qualifier* folgen. Der *.qualifier*-Teil ist dabei optional. Er wird beim Build durch einen Zeitstempel ersetzt (z. B. 1.3.0.202205011550).

Die Felder *Name* und *Vendor* sind übersetzbar und repräsentieren den Plug-in-Namen und dessen Anbieter.

Beim *Execution Environment* ist die minimal erforderliche Java-Version einzutragen. Für die ADT Plug-ins ist aktuell Java 11 die Mindestvoraussetzung und sollte demnach auch für eigene Plug-ins gesetzt werden.

Wenn die Option *Generate an activator* gesetzt ist, wird eine *Activator*-Klasse generiert. Solch eine Klasse kann pro Plug-in genau einmal existieren und ist nur notwendig, wenn Aktivitäten beim Starten bzw. beim Stoppen des Plug-in notwendig sind. Die Option *This plug-in will make contributions to the UI* regelt die verfügbaren Templates, die auf der nächsten Seite des Wizard ausgewählt werden können.

Als letzten optionalen Schritt kann auf der nächsten Seite noch ein Template ausgewählt werden. Templates existieren zum Beispiel für das Erstellen von eigenen Views oder Editoren.

Nach Abschluss des Wizard mittels *Finish* wird das Plug-in-Projekt an der ausgewählten Stelle im Dateisystem generiert und anschließend im Eclipse Workspace angezeigt.

### Struktur eines Plug-In-Projektes

Ein Plug-in-Projekt hat immer den folgenden Aufbau. Die Datei *plugin.xml* und der Ordner *OSGI-INF* sind dabei optional und existieren nur, wenn die Notwendigkeit besteht.

![](./Kapitel 7 - Plug-ins/media/image15.png)

*Abbildung: Plug-in-Projekt im Project Explorer View*

Die wichtigsten Dateien sind *manifest.mf*, *build.properties* und *plugin.xml*. Öffnet man eine dieser drei Dateien, wird standardmäßig der Plug-in-Manifest-Editor geöffnet. Dieser Editor ermöglicht die Pflege aller Metadaten eines Plug-in, welcher der Editor in folgende Bereiche untergliedert:

-   **Overview**

> Diese Sicht dient als genereller Einstiegspunkt. Sie erlaubt die Pflege der grundlegenden Plug-in-Daten wie Name, Version etc. und den Absprung zu den anderen Sichten.

-   **Dependencies**

> Hier müssen alle Plug-ins aufgelistet werden, die in diesem Plug-in benötigt werden.

-   **Runtime**

> Dient zur Spezifikation der Java-Pakete, die für andere Plug-ins sichtbar sein sollen.
>
> Für jedes Paket kann außerdem noch ein API-Status gesetzt werden.

-   **Extensions**

> Hier erfolgt die eigentliche Erweiterung von Eclipse um z. B. neue Menüs, Commands, Views etc.

-   **Extension Points**

> Definition der Erweiterungspunkte, die dieses Plug-in für andere bereitstellt.

-   **Build**

> Konfiguration, welche Dateien im Build-Ergebnis enthalten sein sollen.

## Erstellung eines Feature-Projektes

Ein neues Feature-Projekt kann über File → New → Feature Project erstellt werden. Daraufhin öffnet sich der Feature Project Wizard:

![](./Kapitel 7 - Plug-ins/media/image19.png)

*Abbildung: Feature Project Wizard - Einstieg*

Die Eigenschaften bei einem Feature-Projekt sind ähnlich wie beim Plug-in-Projekt, und somit gelten auch die gleichen Regeln für z. B. *ID*, *Name* oder *Version*.

Nun kann der Wizard beendet werden oder man navigiert zur nächsten Seite, auf der man gleich die Plug-ins selektieren kann, die in diesem Feature enthalten sein sollen:

![](./Kapitel 7 - Plug-ins/media/image23.png)

*Abbildung: Feature Project Wizard - Plug-in-Auswahl*

Nach Abschluss wird das Feature-Projekt generiert und im Workbench angezeigt.

### Struktur eines Feature-Projekts

Ein Feature-Projekt hat eine sehr einfache Struktur. Es enthält nur die zwei Dateien *feature.xml* und *build.properties*. Wie beim Plug-in-Projekt gibt es zur Pflege der Feature-Metadaten einen eigenen Manifest-Editor, welcher sich automatisch beim Öffnen einer der beiden Dateien öffnet.

Dieser ist in die folgenden Sektionen unterteilt:

-   **Overview**

> Diese Sicht dient als genereller Einstiegspunkt. Sie erlaubt die Pflege der grundlegenden Plug-in-Daten wie Name, Version etc. und den Absprung zu den anderen Sichten.

-   **Information**

> Hier können Beschreibung, Copyright-Notice und Lizenzvereinbarung gepflegt werden.

-   **Included Plug-ins**

> Auswahl der Plug-ins, die in diesem Feature enthalten sind.

-   **Included Features**

> Features können zur Gruppierung anderer Features verwendet werden und somit können hier die enthaltenen Features gelistet werden.

-   **Dependencies**

> Normalerweise werden alle Abhängigkeiten beim Build berechnet. Dies passiert durch Analyse der Abhängigkeiten aller enthaltenen Plug-ins. Es besteht jedoch auch die Möglichkeit, die Abhängigkeiten hier manuell zu pflegen.

-   **Build**

> siehe Plug-in-Manifest

## Erstellung einer Update-Site

Ein neues Update-Site-Projekt kann über File → New → Project... → Plug-in Development →\> Update Site Project erstellt werden. Daraufhin öffnet sich der Update Site Project Wizard:

![](./Kapitel 7 - Plug-ins/media/image14.png)

*Abbildung: Update Site Wizard*

Der Wizard enthält nur eine Seite, auf der man dem Projekt einen Namen gibt und den Ablageort auswählen kann. Nach Abschluss des Wizard sollte sich im Workspace ein Ordner mit dem gewählten Projektnamen befinden. In diesem Ordner befindet sich die Manifestdatei der Update-Site, genannt *site.xml*.

Bei Doppelklick auf diese Datei öffnet sich der Manifest-Editor für die Update-Site. In diesem Editor können nun die Features hinzugefügt werden, die auf der Site veröffentlicht werden sollen. Zur besseren Übersicht sollten die Features in Kategorien unterteilt werden.

Nachdem der Inhalt der Update-Site fertig konfiguriert ist, kann diese über den Button *Build all* im Editor erstellt werden. Es ist auch möglich, nur einzelne bzw. ausgewählte Features zu erstellen.

**WICHTIG**: Bevor man nun die Update-Site erstellt, sollte man nochmal die Java-Compiler-Einstellungen über Window → Preferences → Java → Compiler prüfen. Diese sollten auf die gleiche Java-Version eingestellt sein, die bei den Plug-ins als minimale Voraussetzung definiert wurde:

![](./Kapitel 7 - Plug-ins/media/image12.png)

*Abbildung: Compiler-Einstellungen im Eclipse-Einstellungsdialog*

Wenn die Erstellung erfolgreich war, befinden sich die folgenden Dateien/Ordner im Anschluss im Projektordner der Update-Site:

-   features (enthält jar-Dateien der Features)

-   plugins (enthält jar-Dateien der Plug-ins)

-   artifacts.jar

-   content.jar

Zusätzlich kann auch noch ein Archiv mit dem Namen *logs.zip* erstellt worden sein. Dort befinden sich alle Meldungen, die während der Kompilierung aufgetreten sind.

### Testen der Update-Site

Bevor die erstellte Site nun auf einem Webserver hochgeladen wird, möchte man diese vorher eventuell noch testen. Dazu sollte man sich eine neue Eclipse-Installation besorgen. Hierfür ist die Variante *Eclipse IDE for Java Developers* völlig ausreichend. In dieser Installation werden nun erst die ADT installiert, nach einem Neustart fügt man jetzt die neue -- bis jetzt noch lokale -- Update-Site über Help → Install New Software... → Add*...* hinzu:

![](./Kapitel 7 - Plug-ins/media/image30.png)

*Abbildung: Dialog zum Hinzufügen einer Update-Site*

Über den Button "Local...*"* wählt man dann das Verzeichnis des Update-Site-Projekts aus. Nach Klick auf den Button "Add" sollten die Kategorien und die zugewiesenen Features der Update-Site aufgelistet und installierbar sein.

### Deployment

Wenn der Test der Update-Site erfolgreich war, kann diese nun auf einem Webserver hochgeladen werden, um die Artefakte für andere bereitzustellen. Sollte man die Kosten für einen eigenen Webserver scheuen, gibt es zum Beispiel über GitHub Pages eine kostenlose Möglichkeit, seine Update-Site bereitzustellen. Dazu initialisiert man im Projektverzeichnis der Update-Site ein neues Git Repository und veröffentlicht dieses in einem öffentlichen Repository auf GitHub. Im Anschluss kann in den Repository-Einstellungen auf GitHub die Option "GitHub Pages" aktiviert werden:

![](./Kapitel 7 - Plug-ins/media/image3.png)

*Abbildung: GitHub-Repository-Einstellungen für GitHub Pages*

Nachdem das Erstellen der GitHub-Pages-Seite durch GitHub abgeschlossen ist, kann diese mit der URL *https://\<username\>.github.io/\<repository-name\>* in Eclipse als Update-Site eingetragen werden.

## Erweiterung des ADT Backends mit ABAP Code

Für die Kommunikation von Eclipse zum ABAP Server verwenden die ADT RESTful APIs. Wie man solche APIs selbst entwickelt, kann in dem SAP Guide [How To\... Create RESTful APIs and consume them in ADT](https://assets.cdn.sap.com/sapcom/docs/2013/04/12289ce1-527c-0010-82c7-eda71af511fa.pdf) nachgelesen werden.

Obwohl hier die Rede von RESTful APIs ist, findet von ADT aus keine Kommunikation mittels HTTP statt. Sie erfolgt mit dem RFC-Protokoll. In der untersten Ebene der Kommunikationsschicht von ADT findet somit ein RFC-Aufruf statt, der einen bestimmten RFC-Funktionsbaustein auf dem ABAP Server aufruft.

Somit steht es jedem offen, entweder, wie im Guide beschrieben, eigene RESTful APIs mit dem BAdI-Erweiterungskonzept zu entwickeln oder alternativ einen RFC-fähigen Funktionsbaustein zu entwickeln und diesen mit dem RFC Java Connector aufzurufen. Die Java Connector API kann über das Plug-in "com.sap.conn.jco" eingebunden und verwendet werden.

Vor allem bei kleineren Plug-ins mag die BAdI-Methode als ziemlicher Overhead wirken, sowohl auf ABAP- als auch auf Java-Seite. Jedoch hat der BAdI-Ansatz auch seine Vorteile. Vor allem durch den Einsatz von EMF (Eclipse Modelling Framework) besteht die Möglichkeit, einen von ABAP nach XML serialisierten String ganz einfach in Objekte in Java umzuwandeln. Einfach beschrieben benötigt man dafür auf der ABAP-Seite eine "Simple Transformation" (Objekttyp XSLT), um ABAP-Daten nach XML zu transformieren.

![](./Kapitel 7 - Plug-ins/media/image18.png)

*Abbildung: Beispiel für eine Simple Transformation zur Transformation von ABAP \<-\> XML*

Und seitens Java ist ein EMF-Modell notwendig.

![](./Kapitel 7 - Plug-ins/media/image16.png)

*Abbildung: Beispiel für EMF-Modell zur Serialisierung von XML- \<-\> Java-Objekt*

Durch diesen Ansatz lässt sich die Datentransformation sehr generisch bauen, und man spart auch wieder Entwicklungszeit ein.

## Java Code Snippets für wiederkehrende Aufgaben in ADT

### Aufruf eines RFC-Funktionsbausteins mit dem Java Connector

// 1) Lesen der Destination Id für eine ABAP Project Instanz

String destinationId = AdtCoreProjectServiceFactory.createCoreProjectService().getDestinationId(project);

// 2) Lesen der JCo destination zur Destination Id

JCoDestination destination = JCoDestinationManager.getDestination(destinationId);

// 3) Lesen des RFC Bausteins

JCoFunction function = destination.getRepository().getFunction(\"name_of_rfc_function\");

// 4) Setzen eines Importing-Parameters

function.getImportParameterList().getField(\"I_PARAM1\").setValue("PARAM_VALUE");

// 5) Ausführen der Funktion

function.execute(destination);

// 6) Lesen eines Exporting Tabellenparameters

JCoTable objectTree = function.getExportParameterList().getTable(\"E_PARAM1\");

### Lesen des ABAP-Projekts abhängig von der aktuellen Selektion im Workbench

// 1) Ermittlung der aktiven Page im Workbench

IWorkbenchPage page = PlatformUI.getWorkbench().getActiveWorkbenchWindow().getActivePage();

// 2) Lesen der Workbench Window Instanz

IWorkbenchWindow window = page.getWorkbenchWindow();

// 3) Ermittlung der aktuellen Selektion im Window

ISelection adtSelection = window.getSelectionService().getSelection();

// 4) Ermittlung des aktiven ABAP Projekts

IProject project = ProjectUtil.getActiveAdtCoreProject(adtSelection, null, null, IAbapProject.ABAP_PROJECT_NATURE);

### Ermittle den Quellcode des aktiven Editors

// 1) Ermittle den aktiven Editor

IAdtFormEditor editor = (IAdtFormEditor)PlatformUI.getWorkbench()

> .getActiveWorkbenchWindow().getActivePage()
>
> .getActiveEditor();

// 2) Ermittle das Document des Editors

IDocument document = editor.getAdapter(AbapSourcePage.class).getDocument();

// 3) Ermittle den Quellcode

String code = document.get();

### Führe den Transaction-Code aus

// 1) Ermittle die Benutzereinstellung der Navigation zum Eclipse Editor für unterstützte Entwicklungsobjekte

boolean navigateToEclipse =

com.sap.adt.sapgui.ui.internal.Activator.getDefault()

> .getPreferenceStore()
>
> .getBoolean(com.sap.adt.sapgui.ui.internal.PreferenceInitializer
>
> .PREF_KEY_USE_ECLIPSE_NAVIGATION);

// 2) Ausführung des Transaction Code

AdtSapGuiEditorUtilityFactory

.createSapGuiEditorUtility()

.openEditorAndStartTransaction(project,TRANSACTION_NAME, navigateToEclipse);

### ABAP Scan Services -- Prüfe, ob der Token ein Keyword ist

// 1) Ermittle die Instanz von AbapSourceUI\
IAbapSourceUi sourceUi = AbapSourceUi.getInstance();

// 2) Ermittle die Instanz von SourceScannerServices

IAbapSourceScannerServices = sourceUi.getSourceScannerServices();

// 3) Ermittle den aktiven ADT Editor

editor = (IAdtFormEditor)PlatformUI.getWorkbench()

> .getActiveWorkbenchWindow().getActivePage().getActiveEditor();

// 4) Ermittle das Dokument vom Editor

IDocument document = editor.getAdapter(AbapSourcePage.class).getDocument();

// 5) Prüfe ob der Token an der Offset-Position ein Keyword ist (oder nicht)

Boolean isKeyword = scannerServices.isKeyword(document,OFFSET);

// 6) Ermittle den nächsten Token basierend auf der Offset-Position

Token nextToken = scannerServices.getNextToken(document,OFFSET);

// 7) Prüfe ob der nächste Token ein Keyword ist (oder nicht)

isKeyword = scannerServices.isKeyword(document,nextToken.offset);

### Ermittle das Projekt und zeige den Selektionsdialog

// 1) Ermittle die Shell

Shell shell = PlatformUI.getWorkbench().getActiveWorkbenchWindow().getShell();

// 2) Zeige den Selektions-Dialog und ermittle das gewählte Projekt

IProject chosenProject = AbapProjectSelectionDialog.open(shell, null);

### Ermittle die User und rufe den Selektionsdialog

// 1) Ermittle den User Service

IAdtUserServiceUI adtUserService = AdtUserServiceUIFactory.createAdtUserServiceUI();

// 2) Rufe den User Selektions-Dialog und ermittle die selektierten User

String\[\] users = adtUserService.openUserNameSelectionDialog(null, false, project,\"\");

### Anmelden auf dem ABAP-System

// 1) Adaptieren eines IProject Objekts zu einem IAbapProject Objekt

final IAbapProject abapProject = project.getAdapter(IAbapProject.class);

// 2) Prüfen des Anmeldestatus mit automatischem Anmeldedialog falls noch keine

// Anmeldung vorliegt

IStatus logonStatus = AdtLogonServiceUIFactory.createLogonServiceUI()

.ensureLoggedOn(abapProject.getDestinationData(), PlatformUI.getWorkbench()

.getProgressService()

.isOK();

## Projekt-Set-up mit Maven

Neben den Standardmöglichkeiten zur Entwicklung von Plug-ins, Features und Update-Sites, welche mit der *Eclipse IDE for RCP and RAP Developers* geliefert werden, gibt es auch noch die Option, Eclipse Tycho zu verwenden. Eclipse Tycho ist eine Sammlung von Plug-ins für Apache Maven. Weitere Informationen können der [Projektseite](https://github.com/eclipse-tycho/tycho) von Tycho entnommen werden. Ein Tutorial zur Plug-in-Entwicklung mit Tycho gibt es [hier](https://github.com/eclipse-tycho/tycho).