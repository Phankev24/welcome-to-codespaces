# Slik jobber du med øvinger på GitHub Codespaces

Hva er GitHub Codespaces?
GitHub Codespaces er et utviklingsmiljø i skyen som kjører direkte i nettleseren. Det gir deg tilgang til Visual Studio Code med alle filene 
fra prosjektet ditt, slik at du kan programmere, teste og lagre endringer uten å måtte installere noe på din egen PC.

## Hva lærer du i denne øvingen?

Etter denne øvingen skal du kunne:
- Lage din egen kopi (fork) av et GitHub-repository
- Åpne repoet i et Codespace og bli kjent med VS Code i nettleseren
- Lagre endringene dine tilbake til GitHub (commit + sync)

**Dette repoet ER øvingen** — du trenger ikke lete etter et annet. Bare følg stegene under og bruk denne siden som utgangspunkt.

Alle øvingene i semesteret følger det samme mønsteret: fork → åpne i Codespace → gjør endringer → commit og sync. Når du har fått det til én gang, kjenner du igjen flyten resten av semesteret.

I dette semesteret kommer vi til å bruke terminalen mye. Er du fersk på kommandolinja? Se [README_TERMINAL_CHEAT.md](README_TERMINAL_CHEAT.md) for en kort jukselapp med de vanligste kommandoene (`pwd`, `cd`, `ls`, `echo` osv.).

## Koster det noe å bruke Codespaces?

Codespaces er en betalt tjeneste hos GitHub, men alle studentkontoer får en romslig **gratiskvote** hver måned — nok til å dekke øvingene i dette faget uten at det koster deg noe. Kvoten måles i **core-timer** (antall CPU-kjerner × timer aktivt bruk) og **lagring** (GB pr. måned).

Bildet under viser hva den gratis kvoten inneholder i skrivende stund:

<img width="813" height="455" alt="image" src="https://github.com/user-attachments/assets/28cbcbd5-dfc1-43fb-8c41-76b5a98ea1a3" />

**Tips for å ikke gå tom for kvote:**
- Stopp Codespacet når du er ferdig for dagen (github.com/codespaces → Stop)
- Slett gamle codespaces du ikke bruker lenger
- Codespaces stopper automatisk etter 30 minutter uten aktivitet

## Del 1: Lag en fork av øvingsrepositoryet

### Steg 1: Logg inn på GitHub
Du er allerede på riktig side — det er dette repoet du skal forke. Sørg bare for at du er logget inn med din egen GitHub-konto (øverst til høyre). Har du ikke konto ennå, opprett en først på [github.com/signup](https://github.com/signup).

### Steg 2: Lag en fork
1. Klikk på **"Fork"**-knappen øverst til høyre på siden
   - Knappen ser ut som en gaffel-ikon med tallet på antall forks ved siden av
2. Du kommer nå til en side som heter "Create a new fork"
3. **VIKTIG**: La følgende innstillinger stå som de er:
   - Owner: Din egen GitHub-konto (skal allerede være valgt)
   - Repository name: La navnet være som det er
   - Description: Valgfritt, men du kan la den stå tom
   - "Copy the main branch only" skal være huket av
4. Klikk på den grønne knappen **"Create fork"**
5. Vent noen sekunder mens GitHub lager din personlige kopi
6. Du blir automatisk sendt til din egen fork når den er ferdig

### Hvordan vite at du har gjort det riktig?
- URL-en i nettleseren skal nå vise: `github.com/DITT-BRUKERNAVN/repository-navn`
- Under repository-navnet står det "forked from [original-repository]"
- Du har nå din egen kopi som du kan jobbe med!

## Del 2: Opprett GitHub Codespace

### Steg 1: Start Codespace fra din fork
1. **VIKTIG**: Sørg for at du er på DIN fork (sjekk at ditt brukernavn står i URL-en)
2. Klikk på den grønne **"Code"**-knappen (midt på siden, over fillisten)
3. I menyen som dukker opp, klikk på fanen **"Codespaces"** (ved siden av "Local" og "SSH")

### Steg 2: Opprett nytt Codespace
1. Klikk på den grønne knappen **"Create codespace on main"**
   - Hvis du allerede har et codespace, vil du se det listet opp. Du kan enten:
     - Klikke på det eksisterende for å gjenbruke det
     - Eller klikke på pluss-ikonet (+) for å lage et nytt
2. Vent mens GitHub setter opp ditt utviklingsmiljø (dette kan ta 1-3 minutter første gang)
3. Du vil se en lasteindikator og tekst som "Setting up your codespace..."

### Steg 3: Codespace er klart
1. Når lasting er ferdig, åpnes VS Code direkte i nettleseren
2. Du ser nå:
   - Filutforskeren til venstre med alle filer fra øvingen
   - En terminal nederst hvor du kan kjøre kommandoer
   - Hovedvinduet hvor du kan redigere kode
3. Du er nå klar til å begynne med øvingen!

> **💡 Pro tip:** Du kan trykke `.` (punktum) når du står på hovedsiden til et GitHub-repo for å åpne det direkte i en nettleser-basert VS Code-editor (`github.dev`). Fint for raske filredigeringer! Merk at denne varianten ikke har terminal, så for å faktisk kompilere og kjøre kode må du bruke Codespace-flyten over.

## Del 3: Kjør din første kode

I dette repoet ligger det en liten Java-fil, `Hello.java`, som skriver ut en hilsen. Repoet har en `.devcontainer/devcontainer.json` som sørger for at Codespacet ditt får en moderne Java-versjon (Java 21) automatisk — så du kan kjøre koden med én gang.

### Slik bruker du terminalen
Terminalen er vinduet nederst i VS Code hvor du skriver inn kommandoer. Hvis du ikke ser den, åpne den med **Ctrl + `** (backtick) eller via menyen: **Terminal → New Terminal**.

Kommandoer skrives inn og kjøres med **Enter**. Prøv for eksempel:

```
ls
```

Denne kommandoen viser alle filene i mappa du står i — du skal se `Hello.java` i lista.

### Kjør Java-programmet
Skriv følgende i terminalen og trykk Enter:

```
javac Hello.java
java Hello
```

Første linje kompilerer koden til en `.class`-fil, andre linje kjører den. Hvis alt fungerer, skal du se `Hei fra Codespace!` i terminalen.

### Prøv å endre koden
Åpne `Hello.java`, endre teksten inne i `System.out.println(...)` til noe eget, lagre (**Ctrl + S**), og kjør kommandoene på nytt. Da har du både redigert og kjørt din første kode i skyen.

## Del 4: Avansert — installer Kotlin og kjør en Kotlin-fil

Java er forhåndsinstallert i Codespaces, men **Kotlin** er det ikke. I denne oppgaven skal du installere Kotlin selv og kjøre `Hello.kt` som allerede ligger i repoet.

### Steg 1: Sjekk at Kotlin ikke finnes
Prøv først:

```
kotlinc -version
```

Du får sannsynligvis `command not found`. Det er forventet.

### Steg 2: Installer Kotlin med SDKMAN
SDKMAN er en pakkebehandler for JVM-språk og er forhåndsinstallert i Codespaces. Kjør:

```
sdk install kotlin
```

Svar `Y` hvis den spør om å sette versjonen som default. Når det er ferdig, sjekk at det virket:

```
kotlinc -version
```

### Steg 3: Kompiler og kjør
```
kotlinc Hello.kt -include-runtime -d Hello.jar
java -jar Hello.jar
```

Du skal nå se `Hei fra Kotlin i Codespace!` i terminalen.

### Bonus: Gjør det permanent med en devcontainer
Installasjonen med SDKMAN forsvinner hvis codespacet slettes. For at Kotlin skal være tilgjengelig automatisk hver gang, kan du legge til en `.devcontainer/devcontainer.json` med Kotlin som *feature*. Se [containers.dev/features](https://containers.dev/features) for hvordan det gjøres.

### Steg 4: Bli kjent med `.devcontainer/devcontainer.json`

Åpne fila `.devcontainer/devcontainer.json` i repoet. Dette er "oppskriften" for Codespacet ditt — GitHub leser fila hver gang miljøet bygges, og installerer det som står der. Her er de viktigste delene:

```json
{
    "image": "mcr.microsoft.com/devcontainers/java:21",  // base-image
    "features": { ... },                                  // ekstra verktøy
    "customizations": {
        "vscode": {
            "extensions": [ ... ]                         // VS Code-utvidelser
        }
    },
    "postCreateCommand": "..."                            // kjøres etter bygg
}
```

Fila er i **JSON**-format. Det betyr blant annet:
- Alle nøkler og strenger må stå i `"anførselstegn"`
- Komma mellom hvert element — **men ikke komma etter det siste**
- Krøllparenteser `{}` for objekter, hakeparenteser `[]` for lister

VS Code markerer JSON-feil med rød understreking. Hold musepekeren over for å se hva som er galt.

### Steg 5: Legg til en VS Code-extension

Under `customizations.vscode.extensions` finner du extensions som installeres automatisk. I dag ligger bare Java-pakken der. Legg til en du har lyst på — for eksempel:

- `eamodio.gitlens` — viser hvem som har skrevet hver linje kode
- `streetsidesoftware.code-spell-checker` — stavekontroll for kode og markdown
- `pkief.material-icon-theme` — penere filikoner i utforskeren

Etter endringen:

```json
"extensions": [
    "vscjava.vscode-java-pack",
    "eamodio.gitlens"
]
```

Legg merke til komma mellom linjene — men ikke etter den siste. Husk å lagre fila (**Ctrl + S**).

### Steg 6: Legg til en *feature* (f.eks. AWS CLI)

*Features* er ferdige oppskrifter for å installere verktøy som ikke ligger i base-imaget. Du finner alle offisielle features på [containers.dev/features](https://containers.dev/features).

Eksempel — legg til AWS CLI ved å utvide `features`-blokken:

```json
"features": {
    "ghcr.io/devcontainers/features/java:1": {
        "version": "21",
        "installGradle": false,
        "installMaven": false
    },
    "ghcr.io/devcontainers/features/aws-cli:1": {
        "version": "latest"
    }
}
```

**Vanlige fallgruver:**

- **Skrivefeil i URL-en** — `ghcr.io` (én `g`), ikke `gghcr.io`. Kopier fra features-siden.
- **Tallet etter kolon** (f.eks. `:1`) er *featurens major-versjon*, ikke av verktøyet. Vanligvis skal denne stå som `1`.
- **Versjonsnummeret på containers.dev/features** (f.eks. `1.1.4` ved siden av `aws-cli`) er *featurens egen release-versjon* — altså versjonen av installasjonsskriptet. Det er **ikke** verdien du skal skrive i `"version"`-feltet. Hvis du gjør det, feiler bygget fordi det ikke finnes noen AWS CLI 1.1.4.
- **`version`-feltet inne i objektet** gjelder verktøyet (AWS CLI, Java osv.). Bruk `"latest"` hvis du er usikker — ikke gjett på tall.
- **Komma mangler eller er på feil sted** — når du legger til en ny feature, må det være komma etter den forrige (men ikke etter den siste).

### Hvorfor virker det ikke med en gang?

Innholdet i `devcontainer.json` leses **kun når Codespacet bygges**. Endringer du gjør i fila trer *ikke* i kraft før du bygger containeren på nytt. En vanlig `Reload Window` eller lukk-og-åpne-fane er ikke nok.

Slik gjør du det:

1. Åpne kommando-paletten: **Ctrl + Shift + P** (Cmd + Shift + P på Mac)
2. Skriv `Rebuild Container` og velg **Codespaces: Rebuild Container**
3. Vent 1–3 minutter mens Codespacet bygges på nytt

Hvis byggingen feiler, får du et panel med byggeloggen. Feilmeldingen står nesten alltid nederst — vanligvis peker den rett på linjenummeret i `devcontainer.json` som er problemet. Velg **"Rebuild with Recovery Mode"** for å komme tilbake til et fungerende miljø hvor du kan rette fila.

Når byggingen er ferdig, kan du sjekke at ting virker:
- Ny extension: se Extensions-panelet i venstre meny (firkant-ikonet)
- Ny feature (f.eks. AWS CLI): kjør `aws --version` i terminalen

## Viktige tips

### Lagre arbeidet ditt
- Codespace lagrer automatisk endringer lokalt
- For å lagre til GitHub (anbefales jevnlig):
  1. Klikk på Source Control-ikonet i venstre meny (ser ut som forgreninger)
  2. Skriv en beskrivelse av hva du har gjort
  3. Klikk "Commit" og deretter "Sync Changes"

### Stoppe og starte Codespace
- **Stoppe**: Lukk nettleser-fanen eller gå til github.com/codespaces og klikk "Stop"
- **Starte igjen**: 
  1. Gå til github.com/codespaces
  2. Finn ditt codespace i listen
  3. Klikk på navnet for å åpne det

### Slette Codespace når du er ferdig
1. Gå til github.com/codespaces
2. Finn codespace du vil slette
3. Klikk på de tre prikkene (...) til høyre
4. Velg "Delete"
