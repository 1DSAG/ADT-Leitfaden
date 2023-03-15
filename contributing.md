# Inhaltsverzeichnis

- [Inhaltsverzeichnis](#inhaltsverzeichnis)
  - [Allgemeine Tips](#allgemeine-tips)
  - [Inhalte erstellen](#inhalte-erstellen)
    - [Metadaten auf den Seiten](#metadaten-auf-den-seiten)
    - [Bilder hinzufügen](#bilder-hinzufügen)

## Allgemeine Tips

- Bitte **lesen Sie diesen Leitfaden sorgfältig**, damit am Anfang nichts schief geht. Wenn Sie Fragen haben oder etwas unklar ist, können Sie uns gerne kontaktieren, damit wir diese Anleitung verbessern können.

- Seien Sie nicht schüchtern mit neuen Inhalten. Sie werden mindestens eine Rückmeldung erhalten, wenn Sie Ihre PR überprüfen. Hier wird der Inhalt nach und nach aufgebaut.

- Committen Sie oft, wenn etwas funktioniert und ein Schritt in die richtige Richtung ist, machen Sie einen Commit oder PR. Auf diese Weise können andere Mitwirkende die Änderungen sehen, und das Risiko von Konflikten beim Zusammenführen wird minimiert.

- Machen Sie sich keine Sorgen, wenn Sie auf Probleme stoßen. Wir sind eine Gemeinschaft und werden Ihnen auf jeden Fall helfen.

- Wenn Sie Inhalte von SAP oder von anderen Seiten verwenden, geben Sie dies bitte deutlich an.

## Inhalte erstellen

Hier folgt eine kurze Beschreibung um Inhalte im Leitfaden zu erstellen

### Metadaten auf den Seiten

TODO...

### Bilder hinzufügen

Jedes Kapitel hat seinen eigenen Unterordner.
Für Bilder muss ein extra Unterordner mit dem Namen `img` angelegt werden (z.B. <https://github.com/1DSAG/ADT-Leitfaden/tree/main/docs/plug-ins>).

Für Bilder sollte außerdem immer eine Bildunterschrift hinzugefügt werden. Über Markdown funktioniere das folgendermaßen:

```markdown
![](./img/image1.png)  
<span class="img-caption" markdown=1>
*Abbildung: Einstieg in die globalen Einstellungen*
</span>
```