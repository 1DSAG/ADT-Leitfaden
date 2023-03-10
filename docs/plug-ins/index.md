---
layout: page
title: Kapitel 7 - Plug-ins
permalink: /plug-ins/
has_children: true
nav_order: 7
---

# Kapitel 7 - Plug-ins

## Einführung

Eclipse ist eine integrierte Entwicklungsumgebung (IDE), die im Kern aus vielen kleinen Einheiten -- sog. Plug-ins -- besteht. Wenn man beispielhaft die Eclipse-Varianten Eclipse IDE for Java Developers oder Eclipse IDE for C/C++ Developers betrachtet, dann sind diese vorkonfigurierten Pakete nur Sammlungen von Plug-ins, die für einen bestimmten Zweck entwickelt worden sind.

Die ABAP Development Tools (ADT) sind kategorisch genau das Gleiche, also eine Sammlung von Plug-ins, und stellen somit ABAP-Entwicklern ein modernes Entwicklungswerkzeug zur Verfügung. Eben genau dieser modulare Aufbau ermöglicht es jetzt jedem Entwickler, eigene Plug-ins zu erstellen, um Eclipse und/oder ADT weiter anzupassen und dadurch z. B. wiederkehrende Aufgaben zu vereinfachen oder Funktionen bereitzustellen, die durch die ADT nicht angeboten werden und nur in der ABAP Workbench zu finden sind.

Solche Plug-ins können aus reinem UI-Code bestehen, wie z. B. das ABAP Favorites Plug-in, welches Funktionen des Easy-Access-Menü (SAP GUI) nach Eclipse bringt. Sie können jedoch auch umfangreicher sein und extra ABAP-Code auf dem SAP-System benötigen. Ein Beispiel dafür ist das ABAP Code Search Plug-in, das vergleichbar ist mit der SAP-GUI-Transaktion CODE_SCANNER.
