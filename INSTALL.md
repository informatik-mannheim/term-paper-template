# Linux

## Arch Linux (und ggf. Derivate, z.B. Manjaro)
Entscheidet man sich gegen [Overleaf](https://www.overleaf.com/) und möchte eine lokale Installation verwenden, ergeben sich folgende Voraussetzungen:

### LaTeX-Abhängigkeiten
Eine *TeX Live* Distribution befindet sich im offiziellen *extra*-Repositorium. 

Die folgenden Pakete dieser Distribution werden für das Kompilieren der Vorlage benötigt:
- `texlive-bibtexextra`
- `texlive-langgreek`
- `texlive-latexextra`
- `texlive-publishers`
- `texlive-science`

Um diese alle auf einmal zu installieren kann man folgenden Befehl verwenden:
```sh
sudo pacman -S texlive-bibtexextra texlive-langgreek texlive-latexextra texlive-publishers texlive-science
```

Möchte man stattdessen lieber *alle* in den offiziellen Repositorien verfügbaren *TeX Live*-Pakete installieren, sollte man stattdessen die Paketgruppen `texlive-most` und `texlive-lang` verwenden:
```sh
sudo pacman -S texlive-most texlive-lang
```

### Weitere Abhängigkeiten und Werkzeuge
Für die lokale Bearbeitung und Kompilierung kann man [Texmaker](https://www.xm1math.net/texmaker/) verwenden,
allerdings benötigt man zusätzlich hierzu noch `biber` um das Projekt [wie vorgesehen einzurichten und zu bauen](https://github.com/informatik-mannheim/term-paper-template#latex-projekt-unter-texmaker-einrichten).
Beide Werkzeuge finden sich ebenfalls in den offiziellen Repositorien.

```sh
sudo pacman -S biber texmaker
```


Unglücklicherweise findet sich in den offiziellen Repositorien kein *JabRef*.
Glücklicherweise gibt es allerdings Pakete im AUR.

> **WARNUNG**
>
> DAS AUR BESTEHT AUS VON NUTZERN HOCHGELADENEN INHALTEN ***UND KANN DAHER POTENTIELL MALWARE*** ENTHALTEN.
>
> ***DAHER GESCHIEHT DESSEN NUTZUNG GRUNDSÄTZLICH AUF EIGENE GEFAHR.***
>
> MÖCHTE MAN ES DENNOCH NUTZEN, SOLLTE MAN *ZUMINDEST* DIE PKGBUILD-DATEIEN DER PAKETE LESEN.
>
> Weitere Informationen zum AUR gibt es im offiziellen [Arch Linux Wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository).

Die dort verfügbaren Pakete sind:
- `jabref` - baut den *aktuellsten Tag* des [Git-Repositories](https://github.com/JabRef/jabref/) lokal.
- `jabref-git` - baut den *master-Branch* des [Git-Repositories](https://github.com/JabRef/jabref/) lokal.
- `jabref-latest` - lädt die *aktuellste kompilierte Version* aus dem [offiziellen *JabRef*-Build-Archiv](https://builds.jabref.org/master/) herunter und installiert diese.

Um eines dieser Pakete zu installieren, kann man entweder [der Anleitung aus dem Arch-Wiki folgen](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_and_upgrading_packages)
oder, falls man einen [AUR-Helper](https://wiki.archlinux.org/index.php/AUR_helpers) verwendet, das Paket wie gewohnt direkt installieren.

Möchte man z.B. `jabref-latest` installieren und benutzt [yay](https://aur.archlinux.org/packages/yay/) (potentiell relevant für Manjaro-Nutzer) kann man einfach folgendes in die Konsole eingeben:
```sh
yay -S jabref-latest
```

Falls `jabref-latest` nicht startet, könnte das Paket `ttf-dejavu` fehlen.
In diesem Fall kann man es nachinstallieren:
```sh
sudo pacman -S ttf-dejavu
```

Eine separate, lokale Installation von Java ist bei Verwendung von `jabref-latest` nicht nötig, da es eine integrierte Version mitbringt.


Möchte man die fertige Seminararbeit via der mitgelieferten Makefile bauen, so benötigt man auch `make`.
`make` sollte in den meisten Fällen bereits installiert sein, da es sich in der `base-devel` Paketgruppe befindet.
Ist das nicht der Fall, hilft ein schnelles:
```sh
sudo pacman -S make
```
