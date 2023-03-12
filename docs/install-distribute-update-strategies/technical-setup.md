---
layout: page
title: Technischer Aufbau einer Eclipse-Installation
parent: Installation, Verteilungs- und Update-Strategien
permalink: /install-distribute-update-strategies/technical-setup/
prev_page_link: /install-distribute-update-strategies/preparations/
prev_page_title: Vorbereitungen
next_page_link: /install-distribute-update-strategies/plug-ins/
next_page_title: Plug-ins
nav_order: 3
---

{: .no_toc}
# Technischer Aufbau einer Eclipse-Installation

1. TOC
{:toc}

Wie bereits in vorhergegangenen Kapiteln erwähnt, besteht eine Eclipse-Installation aus den folgenden Komponenten:

- Installationsordner (reine Software-Pakete und eclipse.exe)
- User-Settings oder Configuration-Area (Plug-ins, Teile der Konfiguration)
- Workspace (benutzerspezifischer Teil: Einstellungen, Ansichten, Systemverbindungen etc.)

Die Installation von Eclipse legt den Installationsordner und User-Settings an. Mittels fortgeschrittener Techniken können auch schon Teile des Workspace vorbelegt werden.

Aufgrund diverser Probleme empfiehlt es sich, alle Komponenten in einen mit normalen Benutzerrechten beschreibbaren Ordner abzulegen (also **nicht** `C:\Program Files\`).

Beispielsweise könnte eine Verzeichnisstruktur für die Eclipse-Installation wie folgt aussehen:

|Pfad|Beschreibung|
|:--|:--|
|`C:\ADT\` | Gesamtverzeichnis für ADT|
|`C:\ADT\IDE` | Verzeichnis für Ablage der verschiedenen Eclipse-Versionen|
|`C:\ADT\IDE\2022-12` | entpackte Dateien der Eclipse-Version 2022-12|
|`C:\ADT\IDE\2023-03` | entpackte Dateien der Eclipse-Version 2023-03|
|`C:\ADT\WS` | Verzeichnis zur Ablage der verschiedenen Workspaces|
|`C:\ADT\WS\2022-12` | Verzeichnis für Workspaces der Version 2022-12|
|... | |

Diesem Beispiel liegt die Annahme zu Grunde, dass die Eclipse-Installation über das Entpacken der zip-Files erfolgt und die Versionen parallel verwendet werden sollen.

Da die Workspaces mit aufsteigenden Versionen in die jeweils neue Version konvertiert werden, sollten die Workspaces pro Version kopiert werden, um bei Bedarf die älteren Versionen weiterhin verwenden zu können.

Inwiefern Workspaces sinnvoll eingesetzt werden, wird in Kapitel [Arbeiten mit ADT](/ADT-Leitfaden) detaillierter erläutert.