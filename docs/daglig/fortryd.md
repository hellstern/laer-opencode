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

## Casen: Ret fejlen i handlingslisten

**Problemet:** Teamet hos [Lyngholt Tæpper](../start/casen.md) bruger `handlingsliste.md` til at holde styr på opgaverne. Men der er sneget sig en fejl ind. Du skal finde den, få agenten til at rette den og gennemgå ændringen, før du stoler på den.

Åbn mappen `case-lyngholt` som projekt igen og start en ny samtale.

### Trin 1: Lav en sikkerhedskopi

Mappen er ikke et Git-projekt, så `/undo` kan ikke rulle filen tilbage. Lav derfor selv en kopi af `handlingsliste.md` i Stifinder eller Finder, og kald den `handlingsliste-original.md`.

### Trin 2: Find fejlen

Vælg **Plan**, så agenten undersøger og beskriver uden at gå i gang med at ændre noget:

```text
Sammenlign @handlingsliste.md med de tre referater. Find de steder, hvor handlingslisten ikke stemmer med det, der står i referaterne. Angiv for hver afvigelse, hvilket referat du bygger på. Ret ikke noget endnu.
```

??? success "Facit: fejlen"
    Handlingslisten siger, at julefrokosten er **fredag 11. december 2026**. Referatet fra 21. oktober siger **fredag 4. december 2026**, og referatet fra 4. november bekræfter datoen.

    Agenten nævner måske også, at handlingslisten mangler opgaverne fra mødet 4. november. Det er rigtigt, men det er ikke en fejl i listen. Den er bare ikke opdateret siden 22. oktober. Det tager du dig af i del 3.

### Trin 3: Ret fejlen

Skift til **Build** og skriv:

```text
Ret datoen for julefrokosten i handlingsliste.md, så den stemmer med referaterne. Ret ikke andet i filen.
```

Agenten spørger, før den retter i filen. Læs, hvad den vil ændre, og vælg **Allow once**.

### Trin 4: Gennemgå ændringen

1. Åbn gennemsynspanelet og se, hvad agenten har ændret. Er det kun datoen? Er der ændret andet, f.eks. formatering eller andre rækker?
2. Åbn `handlingsliste.md` og `handlingsliste-original.md` ved siden af hinanden og sammenlign selv.
3. Er der ændret mere end datoen, så sig det til agenten: "Du har ændret mere end datoen. Gendan resten, så den eneste ændring er datoen."

### Trin 5: Prøv fortryd

Skriv `/undo`. Se, hvad der sker med samtalen, og åbn derefter `handlingsliste.md`. Er datoen stadig rettet? Det er den, fordi mappen ikke er et Git-projekt. Derfor var sikkerhedskopien i trin 1 vigtig.

!!! example "Tjekliste"
    - [ ] Jeg har lavet en sikkerhedskopi, før agenten rettede i filen
    - [ ] Agenten har fundet fejlen og henvist til det referat, den bygger på
    - [ ] Jeg har godkendt rettelsen med Allow once
    - [ ] Jeg har gennemgået ændringen og tjekket, at kun datoen er ændret
    - [ ] Jeg har set, at `/undo` ikke ruller filen tilbage
