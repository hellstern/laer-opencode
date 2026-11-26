# Plan og Build

OpenCode har to indbyggede hovedagenter, som du kan skifte imellem:

| Agent | Hvad den gør | Brug den når |
| --- | --- | --- |
| **Build** | Standardagenten. Den læser, skriver og retter filer og kan køre kommandoer | Du ved, hvad du vil have, og agenten skal udføre det |
| **Plan** | Undersøger opgaven og foreslår en fremgangsmåde, før der bliver gjort noget | Opgaven er stor eller uklar, og du vil gennemgå fremgangsmåden først |

Du vælger agent i menuen ved tekstfeltet. Det står hele tiden, hvilken agent der er aktiv.

## Plan er et værktøj til at gennemgå fremgangsmåden

Plan er lavet til at tænke, før der handles. Den læser dine filer, stiller spørgsmål og beskriver, hvordan opgaven kan løses. Så kan du rette fremgangsmåden, inden der bliver lavet noget.

Plan er sat op til ikke at redigere dine almindelige projektfiler. Men den er ikke en garanti:

- Plan kan gemme sine egne planfiler, hvis du beder om det
- Kommandoer styres stadig af dine rettigheder, og en kommando kan i princippet ændre filer
- Dine egne indstillinger i `opencode.json` kan ændre, hvad agenterne må

Skal du være sikker på, at intet bliver ændret, så brug rettigheder, f.eks. `edit` og `shell` sat til `ask`, og arbejd på kopier. Se [Godkend, hvad agenten må](../daglig/godkendelser.md).

## Arbejdsgangen: Planlæg, ret, udfør

1. **Vælg Plan** og beskriv opgaven.
2. **Læs planen.** Er der trin, der mangler, eller trin, du ikke vil have?
3. **Ret planen** i samme samtale: "Drop trin 3. Tilføj et trin, hvor du tjekker datoerne."
4. **Skift til Build** og skriv: "Udfør planen."

Det tager et par minutter ekstra, men du undgår, at agenten bruger lang tid på noget forkert.

## Eksempel

Bed først agenten om at lave en fil med opdigtede deltagere. Vælg **Build** og skriv:

```text
Lav en fil, deltagere.csv, med 25 opdigtede deltagere: fornavn, efternavn og kursusdato. Brug almindelige danske navne, men ingen rigtige personer.
```

Skift derefter til **Plan** og skriv:

```text
Jeg skal lave et kursusbevis til hver deltager i @deltagere.csv. Lav en plan for, hvordan du laver ét bevis pr. deltager som PDF. Gør ikke noget endnu.
```

Agenten svarer med en plan i trin. Måske foreslår den at lave en skabelon først, så du kan godkende layoutet. Ret planen, og skift derefter til **Build**.

!!! warning "Fiktive data i øvelserne"
    Brug aldrig en rigtig deltagerliste i en øvelse med en gratis model. Navne er personoplysninger. Se [Modeller og dine data](../start/modeller-og-data.md).

!!! tip "Plan er også god til spørgsmål"
    Vil du bare forstå noget, er Plan et godt valg. Bed f.eks. agenten om at lave tre korte eksempelkontrakter med forskellige opsigelsesvilkår, og spørg derefter i Plan: "Hvad står der i disse tre eksempelkontrakter om opsigelse? Lav en sammenligning." Så gennemgår agenten indholdet uden at gå i gang med at ændre noget.

## Casen: Én samlet handlingsliste

**Problemet:** Hos [Lyngholt Tæpper](../start/casen.md) er handlingslisten ikke opdateret siden 22. oktober, og beslutningerne fra mødet 4. november mangler. Teamet vil have én samlet handlingsliste, hvor man kan se, hvor hver opgave kommer fra. Det er en opgave med flere filer og flere trin, så du starter med en plan.

Åbn mappen `case-lyngholt` som projekt og start en ny samtale.

### Trin 1: Få en plan

Vælg **Plan** og skriv:

```text
Teamet skal have én samlet, opdateret handlingsliste. Brug filerne i mappen som kilder. Hver opgave skal have: opgave, ansvarlig, frist, status og kildefil (det referat eller den fil, oplysningen kommer fra). Lav en plan for, hvordan du gør det, og fortæl, hvordan du vil håndtere opgaver, der er nævnt i flere referater. Gør ikke noget endnu.
```

### Trin 2: Gennemgå og ret planen

Læs planen og overvej:

- Bruger agenten alle tre referater og den eksisterende handlingsliste?
- Hvad gør den, når den samme opgave nævnes i flere referater? Den nyeste oplysning bør vinde.
- Hvad skriver den, når der ikke står en frist? Den bør skrive "ikke angivet" og ikke gætte.
- Hvordan bestemmer den status, f.eks. "færdig", "i gang" eller "godkendt"?

Ret planen i samme samtale, f.eks.:

```text
Godt. Tilføj to ting: Brug kun oplysninger, der står i referaterne, til status. Og marker opgaver, hvor kilderne er uenige, med "tjek".
```

### Trin 3: Udfør planen

Skift til **Build** og skriv:

```text
Udfør planen. Gem resultatet som handlingsliste-samlet.md. Ret ikke i de eksisterende filer.
```

Godkend skrivningen med **Allow once**.

### Trin 4: Kontrollér tre linjer

Åbn `handlingsliste-samlet.md` og kontrollér tre opgaver mod kildefilen:

1. **Julefrokosten:** Står der fredag 4. december 2026?
2. **Kundeundersøgelsen:** Står der, at den sendes 16. november, og at Lone er ansvarlig?
3. **Den nye hjemmeside:** Hvad står der i status? Og hvilken kildefil henviser agenten til?

Gem dit svar på punkt 3. Det skal du bruge på næste side, [Tekst i filer er ikke ordrer](kilder-og-instruktioner.md).

!!! example "Tjekliste"
    - [ ] Jeg har fået en plan og rettet mindst én ting i den
    - [ ] Agenten har lavet handlingsliste-samlet.md med kildefil på hver opgave
    - [ ] Jeg har kontrolleret tre opgaver mod kildefilen
