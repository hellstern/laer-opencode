# Faste instruktioner med AGENTS.md

Hver gang du starter en ny samtale, har agenten glemt alt. Indtil nu har du derfor skrevet de samme regler i opgaven igen og igen, og du har gemt dem i `regler-kladde.md`. Nu får de en fast plads, hvor agenten selv finder dem: **AGENTS.md**.

Kender du projekter i Claude, hvor du skriver projektinstruktioner én gang, og de så gælder for alle samtaler i projektet? AGENTS.md er det samme i OpenCode.

## Fra kladde til AGENTS.md

1. Åbn mappen `case-lyngholt` i Stifinder eller Finder.
2. Omdøb `regler-kladde.md` til `AGENTS.md`. Store bogstaver i AGENTS, små i .md.
3. Start en ny samtale i OpenCode og skriv:

```text
Hvilke regler har du fået for dette projekt?
```

Agenten svarer med dine regler, uden at du har nævnt filen. Fra nu af kan du skrive kortere opgaver. "Ret ikke i referaterne" og de andre regler gælder automatisk.

## Hvad er AGENTS.md?

`AGENTS.md` er en almindelig tekstfil med faste regler, som agenten læser, **hver gang** den arbejder i projektet. Den er som en arbejdsbeskrivelse til en ny kollega.

| Placering | Gælder for |
| --- | --- |
| `AGENTS.md` i projektmappen | Kun det projekt |
| `AGENTS.md` i OpenCodes indstillingsmappe (`~/.config/opencode/`) | Alle dine projekter |

Har du både en fælles og en projektfil, bruger agenten begge. Skriv derfor ikke regler, der modsiger hinanden.

## Et eksempel

Her er et eksempel på en mere fyldig AGENTS.md til andre projekter:

```markdown
# Regler for dette projekt

## Sprog og tone
- Skriv altid på dansk
- Brug du-form og et venligt, professionelt sprog
- Undgå fagudtryk, eller forklar dem kort

## Filer
- Ret aldrig i de originale filer
- Gem altid resultater som nye filer med datoen i navnet, f.eks. rapport-2026-11-26.md

## Fakta
- Brug kun oplysninger fra filerne i mappen, medmindre jeg beder om andet
- Skriv tydeligt, hvis du er usikker eller mangler oplysninger
```

Start en ny samtale og giv agenten en opgave. Den følger nu reglerne, uden at du skriver dem.

## Lad agenten skrive den

Du kan også bede agenten om at lave filen:

```text
Lav en AGENTS.md i denne mappe. Spørg mig først om fem ting: hvem resultaterne er til, hvilken tone jeg vil have, hvordan filer skal navngives, hvad du aldrig må, og hvordan jeg vil have kilder angivet.
```

!!! tip "Hold den kort"
    AGENTS.md læses ved hver eneste opgave. Skriv kun de regler, der altid gælder. Særlige ønsker til én opgave skriver du i opgaven.

!!! info "CLAUDE.md"
    Har du brugt Claude Code, kender du måske `CLAUDE.md`. OpenCode læser også den, hvis der ikke er en `AGENTS.md` i mappen.

!!! example "Øvelse"
    1. Tilføj mindst én regel om sprog og tone til din AGENTS.md i `case-lyngholt`.
    2. Giv agenten samme opgave i to nye samtaler, én med og én uden filen (omdøb den midlertidigt til `AGENTS-pause.md`).
    3. Hvad er forskellen på de to resultater?
