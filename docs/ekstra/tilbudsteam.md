# Opgave 4: Byg et tilbudsteam fra bunden

**Niveau:** Svær · **Tid:** ca. 1½ time · **Bygger på:** [Tre agenter, ét team](../arbejdsgange/agentteam.md) og gerne opgave 1 til 3

I de andre opgaver har du rettet i agenter, der fandtes i forvejen. Nu starter du fra en mappe uden agenter. Du skal designe og bygge et helt team: én hovedagent og tre hjælpere, der sammen laver et udkast til et tilbud til en rigtig kundeforespørgsel.

Opgaven ligner det, mange små virksomheder bruger tid på hver uge: Der kommer en mail fra en kunde, nogen skal finde de rigtige varer, regne prisen ud efter virksomhedens regler, tjekke det hele og skrive et tilbud, en sælger kan stå inde for.

## Casen

Birgitte Lund fra Fjordby Advokater vil have et tilbud på tæpper til tre mødelokaler. Du arbejder i salgsafdelingen hos [Lyngholt Tæpper](../start/casen.md). Alt i opgaven er opdigtet.

!!! info "Der er en hage"
    Forespørgslen kan ikke opfyldes præcis, som kunden har skrevet den. Et godt team opdager det, siger det tydeligt og foreslår et alternativ. Et dårligt team lover kunden noget, Lyngholt ikke kan holde.

## Det skal du bruge

- Hent [tilbud-opgave.zip](../filer/tilbud-opgave.zip), pak den ud, og åbn mappen `tilbud-opgave` som projekt
- En gratis model
- Papir eller et tomt dokument til at planlægge teamet
- En lommeregner til at tjekke tallene

Mappen indeholder:

| Fil | Indhold |
| --- | --- |
| `forespoergsel.txt` | Mailen fra kunden |
| `produktkatalog.md` | Lyngholts tre kontortæpper med slidklasser og farver |
| `prisliste.csv` | Priser og lagerstatus |
| `betingelser.md` | Rabat, spild, montering, levering og moms |
| `skrivestil.md` | Sådan skriver Lyngholt til kunder |
| `opencode.json` | Får agenten til at spørge dig, før den skriver i filer |

## Del 1: Planlæg teamet (ca. 15 minutter)

Byg ikke noget endnu. Læs først de fem filer, og planlæg teamet på papir. En god plan sparer dig for mange forsøg.

Teamet skal have én hovedagent og tre hjælpere:

| Agent | Type | Opgave |
| --- | --- | --- |
| `tilbudschef` | hovedagent | Den, du taler med. Planlægger, sender opgaver videre, skriver udkastet og gemmer det |
| `produktraadgiver` | hjælper | Finder det produkt, der passer bedst til kundens ønsker, og tjekker, om det kan leveres til tiden |
| `prisberegner` | hjælper | Regner prisen ud efter betingelserne og viser hvert regnestykke |
| `kontrollant` | hjælper | Tjekker det færdige udkast mod forespørgslen, prislisten og betingelserne |

Udfyld en tabel som denne for hver af de fire agenter:

| Spørgsmål | Dit svar |
| --- | --- |
| Hvilke filer skal agenten læse? | |
| Må den oprette eller ændre filer? | |
| Har den brug for nettet? | |
| Må den starte andre agenter? | |
| Hvad må den aldrig gøre? | |
| Hvad skal den sende tilbage, og i hvilken form? | |

??? tip "Hjælp til planen"
    - Kun én agent bør skrive filer. Ellers ved du ikke, hvilken udgave der er den rigtige.
    - Ingen af agenterne har brug for nettet. Alt, de skal bruge, ligger i mappen.
    - Tænk på, hvad der går galt, hvis prisberegneren også vælger produktet. Hvem tjekker så valget?
    - Kontrollanten skal være kritisk. Den skal lede efter fejl, ikke rose.

## Del 2: Byg agenterne (ca. 35 minutter)

1. Opret mappen `.opencode/agents` i `tilbud-opgave`.
2. Opret de fire filer: `tilbudschef.md`, `produktraadgiver.md`, `prisberegner.md` og `kontrollant.md`.
3. Skriv indstillingerne øverst i hver fil ud fra din plan. Se [Inde i en agentfil](../arbejdsgange/agentteam.md#inde-i-en-agentfil), hvis du er i tvivl om formen.
4. Skriv instruktionerne under. Brug din plan, og skriv det på almindeligt dansk, som til en ny kollega.

Krav til teamet:

- **Tilbudschefen** sender opgaverne i denne rækkefølge: produktrådgiver, prisberegner, kontrollant. Den gemmer udkastet i `tilbud-udkast.md` og retter det, hvis kontrollanten finder fejl.
- **Produktrådgiveren** skal vurdere slidklasse, farve og lagerstatus, og om tæppet kan leveres til tiden. Den skal foreslå et alternativ, hvis kundens ønske ikke kan opfyldes.
- **Prisberegneren** skal bruge prislisten og betingelserne og vise hvert regnestykke på sin egen linje: areal med spild, tæppe, rabat, montering, kørsel, i alt ekskl. moms, moms og i alt inkl. moms.
- **Kontrollanten** skal tjekke hvert tal, hver dato og hvert løfte i udkastet og svare med en liste over fejl. Den må ikke selv rette.
- **Udkastet** skal være mærket "UDKAST, ikke godkendt af en sælger" og følge `skrivestil.md`. Ingen agent må love rabatter eller leveringsdatoer, der ikke står i betingelserne.

!!! tip "Byg én ad gangen"
    Start med tilbudschefen og produktrådgiveren, og test dem, før du bygger de næste. Så ved du, hvor fejlen er, hvis noget går galt.

## Del 3: Kør teamet (ca. 15 minutter)

Start en ny samtale, vælg **tilbudschef** i menuen ved tekstfeltet, og skriv:

```text
Lav et udkast til et tilbud på forespørgslen fra Fjordby Advokater.
```

Følg med i samtalen. Hvilke hjælpere bliver startet, og hvad sender de tilbage?

## Del 4: Tjek og forbedr (ca. 25 minutter)

Åbn `tilbud-udkast.md`, og tjek det mod tjeklisten. Regn selv tallene efter med en lommeregner. Det er din opgave som menneske, også selvom teamet har en kontrollant.

!!! example "Tjekliste"
    - [ ] Udkastet siger tydeligt, at Lyngholt Kontor Robust i grå ikke kan leveres i januar
    - [ ] Udkastet foreslår mindst ét alternativ og forklarer, hvad kunden får og giver afkald på
    - [ ] Arealet til tæppet er 99 m2 (90 m2 plus 10 % spild), og montering er beregnet af 90 m2
    - [ ] Mængderabatten på 5 % er kun trukket fra tæppet, ikke fra montering og kørsel
    - [ ] Priserne står både ekskl. og inkl. moms
    - [ ] Udkastet nævner, at prisen er over kundens budget, eller spørger, om budgettet er med eller uden moms
    - [ ] Fjernelse af gammelt tæppe er ikke regnet med, men kunden bliver spurgt, om de ønsker det
    - [ ] Der er ingen andre rabatter, og ingen leveringsdato, der ikke kan holdes
    - [ ] Udkastet er mærket som et udkast og slutter med [Sælgerens navn]
    - [ ] Kontrollanten fandt mindst én ting at rette, eller skrev, hvad den tjekkede, og at det holdt

Mangler der flueben, så find ud af, hvilken agent der burde have fanget det, og ret dens instruktioner. Kør teamet igen i en ny samtale. De fleste skal bruge to eller tre runder.

!!! question "Spørgsmål til dig selv"
    - Hvilken agent lavede flest fejl? Skyldtes det instruktionen, rettighederne eller modellen?
    - Fangede kontrollanten de samme fejl som dig?
    - Hvad ville du ændre, før en rigtig sælger kunne bruge teamet hver dag?

## Vejledende løsning

!!! warning "Prøv selv først"
    Åbn først løsningen, når du har bygget og kørt dit eget team mindst én gang. Den er vejledende. Der er mange gode måder at dele opgaven op og skrive instruktionerne på. Klarer dit team tjeklisten, er det lige så godt som vores.

??? success "Vejledende facit: tallene"
    Kundens ønske, Lyngholt Kontor Robust i grå, er udsolgt og kommer først på lager 15. februar 2027. Efter betingelserne kan det tidligst leveres 2 uger senere, altså 1. marts 2027. Det kan derfor ikke lægges i januar, og kunden har gæster fra 1. februar.

    **Alternativ A: Lyngholt Kontor Robust i antracit.** Samme slidklasse 33 og på lager. Farven er mørkere grå.

    | Linje | Beregning | Kr. ekskl. moms |
    | --- | --- | --- |
    | Tæppe | 99 m2 × 289 kr. | 28.611,00 |
    | Mængderabat 5 % på tæppet | 28.611,00 × 5 % | -1.430,55 |
    | Montering | 90 m2 × 65 kr. | 5.850,00 |
    | Kørsel | 1 levering | 950,00 |
    | **I alt ekskl. moms** | | **33.980,45** |
    | Moms 25 % | | 8.495,11 |
    | **I alt inkl. moms** | | **42.475,56** |

    **Alternativ B: Lyngholt Kontor Basis i grå.** På lager og i grå, men kun slidklasse 32, som ikke er beregnet til mødelokaler med meget trafik.

    | Linje | Beregning | Kr. ekskl. moms |
    | --- | --- | --- |
    | Tæppe | 99 m2 × 219 kr. | 21.681,00 |
    | Mængderabat 5 % på tæppet | 21.681,00 × 5 % | -1.084,05 |
    | Montering | 90 m2 × 65 kr. | 5.850,00 |
    | Kørsel | 1 levering | 950,00 |
    | **I alt ekskl. moms** | | **27.396,95** |
    | Moms 25 % | | 6.849,24 |
    | **I alt inkl. moms** | | **34.246,19** |

    Lyngholt Uld Premium i grå kan også leveres, men koster 58.433,45 kr. ekskl. moms og er langt over budgettet. Den kan nævnes, men bør ikke være hovedforslaget.

    **Budgettet:** Kunden skriver ca. 30.000 kr. uden at sige, om det er med eller uden moms. Alternativ A er over budgettet begge veje. Alternativ B er under budgettet ekskl. moms, men over inkl. moms. Det skal udkastet spørge om.

    **Tre gode spørgsmål til kunden:** Er budgettet med eller uden moms? Skal vi fjerne det gamle tæppe (35 kr. pr. m2)? Er antracit i orden, eller er grå vigtigere end slidklassen?

??? success "Vejledende løsning: tilbudschef.md"
    ```markdown
    ---
    description: Hovedagent, der laver udkast til tilbud ud fra en kundeforespørgsel med hjælp fra produktrådgiver, prisberegner og kontrollant
    mode: primary
    permissions:
      - action: edit
        resource: "*"
        effect: ask
      - action: shell
        resource: "*"
        effect: deny
      - action: webfetch
        resource: "*"
        effect: deny
      - action: subagent
        resource: "*"
        effect: allow
    ---

    Du er tilbudschef i salgsafdelingen hos Lyngholt Tæpper. Du laver udkast til tilbud, som en sælger skal godkende, før de bliver sendt.

    Sådan arbejder du:

    1. Læs forespoergsel.txt, og skriv kundens krav som en kort liste: areal, brug, farve, tidspunkt, ydelser og budget.
    2. Send kravene til subagenten produktraadgiver, og få et anbefalet produkt og mindst ét alternativ.
    3. Send det anbefalede produkt og alternativet til subagenten prisberegner, og få en beregning for hver.
    4. Skriv udkastet i tilbud-udkast.md efter skrivestil.md.
    5. Send udkastet til subagenten kontrollant.
    6. Ret alle fejl, kontrollanten finder. Er du uenig i en fejl, så skriv hvorfor under udkastet.
    7. Afslut med tre linjer til mig: hvad du anbefaler, hvad kontrollanten fandt, og hvad en sælger skal tage stilling til.

    Udkastet skal indeholde:

    - Overskriften "UDKAST, ikke godkendt af en sælger"
    - Kundens ønske i én sætning
    - Hvad vi kan og ikke kan levere, og hvorfor
    - En pristabel for hvert forslag, ekskl. og inkl. moms
    - Højst tre spørgsmål til kunden
    - Gyldighed: 30 dage fra i dag
    - [Sælgerens navn] til sidst

    Regler:

    - Skriv på dansk.
    - Brug kun oplysninger fra filerne i mappen. Opfind aldrig priser, datoer eller produkter.
    - Lov aldrig rabatter eller leveringsdatoer, der ikke står i betingelser.md.
    - Du sender aldrig noget til kunden. Du laver kun et udkast.
    ```

??? success "Vejledende løsning: produktraadgiver.md"
    ```markdown
    ---
    description: Finder det tæppe, der passer bedst til kundens krav, og tjekker lager og leveringstid
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

    Du er produktrådgiver hos Lyngholt Tæpper. Du anbefaler produkter, men du regner ikke priser ud og skriver ikke til kunden.

    Sådan arbejder du:

    1. Læs kravene, du får fra tilbudschefen, og læs produktkatalog.md, prisliste.csv og afsnittet om levering i betingelser.md.
    2. Vurder hvert produkt og hver farve mod kravene: slidklasse, farve, lagerstatus og om det kan leveres til tiden.
    3. Svar med:
       - Kundens ønske, og om det kan opfyldes. Hvis ikke, så hvorfor
       - Et anbefalet produkt med varenummer og begrundelse
       - Mindst ét alternativ med varenummer, og hvad kunden får og giver afkald på
       - Det, du er usikker på

    Regler:

    - Skriv på dansk.
    - Brug kun produktkatalog.md, prisliste.csv og betingelser.md.
    - Slidklasse 32 er ikke beregnet til mødelokaler med meget trafik. Sig det, hvis du foreslår den.
    - Du må ikke oprette eller ændre filer.
    ```

??? success "Vejledende løsning: prisberegner.md"
    ```markdown
    ---
    description: Beregner prisen på et tilbud efter prislisten og betingelserne og viser hvert regnestykke
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

    Du er prisberegner hos Lyngholt Tæpper. Du regner priser ud, men du vælger ikke produkter.

    Sådan arbejder du:

    1. Læs prisliste.csv og betingelser.md, før du regner.
    2. Regn for hvert produkt, du får, i denne rækkefølge, og vis regnestykket på hver linje:
       - Areal til tæppe: areal, der skal dækkes, plus 10 % spild
       - Tæppe: areal med spild × pris pr. m2
       - Mængderabat: 5 % af tæppet, hvis der købes mere end 80 m2 tæppe
       - Montering: areal, der skal dækkes, × 65 kr.
       - Kørsel: 950 kr. pr. levering
       - I alt ekskl. moms
       - Moms: 25 %
       - I alt inkl. moms
    3. Skriv beløb med to decimaler og punktum som tusindtalsskilletegn, f.eks. 28.611,00 kr.

    Regler:

    - Skriv på dansk.
    - Rabatten gælder kun tæppet, ikke montering, fjernelse eller kørsel.
    - Regn ikke fjernelse af gammelt tæppe med, medmindre kunden har bedt om det.
    - Giv aldrig andre rabatter.
    - Regn hvert tal to gange. Er du i tvivl, så skriv det.
    - Du må ikke oprette eller ændre filer.
    ```

??? success "Vejledende løsning: kontrollant.md"
    ```markdown
    ---
    description: Tjekker et tilbudsudkast mod forespørgslen, prislisten og betingelserne og finder fejl
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

    Du er kontrollant hos Lyngholt Tæpper. Din opgave er at finde fejl, før en kunde gør det. Du retter ikke selv.

    Sådan arbejder du:

    1. Læs tilbud-udkast.md, forespoergsel.txt, prisliste.csv, betingelser.md og skrivestil.md.
    2. Tjek:
       - Hvert tal: Regn det efter selv
       - Hver dato og leveringstid: Kan den holdes efter betingelserne og lagerstatus?
       - Hvert løfte: Står det i betingelserne?
       - Kundens krav: Er hvert krav besvaret, også når svaret er nej?
       - Skrivestilen: Er udkastet mærket som udkast, og er der højst tre spørgsmål?
    3. Svar med en nummereret liste over fejl. For hver fejl: hvad der står, hvad der burde stå, og hvilken fil der siger det.
    4. Finder du ingen fejl, så skriv, hvad du har tjekket, punkt for punkt.

    Regler:

    - Skriv på dansk.
    - Vær kritisk. Du skal ikke rose udkastet.
    - Du må ikke oprette eller ændre filer.
    ```

??? tip "Hvorfor er teamet bygget sådan?"
    - **Kun tilbudschefen skriver filer,** og den spørger dig først. Så er der én udgave af udkastet, og du ser hver ændring.
    - **Ingen af agenterne har nettet.** Priser og betingelser skal komme fra Lyngholts egne filer, ikke fra en webside.
    - **Rådgiveren vælger, beregneren regner.** Hvis den samme agent både vælger og regner, er der ingen, der stiller spørgsmål ved valget.
    - **Kontrollanten retter ikke selv.** Den finder fejl, og tilbudschefen retter. Det er det samme princip som fire øjne på en arbejdsplads.
    - **Du er den sidste kontrol.** Sprogmodeller kan regne forkert, også når de viser regnestykket. Derfor står der i opgaven, at du selv skal regne efter.

## Gå videre

- Tilføj en femte agent, `korrektur`, der kun tjekker udkastet mod `skrivestil.md`.
- Lav en kommando, f.eks. `/tilbud`, der starter tilbudschefen med den rigtige opgave. Se [Agenter og skills](../spor/agenter-og-skills.md).
- Skriv en ny forespørgsel fra en anden kunde, f.eks. 60 m2 i beige til et kontor, og se, om teamet klarer den uden ændringer.
