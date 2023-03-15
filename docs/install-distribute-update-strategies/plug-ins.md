---
layout: page
title: Plug-ins
parent: Installation, Verteilungs- und Update-Strategien
permalink: /install-distribute-update-strategies/plug-ins/
prev_page_link: /install-distribute-update-strategies/technical-setup/
prev_page_title: Technischer Aufbau einer Eclipse-Installation
next_page_link: /install-distribute-update-strategies/install-and-distribute/
next_page_title: Installations- und Verteilungsstrategien
nav_order: 4
---

{: .no_toc}
# Plug-ins

1. TOC
{:toc}

Plug-ins wie die ADT können über die Angabe der Update-Site im Dialog Help → Install New Software zu einer bestehenden Eclipse-Plattform hinzugefügt werden. Einfacher ist jedoch die Verwendung des Eclipse Marketplace, sofern das Plug-in dort gelistet ist. Die ADT sind hier Stand 2022 leider nicht gelistet, so dass für die ADT der Weg über die Update-Site notwendig ist.

## Eclipse Marketplace

Der Eclipse Marketplace ist im Help-Menü versteckt.

![](./img/image8.png)  
<span class="img-caption" markdown=1>
*Abbildung: Einstieg in den Eclipse Marketplace*
</span>

Hier kann dann nach Plug-ins gesucht werden. Das Suchwort *ABAP* lieferte Stand 2022 in diesem Beispiel 11 Treffer.

![](./img/image13.png)  
<span class="img-caption" markdown=1>
*Abbildung: Exemplarische Suche nach Plug-ins im Eclipse Marketplace*
</span>

Jedes Plug-in besitzt auf der rechten Seite einen eigenen *Install*-Button. Gegebenenfalls müssen noch eine Lizenz bestätigt und Zertifikaten vertraut werden. Abschließend ist ein Neustart von Eclipse notwendig.

## Update-Site

Kennt man die Update-Site eines Plug-ins oder ist es nicht auf dem Eclipse Marketplace gelistet, kann auch der klassische Installationsweg verwendet werden.

![](./img/image4.png)  
<span class="img-caption" markdown=1>
*Abbildung: Installation neuer Software über das Kontextmenü*
</span>

Im Feld *Work with* wird die Update-Site eingetragen. Ist diese gültig, werden unten die dort verfügbaren Plug-ins angezeigt. Neben Webseiten kann auch eine heruntergeladene Version des Plug-ins in einer zip-Datei eine Update-Site sein. In letzterem Fall müssen Updates jedoch händisch mit einem weiteren Download durchgeführt werden.

![](./img/image14.png)  
<span class="img-caption" markdown=1>
*Abbildung: Eintragen der Update-Site*
</span>

Auch hier müssen gegebenenfalls Lizenzen akzeptiert und Zertifikaten vertraut werden. Nach einem Neustart steht das Plug-in zur Verfügung.