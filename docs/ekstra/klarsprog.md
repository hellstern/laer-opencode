# Opgave 1: Klarsprogsagenten

**Niveau:** Let · **Tid:** ca. 30 minutter · **Bygger på:** [Tre agenter, ét team](../arbejdsgange/agentteam.md)

Teamet skriver gode tekster, men de er ofte lidt lange og fulde af fagord. Du skal give teamet en fjerde hjælper: en **klarsprogsagent**, der gør teksten lettere at læse for kolleger uden teknisk baggrund.

## Det skal du bruge

- Mappen `agent-eksempler` fra [Tre agenter, ét team](../arbejdsgange/agentteam.md), åbnet som projekt i OpenCode
- En gratis model

## Opgaven

1. Opret filen `klarsprog.md` i `.opencode/agents`. Kopiér gerne `redaktoer.md` og ret i kopien.
2. Skriv indstillingerne. Klarsprogsagenten er en hjælper. Hvad skal den have lov til, og hvad må den ikke?
3. Skriv instruktionerne. Den skal:
    - skrive teksten om med korte sætninger og almindelige ord
    - forklare eller fjerne fagord og forkortelser
    - bevare alle fakta, tal og kilder præcis som de står
    - sende den omskrevne tekst tilbage til projektlederen
4. Åbn `projektleder.md`, og tilføj et trin: Efter redaktørens feedback sendes udkastet til klarsprog, før den endelige version gemmes.
5. Start en ny samtale med **projektleder**, og kør testopgaven:

```text
Skriv en kort nyhedsmail til kollegerne om, hvad Microsoft Copilot er, og hvad de skal være opmærksomme på. Brug researcher til fakta og redaktoer til feedback.
```

## Tjek dit resultat

!!! example "Tjekliste"
    - [ ] Klarsprog bliver startet af projektlederen efter redaktøren
    - [ ] Den endelige tekst har kortere sætninger end udkastet
    - [ ] Alle kilder og tal fra researcher står der stadig
    - [ ] Klarsprog har ikke selv gemt eller ændret filer. Det har projektlederen

Sammenlign udkastet med den endelige fil. Er der noget, klarsprog har ændret, som den ikke måtte?

## Vejledende løsning

!!! warning "Prøv selv først"
    Åbn først løsningen, når du har prøvet selv. Den er vejledende. Virker din agent, og overholder den reglerne i opgaven, er den lige så god.

??? success "Vejledende løsning: klarsprog.md"
    ```markdown
    ---
    description: Skriver en tekst om til klart og enkelt dansk, uden at ændre fakta, tal eller kilder
    mode: subagent
    permissions:
      - action: edit
        resource: "*"
        effect: deny
      - action: shell
        resource: "*"
        effect: deny
      - action: webfetch
        resource: "*"
        effect: deny
    ---

    Du er klarsprogsredaktør. Du gør tekster lette at læse for kolleger uden teknisk baggrund.

    Sådan arbejder du:

    1. Læs teksten, du får fra projektlederen.
    2. Skriv den om med korte sætninger, højst 20 ord pr. sætning, og almindelige ord.
    3. Forklar fagord og forkortelser første gang, de bruges, eller skriv dem om.
    4. Send den omskrevne tekst tilbage. Skriv under teksten, hvilke ord du har forklaret eller ændret.

    Regler:

    - Skriv på dansk.
    - Bevar alle fakta, tal, datoer og kilder præcis som de står.
    - Tilføj aldrig nye oplysninger.
    - Du må ikke oprette eller ændre filer. Det gør projektlederen.
    ```

    **Det nye trin i projektleder.md** kan se sådan ud. Sæt det ind mellem trin 5 og 6:

    ```markdown
    6. Send udkastet med redaktørens rettelser til subagenten klarsprog, og brug den omskrevne tekst i den endelige version.
    ```

    Husk at rette nummereringen af de næste trin.

??? tip "Hvorfor disse rettigheder?"
    Klarsprog skal kun arbejde med den tekst, den får. Den har ikke brug for nettet, og den skal ikke gemme noget, for projektlederen ejer filen. Hvis klarsprog også måtte skrive filer, kunne to agenter rette i samme fil, og så ved du ikke, hvilken udgave der er den rigtige.

## Gå videre

- Lav en `oversaetter`, der laver en engelsk udgave til nye kolleger.
- Prøv at give klarsprog en målgruppe i instruktionen, f.eks. "lagermedarbejdere" eller "ledelsen". Hvad ændrer sig?
