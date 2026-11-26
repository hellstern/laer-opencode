# Fejlfinding

## Modellen

| Problem | Løsning |
| --- | --- |
| Modellen svarer ikke eller giver en fejl | Den gratis model kan være skiftet ud. Vælg en anden gratis model |
| "Rate limit" eller "too many requests" | Du har lavet for mange kald på kort tid. Vent et minut eller skift model |
| Agenten svarer på engelsk | Skriv "Skriv altid på dansk" i din `AGENTS.md` |
| Agenten bruger ikke sine værktøjer, men beskriver bare, hvad den ville gøre | Nogle modeller er dårligere til værktøjer. Prøv en anden gratis model |
| Websøgning virker ikke eller giver fejl | Søgetjenesten kan have nået sin grænse. Vent et minut, vælg en anden søgetjeneste, eller giv agenten links i stedet. Se [Research og analyse](../spor/research.md) |
| Agenten kan ikke se mit billede eller min PDF | Modellen kan ikke læse den filtype. Skift model eller lav filen om til tekst |

## Projekter og filer

| Problem | Løsning |
| --- | --- |
| Agenten arbejder i den forkerte mappe | Tjek projektvælgeren og start en ny samtale i det rigtige projekt |
| Agenten kan ikke finde min fil | Brug `@` og vælg filen fra listen. Tjek, at filen ligger i projektmappen |
| Agenten kan ikke læse min Word- eller Excel-fil | Gem en kopi som PDF, TXT eller CSV. Se [Giv agenten filer](../daglig/filer.md) |
| `/undo` fortrød ikke ændringerne i mine filer | Det virker kun i Git-projekter. Se [Fortryd og gennemse ændringer](../daglig/fortryd.md) |
| Min `opencode.json` virker ikke | Tjek, at filen ikke hedder `opencode.json.txt`, og at alle kommaer og klammer står rigtigt. Bed agenten tjekke filen |

## Egne agenter, skills og kommandoer

| Problem | Løsning |
| --- | --- |
| Min agent vises ikke | Tjek, at filen ligger i `.opencode/agents`, og start en ny samtale |
| Agenten bruger ikke min hjælpeagent | Skriv i opgaven, at den skal bruge den, f.eks. "brug redaktoer" |
| Agenten bruger ikke min skill | Tjek, at `SKILL.md` har en `description`. Uden den kan agenten ikke se skillen |
| Min kommando findes ikke | Tjek, at filen ligger i `.opencode/commands` og ender på `.md` |

## Når intet andet virker

1. Start en ny samtale og forklar opgaven forfra.
2. Genstart OpenCode.
3. Spørg agenten: "Forklar mig i almindeligt sprog, hvad der gik galt, og hvad jeg kan gøre."
4. Skriv i Teams-kanalen med et skærmbillede af fejlen.
