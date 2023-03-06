---
layout: page
title: Kapitel 2 - Motivation für ADT
permalink: /kapitel2/
nav_order: 2
---

Autoren:, Bärbel Winkler, Michael Biber, Michael Keller, Florian Henninger, Wolfgang Röckelein, Peter Luz

**Kapitelstatus:** "Ready for Review" - finales kapitel meeting Anfang Dezember

Review von Sebastian am 11.01.23 auf alle Kapitel

**[Sie möchten modernes ABAP anwenden und umsetzen.](#sie-möchten-modernes-abap-anwenden-und-umsetzen.) 2**

**[Sie möchten eine Entwicklungsumgebung für \"alles\" nutzen. ".](#sie-möchten-eine-entwicklungsumgebung-für-alles-nutzen) 2**

> [Technologischer Aspekt](#technologischer-aspekt) 2
>
> [Entwicklung auf mehreren Systemlinien](#entwicklung-auf-mehreren-systemlinien) 3

**[Sie möchten sich von technischen Einschränkungen des SAP GUI lösen.](#sie-möchten-sich-von-technischen-einschränkungen-des-sap-gui-lösen.) 3**

> [Ihnen sind sechs Sessions in einem System zu wenig.](#ihnen-sind-sechs-sessions-in-einem-system-zu-wenig.) 3
>
> [Sie möchten durch Netzwerkunterbrechungen keinen Code verlieren.](#sie-möchten-durch-netzwerkunterbrechungen-keinen-code-verlieren.) 4

[Sie verbessern Ihren ABAP-Code gerne durch Refactoring.](#sie-verbessern-ihren-abap-code-gerne-durch-refactoring.) **4**

[Sie passen die Darstellung Ihrer Entwicklungsumgebung gerne Ihren Wünschen an](#sie-passen-die-darstellung-ihrer-entwicklungsumgebung-gerne-ihren-wünschen-an) **4**

**[Sie möchten noch mehr Toolbasierte Unterstützung?](#sie-möchten-noch-mehr-toolbasierte-unterstützung) 5**

[Sie kennen Eclipse bereits von anderen Programmiersprachen. Prima!](#sie-kennen-eclipse-bereits-von-anderen-programmiersprachen.-prima) **5**

**[Sie haben Interesse an Neuem](#sie-haben-interesse-an-neuem) 6**

**[Vorteile für die Organisation](#die-vorteile-für-die-organisation) 6**

**[Ihnen fehlt der formularbasierte Editor](#ihnen-fehlt-der-formularbasierte-editor) 7**

In diesem Kapitel stellen wir Ihnen mehrere Gründe vor, die für den Einsatz der ABAP Development Tools (ADT) als Entwicklungsumgebung sprechen. Am Ende gehen wir auch auf den mitunter größten "Knackpunkt" für langjährige ABAP-Entwickler ein und geben Hinweise, warum dieser manchmal als Nachteil betrachtete Punkt in Wirklichkeit ein Vorteil ist.

Wir freuen uns, wenn wir Sie mit diesem Kapitel vom Nutzen der ADT überzeugen können oder zumindest Ihre Neugier geweckt haben, diesen Leitfaden zu studieren.

## Sie möchten modernes ABAP anwenden und umsetzen.

Der erste und naheliegendste Grund für eine umfassende Nutzung der ABAP Development Tools in Eclipse ist die strategische Ausrichtung seitens SAP. Die ABAP Development Tools wurden 2012 eingeführt und haben sich in diesen 10 Jahren zu einer stabilen Entwicklungsumgebung mit einem großen Funktionsumfang entwickelt.

Im Gegensatz dazu befinden sich die SAP GUI-gebundenen Entwicklungswerkzeuge, mit ihrem prominentesten Beispiel, der ABAP-Workbench, im Wartungsmodus. Das bedeutet, dass hier zwar weiterhin Fehlerkorrekturen stattfinden, jedoch keine neuen Funktionen mehr ausgeliefert werden.

Dies ist vielleicht kurzfristig nicht der motivierendste Grund, allerdings wird dies jeden Entwickler im SAP-Umfeld eines Tages einholen. Daher empfehlen wir den Einstieg und Umstieg in und auf die ABAP Development Tools lieber heute als morgen anzugehen.

Aus diesem Grund empfiehlt die SAP den Einsatz der ADT als Standardumgebung für die ABAP-Entwicklung, um mit jedem Release von neuen Funktionen und Korrekturen zu profitieren. Der tatsächlich vorhandene Funktionsumfang hängt vom Release-Stand des ABAP-Stacks der verwendeten SAP-Systeme ab. Eine grobe Übersicht und weitere Informationen hierzu finden sich im Abschnitt: [[Kapitel 1 - Einführung Eclipse und ADT]{.underline}](https://docs.google.com/document/u/0/d/1_R0cnFWdcItzWNu9ta434iE7rT7ldiJFOiujvyJdj6w/edit).

## Sie möchten eine Entwicklungsumgebung für Alles nutzen

### Technologischer Aspekt 

Mit den ABAP Development Tools (ADT) können Sie nicht nur für On-Premise Systeme wie beispielsweise SAP-ERP oder S/4HANA entwickeln. Die ADT sind auch die einzige Möglichkeit, Entwicklungen für Cloudsysteme wie die Business Technology Platform (BTP) durchzuführen.

Dieser Umstand ist insbesondere für ABAP-Entwickler wichtig, die im SAP Cloud ABAP Environment ("Steampunk") entwickeln. In diesem Kontext können klassische, SAP GUI orientierte Entwicklungswerkzeuge nicht verwendet werden und Entwicklungen können nur mit den ADT durchgeführt werden.

Eng damit verbunden ist auch die Arbeit mit einigen neuen Entwicklungsartefakten. Die Erstellung bzw. Pflege von [**[CDS Views]{.underline}**](https://help.sap.com/docs/ABAP_PLATFORM_NEW/f2e545608079437ab165c105649b89db/978e8e4d8ae14c76b4f6505023f0a019.html) ist nur mit ADT möglich. Und auch das neue Programmiermodell der SAP, das "RESTful Application Programming Model" (RAP) kann nur mit ADT verwendet werden.

### Entwicklung auf mehreren Systemlinien

Eine Entwicklungsumgebung für alles gilt bei den ADT aber auch für den Fall, dass Sie auf mehreren Entwicklungssystemen arbeiten dürfen oder müssen. In der Eclipse Umgebung sind verschiedene Systeme als Projekte aufgeführt und Sie können hierüber sehr komfortabel und übersichtlich auf diese zugreifen. Mittels der [[Working Sets]{.underline}](https://docs.google.com/document/u/0/d/16emZEtUlOHQpYIIreZMAnsDXAdIas9H36MMugzDdQPw/edit) können die Systeme in Überbegriffen gruppiert und sogar mittels zusätzlichen [[Plugins]{.underline}](https://docs.google.com/document/u/0/d/1fKzErsZ4AaeOuU9JjJM585bLN8kMpPn9DDPbXvFywiU/edit) (s. Kapitel 7) farblich gekennzeichnet werden. Das Öffnen der Systeme aus dem SAP Logon Pad, Anmelden am System und Öffnen der SE80, entfällt.

Daraus ergeben sich zahlreiche weitere Synergien bei der Arbeit, die in diesem Leitfaden beschrieben werden.

## Sie möchten sich von technischen Einschränkungen des SAP GUI lösen.

### Ihnen sind sechs Sessions in einem System zu wenig.

SAP GUI basierte Entwicklungswerkzeuge wie die ABAP Workbench unterliegen aufgrund ihrer Ausführung im SAP GUI verschiedenen Einschränkungen, die nicht relevant sind, wenn Sie mit den ADTs arbeiten.

Hierzu zählen bspw. die Abhängigkeit von der maximalen Anzahl gleichzeitiger SAP GUI Sessions (Modi, vgl. Parameter "rdisp/max_alt_modes"). Dieser Wert wird von dem per SAP GUI aufgerufenen System individuell vorgegeben. Im Standard sind es 6 gleichzeitige SAP GUI Sessions pro Benutzer im gleichen System. Für die ADT gilt diese Vorgabe nicht.

Wenn Sie als Entwickler mit unterschiedlichen Systemen gleichzeitig arbeiten, profitieren Sie von einem weiteren Vorteil: Jede Verbindung zu einem System wird als "ABAP Project" für On-Premise Systeme, bzw. "ABAP Cloud Project" für Cloud Systeme innerhalb der ADT gepflegt.. Die Verbindungen zu diesen Systemen können gleichzeitig genutzt werden. Das ermöglicht es Ihnen, Quelltext aus einem Quellsystem in die Zwischenablage zu übernehmen und in einem gleichzeitig geöffneten Zielsystem einzufügen - und das alles innerhalb desselben Anwendungsfensters von Eclipse.\
Darüber hinaus ist auf diese Weise auch ein einfacher Codevergleich zwischen verschiedenen Systemen, auch zwischen Systemen ohne bestehende RFC-Verbindung, möglich. Die Anzeige mehrerer SAP GUI Fenster wie in früheren Zeiten entfällt.

### Sie möchten durch Netzwerkunterbrechungen keinen Code verlieren.

Aufgrund technischer Gegebenheiten der SAP GUI ist es erforderlich, dass die Netzwerkverbindung stabil und unterbrechungsfrei läuft. Gibt es Netzwerkunterbrechungen, während Sie in einem GUI Fenster Code erstellen, kann es vorkommen, dass die Arbeit der letzten Minuten vergebens war, da SAP GUI die Verbindung zum Server verloren hat und das Fenster schließt.

Mit den ADT ist eine Netzwerkunterbrechung kein Problem mehr. Das Eclipse-Fenster bleibt geöffnet, auch wenn die Verbindung unterbrochen ist. Sobald die Verbindung wiederhergestellt ist, kann der Code im SAP System gespeichert werden.\
Sollten größere Probleme im Netzwerk auftreten, kann der Code notfalls einfach komplett als Text per Copy & Paste in einem alternativen Texteditor \"zwischengespeichert\" werden, bis das SAP System wieder verfügbar ist.

## Sie verbessern Ihren ABAP-Code gerne durch Refactoring.

Die Wartbarkeit von Entwicklungsartefakten ist eine zentrale Herausforderung der Softwareentwicklung. Um eine gute Wartbarkeit zu erreichen, orientiert sich das Vorgehen beim Entwickeln häufig an Clean Code Prinzipien (vgl. Clean ABAP). Zur Einhaltung der Clean Code Prinzipien ist ein wiederholtes Überarbeiten von Entwicklungsartefakten, auch Refactoring genannt, unabdingbar.

Die ADT unterstützen typische Refactoring-Aufgaben mit Hilfe der "[[**Quick Assists**"]{.underline}](https://help.sap.com/docs/ABAP_PLATFORM_NEW/c238d694b825421f940829321ffa326a/4ec1d7ba6e391014adc9fffe4e204223.html) Funktionen, zu denen auch die "Quick-Fixes" gehören. Die Quick Assists sind kontextsensitiv. Sie können beispielsweise komplexe Quelltextabschnitte in kleinere, neue und vor allem eigenständige Methoden auslagern, was letztendlich die Verständlichkeit und damit die Wartbarkeit deutlich erhöht. Ohne Unterstützung durch die Quick Assists ist ein solches iteratives Vorgehen deutlich arbeitsintensiver und auch fehleranfälliger.

Weitere und detailliertere Informationen zum Refactoring und Werkzeugen, die Ihnen in den ADT dafür zur Verfügung gestellt werden, finden Sie in [[Kapitel 4 - Arbeiten mit ADT]{.underline}](https://docs.google.com/document/u/0/d/16emZEtUlOHQpYIIreZMAnsDXAdIas9H36MMugzDdQPw/edit)

## Sie passen die Darstellung Ihrer Entwicklungsumgebung gerne Ihren Wünschen an

Die ADT basieren auf Eclipse, einer weit verbreiteten Open Source Entwicklungsumgebung. Stärken dieser Entwicklungsumgebung sind u. a. die vielfältigen Anpassungsmöglichkeiten wie bspw. an der Darstellung (vgl. Views und Perspektiven in [[Kapitel 4 - Arbeiten mit ADT]{.underline}](https://docs.google.com/document/u/0/d/16emZEtUlOHQpYIIreZMAnsDXAdIas9H36MMugzDdQPw/edit)) als auch an den Shortcuts ([[Tastaturkürzel]{.underline}](https://docs.google.com/document/u/0/d/1_R0cnFWdcItzWNu9ta434iE7rT7ldiJFOiujvyJdj6w/edit)) und der Unterstützung durch hilfreiche Funktionen wie bspw. einer umfassenden Suche.

Als Nutzer von Eclipse können Sie die Entwicklungsumgebung daher auf vielfältige Art individualisieren und verwenden, was letztendlich jedem Anwender eine bessere Unterstützung ihrer bevorzugten Arbeitsweise erlaubt.

Da die ADT den Zugriff auf verschiedene SAP-Systeme gleichzeitig ermöglicht, können Sie über alle Systeme hinweg einheitlich arbeiten. Dies steht im Kontrast zur Arbeit mit SAP GUI gebundenen Entwicklungswerkzeugen wie der ABAP Workbench, die in jedem System separat individualisiert werden müssen.

Mit den sogenannten Workspaces haben Sie die Möglichkeit, verschiedene Konfigurationen der Arbeitsumgebung abzuspeichern. Zum Beispiel sind hier verschiedene Projekte, verschiedene Favorite Packages, welche Sichten und Objekte geöffnet sind und sogar die Stelle im Code, an der zuletzt gearbeitet wurde, im jeweiligen Working Set gespeichert. Zusätzlich können verschiedene Workspaces in mehreren parallel laufenden Eclipse-Instanzen geöffnet werden. Damit haben Sie die Möglichkeit, abhängig vom Projekt, Kunde oder Aufgabe, sich jeweils die effizienteste Umgebung zusammenzustellen. In Kapitel 4 - arbeiten mit ADT und in Kapitel 3 Installation finden Sie Informationen, wie Workspaces zu verwenden sind.

## Sie möchten noch mehr Toolbasierte Unterstützung?

Falls Ihnen der Funktionsumfang der von SAP bereitgestellten Funktionen nicht ausreicht, können Sie den Funktionsumfang durch weitere Plugins, die es als Ergänzung zu ADT gibt, erweitern.

Eine Auswahl dieser Plugins wird in [[Kapitel 7 - Plug-Ins]{.underline}](https://docs.google.com/document/u/0/d/1fKzErsZ4AaeOuU9JjJM585bLN8kMpPn9DDPbXvFywiU/edit) vorgestellt.\
Mit dem richtigen Know-How können Sie bei Bedarf auch eigene Plugins erstellen und der SAP Community zur Verfügung gestellt werden.\
In der Vergangenheit haben verschiedene ABAP-Entwickler von dieser Möglichkeit bereits Gebrauch gemacht und eigene Plugins entwickelt, die sie der SAP Community kostenlos zur Verfügung stellen.

Ein Beispiel hierfür sind die "[[ABAP Quick Fix]{.underline}](https://marketplace.eclipse.org/content/abap-quick-fix)". Dies ist eine Erweiterung der im Standard der ADT angebotenen "Quick Fixes"zur Unterstützung der automatischen Konvertierung der klassischen ABAP-Syntax in das jeweilige moderne ABAP-Syntax-Pendant.

## Sie kennen Eclipse bereits von anderen Programmiersprachen. Prima!

Eclipse als Grundlage der ADT ist in verschiedenen Unternehmen bereits im Einsatz. Das liegt daran, dass es z. B. für JAVA eine der am weit verbreitetsten Entwicklungsumgebungen ist. JAVA wiederum ist eine häufig verwendete Programmiersprache (vgl. [[TIOBE-Index]{.underline}](https://www.tiobe.com/tiobe-index/)) und spielt daher in vielen Entwicklungsprojekten eine Rolle. Daneben ist Eclipse aber auch für andere Entwicklungszwecke einsetzbar, z. B. für die Entwicklung in der Programmiersprache Python oder der Arbeit mit Daten im Extensible Markup Language (XML) Format.

Es besteht also eine gewisse Wahrscheinlichkeit, dass Entwickler und Unternehmen bereits Vorkenntnisse im Umgang mit Eclipse als Entwicklungsumgebung besitzen. Hierdurch gelingt der erweiterte Einsatz auf Basis der ADT einfacher und schneller, als wenn auf ein vollständig neues, möglicherweise gänzlich unbekanntes Entwicklungswerkzeug gesetzt wird.

## Sie haben Interesse an Neuem

Zu guter Letzt möchten wir noch auf das Interesse vieler Menschen an Neuem und der damit verbundenen Attraktivität als Motivationsfaktor für den Umstieg hinweisen. Handelte es sich bei den Gründen zum Umstieg in den vorherigen Abschnitten um eher sachliche Aspekte, geht es hier um im Menschen tief verankerte Emotionen und Werte: das Interesse an etwas Neuem und die Attraktivität, die etwas Neues hat. Oder kurz: um Fortschritt und Veränderung.

Für manche Menschen bedeutet der Stillstand mit gelegentlichen kleinen Veränderungen eine gewisse Sicherheit im Arbeitsalltag. Diese Sicherheit ist allerdings trügerisch, da sich die (IT-)Welt rasant verändert und nicht immer bieten bestehende Technologien und Methoden die passenden Antworten auf aktuelle und zukünftige Herausforderungen.

Insbesondere in der ABAP Welt hat sich in den letzten 10 Jahren sehr viel verändert. Nachdem zahlreiche neue Sprachkonstrukte ABAP bereichert haben, sind neue Artefakte wie CDS Views und neue Programmiermodelle wie das ABAP Restful Application Programming Model (RAP) dazugekommen. Und auch der technologische Wandel wie der Weg in die Cloud sind nicht von der Hand zu weisen. Konsequenterweise erfordert dies auch die Weiterentwicklung der Tools, die bei der Entwicklung verwendet werden.

Zudem kann es bei einem technologischen Stillstand auch zu einem Ausschluss nachfolgender Generationen an Entwicklern kommen, da diese Technologien mit einem oftmals gänzlich anderen Blick betrachten, ihre bereits gemachten Erfahrungen mit anderen Entwicklungsumgebungen und Programmiersprachen abgleichen und ihre Bewertung auf dieser Basis vornehmen.

## Die Vorteile für die Organisation

Wir möchten mit diesem Leitfaden nicht nur den ABAP-Entwickler motivieren, ADT einzusetzen. Auch für die Organisation ergeben sich durch den umfassenden Einsatz von ADT im SAP-Entwicklungsbereich zahlreiche Vorteile.

Neben der höheren Effizienz der Entwickler, u. a. durch bessere Toolunterstützung zur Erstellung und Verbesserung des Codes, stellen hier auch wieder Zukunftsfähigkeit und einheitliches Tooling die wichtigsten Gründe für die Organisation dar, den Einsatz der ADTs in den SAP Entwicklungsteams zu fördern und einzufordern.

Um den Einsatz für den einzelnen Entwickler reibungsfrei zu ermöglichen und Umstiegshemmnisse von Anfang an zu vermeiden und damit einen breiten Einsatz der ADTs zu erreichen, müssen folgende Themen zentral geklärt und in Form von allgemein verfügbaren Dokumentationen den Entwicklern bereitgestellt werden.

-   Rahmenbedingungen und generelle Informationen zu ADT

-   Installation von Eclipse

-   Zugriff von Eclipse auf Ressourcen im Internet (Updates und Plugin Installationen)

-   Berechtigungen der Entwickler für ADT Objekte im Backend (S_RFC for ADT\*)

Dies stellt auch hier wieder zuerst eine Investition dar, die sich aber auszahlt, sobald die Entwicklerteams einheitlich mit ADT arbeiten und die Vorteile der Entwicklungsumgebung in der täglichen Arbeit voll ausgenutzt werden können.

Zahlreiche Informationen, Hilfestellungen und Best-Practices hierzu finden Sie in [[Kapitel 5 - Installation, Verteilung- und Updatestrategien]{.underline}](https://docs.google.com/document/u/0/d/1eBXEXs5uZEJ7GqjRkO315sWdnM2A1QyaJMsYEEruFiI/edit).

## 

## Ihnen fehlt der formularbasierte Editor

Die ADT nutzen an vielen Stellen eine textorientierte Darstellung von Entwicklungsartefakten, was Ihnen von anderen Entwicklungsumgebungen wie beispielsweise Microsoft Visual Studio Code (VSCode) bekannt ist. Damit wird auf die bisherige, formularbasierte Darstellung, die Sie von den SAP GUI orientierten Entwicklungswerkzeugen kennen, verzichtet.

Dies ist sicher eine der größten Hürden für eingefleischte ABAP-Entwickler, die von GUI-basierten Werkzeugen auf Eclipse umsteigen wollen oder sollen. Um diese Hürde zu überwinden, finden Sie einen ausführlichen Einstieg in die Arbeit mit den ADT in [[Kapitel 4 - Arbeiten mit ADT]{.underline}](https://docs.google.com/document/u/0/d/16emZEtUlOHQpYIIreZMAnsDXAdIas9H36MMugzDdQPw/edit).

Mit dieser Veränderung in der Darstellung geht auch eine gewisse Veränderung der Arbeitsweise einher. Der häufige Wechsel zwischen verschiedenen SAP GUI Oberflächen, die in einem bestimmten Kontext stehen, entfällt. Stattdessen gibt es oftmals "nur" Text - also Anweisungen, die eingegeben bzw. gelesen werden. Das führt zu einer starken Konzentration auf die eigentlichen Anweisungen, ihre Wirkungen und Zusammenhänge (Syntax und Semantik).

Ein Beispiel für diese veränderte Darstellung ist die Signatur eines Funktionsbausteins. Mit den SAP GUI basierten Entwicklungswerkzeugen wird die Signatur eines Funktionsbausteins, bestehend aus IMPORT, EXPORT, CHANGING, TABLES und EXCEPTIONS als fünf, separate Register dargestellt. In den ADT wird die Signatur als Text dargestellt und gepflegt. Ein Wechsel zwischen unterschiedlichen kontext-gebundenen Registern entfällt.

Nach der anfänglichen Umgewöhnung werden Sie sicherlich schnell die Vorteile der textorientierten Arbeitsweise erkennen, die sich durch den Wegfall der Navigationschritte durch die GUI und auch durch die zahlreichen Unterstützungen wie Code-Vervollständigung und Quick Fixes ergeben.

## Warum ABAP Development Tools

Falls Sie die bisher beschriebenen Vorteile von ADT noch nicht überzeugt haben, möchten wir Sie mit Zitaten der Autoren des Leitfadens motivieren, sich einmal in die Sicht von ADT-Usern zu versetzen. Eventuell finden Sie ja hier den Anstoß, sich doch dem Thema anzunehmen.

Vorschlag Zitat Michael Keller: "*Clean ABAP ohne die ADT und damit die Unterstützung durch die Quick Fixes ist für mich undenkbar - schließlich sparen sie dem Entwickler viel Zeit und Arbeit.*"

Florian Henninger: "*Refactoring ohne ADT ist so ein bisschen wie zu versuchen, eine Suppe mit einer Gabel essen zu wollen... kann funktionieren, macht nur keiner.*"

Bärbel Winkler: "*Durch die Mitarbeit bei der Erstellung dieses Leitfadens habe ich viele gute Gründe kennengelernt, in Zukunft häufiger als bisher mit den ADT zu arbeiten.*"

Jens Zähringer: "Obwohl die ABAP Development Tools bereits seit über 10 Jahren zur Verfügung stehen, habe ich erst kürzlich den Umstieg von ABAP Workbench zu ADT für mich vollzogen. Die Umstellung war nicht ohne Herausforderungen, aber am Ende hat es sich definitiv gelohnt!"

Peter Luz: "Mittels des Verwendungsnachweises schnell ermitteln, wo eine Methode verwendet und wie sie dort aufgerufen wird. Dann diese mehrfach verwendete Methode umbenennen. Anschließend ein Stück Code daraus in eine eigene Methode extrahieren. Dann noch zum Abschluss den Code auf dem zentralen Entwicklungssystem mit der Version auf der Q-Maschine einer Systemlinie vergleichen.\
In ADT nur ein paar Tastenkombinationen entfernt und in Sekundenschnelle durchgeführt. So macht das Erstellen und Überarbeiten von Software Spass und hilft die Qualität der Software maßgeblich durch Nutzung der hier im Leitfaden beschriebenen Werkzeuge zu verbessern.\
Für mich ist Entwickeln in ABAP ohne ADT inzwischen undenkbar."

Michael Biber: Ja, SE80 ist mittlerweile ganz gut. Jedoch sehe ich dies wie mit dem Umstieg auf Objektorientierung: Am Anfang fragt man sich "warum" und sieht vorhandene Stolpersteine. Sobald man jedoch mal die andere Seite (Objektorientierung, ADT, ...) erlebt hat, möchte man nicht mehr zurück. Die Vorteile der besseren Übersichtlichkeit (Element Info), theoretisch unendlich parallel geöffneten Sourcen, Live-Syntaxprüfung und vielen mehr überwiegen für mich über alle kleinen Medienbrüche (\--\> ältere SAP Releases) und andere Denkansätze.

Björn Schulz: *"Ohne die ADTs würde ich viel langsamer an Informationen aus dem System kommen und wahrscheinlich mit nur 6 Modi nicht mehr klarkommen".*

Dr. Wolfgang Röckelein: "*Gibt es ABAP Entwicklung ohne ADT?" "Kein Clean Code ohne Refactoring, kein Refactoring ohne ADT.*"

Uwe Fetzer: "*Schneller, komfortabler, sicherer kann man ABAP Clean Code nicht entwickeln*".
