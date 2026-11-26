# Research og analyse

En konsulent bruger meget tid på at finde, læse og sammenfatte information. I dette spor lærer du at lade agenten gøre grovarbejdet, mens du står for vurderingen.

## Forberedelse

Lav en mappe, `spor-research`, med en `AGENTS.md`:

```markdown
# Regler for research
- Angiv altid kilde med link eller filnavn efter hver påstand
- Skeln tydeligt mellem fakta fra kilderne og dine egne vurderinger
- Skriv "ikke fundet", hvis du ikke kan finde noget, i stedet for at gætte
- Skriv på dansk, men behold citater på originalsproget
```

## Agenten og internettet

Agenten har to værktøjer til nettet:

| Værktøj | Det gør | Kræver |
| --- | --- | --- |
| **Hent webside** (`webfetch`) | Læser en bestemt side, når du giver agenten linket | Ingenting |
| **Websøgning** (`websearch`) | Søger selv på nettet, læser resultaterne og angiver links til kilderne | At du slår det til første gang |

### Slå websøgning til

Websøgning sker gennem en ekstern søgetjeneste. Første gang agenten vil søge, spørger OpenCode, om du vil tillade websøgning, og hvilken søgetjeneste du vil bruge. Dit valg bliver husket til de næste samtaler.

| Søgetjeneste | Nøgle |
| --- | --- |
| **TinyFish** | Kræver ifølge dokumentationen ikke en nøgle. Vælg den på kurset |
| Exa, Firecrawl, Parallel, Tavily | Kræver en API-nøgle fra tjenesten |

Prøv det med denne opgave:

```text
Søg på nettet efter de seneste nyheder om EU's AI-forordning. Lav et kort resumé med tre punkter og et link til kilden efter hvert punkt.
```

Når OpenCode spørger, så tillad websøgning og vælg **TinyFish**.

!!! warning "Dine søgeord sendes ud"
    Det, agenten søger på, sendes til søgetjenesten. Søg derfor aldrig på navne på personer, kunder eller andet fortroligt.

!!! tip "Hvis websøgning ikke virker"
    Søgetjenesterne har grænser for, hvor mange søgninger du må lave. Bliver en tjeneste overbelastet, holder den pause i cirka et minut. Vent lidt, eller giv agenten links i stedet. **Hent webside** virker altid.

??? info "Søg uden at blive spurgt hver gang"
    OpenCode spørger før hver søgning, som standard. Vil du give agenten lov til at søge frit i et projekt, så tilføj denne regel i projektets `opencode.json`:

    ```json
    {
      "$schema": "https://opencode.ai/config.json",
      "websearch": { "provider": "tinyfish" },
      "permissions": [
        { "action": "websearch", "resource": "*", "effect": "allow" }
      ]
    }
    ```

    Linjen med `websearch` vælger søgetjenesten, så du ikke bliver spurgt om den. Reglen under `permissions` giver lov til alle søgninger. Vil du hellere godkende hver søgning, så skriv `ask` i stedet for `allow`.

## Projekt 1: Læs og sammenfat en webside

Find en offentlig rapport eller artikel om AI og arbejdsmarkedet, og kopiér linket.

```text
Læs denne side: [indsæt link]
Lav en fil, resume.md, med:
1. Hovedbudskabet i to sætninger
2. De fem vigtigste fund som punkter, hver med et kort citat som belæg
3. Hvem der står bag, og hvornår det er udgivet
```

## Projekt 2: Sammenlign flere kilder

Lad agenten finde kilderne selv med websøgning:

```text
Søg på nettet og find tre troværdige kilder om EU's AI-forordning, gerne fra myndigheder eller anerkendte medier. Lav en tabel i sammenligning.md over, hvad kilderne siger om: hvornår reglerne gælder, hvem de gælder for, og hvad bøderne er. Marker, hvor kilderne er uenige. Skriv til sidst, hvilke kilder du valgte og hvorfor.
```

Virker websøgning ikke, så find selv tre links og skriv "Læs disse sider:" efterfulgt af linkene i stedet for at bede agenten søge.

!!! warning "Tjek mindst ét citat"
    Åbn mindst én af kilderne selv og find et af de citater, agenten har brugt. Står det der? Det er sådan, du lærer, hvor meget du kan stole på resultatet.

## Projekt 3: Kundeanalyse til et første møde

Vælg en offentlig dansk virksomhed, f.eks. en kendt SMV. Agenten finder selv kilderne med websøgning, men giv den gerne virksomhedens hjemmeside som udgangspunkt.

Brug **Plan** først:

```text
Jeg skal til et første møde med [virksomhed] om, hvordan de kan bruge AI. Lav en plan for en kort kundeanalyse Start med virksomhedens hjemmeside [link], og søg derefter på nettet efter nyheder, årsrapporter og pressemeddelelser fra de seneste to år. Analysen skal hjælpe mig med at stille gode spørgsmål på mødet.
```

Ret planen, skift til **Build**, og bed om:

```text
Udfør planen. Gem analysen i kundeanalyse.md med disse afsnit: Kort om virksomheden, Hvad de selv siger om digitalisering, Tre mulige AI-muligheder, Fem spørgsmål til mødet, Kilder.
```

!!! tip "Gør det til en fast arbejdsgang"
    Synes du godt om resultatet, så gem opgaven som en genvejskommando, f.eks. `/kundeanalyse`. Det lærer du i [Agenter og skills](agenter-og-skills.md).

!!! example "Tjekliste"
    - [ ] Jeg har fået sammenfattet en webside med kilder
    - [ ] Jeg har slået websøgning til og fået et svar med links
    - [ ] Jeg har sammenlignet flere kilder i en tabel
    - [ ] Jeg har lavet en kundeanalyse og selv tjekket mindst ét citat
