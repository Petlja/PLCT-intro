# PLCT Dokumentacija

PLCT ili **Petlja Learning Content Tool** je set alata koji ima za cilj da olakša kreiranje kurseva i lekcija na Petlja platformi. Ovaj projekat sadrži dokumentaciju koja će vam pomoći da se upoznate sa osnovnim funkcionalnostima PLCT-a i kako ga koristiti za izradu kurseva.

## PLCT-CLI

[PLCT-CLI](https://github.com/Petlja/PLCT-CLI) je alat komandne linije koji omogućava lakše korišćenje [Sphinx-a](https://www.sphinx-doc.org/en/master/). Glavne funkcionalnosti uključuju:

- **Preview**: Omogućava vam da pregledate kurs u lokalnom okruženju pre nego što bude objavljen na Petlji.

```bash
plct preview
```

- **Build**: Generiše HTML fajlove iz vašeg kursa bez prikaza u lokalnom okruženju. Ova komanda je pogodna za proveru da li build proces prolazi bez grešaka.

```bash
plct build
```

- **Publish**: Generiše `docs` folder koji sadrži sve potrebne datoteke za objavljivanje kursa na GitHub Pages platformi.

```bash
plct publish
```

- **Clean**: Briše generisane datoteke i vraća projekat u prvobitno stanje.

```bash
plct clean
```

## PLCT-Sphinx-Components

[PLCT-Sphinx-Components](https://github.com/Petlja/PLCT-Sphinx-Components) je set veb komponenti za Sphinx (eng. Sphinx extensions) koji omogućava strukturirani pristup pravljenju sadržaja. Među najvažnijim komponentama su **pitalice** i **notes**.

```{learnmorenote} Šta su **Notes**

Notes su važni delovi teksta koje želite posebno da istaknete. Grupisane su po tipu informacije koju sadrže:
- learnmore 
- technical
- questionnote
- suggestionnote 
- infonote
```
