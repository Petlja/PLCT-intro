# Petlja PLCT Dokumentacija

Ovaj repozitorijum za cilj ima da pojasni i olaksa prve korake u izradi kurseva koristeci [Sphinx](https://www.sphinx-doc.org/) uz pomoc [PLCT-CLI](https://github.com/Petlja/PLCT-CLI/tree/main)

##  Fast Start 

Pre nego sto krenete sa izradom kursa, potrebno je pripremiti okruženje. U ovom delu ćemo proći kroz osnovne korake kako da to uradite.

### Virutalno okruženje

Zbog potencijalnih problema sa verzijama paketa ovog i drugih projekata, preporucuje se koriscenje virutalno okruzenja. Evo kako to uraditi:

```bash
python -m venv .venv
```
Ova naredba ce napraviti folder pod imenom `.venv` u trenutnom direktorijumu.


Ako koristite Windows, aktivirajte virtuelno okruženje pomoću sledeće komande:

```bash
.venv\Scripts\activate.bat
```
Nakon aktiranja okruzenja vas comand prompt ce imati prefiks `(.venv)`:

```bash
(.venv) ...
```

### Instalacija potrebih paketa

Python pakete koje su potrebne za izradu kursa se nalaze u `requirements.txt`. Da bi ih instalirali, pokrenite sledecu komandu:

```bash
pip install -r requirements.txt
```

### Pokretanje PLCT-CLI

Pregledanje kursa u lokalnom okruženju se vrši pomoću sledeće komande:

```bash
plct preview
```

Vase lekcije se prevode u HTML format, a zatim ce se kurs prikazati u vašem podrazumevanom web pretraživaču.

