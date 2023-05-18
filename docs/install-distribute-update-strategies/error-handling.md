---
layout: page
title: Fehlersituationen
parent: Installation, Verteilungs- und Update-Strategien
permalink: /install-distribute-update-strategies/error-handling/
prev_page_link: /install-distribute-update-strategies/install-and-distribute/
prev_page_title: Installations- und Verteilungsstrategien
next_page_link: /best-practices-configuration/
next_page_title: Best Practices Eclipse-Konfiguration
nav_order: 6
---

{: .no_toc}
# Fehlersituationen

1. TOC
{:toc}

Während der Installation oder eines Updates kann es zu verschiedenen Fehlern kommen. Auf die häufigsten Fehler soll hier einmal eingegangen werden.

## Fehler beim Update oder Upgrade

Bei der Durchführung eines Updates oder Upgrades kann es vorkommen, dass die Installation fehlschlägt.

Eine Installation läuft in der Regel in den folgenden Phasen ab:

1. Zielversionen aller Komponenten und deren Pakete berechnen, inklusive Beachtung der Abhängigkeiten
2. Pakete herunterladen
3. Pakete installieren

Die erfahrungsgemäß häufigste Fehlerursache bei der Berechnung der Zielversionen sind nicht erfüllbare Abhängigkeiten.

So fordert in einem erfundenen Beispiel ein ADT-Upgrade auch eine neuere Version von Eclipse selbst. In den verfügbaren Update-Sites ist jedoch nur die aktuelle Version zu finden. Somit ist die Fehlerursache hier eine falsche oder veraltete Update-Site.

In schwierigeren Fällen kann es sein, dass beispielsweise in neueren Releases von Eclipse eine Komponente entfernt oder ersetzt wird. Ein Plug-in wie die ADT hat jedoch noch eine Abhängigkeit dazu definiert. Hier kann nur der Hersteller des Plug-in Abhilfe schaffen.

Eine solche Situation kann bei Verwendung von HANA Studio als Eclipse-Plattform entstehen. Hier werden bei der Installation keine öffentlichen Update-Sites für die Eclipse-Plattform eingestellt, weshalb sie spätestens nach sechs Monaten (= zwei vierteljährliche Releases) nicht mehr mit aktuellen ADT-Versionen zusammenpasst.

Deutlich seltener treten Fehler beim Download auf. Im ersten Schritt wurden bereits die Inventarlisten der Update-Sites (artifacts.xml und contents.xml) untersucht, und es wurde eine passende Paketversion gefunden. Befindet sich diese dann allerdings nicht im entsprechenden Unterordner, so kommt es zu einem Download-Fehler. Hier ist dann die Update-Site inkonsistent. Dies kann ebenfalls nur der Anbieter des Pakets beheben.

## Single-sign-on-Bibliotheken

Je nach Single-sign-on-Strategie können Umgebungsvariablen auf Bibliotheken notwendig sein. Wenn SAP GUI lediglich als 32-Bit-Anwendung installiert wird (bis SAP GUI 7.70 einzige Option), werden immer die Bibliotheken verwendet, die in den Umgebungsvariablen SNC_LIB und SNC_LIB_2 referenziert werden.

Wird Eclipse jedoch als 64-Bit-Anwendung installiert (Standardfall), so wird die in der Umgebungsvariable SNC_LIB_64 referenzierte SSO-Bibliothek verwendet.

In älteren Blog-Einträgen werden noch die Kerberos-Bibliotheken von Windows empfohlen (32 Bit: gsskrb5.dll, 64 Bit: gx64krb5.dll). Diese sind jedoch in neueren Windows-Installationen nicht mehr vorhanden und sollten auch nicht mehr verwendet werden. SAP liefert mit dem SAP GUI eine SAP CryptoLib aus. Diese liegt in 32 Bit und 64 Bit vor.

## "No repository found containing"

[https://launchpad.support.sap.com/#/notes/2186770](https://launchpad.support.sap.com/#/notes/2186770)

Ab und zu scheint es Probleme zu geben, die ADT zu aktualisieren. Im Protokoll erscheinen mehrere Fehler "No repository found containing: ...". Der Hinweis empfiehlt, die Update-Site zu entfernen, Eclipse neu zu starten und dann die Update-Site neu hinzuzufügen.

## PKIX - Certificate Error

[https://launchpad.support.sap.com/#/notes/3131747](https://launchpad.support.sap.com/#/notes/3131747)

Hier handelt es sich um einen Zertifikatsfehler. Zur Update-Site wird eine verschlüsselte Verbindung aufgebaut (HTTPS). Wenn im Unternehmensnetzwerk SSL-Verbindungen aufgebrochen werden oder es keinen gemeinsamen Keystore für interne und externe Update-Sites gibt, dann kann es zu diesem Fehler kommen. Der Hinweis gibt eine mögliche Lösung hierfür. Eine andere Möglichkeit ist die Verteilung eigener angepasster JDK.

## macOS aarch64 support & SAP GUI for Java

[https://launchpad.support.sap.com/#/notes/3251738](https://launchpad.support.sap.com/#/notes/3251738)

Die Architektur von SAP GUI und Eclipse-Installation sollte grundsätzlich mit derselben Prozessorarchitektur installiert werden. Gerade bei Apple M1 und folgend könnte es hier zu Abweichungen kommen.

## Offline-Installation -- Download ADT-Abhängigkeiten

[https://launchpad.support.sap.com/#/notes/2369308](https://launchpad.support.sap.com/#/notes/2369308)

Soll ADT offline installiert werden, müssen diverse Abhängigkeiten beachtet werden. Dieser Hinweis gibt einige Möglichkeiten für Abhilfe in diesem Fall.

## Fehler bei Anlage eines ABAP Projekts

In manchen Fällen kann es vorkommen, dass Sie bei einer Anlage eines neuen ABAP Projekts einen Fehler bekommen und die Verbindung nicht hergestellt werden kann. In solchen Fällen können die bereitgestellten Informationen aus den GUI Einstellungen nicht korrekt übernommen werden oder sind unvollständig gepflegt. Dazu sollten Sie die folgenden Dateien geprüft werden:
* [SAP UI Landscape XML](https://help.sap.com/docs/sap_gui_for_java/faf5bfb0ed2145e4bec83d73f25449d4/dccc7b2d0f7a432a9dbc38642c5ca309.html)
* [Message Server](https://help.sap.com/docs/sap_gui_for_java/faf5bfb0ed2145e4bec83d73f25449d4/1feb6e31fa40478ab58d07ecfbca72bc.html)

Hier kann es helfen, wenn Sie fehlende Informationen für den Message Server ergänzen. Sollten die Daten unbekannt sein, können Sie sich an ihren Systemadministrator wenden.