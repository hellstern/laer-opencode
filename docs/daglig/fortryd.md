# Fortryd og gennemse ændringer

## Se, hvad agenten har ændret

I skrivebordsprogrammet kan du åbne et **gennemsynspanel** (review) i siden. Her ser du de filer, agenten har lavet eller rettet i samtalen, og præcis hvad der er ændret. Tekst, der er fjernet, vises typisk med rødt, og ny tekst med grønt.

Gør det til en vane at kigge her, før du bruger resultatet.

## Fortryd agentens seneste svar

Er du ikke tilfreds med det, agenten lige har gjort, kan du **fortryde** (*undo*):

- Skriv `/undo` i tekstfeltet, eller
- Vælg en tidligere besked i samtalen og vælg **Revert**

Din sidste besked kommer så tilbage i tekstfeltet, så du kan rette den og prøve igen. Fortrydelsen gennemføres først, når du sender den rettede besked. Fortryder du fortrydelsen, så skriv `/redo`.

## Den vigtige begrænsning

!!! warning "Fortryd virker kun på filer i et Git-projekt"
    OpenCode kan kun rulle **filer** tilbage, når projektmappen er et såkaldt Git-projekt. Git er et versionsstyringsprogram, som udviklere bruger.

    Din øvelsesmappe er højst sandsynligt **ikke** et Git-projekt. Så fjerner `/undo` kun beskederne fra samtalen. **Filerne, agenten har ændret, forbliver ændret.**

Derfor er reglen på kurset:

1. **Arbejd altid på kopier.** Læg en kopi af filerne i projektmappen, ikke originalerne.
2. **Bed agenten om nye filer.** Skriv "Gem resultatet i en ny fil" i stedet for "ret i filen". Så har du altid originalen.
3. **Gem undervejs.** Er et resultat godt, så lav en kopi af filen, før du beder om flere ændringer.

Selv i et Git-projekt kan fortryd ikke rulle alt tilbage. Hvis agenten har kørt en kommando, der f.eks. har sendt en mail eller slettet noget uden for mappen, kan det ikke gøres om.

??? info "For de nysgerrige: Gør mappen til et Git-projekt"
    Har du Git installeret, kan du bede agenten om det: "Gør denne mappe til et Git-projekt og gem den nuværende tilstand." Så kan OpenCode også rulle filer tilbage. Det er ikke nødvendigt på kurset.

!!! example "Øvelse"
    1. Bed agenten om at lave en fil, `huskeliste.md`, med fem punkter.
    2. Bed den om at slette to af punkterne.
    3. Skriv `/undo`. Hvad sker der med samtalen? Og hvad sker der med filen?
    4. Prøv samme opgave igen, men skriv "Gem den nye version som huskeliste-v2.md".
