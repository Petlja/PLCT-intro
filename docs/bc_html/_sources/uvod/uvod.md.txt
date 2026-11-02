# PLCT Dokumentacija

PLCT ili **Petlja Learning Content Tool** je set alata koji ima za cilj da olakša kreiranje kurseva i lekcija na Petlja platformi. Ovaj projekat sadrži dokumentaciju koja će vam pomoći da se upoznate sa osnovnim funkcionalnostima PLCT-a i kako ga koristiti za izradu kurseva.

## Sphinx & PLCT-CLI

[Sphinx](https://www.sphinx-doc.org/en/master/) je alat napisan u python-u. Omogućava kreiranje dokumentacije zapisane u **lightweight markup** jeziku. Može genrisati HTML, PDF i druge formate.

[PLCT-CLI](https://github.com/Petlja/PLCT-CLI) je alat komandne linije koji omogućava konfiguraciju i generisanje Sphinx projekata. Glavne funkcionalnosti koje PLCT-CLI nudi su:

- **Preview**: Omogućava vam da pregledate kurs u lokalnom okruženju pre nego što bude objavljen na Petlji.

```bash
plct preview
```

- **Build**: Generiše HTML fajlove iz vašeg kursa bez prikaza u lokalnom okruženju. Ova komanda je pogodna za proveru da li build proces prolazi bez grešaka.

```bash
plct build
```

- **Publish**: Generiše `docs` folder koji sadrži sve potrebne datoteke za objavljivanje kursa na GitHub Pages platformi. (neophodno je uraditi  **plct build** pre publish-a)

```bash
plct publish
```

- **Clean**: Briše generisane fajlove.

```bash
plct clean
```

## PLCT-Sphinx-Components

[PLCT-Sphinx-Components](https://github.com/Petlja/PLCT-Sphinx-Components) je set veb komponenti za Sphinx (eng. Sphinx extensions) koji omogućava strukturirani pristup pravljenju sadržaja. Komponente grubo mogu biti podeljene u sledeće grupe:

- pitalice
- koderske komponente
- napomene (eng. notes)


## Izbor markup jezika

Kursevi se pišu u Markdown-u. Markdown je jednostavan markup jezik koji omogućava lako formatiranje teksta. Detaljnije informacije o sintaksi možete pronaći u [Markdown dokumentaciji](https://www.markdownguide.org/basic-syntax/).

```{technicalnote}
Ako ste ranije radili sa Sphinx-om, znate da fajlovi obično imaju `.rst` ekstenziju, jer Sphinx koristi reStructuredText format. U našem iskustvu, Markdown (`.md`) je poznatiji autorima, pa je rad sa njim jednostavniji. Zato koristimo Sphinx ekstenziju `myst_parser`, koja omogućava korišćenje Markdown fajlova u kursu.
```
