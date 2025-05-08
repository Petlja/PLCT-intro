# Kurs

Sphinx podržava različite tipove strukture fajlova koji, kroz definisanu hijerarhiju, na kraju čine jedan dokument. Mi takav dokument nazivamo kursom.
Kada govorimo o Petljinim kursevima, moramo imati na umu da nije svaki Sphinx projekat kurs, ali svaki kurs jeste Sphinx projekat.

Kursevi svoj sadržaj dele na **lekcije** i **aktivnosti**.

`Lekcije` predstavljaju celine koje se bave jednom temom i sadrže više `aktivnosti`.

## Struktura kursa

Fokusirajmo se na strukturu `source` foldera na sledećem primeru.

```
Kurs/
├── source/
│   ├── index.md
│   ├── conf.py
│   ├── uvod/
│   │   └── aktivnost.md
│   ├── lekcija/
│   │   ├──  intro_u_temu.md
│   │   └──  kviz.md/
│   ├── prvi_koraci/    
│   │    └── plct.md 
│   └── zanimljiva_tema/
│       ├── aktivnost.md
│       ├── aktivnost2.md
└──     └── kviz.md
  
```

## Glavni `index.md` fajl

Glavni `index.md` fajl je ulazna tačka u kurs. U njemu se nalaze osnovne informacije o kursu, kao i toctree koji definiše strukturu kursa.

### Table of contents

Sphinx svoju strukturu gradi na osnovu `toctree` direktive. Index fajlovi služe kao veza između različitih lekcija i aktivnosti. Evo kako izgleda ``toctree`` za strukturu opisanu iznad:

````markdown
```{toctree}
:maxdepth: 2
:hidden:

uvod/index
lekcija/index
prvi_koraci/index
zanimljiva_tema/index
```
````

Ovaj `toctree` komunicira da se, relativno u odnosu na njega, nalaze folderi `uvod`, `lekcija`, `prvi_koraci` i `zanimljiva_tema` koji sadrže index.md fajlove. 

```{infonote}
Folderi su zapravo konkretizacija lekcije a fajlovi konkretizacija aktivnosti. Lekcije svoj naziv dobijaju iz naslova `index.md` fajla.
Aktivnosti svoj naziv dobijaju iz top level naslova fajla koji ih definiše.
```

Ako odemo korak dalje i posmatramo jedan `index.md` fajl u lekciji onda u njemu imamo `toctree` koji će opisati koje sve aktivnosti se nalaze u toj lekciji. Na primer file
`zanimljiva_tema/index.md` može izgledati ovako:

````markdown
```{toctree}
:maxdepth: 2
:hidden:

aktivost
aktivnost2
kviz
```
````

Ovaj `toctree` komunicira da se u folderu `zanimljiva_tema` nalaze 3 fajla: `aktivnost.md`, `aktivnost2.md`, `kviz.md` koji predstavljaju sadržaj lekcije. 


### Iskljucivanje aktivnosti iz kursa

Za Sphinx index fajlovi mogu imati sadržaj kao i bilo koji drugi fajl. Ovo nije slučaj na Petlja platformi. Kako bismo olakšali navigaciju kroz kurs i uskladili je sa Petljinim navigacionim sistemom, `index.md` fajlove možete isključiti dodavanjem sledećeg koda (Markdown front matter) na sam vrh fajla:

````text
---
status: exclude
---
````

```{infonote}
Ovu opciju možete koristiti u bilo kojoj aktivnosti, posebno za sadržaj koji još nije završen ili je u fazi testiranja. HTML fajlovi će biti generisani, ali se u pregledima (preview) neće prikazivati.

```


### Meta podaci

Po konvencija u glavni `index.md` upisujete meta podatke o kursu. Neki od ovih podataka kao sto je **alias** bice vec upisani u `index.md` fajl. Ostale podatke kao sto su "opisi", "šta ćete naučiti" i "šta vam je potrebno" da bi ste pratili kurs prepustamo vama.


````markdown
---
alias: alias_kursa
short_descripiton: Kratak opis koji će se prikazivati naslovnoj strani kursa.
long_description: >
    <p> Opis kursa koji će se prikazivati na naslovnoj strani kursa. </p>
    <a rel="license" href="https://creativecommons.org/licenses/by/4.0/deed.sr_LATN">
    <img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png"></a>
    <br>Овај курс Фондација Петља објавила je под лиценцом <a rel="license" href="https://creativecommons.org/licenses/by/4.0/deed.sr_LATN">Creative Commons Autorstvo 4.0 Međunarodna Licenca (CC BY 4.0)</a>.
    </p>
will_learn:
    - Lista stvari koje ćete naučiti tokom kursa.
    - Jako zanimljivih stvari

needed: 
    - Racunar 
    - Specificni softver
useful:
    - Python 3.12 documentation: https://docs.python.org/3.12/
    - Google: https://google.com/

---
````