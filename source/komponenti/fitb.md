# Popuni tekst koji nedostaje (Fill in the blank) 

U ovoj vrsti pitanja u kojoj se traži da se popuni prazno mesto u tekstu. Broj praznih mesta može biti proizvoljan, a tačan odgovor tretira se kao regularni izraz (regex).

Primer sa jednom prazninom:

````markdown
```{fitb}
:answer: OpenAI

The GPT-3 model is developed by |blank|. 
```
````

```{fitb}
:answer: OpenAI

The GPT-4o model is developed by |blank|. 
```

Primer sa više tačnih odgovora:

````markdown
```{fitb}
:answer: 9|^[Dd]evet$|^[Дд]евет$

Koliko je 3²? |blank|
```
````

```{fitb}
:answer: 9|^[Dd]evet$|^[Дд]евет$

Koliko je 3²? |blank|
```

Primer sa više praznina i više tačnih odgovora:

````markdown
```{fitb}
:answer: [Bb]ug, [Ff]eature

It's not a |blank| it's a |blank|.
```
````

```{fitb}
:answer: [Bb]ug, [Ff]eature

It's not a |blank| it's a |blank|.
```