# Godkend, hvad agenten må

Agenten har adgang til værktøjer, der kan ændre ting på din computer. Derfor har OpenCode **rettigheder** (på engelsk *permissions*), der styrer, hvad agenten må gøre uden at spørge.

## Projektmappen er agentens arbejdsområde

Den mappe, du åbner som projekt, er agentens **arbejdsområde**. Det er her, den læser, skriver og kører kommandoer, når den løser din opgave.

Men projektmappen er ikke et aflåst rum. Om agenten må læse og skrive **uden for** projektmappen, styres af en særskilt rettighed, `external_directory`. I OpenCode 2 er den som standard sat til at tillade adgang. Agenten kan altså godt nå andre mapper på din computer, hvis opgaven får den til at forsøge det.

Vil du have, at agenten spørger, før den går uden for projektmappen, skal du selv slå det til. Det ser du nedenfor.

## De tre indstillinger

Hver handling kan have én af tre indstillinger:

| Indstilling | Betyder |
| --- | --- |
| **Allow** (tillad) | Agenten må gøre det uden at spørge |
| **Ask** (spørg) | Agenten skal spørge dig først |
| **Deny** (afvis) | Agenten må ikke gøre det |

De vigtigste handlinger:

| Handling | Betyder |
| --- | --- |
| `read` | Læse filer |
| `edit` | Oprette og ændre filer |
| `shell` | Køre kommandoer på computeren |
| `external_directory` | Arbejde i mapper uden for projektet |
| `webfetch` | Hente en webside |
| `websearch` | Søge på nettet |

## Når agenten spørger dig

Når en handling står til "spørg", stopper agenten og venter på dig. Du får tre valg:

| Valg | Hvad sker der |
| --- | --- |
| **Allow once** | Agenten må gøre netop denne ene ting. Næste gang spørger den igen |
| **Allow always** | Agenten må gøre denne type ting i dette projekt fremover |
| **Reject** | Agenten må ikke. Du kan skrive en kort besked om hvorfor, eller hvad den skal gøre i stedet |

Brug **Allow once**, mens du lærer. Så ser du hver eneste handling og lærer, hvad agenten typisk vil gøre. Gem **Allow always** til handlinger, du har set mange gange og er tryg ved.

!!! tip "Læs, før du klikker"
    Det er fristende bare at klikke ja. Men læs, hvad agenten vil gøre. Står der noget, du ikke forstår, så afvis og skriv: "Forklar mig først, hvad den kommando gør."

## Hvad står som standard?

OpenCode er som udgangspunkt indstillet til udviklere, der gerne vil have agenten til at arbejde hurtigt:

- Standardagenten **må næsten alt** uden at spørge, også at rette i filer og køre kommandoer
- Den spørger, før den læser filer, der typisk indeholder hemmeligheder, og før den søger på nettet
- Den må arbejde **uden for** projektmappen, medmindre du siger andet

Det er en af grundene til, at du altid skal arbejde i en øvelsesmappe med kopier.

## Instruktion eller rettighed?

Der er to måder at fortælle agenten, hvad den ikke må. De virker meget forskelligt:

| | Instruktion | Rettighed |
| --- | --- | --- |
| **Hvor** | I din opgave eller i `AGENTS.md` | I `opencode.json` |
| **Eksempel** | "Ret aldrig i de originale filer" | `{ "action": "edit", "resource": "*", "effect": "ask" }` |
| **Hvem håndhæver** | Modellen, som kan misforstå eller glemme det | OpenCode selv, før handlingen udføres |
| **Brug det til** | Arbejdsmåde, tone og vaner | Det, der ikke må ske ved en fejl |

En instruktion er en **besked** til modellen. Den følges som regel, men ikke altid. En rettighed er en **lås** i programmet. Har du sat `edit` til `ask`, kan agenten ikke ændre en fil uden at spørge, uanset hvad modellen finder på.

Brug begge dele: instruktioner til at forklare, hvordan du vil have det, og rettigheder til at sikre det vigtigste. Du lærer om `AGENTS.md` i [Faste instruktioner med AGENTS.md](../arbejdsgange/agents-md.md).

## Gør agenten mere forsigtig

Du bestemmer selv, hvad agenten skal spørge om. Det gør du i en lille indstillingsfil, `opencode.json`, som du lægger i projektmappen. Kopiér dette ind i en ny fil med det navn:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "permissions": [
    { "action": "edit", "resource": "*", "effect": "ask" },
    { "action": "shell", "resource": "*", "effect": "ask" },
    { "action": "external_directory", "resource": "*", "effect": "ask" }
  ]
}
```

Nu spørger agenten, før den retter i en fil (`edit`), før den kører en kommando (`shell`), og før den arbejder uden for projektmappen (`external_directory`). Reglerne læses oppefra og ned, og den sidste regel, der passer, vinder. Det er den samme fil, der ligger i øvelsesmappen fra [Din første opgave](../start/foerste-opgave.md).

!!! warning "Gem som .json, ikke .txt"
    Notesblok på Windows gemmer gerne som `opencode.json.txt`. Vælg **Alle filer** under filtype, når du gemmer, og tjek filnavnet.

!!! warning "Skrevet til OpenCode 2"
    Indstillingerne på denne side er skrevet til OpenCode 2. I OpenCode 1 så filen anderledes ud, f.eks. `"permission": { "edit": "ask" }` og `bash` i stedet for `shell`. Finder du et eksempel på nettet i den gamle form, virker det ikke i OpenCode 2. Tjek din version under **Indstillinger** eller **Om** i programmet.

!!! example "Øvelse"
    1. Læg `opencode.json` ovenfor i din øvelsesmappe, eller brug mappen fra [Din første opgave](../start/foerste-opgave.md).
    2. Start en ny samtale og bed agenten om at lave en fil, `hilsen.md`, med en kort hilsen.
    3. Når agenten spørger, så vælg **Allow once**. Åbn filen og tjek den.
    4. Bed nu agenten om at rette en stavefejl i en af de andre filer.
    5. Vælg denne gang **Reject** og skriv: "Vis mig rettelsen først, uden at gemme den."
    6. Hvad gør agenten nu?
