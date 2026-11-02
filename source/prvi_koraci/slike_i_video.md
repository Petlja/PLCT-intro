# Dodavanje slika i videa

## Slike

Za slike preporučujemo MyST `figure` direktivu, jer omogućava širinu, alt tekst i stilizaciju:

````markdown
```{figure} img/sample-image.jpg
:width: 600px
:class: with-border
:alt: Opis slike
```
````

```{figure} img/sample-image.jpg
:width: 600px
:class: with-border
:alt: Opis slike
```

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

Video fajlove čuvamo u `source/_static/video/` (na primer `source/_static/video/sample-video.mp4`).

