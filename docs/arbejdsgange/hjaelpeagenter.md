# Hjælpeagenter

En hovedagent kan sende delopgaver videre til **hjælpeagenter** (på engelsk *subagents*). Det er som en projektleder, der beder en kollega om at finde fakta, mens projektlederen selv skriver.

## Hvorfor bruge hjælpeagenter?

- **Ren start.** Hjælpeagenten starter med en tom hukommelse og får kun den delopgave, den skal løse. Det giver mere fokuserede svar.
- **Plads i hovedet.** Hovedagenten får kun hjælpeagentens resultat tilbage, ikke alle mellemregningerne. Så holder den bedre overblikket i lange opgaver.
- **Forskellige rettigheder.** En hjælpeagent, der kun skal læse, kan få forbud mod at rette i filer.

## De indbyggede hjælpeagenter

| Hjælpeagent | Gør |
| --- | --- |
| **General** | Klarer research og opgaver i flere trin |
| **Explore** | Søger i og læser filer og websider. Er sat op til ikke at redigere filer |

Hovedagenten bestemmer selv, hvornår den bruger dem. Du kan også bede om det:

```text
Brug explore til at finde alle steder i mapperne, hvor ordet "deadline" står. Lav derefter en oversigt i deadlines.md.
```

Du kan følge hjælpeagenternes arbejde i samtalen, hvor de vises som små opgaverækker.

## Dine egne hjælpeagenter

Du kan lave dine egne hjælpeagenter med deres egne instruktioner, f.eks. en "redaktør", der kun giver feedback, eller en "oversætter". Det lærer du i sporet [Agenter og skills](../spor/agenter-og-skills.md) og i uge 6 på forløbet.

!!! example "Øvelse"
    Læg tre korte tekster i en mappe. Skriv:

    ```text
    Brug en hjælpeagent for hver tekst til at finde tekstens vigtigste pointe. Saml pointerne i én fil, pointer.md.
    ```

    Kan du se i samtalen, at der arbejdes i flere hjælpeagenter?
