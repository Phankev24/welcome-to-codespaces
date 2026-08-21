# Terminal-jukselapp

En kort introduksjon til de mest brukte kommandoene i terminalen. Åpne terminalen i VS Code med **Ctrl + `** (backtick) eller **Terminal → New Terminal**.

## Hvor er jeg?

### `pwd` — print working directory
Viser hvilken mappe du står i akkurat nå.

```
pwd
```

## Se hva som ligger her

### `ls` — list
Lister alle filer og mapper i mappa du står i.

```
ls
```

Legg til `-la` for å se skjulte filer og mer detaljer:

```
ls -la
```

## Flytte deg mellom mapper

### `cd` — change directory
Bytter mappe. Skriv navnet på mappa du vil inn i:

```
cd mappenavn
```

Nyttige snarveier:
- `cd ..` — gå ett nivå opp
- `cd ~` — gå til hjemmemappa
- `cd -` — gå tilbake til forrige mappe

## Skrive ut tekst

### `echo` — skriv ut
Skriver det du gir den, tilbake i terminalen.

```
echo Hei verden
```

Kan også brukes til å lage en fil (`>` sender output til fil i stedet for skjerm):

```
echo Hei > hilsen.txt
```

## Lese en fil

### `cat` — concatenate / vis fil
Skriver ut innholdet i en fil.

```
cat hello.kt
```

## Lage og fjerne

### `mkdir` — make directory
Lager en ny mappe.

```
mkdir min-mappe
```

### `touch` — lag tom fil
Lager en tom fil.

```
touch notater.md
```

### `rm` — remove
Sletter en fil. **Vær forsiktig — sletting kan ikke angres i terminalen!**

```
rm gammelfil.txt
```

For å slette en mappe med innhold: `rm -r mappenavn`.

## Rydde opp

### `clear`
Tømmer skjermen. (Snarvei: **Ctrl + L**.)

## Nyttige snarveier

- **Pil opp / ned** — bla i tidligere kommandoer
- **Tab** — autofullfør fil- eller mappenavn
- **Ctrl + C** — avbryt kommando som kjører
- **Ctrl + L** — tøm skjermen
