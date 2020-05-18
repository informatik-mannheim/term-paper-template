# Vorlage für Seminararbeiten mit LaTeX

Diese Vorlage ist für Seminararbeiten mit LaTeX an der Hochschule Mannheim gedacht. Sie erhebt keinen Anspruch darauf, den Wünschen aller Professoren zu entsprechen. Klären Sie daher immer im Voraus mit Ihrem Betreuer, ob die Vorlage seinen Vorstellungen entspricht.

Diese Vorlage wurde entwickelt von [Prof. Thomas Smits](http://www.smits-net.de).


### Cloud-Dienste

Diese Vorlage wurde bereits von Studierenden erfolgreich bei Cloud-Diensten eingesetzt, mit denen man LaTeX-Dokumente schreiben, kompilieren und verwalten kann. Positive Erfahrungsberichte liegen bisher mit [Overleaf](https://www.overleaf.com) vor. Eine Anleitung zu Overleaf finden Sie weiter unten.


## Werkzeuge, Dateiformat

Zum Erzeugen der fertigen Arbeit dient das `Makefile` im Verzeichnis `/tex`. Sie benötigen hierzu das Werkzeug `make`, das auf Linux und MacOS standardmäßig installiert ist.

Sie können die Datei auch von Hand compilieren. Gehen Sie hierzu in das Verzeichnis `/tex` und geben Sie folgende Kommandos nacheinander ein:

    pdflatex seminararbeit.tex
    biber seminararbeit
    pdflatex seminararbeit.tex
    pdflatex seminararbeit.tex
    pdflatex seminararbeit.tex

Sie können auch eine integrierte Entwicklungsumgebung verwenden. Hierbei haben sich folgende bewährt:

  * [TeXnicenter](http://www.texniccenter.org/) für Windows
  * [Texmaker](http://www.xm1math.net/texmaker/) für Windows, MacOS und Linux

Außerdem müssen sie LaTeX auf Ihrem Rechner installieren. Bei Linux erfolgt dies einfach über den Paketmanager der verwendeten Distribution. Für Windows und MacOS empfehlen sich:

  * [MikTeX](http://miktex.org/) für Windows
  * [MacTeX](http://tug.org/mactex/) für MacOS

Für die Verwaltung der Literaturliste wird das BibTeX-Format verwendet (Datei `literatur.bib`). Obwohl Sie diese Datei auch von Hand bearbeiten können, empfiehlt es sich, hierfür ein Werkzeug einzusetzen. Bewährt haben sich:

  * [JabRef](http://jabref.sourceforge.net/) für Windows, MacOS und Linux
  * [BibDesk](http://bibdesk.sourceforge.net/) für MacOS

Achten Sie darauf, die Dokumente im UTF-8-Format abzulegen. Nur so ist eine plattformunabhängige Verwendung gewährleistet. Die Vorlagen hier sind ebenfalls im UTF-8-Format.

Verwenden Sie auf jeden Fall ein Werkzeug, um die Literatur zu verwalten. BibTex-Dateien von Hand zu bearbeiten ist extrem fehleranfällig.


## Aufbau der Vorlage im Verzeichnis `tex`

Die Vorlage besteht aus einer einzigen Datei, die Sie teilweise nach Ihren Bedürfnissen anpassen müssen bzw. mit Ihren Inhalten füllen.

Anpassen müssen Sie die folgenden Dateien

  * `seminararbeit.tex` - Hauptdokument. Hier müssen Sie Ihren Text hineinschreiben.
  * `literatur.bib` - Literaturdatenbank im BibTeX-Format.

Normalerweise nicht verändern müssen Sie

  * `preambel.tex` - Einstellungen zum Dokument.

Neben den Dateien gibt es noch zwei Ordner

  * `/img` - Ablageort für die verwendeten Bilder
  * `/src` - Ablageort für die verwendeten Quelltexte


## Ergebnisse im Ordner `result`

Die Ergebnisse finden sich im Ordner `result`. Zum einfacheren Verständnis ist hier ein fertiges Dokument, das aus den Quellen erzeugt wurde, eingecheckt.


## LaTeX-Projekt unter Overleaf einrichten

 * Laden Sie die ZIP-Version des Projektes [hier](https://github.com/informatik-mannheim/term-paper-template/raw/master/term-paper-overleaf.zip) herunter.
 * Melden Sie sich bei [Overleaf](https://www.overleaf.com) an und loggen Sie sich ein.
 * Gehen Sie auf "New Project" und wählen Sie "Upload Project"
 * Laden Sie die ZIP-Datei hoch.
 * Sie werden jetzt möglicherweise Compile-Fehler bekommen, aber keine Panik, dies liegt daran, dass Overleaf nicht weiß, welches das Hauptdokument ist
 * Wählen Sie das Overleaf Logo oben links, um das Einstellungsmenue aufzurufen und stellen Sie die Option "Main document" auf `seminararbeit.tex`
 * Wählen Sie nun in der Dateiliste ebenfalls `seminararbeit.tex`
 * Drücken Sie auf "Recompile" - das Projekt sollte jetzt bauen

## LaTeX-Projekt unter Texmaker einrichten

[Texmaker](https://www.xm1math.net/texmaker/) unterstützt alle Betriebssysteme.

  * Öffnen Sie die Datei `seminararbeit.tex` mit Texmaker
  * Gehen Sie auf "Options" -> "Define current document as 'Master Document'"
  * Gehen Sie auf "Options" -> "Configure Texmaker"
    * Tragen Sie unter "Commands" -> "Bib(la)tex" als Kommando `biber %` ein<br><img src="https://github.com/informatik-mannheim/thesis-template/raw/master/latex/images/biber.png" width="400">
    * Wählen Sie unter "Quick Build" die Option "PdfLaTeX + Bib(la)tex + BdfLaTeX (x2) + View Pdf<br><img src="https://github.com/informatik-mannheim/thesis-template/raw/master/latex/images/quick_build.png" width="400">
  * Wählen Sie in der Menuezeile "Quick Build" aus<br><img src="https://github.com/informatik-mannheim/thesis-template/raw/master/latex/images/run.png" width="150">
  * Klicken Sie auf den Pfeil links von "Quick Build"
  * Das Dokument sollte gebaut werden und rechts im Bildschirm erscheinen



## Latex-Projekt unter TexnicCenter einrichten

Ab der Version 2 von TexnicCenter wird das UTF-8-Format richtig unterstützt.

  * Öffnen Sie die Datei `seminararbeit.tex` mit TexnicCenter
  * Projekt / Erzeugen mit aktueller Datei als Hauptdatei
  * "verwendet BibTex" ankreuzen
  * Sprachinformation für die Rechtschreibkorrektur setzen

Sie können dann beispielsweise bequem auf die Dokumentstruktur, Dateien und
Literaturreferenzen zugreifen.
