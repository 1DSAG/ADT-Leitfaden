# DSAG's ADT-Leitfaden

![GitHub repo size](https://img.shields.io/github/repo-size/1DSAG/ADT-Leitfaden)
![GitHub contributors](https://img.shields.io/github/contributors/1DSAG/ADT-Leitfaden)
![GitHub](https://img.shields.io/github/license/1DSAG/ADT-Leitfaden)
![GitHub stars](https://img.shields.io/github/stars/1DSAG/ADT-Leitfaden?style=social)
![GitHub forks](https://img.shields.io/github/forks/1DSAG/ADT-Leitfaden?style=social)

dies ist nicht der Leitfaden selbst (dieser ist über <https://1dsag.github.io/ADT-Leitfaden> erreichbar), sondern das zugehörige Repository mit Anweisungen wie man zum Leitfaden beitragen kann.

Der DSAG ADT Leitfaden ist ein lebendiges Dokument 👨‍💻 - es lebt von und mit seiner Community 🥳.

Der Leitfaden ist in `markdown` (Variante `kramdown`) geschrieben und wird mittels `jekyll` in `GitHub Pages` (<https://1dsag.github.io/ADT-Leitfaden>) bereit gestellt.

## Inhalte

- [DSAG's ADT-Leitfaden](#dsags-adt-leitfaden)
  - [Inhalte](#inhalte)
  - [Erste Schritte](#erste-schritte)
    - [Schnellstart mit GitHub Web-Editor](#schnellstart-mit-github-web-editor)
    - [Entwicklung mit Docker-Container](#entwicklung-mit-docker-container)
      - [Installation Steps Docker Container](#installation-steps-docker-container)
    - [Lokale Installation](#lokale-installation)
      - [Vorbedingungen für Windows](#vorbedingungen-für-windows)
      - [Installationsschritte für Lokale Installation](#installationsschritte-für-lokale-installation)
  - [Mitwirken](#mitwirken)
  - [Lizenzierung](#lizenzierung)

## Erste Schritte

### Schnellstart mit GitHub Web-Editor

:point_right: Keine Lokale Installation  
:point_right: Alles im Browser  
:point_right: Vorschau nach jedem Commit

----

Der [webbasierte Editor](https://docs.github.com/en/codespaces/the-githubdev-web-based-editor) ist eine IDE, die vollständig in Ihrem Browser ausgeführt wird. Mit dem webbasierten Editor können Sie durch Dateien und Quellcode-Repositories von GitHub navigieren und Codeänderungen vornehmen und übertragen. Sie können jedes Repository, jeden Fork und jede Pull-Anfrage mit dem Editor öffnen.
Außerdem können Sie Markdown-Dateien während der Bearbeitung in der Vorschau anzeigen.
Dies macht den Einstieg sehr einfach, da keine lokale Installation erforderlich ist.
Sie können das Endergebnis nicht sofort sehen, aber auch das kann GitHub für Sie generieren.

1. Fork erstellen

![Fork erstellen](img/00-fork.png)

2. Navigieren Sie zu dem erstellten Fork

![Zu Fork springen](img/01-jump-to-fork.png)

3. Drücken sie `.` auf Ihrer Tastatur um in die IDE zu wechseln

4. Erstellen Sie einen neuen Branch

![Branch erzeugen](img/02-create-new-branch.png)

5. Vergeben Sie einen Namen für den Branch

![Branch Namen vergeben](img/03-branch-name.png)

6. Fangen sie an zu schreiben

Under `/docs` is the documentation. Just start editing or create a new folder for a new topic

7. Vorschau der Seite

Sie können sich die finale Seite auch auf GitHub ansehen.

Wechseln Sie einfach in die Einstellungen Ihres Repositories und dann auf `Pages`.
Der Link dahin setzt sich wie folgt zusammen <https://github.com/YOURUSERNAME/ADT-Leitfaden/settings/pages>.
Wählen Sie Ihren Branch aus auf dem Sie gerade arbeiten und wählen Sie den `docs` Ordner.
Nachdem Sie gespeichert haben, dauert es ein paar Minuten bis die Seite unter der angegeben URL erreichbar ist.
Von da an wird die Seite nach jedem Commit neu erzeugt.

![fork a github project](img/04-publish-branch.png)

### Entwicklung mit Docker-Container

:point_right: Nur Visual Studio Code und Docker werden benötigt
:point_right: Sofortige Vorschau ihrer Änderungen
:point_right: Run linting before commiting  

----

This is the easiest way to have your development environment ready in no time.
You get a ready to use configured Debian Container which is transparently used by Visual Studio Code.

#### Installation Steps Docker Container

Install the following programs:

* [Visual Studio Code](https://code.visualstudio.com/)
* [Remote Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
* [Docker](https://code.visualstudio.com/docs/remote/containers)

Clone the repository with the command _[Remote-Containers: Clone Repository in Container Volume...](https://code.visualstudio.com/docs/remote/containers-advanced#_use-clone-repository-in-container-volume)_

This will

* Klonen sie das Repository in einem Container-Volume
* Erzeugen Sie das Docker Abbild
* Starten Sie den Docker Container und weisen Sie die erforderlichen Ports zu
* Mounten Sie das erstellte Container Laufwerk
* Install the required npm packages
* Install the required ruby gems

The only thing left to do is open the console in Visual Studio Code (it is attached to the running Development Container), navigate into the docs folder and start the Development Server:

```shell
cd docs
bundle exec jekyll serve --livereload
```

### Lokale Installation

:point_right: Same as Docker Container  
:point_right: Complete Control over Enviroment  

----

#### Vorbedingungen für Windows

* Install <https://chocolatey.org/>
* Install MSYS2 `choco install msys2` <https://chocolatey.org/packages/msys2>
* Install Ruby `choco install ruby` <https://chocolatey.org/packages/ruby>
* Update Build Toolchain `ridk install 3`
* see setup local github pages site 😉

#### Installationsschritte für Lokale Installation

* make sure, `ruby` 2.7 is installed on your system
* clone the repo
* switch to the document base
  `$ cd docs`
* `$ bundle install`  
  for installing the `github-pages` jekyll incarnation
* start the local gh-pages instance, including automatic browser live-reload

  ```shell
  bundle exec jekyll serve --livereload
  Configuration file: /Users/you/ADT-Leitfaden/docs/_config.yml
              Source: /Users/you/ADT-Leitfaden/docs
         Destination: /Users/you/ADT-Leitfaden/docs/_site
   Incremental build: disabled. Enable with --incremental
        Generating...
         Jekyll Feed: Generating feed for posts
                      done in 0.233 seconds.
   Auto-regeneration: enabled for '/Users/you/ADT-Leitfaden/docs'
   LiveReload address: http://127.0.0.1:35729
      Server address: http://127.0.0.1:4000/
    Server running... press ctrl-c to stop.
  ```

* point your web browser to <http://localhost:4000>

## Mitwirken

Alle Informationen über den Entwicklungsprozess und bewährte Verfahren für die Erstellung von Inhalten finden Sie unter [Mitwirken](contributing.md)

## Lizenzierung

Dieses Projekt verwendet die CC BY 4.0 Lizenz : [LICENSE](LICENSE).
