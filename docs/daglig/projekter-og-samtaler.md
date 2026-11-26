# Projekter og samtaler

## Projekter

Et **projekt** er en mappe på din computer, som agenten arbejder i. Agenten ser filerne i mappen og gemmer nye filer der.

Gode vaner:

- **Én mappe pr. opgave.** Lav f.eks. en mappe til "nyhedsbrev-december" og en anden til "kundeanalyse". Så blander agenten ikke tingene sammen.
- **Kun det nødvendige i mappen.** Jo færre filer, jo lettere er det for agenten at finde det rigtige, og jo mindre kan gå galt.
- **Tjek projektnavnet.** Før du skriver en opgave, så se efter, at det rigtige projekt er valgt i projektvælgeren.

Du skifter projekt i projektvælgeren eller fra startskærmen, hvor dine seneste projekter står.

## Samtaler

Hver gang du giver agenten en opgave, sker det i en **samtale** (i OpenCode også kaldet en *session*). Agenten husker alt, hvad der er sagt i den samme samtale, men ikke det, der er sagt i andre samtaler.

| Situation | Gør dette |
| --- | --- |
| Du vil rette i det, agenten lige har lavet | Skriv videre i samme samtale |
| Du starter på en ny opgave | Start en **ny samtale** |
| Agenten er blevet forvirret eller kører i ring | Start en ny samtale og forklar opgaven forfra |
| Du vil fortsætte med noget fra i går | Find den gamle samtale i listen over samtaler |

I skrivebordsprogrammet finder du dine samtaler i sidepanelet, og du kan åbne flere samtaler i hver sin fane.

!!! tip "Lange samtaler"
    En AI-model kan kun holde en vis mængde tekst i hovedet ad gangen. Når en samtale bliver meget lang, laver OpenCode automatisk et resumé af det tidligere, så der er plads til mere. Det betyder, at detaljer fra starten af samtalen kan gå tabt. Har du en ny opgave, er en ny samtale næsten altid bedre.

## Et lille spørgsmål ved siden af

Vil du spørge om noget, uden at det bliver en del af opgaven, f.eks. "hvad betyder ordet compliance?", kan du starte beskeden med `/btw`:

```text
/btw hvad er forskellen på en CSV-fil og en Excel-fil?
```

Svaret kommer, men samtalen fortsætter, som om du ikke havde spurgt.

!!! example "Øvelse"
    1. Lav to mapper: `opgave-a` og `opgave-b`.
    2. Åbn `opgave-a` som projekt og bed agenten skrive et kort digt om kaffe i en fil.
    3. Skift til `opgave-b` og bed agenten om at lave en huskeliste til en ferie.
    4. Gå tilbage til samtalen i `opgave-a` og bed om en ekstra strofe. Husker agenten digtet?
