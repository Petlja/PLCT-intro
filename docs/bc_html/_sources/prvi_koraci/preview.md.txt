# Prikaz kursa u lokalnom okruženju

Kako biste pregledali kurs u lokalnom okruženju, potrebno je da pokrenete sledeću komandu:

```bash
plct preview
```

Ova komanda će pokrenuti lokalni server i otvoriti kurs u vašem podrazumevanom veb pregledaču. Svaka promena koju napravite u kursu će automatski biti osvežena u pregledu.



![live update](live_update.gif)


Kada radite veće izmene u kursu, kao što su promene u strukturi, instalacija novih ekstenzija ili izmene u fajlu conf.py, preporučuje se da prvo zaustavite preview komandu i očistite trenutno stanje sledećom komandom:

```bash
plct clean
```
Zatim nastavite sa izradom kursa ponovnim pokretanjem preview komande.