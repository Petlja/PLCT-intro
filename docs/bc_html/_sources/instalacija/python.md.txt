# Instalacija Python-a

PLCT i Sphinx su napisani u Python-u, pa je potrebno da ga instalirate na vašem računaru.  
Preuzmite Python 3.10 ili noviju verziju sa [zvanične stranice](https://www.python.org/downloads/).

Dobra praksa je da dodate Python u PATH promenljivu okruženja. Ako koristite Windows, to možete uraditi tako što ćete prilikom instalacije čekirati opciju "Add Python to PATH".

## Virtuelno okruženje

Naša preporuka je da za potrebe razvoja kurseva koristite virtuelno okruženje. Ovo će izolovati Python pakete koje koristite od drugih instaliranih na vašem računaru i generalno olakšati rad.

Kako biste napravili virtuelno okruženje, otvorite terminal i pokrenite sledeće komande:

```bash
python -m venv .venv
```

Ova komanda će napraviti folder `.venv` u trenutnom direktorijumu. Da biste aktivirali virtuelno okruženje, pokrenite sledeću komandu:

Svaki put kada želite da koristite virtuelno okruženje, potrebno je da ga aktivirate. Da biste ga aktivirali, pokrenite sledeću komandu:

**Za Windows:**

```bash
.venv\Scripts\activate
```

**Za Linux/MacOS:**

```bash
source .venv/bin/activate
```

```{learnmorenote} Naziv virtuelnog okruženja

Obično se koristi naziv `.venv`, ali možete koristiti bilo koji naziv koji želite. Samo pazite na `.gitignore` fajl kako ne biste dodali folder u git repozitorijum.
```

## Instalacija potrebnih paketa

Instalacija potrebnih paketa se vrši pomoću `pip` alata. Da biste instalirali potrebne pakete, pokrenite sledeću komandu:

```bash
pip install -r requirements.txt
```

## Ažuriranje virtuelnog okruženja

Ako pronađete neku Sphinx ekstenziju koja vam se dopada i želite da je koristite, potrebno je da pratite sledeće korake:

### 1. Instalirajte ekstenziju

Ako želite da koristite [collapse](https://sphinx-toolbox.readthedocs.io/en/stable/extensions/collapse.html) ekstenziju, potrebno je da je instalirate koristeći `pip` alat:

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