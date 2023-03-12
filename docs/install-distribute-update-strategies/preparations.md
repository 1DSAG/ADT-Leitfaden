---
layout: page
title:  Vorbereitungen
parent: Installation, Verteilungs- und Update-Strategien
permalink: /install-distribute-update-strategies/preparations/
prev_page_link: /install-distribute-update-strategies/delimitations/
prev_page_title: Abgrenzungen
next_page_link: /install-distribute-update-strategies/technical-setup/
next_page_title: Technischer Aufbau einer Eclipse-Installation
nav_order: 2
---

{: .no_toc}
# Vorbereitungen

1. TOC
{:toc}

Für jede ADT-Installation (teilweise auch Eclipse ohne ADT) gibt es gewisse Voraussetzungen. Diese sind unabhängig von der Installations-/Verteilungsstrategie und werden detailliert im o. g. ADT Installation Guide beschrieben.

## Java Development Kit und Java Runtime Environment

Wird mit der Installation lediglich ABAP entwickelt (und insbesondere kein Java, d. h. auch keine Plug-in-Entwicklung zur Ergänzung der ADT, siehe Kapitel [Plug-ins](/ADT-Leitfaden/plug-ins)), so ist auch kein Java Development Kit (JDK) notwendig. Ein Java Runtime Environment (JRE) reicht aus. Wird der offizielle Installer von Eclipse als Basis verwendet (siehe Kapitel [Installation, Verteilungs- und Update-Strategien](/ADT-Leitfaden/install-distribute-update-strategies)), kommt dies automatisch mit.

Zu beachten ist dabei, dass Eclipse mittlerweile standardmäßig als 64-Bit-Anwendung installiert wird (oft auch als *x64* oder *x86_64* bezeichnet). Da das JRE dieselbe Architektur verwenden muss wie die Eclipse-Installation, wird auch eine 64-Bit-JRE installiert.

## Backend

Neben der lokalen ADT-Installation muss im Falle der Entwicklung auf einem On-Premise-System auch selbiges für die Verbindung mit ADT vorbereitet werden. Diese Schritte werden ebenfalls im offiziellen [SAP ADT Configuration Guide](http://help.sap.com/download/netweaver/adt/SAP_ADT_Configuration_Guide_Backend_en.pdf) beschrieben. Zwei essentielle Schritte werden darin jedoch gerne übersehen, weshalb hier noch einmal explizit darauf hingewiesen werden soll.

### Web-Services

Für die Kommunikation nutzen die ADT spezielle Web-Services auf dem Backend, die mit den unterstützten Basis-Releases ausgeliefert werden. Die Definition der Web-Services und die darin eingetragenen Handler-Klassen sind ein Grund, warum der Funktionsumfang der ADT zwischen den Basis-Releases unterschiedlich ist. Diese Web-Services sind standardmäßig inaktiv und müssen zunächst aktiviert werden. Die aktuelle Liste kann dem oben verlinkten Configuration Guide von SAP entnommen werden.

Zum Zeitpunkt dieses Dokuments sind dies die folgenden Services:

- ABAP Docu (notwendig)
  - *default_host → sap → public → bc → abap → docu*
  - *default_host → sap → bc → abap → docu*
- Fehlertexte und Element Info (notwendig)
  - *default_host → sap → public → bc → abap → toolsdocu*
  - *default_host → sap → bc → abap → toolsdocu*
- Teilen von HTTP-Links (optional)
  - *default_host → sap → bc → adt*
- Web Dynpro (nur notwendig für WD-Entwickler)
  - *default_host → sap → bc → webdynpro → sap → wdy_aie_vd_preview*

### Berechtigungen

Um die genannten Web-Services nutzen zu dürfen, müssen die User berechtigt werden. Zusätzlich werden noch RFC-Bausteine und Transaktions-Codes benötigt.

SAP liefert hierzu zwei Rollen als Vorlage aus:

1. *SAP_BC_DWB_ABAPDEVELOPER* → Entwicklerrolle mit allen Features
2. *SAP_BC_DWB_WBDISPLAY* → Anzeigeberechtigungen für alle Features

Details bezüglich der darin verbauten Berechtigungen und deren Zweck können dem [SAP ADT Configuration Guide](http://help.sap.com/download/netweaver/adt/SAP_ADT_Configuration_Guide_Backend_en.pdf) entnommen werden.

## SAP-GUI-Installation

Soll auf einem Backend-System ein SAP-GUI-Transaktionsstart möglich sein (nicht verfügbar in SAP Public Cloud und SAP BTP ABAP Environment/Steampunk), so wird hierfür eine lokale SAP-GUI-Installation benötigt. Die ADT liefern diese nicht mit.

## Visual Studio Redistributable

Unter Windows wird zudem das Visual-Studio-2013 (VC++ 12.0)-Redistributable-Paket in exakt dieser Version benötigt. Oftmals ist diese Abhängigkeit schon aufgrund anderer bereits auf dem Zielgerät installierter Software vorhanden.
