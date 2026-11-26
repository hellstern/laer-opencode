# Godkend, hvad agenten må

Agenten har adgang til værktøjer, der kan ændre ting på din computer. Derfor har OpenCode **rettigheder** (på engelsk *permissions*), der styrer, hvad agenten må gøre uden at spørge.

## De tre muligheder

Hver handling kan have én af tre indstillinger:

| Indstilling | Betyder |
| --- | --- |
| **Allow** (tillad) | Agenten må gøre det uden at spørge |
| **Ask** (spørg) | Agenten skal spørge dig først |
| **Deny** (afvis) | Agenten må aldrig gøre det |

## Når agenten spørger dig

Når en handling står til "spørg", stopper agenten og venter på dig. Du får tre valg:

| Valg | Hvad sker der |
| --- | --- |
| **Allow once** | Agenten må gøre netop denne ene ting |
| **Allow always** | Agenten må gøre denne type ting i dette projekt fremover |
| **Reject** | Agenten må ikke. Du kan skrive en kort besked om, hvorfor, eller hvad den skal gøre i stedet |

!!! tip "Læs, før du klikker"
    Det er fristende bare at klikke ja. Men læs, hvad agenten vil gøre. Står der noget, du ikke forstår, så afvis og skriv: "Forklar mig først, hvad den kommando gør."

## Hvad står som standard?

Vær opmærksom på, at OpenCode som udgangspunkt er indstillet til udviklere, der gerne vil have agenten til at arbejde hurtigt:

- Standardagenten **må næsten alt** uden at spørge, også at rette i filer og køre kommandoer
- Den spørger, før den læser filer, der typisk indeholder hemmeligheder, og før den søger på nettet
- Den må også arbejde i mapper **uden for** dit projekt, medmindre du siger andet

Det er en af grundene til, at du altid skal arbejde i en øvelsesmappe med kopier.

## Gør agenten mere forsigtig

Du kan selv bestemme, at agenten skal spørge først. Det gør du i en lille indstillingsfil, `opencode.json`, som du lægger i projektmappen. Kopiér dette ind i en ny fil med det navn:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "permissions": [
    { "action": "edit", "resource": "*", "effect": "ask" },
    { "action": "shell", "resource": "*", "effect": "ask" }
  ]
}
```

Nu spørger agenten, før den retter i en fil (`edit`), og før den kører en kommando (`shell`). Reglerne læses oppefra og ned, og den sidste regel, der passer, vinder.

!!! warning "Gem som .json, ikke .txt"
    Notesblok på Windows gemmer gerne som `opencode.json.txt`. Vælg **Alle filer** under filtype, når du gemmer, og tjek filnavnet.

!!! example "Øvelse"
    1. Læg `opencode.json` ovenfor i din øvelsesmappe.
    2. Start en ny samtale og bed agenten om at rette en stavefejl i en af dine filer.
    3. Vælg **Reject** og skriv: "Vis mig rettelsen først, uden at gemme den."
    4. Hvad gør agenten nu?
