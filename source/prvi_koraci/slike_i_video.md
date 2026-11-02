# Dodavanje slika i videa

## Gde se nalaze fajlovi

Pre nego što dodamo sliku ili video, pogledajmo gde se u projektu nalaze fajlovi koje koristimo u primerima ispod:

```text
source/
├── _static/
│   └── video/
│       └── sample-video.mp4      ← video
└── prvi_koraci/
    ├── img/
    │   └── sample-image.jpg      ← slika
    └── slike_i_video.md          ← ova stranica (ovde pišemo kod)
```

Ukratko:

- **Slika** stoji **pored** stranice, u folderu `img` unutar iste lekcije (`prvi_koraci`).
- **Video** stoji u zajedničkom folderu `_static/video`, na vrhu `source` foldera, koji dele sve lekcije.

### Kako čitati putanju

Putanja je opis puta **od stranice na kojoj pišemo** (`slike_i_video.md`) **do fajla** koji želimo da prikažemo. Delovi putanje su razdvojeni kosom crtom `/`, a svaki deo je jedan korak:

| Oznaka       | Značenje                                       |
|--------------|------------------------------------------------|
| `./`         | ostani u folderu u kome se nalazi stranica     |
| `../`        | izađi jedan folder iznad                       |
| `ime/`       | uđi u folder sa tim imenom                     |
| `ime.jpg`    | fajl do kog smo došli (kraj puta)              |

## Slike

Za slike preporučujemo MyST `figure` direktivu, jer omogućava širinu, alt tekst i stilizaciju:

````markdown
```{figure} ./img/sample-image.jpg
:width: 600px
:class: with-border
:alt: Opis slike
```
````

```{figure} ./img/sample-image.jpg
:width: 600px
:class: with-border
:alt: Opis slike
```

Putanja `./img/sample-image.jpg` čita se ovako:

1. `./` – krećemo iz foldera `prvi_koraci` (tu je naša stranica)
2. `img/` – ulazimo u folder `img`
3. `sample-image.jpg` – to je naša slika

Slike po pravilu čuvamo u `img` folderu unutar lekcije (na primer `source/prvi_koraci/img/`).

## Video

Za video koristimo `raw html` blok sa `<video>` tagom:

````markdown
```{raw} html
<center>
<video style="width: 100%;" controls>
  <source src="../_static/video/sample-video.mp4" type="video/mp4">
  Your browser does not support HTML video.
</video>
</center>
```
````

```{raw} html
<center>
<video style="width: 100%;" controls>
  <source src="../_static/video/sample-video.mp4" type="video/mp4">
  Your browser does not support HTML video.
</video>
</center>
```

Putanja `../_static/video/sample-video.mp4` čita se ovako:

1. `../` – izlazimo iz foldera `prvi_koraci` i dolazimo u `source`
2. `_static/` – ulazimo u folder `_static`
3. `video/` – ulazimo u folder `video`
4. `sample-video.mp4` – to je naš video

Video fajlove čuvamo u `source/_static/video/` (na primer `source/_static/video/sample-video.mp4`).

```{infonote}
Broj koraka `../` na početku putanje zavisi od toga koliko je stranica duboko u `source` folderu. Stranica u `source/prvi_koraci/` ima jedan `../`. Kada bi stranica bila u `source/lekcija/podlekcija/`, morali bismo da izađemo dva puta, pa bi putanja počinjala sa `../../_static/video/`.
```
