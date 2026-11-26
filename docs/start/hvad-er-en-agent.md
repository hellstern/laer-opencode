# Hvad er en AI-agent?

## Fra chat til agent

Når du chatter med en AI, svarer den med tekst. Du gør resten selv: kopierer, indsætter, gemmer og retter.

En **agent** er en AI, der også kan **handle**. Den har adgang til en række værktøjer, f.eks.:

| Værktøj | Det betyder |
| --- | --- |
| Læse filer | Agenten kan åbne og læse filerne i din mappe |
| Skrive filer | Agenten kan lave nye filer og rette i eksisterende |
| Hente websider | Agenten kan læse en side på nettet, når den får et link |
| Søge på nettet | Agenten kan selv søge og angive links til kilderne (skal slås til første gang) |
| Køre kommandoer | Agenten kan starte små programmer på din computer |
| Starte hjælpeagenter | Agenten kan sende en delopgave videre til en anden agent |

Agenten arbejder i en løkke: Den læser opgaven, laver en plan, bruger et værktøj, ser på resultatet og beslutter næste skridt. Det fortsætter, indtil opgaven er løst, eller den har brug for dig.

## Et eksempel

Forestil dig, at du har en mappe med 12 mødereferater og vil have en oversigt over alle beslutninger.

**Med en chat:** Du åbner hvert referat, kopierer teksten ind, beder om beslutningerne, kopierer svaret ud i et dokument og gentager det 12 gange.

**Med en agent:** Du skriver én opgave:

```text
Læs alle referaterne i denne mappe. Lav en fil, beslutninger.md, med en tabel over alle beslutninger: dato, beslutning og hvem der er ansvarlig.
```

Agenten åbner selv filerne, samler beslutningerne og gemmer resultatet. Du læser det igennem bagefter.

![Sammenligning: Med en chat gentager du selv fire trin for hvert af de 12 referater, i alt 48 håndgreb. Med en agent skriver du én opgave, agenten åbner filerne, samler beslutningerne og gemmer beslutninger.md, og du kontrollerer resultatet. 2 håndgreb for dig.](../billeder/chat-vs-agent.svg)

Forskellen er ikke, at agenten er klogere end chatten. Det kan sagtens være den samme model. Forskellen er, at agenten har **værktøjer**: Den kan selv læse og skrive filer og gentage arbejdet for hver fil. Dit arbejde flytter fra at kopiere tekst til at give en god opgave og kontrollere resultatet.

## Hvad er OpenCode?

OpenCode er et program, der giver en AI-model de værktøjer, den skal bruge for at være en agent. Det er:

- **Gratis og open source.** Koden er offentlig, og du betaler ikke for programmet.
- **Uafhængigt af modellen.** Du kan bruge mange forskellige AI-modeller, også gratis modeller, der følger med.
- **Lavet til udviklere, men brugbart for alle.** OpenCode kalder sig en "coding agent", men værktøjerne virker lige så godt på tekster, regneark og rapporter.

OpenCode findes som skrivebordsprogram, som terminalprogram og som webudgave. På kurset bruger vi **skrivebordsprogrammet**, fordi det har knapper og menuer i stedet for tekstkommandoer.

## Du er stadig chefen

En agent er hurtig, men den kan tage fejl. Den kan misforstå opgaven, finde på fakta eller rette i en fil, du ikke havde tænkt dig. Derfor:

- Giv agenten en klar opgave og en afgrænset mappe at arbejde i
- Læs altid resultatet igennem, før du bruger det
- Brug godkendelser, så agenten spørger, før den gør noget vigtigt

Du lærer alle tre ting i del 2.

!!! example "Øvelse: Find din egen opgave"
    Skriv tre opgaver ned fra dit arbejde, hvor du i dag kopierer tekst frem og tilbage mellem en AI og dine dokumenter. Gem listen. Du skal bruge den senere i kurset.
