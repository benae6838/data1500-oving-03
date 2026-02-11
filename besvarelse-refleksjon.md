# Besvarelse av refleksjonsspørsmål - DATA1500 Oppgavesett 1.3

Skriv dine svar på refleksjonsspørsmålene fra hver oppgave her.

---

## Oppgave 1: Docker-oppsett og PostgreSQL-tilkobling

### Spørsmål 1: Hva er fordelen med å bruke Docker i stedet for å installere PostgreSQL direkte på maskinen?

**Ditt svar:**
Med Docker kan man kjøre PostgreSQL i en isolert container, uten å installere databasen direkte på maskinen. Dette gjør det da enklere å sette opp og kjøre databaseoppsettet på ulike maskiner.
---

### Spørsmål 2: Hva betyr "persistent volum" i docker-compose.yml? Hvorfor er det viktig?

**Ditt svar:**
Persistent volum som beholder dataen din selv om containeren stopper eller blir slettet. Dette er viktig for ikke å miste dataen. 

---

### Spørsmål 3: Hva skjer når du kjører `docker-compose down`? Mister du dataene?

**Ditt svar:**
Nei. På grunn avv persistent volum så vil dataen min ikke bli borte. Kjører man docker-compose down skrur man av dataen, men dataen i det persistente volumet blir beholdt, og når man starter containerne igjen vil dataen være tilgjengelig.

---

### Spørsmål 4: Forklar hva som skjer når du kjører `docker-compose up -d` første gang vs. andre gang.

**Ditt svar:**
Første gang koden kjører vil docker bygge og starte alle containere som ligger i docker-compose.yml, når man  kjører linjen på nytt vil den starte og kjøre alle containere som ikke allerede kjører.

---

### Spørsmål 5: Hvordan ville du delt docker-compose.yml-filen med en annen student? Hvilke sikkerhetshensyn må du ta?

**Ditt svar:**
Man kan dele filen gjennom for eksempel github. Men man må passe på å ikke inkludere sensitiv infirmasjon som passord eller nøkler.

---

## Oppgave 2: SQL-spørringer og databaseskjema

### Spørsmål 1: Hva er forskjellen mellom INNER JOIN og LEFT JOIN? Når bruker du hver av dem?

**Ditt svar:**
INNER JOIN brukes når man vil hente rader som finnes i begge tabeller. Hvis første tabell ikke har en match med den andre tabellen, vil den ikke hentes. For eksempel vil man finne kun studenter som har et program, og ikke vise de studentene som ikke har et program.
LEFT JOIN henter rader fra begge tabellene uansett om det ikke er en match i den andre tabellen. Da vil de kolonnene i andre tabell være NULL. Som i første eksempel så ville man da hentet alle studenter, selv om de ikke var skrevet opp i programmer enda.
---

### Spørsmål 2: Hvorfor bruker vi fremmednøkler? Hva skjer hvis du prøver å slette et program som har studenter?

**Ditt svar:**
Vi bruker fremmed nøkler for å kunne koble en rad i en tabell til en rad i en annen tabell. Slik henger tabellene sammen. Hvis man prøver å slette en tabell msom har fremmednøkkel vil ikke databasen tilate dette.
---

### Spørsmål 3: Forklar hva `GROUP BY` gjør og hvorfor det er nødvendig når du bruker aggregatfunksjoner.

**Ditt svar:**
GROUP BY brukes til å samle rader i grupper basert på én eller flere kolonner. Det er nødvendig når man bruker aggregatfunksjoner, fordi funksjonene da beregnes per gruppe i stedet for for hele tabellen. Uten GROUP BY ville for eksempel SUM() eller AVG() regnet ut ett tall for alle radene samlet, i stedet for per kategori, som for eksempel per student.
---

### Spørsmål 4: Hva er en indeks og hvorfor er den viktig for ytelse?

**Ditt svar:**
En indeks er en datastruktur som gjør det raskere å finne rader i en tabell. Den er viktig for ytelse fordi databasen slipper å lete gjennom alle radene i tabellen når man søker, sorterer eller kobler tabeller, noe som sparer mye tid i store databaser.
---

### Spørsmål 5: Hvordan ville du optimalisert en spørring som er veldig treg?

**Ditt svar:**
For å optimalisere en treg spørring bør man hente kun nødvendige kolonner, filtrere rader med WHERE, bruke indekser på kolonner som søkes eller joines.
---

## Oppgave 3: Brukeradministrasjon og GRANT

### Spørsmål 1: Hva er prinsippet om minste rettighet? Hvorfor er det viktig?

**Ditt svar:**

[Skriv ditt svar her]

---

### Spørsmål 2: Hva er forskjellen mellom en bruker og en rolle i PostgreSQL?

**Ditt svar:**

[Skriv ditt svar her]

---

### Spørsmål 3: Hvorfor er det bedre å bruke roller enn å gi rettigheter direkte til brukere?

**Ditt svar:**

[Skriv ditt svar her]

---

### Spørsmål 4: Hva skjer hvis du gir en bruker `DROP` rettighet? Hvilke sikkerhetsproblemer kan det skape?

**Ditt svar:**

[Skriv ditt svar her]

---

### Spørsmål 5: Hvordan ville du implementert at en student bare kan se sine egne karakterer, ikke andres?

**Ditt svar:**

[Skriv ditt svar her]

---

## Notater og observasjoner

Bruk denne delen til å dokumentere interessante funn, problemer du møtte, eller andre observasjoner:

[Skriv dine notater her]


## Oppgave 4: Brukeradministrasjon og GRANT

1. **Hva er Row-Level Security og hvorfor er det viktig?**
   - Svar her...

2. **Hva er forskjellen mellom RLS og kolonnebegrenset tilgang?**
   - Svar her...

3. **Hvordan ville du implementert at en student bare kan se karakterer for sitt eget program?**
   - Svar her...

4. **Hva er sikkerhetsproblemene ved å bruke views i stedet for RLS?**
   - Svar her...

5. **Hvordan ville du testet at RLS-policyer fungerer korrekt?**
   - Svar her...

---

## Referanser

- PostgreSQL dokumentasjon: https://www.postgresql.org/docs/
- Docker dokumentasjon: https://docs.docker.com/

