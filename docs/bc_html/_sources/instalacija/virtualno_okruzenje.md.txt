# Virtuelno okruženje

Naša preporuka je da za potrebe razvoja kurseva koristite virtuelno okruženje. Ovo će izolovati Python pakete koje koristite od drugih instaliranih na vašem računaru i generalno olakšati rad.

Pozicionirajte se u `root` folder vašeg kursa. Ovo je folder koji sadrži `source` folder i konfiguracione fajlove. U ovom folderu možete da napravite virtuelno okruženje koje će sadržati sve potrebne pakete za rad sa vašim kursom.

Kako biste napravili virtuelno okruženje, otvorite terminal i pokrenite sledeću komandu:

```bash
python -m venv .venv
```

Ova komanda će napraviti folder `.venv` u trenutnom direktorijumu.

```markdown
Kurs/
├── .venv
├── source
│   ├── conf.py
│   └── index.md
├── requirements.txt
└── plct_config.yaml
```

Svaki put kada želite da koristite virtuelno okruženje, potrebno je da ga aktivirate. Da biste ga aktivirali, pokrenite sledeću komandu:

**Za Windows:**

```text
.venv\Scripts\activate
```

**Za Linux/MacOS:**

```shell
source .venv/bin/activate
```

Vaš terminal će dobiti prefix `.venv` u promptu, što znači da je virtuelno okruženje aktivirano.

```bash
(.venv) ... 
```

```{learnmorenote} Naziv virtuelnog okruženja

Obično se koristi naziv `.venv`, ali možete koristiti bilo koji naziv koji želite. Samo pazite na `.gitignore` fajl kako ne biste dodali folder u git repozitorijum.
```

## Instalacija potrebnih paketa

PLCT-CLI možete instalirati pomoću sledeće komande:

```bash
pip install plct-cli
```
Kursevi se mogu razlikovati po komponentama koje koriste. Svaki kurs u PLCT-u ima `requirements.txt` fajl koja sadrži sve potrebne pakete za rad sa tim kursom. Da biste ih instalirali, pokrenite sledeću komandu u terminalu:

```bash
pip install -r requirements.txt
```

## Ažuriranje virtuelnog okruženja

Ako pronađete neku Sphinx ekstenziju kou želite da koristite pri izradi kursa, potrebno je da pratite sledeće korake:

### 1. Instalirajte ekstenziju

Ekstenziju kao sto je [collapse](https://sphinx-toolbox.readthedocs.io/en/stable/extensions/collapse.html), potrebno je da instalirate koristeći `pip` alat u vase virtuelno okruženje:

```bash
pip install sphinx-toolbox
```

### 2. Dodajte ekstenziju u `conf.py` datoteku

U `conf.py` datoteci, u okviru `extensions` promenljive, dodajte naziv ekstenzije koju ste instalirali:

```python
extensions = [
    ...
    "sphinx_toolbox.collapse",
    ...
]
```

```{technicalnote}
`conf.py` je centralni konfiguracioni fajl za Sphinx. U njemu se nalaze sve potrebne informacije o projektu, kao i sve ekstenzije koje koristite. Lociran je u `source` folderu.
```

### 3. Dodajte ekstenziju u `requirements.txt` datoteku

Poslednji korak je da novu ekstenziju dodate u `requirements.txt` fajl. Ovo je važno jer će vam omogućiti da lako instalirate sve potrebne pakete kada prebacite projekat na drugi računar ili kada ga podelite sa drugim ljudima.