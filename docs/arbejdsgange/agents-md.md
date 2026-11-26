# Faste instruktioner med AGENTS.md

Hver gang du starter en ny samtale, har agenten glemt alt. Skriver du hver gang "skriv på dansk, brug du-form, og gem altid som nye filer", så er det tid til en **AGENTS.md**.

## Hvad er AGENTS.md?

`AGENTS.md` er en almindelig tekstfil med faste regler, som agenten læser, **hver gang** den arbejder i projektet. Den er som en arbejdsbeskrivelse til en ny kollega.

| Placering | Gælder for |
| --- | --- |
| `AGENTS.md` i projektmappen | Kun det projekt |
| `AGENTS.md` i OpenCodes indstillingsmappe (`~/.config/opencode/`) | Alle dine projekter |

Har du både en fælles og en projektfil, bruger agenten begge. Skriv derfor ikke regler, der modsiger hinanden.

## Et eksempel

Lav en fil, der hedder `AGENTS.md`, i din øvelsesmappe med dette indhold:

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
    1. Lav en AGENTS.md med mindst tre regler, der passer til dit arbejde.
    2. Giv agenten samme opgave i to nye samtaler, én med og én uden filen (omdøb den midlertidigt til `AGENTS-pause.md`).
    3. Hvad er forskellen på de to resultater?
