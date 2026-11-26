# Din første opgave

Nu skal du give agenten en mappe at arbejde i og en lille opgave at løse.

## Trin 1: Lav en øvelsesmappe

Lav en ny, tom mappe, f.eks. `Dokumenter/opencode-kursus`. Læg en eller to ufarlige tekstfiler i den, f.eks. en indkøbsliste eller noter fra et kursus. Du kan også lave filerne i Notesblok (Windows) eller TextEdit (Mac).

!!! warning "Brug en tom øvelsesmappe"
    Agenten kan læse og ændre **alt** i den mappe, du åbner. Åbn derfor aldrig hele din Dokumenter-mappe eller dit skrivebord som projekt.

## Trin 2: Åbn mappen som projekt

I OpenCode hedder en mappe, agenten arbejder i, et **projekt**.

1. Klik på projektvælgeren (under eller ved tekstfeltet) og vælg **Add project**. På startskærmen kan knappen også hedde **Open project**.
2. Vælg din øvelsesmappe.
3. Tjek, at mappens navn står som projektnavn, før du skriver noget.

## Trin 3: Vælg en gratis model

Modellen er den AI, der tænker for agenten. Ved tekstfeltet finder du **modelvælgeren**.

1. Klik på modelvælgeren.
2. Vælg en model, der er markeret som gratis. De har ofte "Free" i navnet.

De gratis modeller skifter løbende. Holder en model op med at svare, så vælg bare en anden gratis model. Læs mere på [Modeller og dine data](modeller-og-data.md).

## Trin 4: Giv agenten en opgave

Skriv denne opgave i tekstfeltet og tryk Enter:

```text
Se hvilke filer der ligger i denne mappe. Lav en ny fil, oversigt.md, med en kort beskrivelse af hver fil på dansk.
```

Det skal du se:

- [ ] Agenten fortæller, hvad den vil gøre
- [ ] Den læser filerne (du kan se det som små trin i samtalen)
- [ ] Den laver filen `oversigt.md`
- [ ] Den fortæller, at den er færdig

Åbn mappen på din computer. Nu ligger der en ny fil, `oversigt.md`. Den kan du åbne i Notesblok, TextEdit eller Word.

!!! info "Hvad er en .md-fil?"
    `.md` står for Markdown. Det er almindelig tekst med enkle tegn til formatering, f.eks. `#` foran en overskrift og `-` foran et punkt. Agenter er gode til Markdown, og du kan altid bede om at få resultatet som Word eller PDF bagefter.

## Trin 5: Bed om en rettelse

Skriv videre i samme samtale:

```text
Lav oversigten om til en tabel med to kolonner: filnavn og beskrivelse.
```

Agenten husker, hvad I lige har talt om, og retter i den fil, den lavede.

!!! example "Øvelse"
    Læg en tekst fra dit eget arbejde i mappen (uden personoplysninger). Bed agenten om at lave tre forslag til en kortere overskrift og gemme dem i en ny fil.

!!! example "Tjekliste"
    - [ ] Jeg har åbnet min øvelsesmappe som projekt
    - [ ] Jeg har valgt en gratis model
    - [ ] Agenten har lavet en ny fil i mappen
    - [ ] Jeg har bedt om en rettelse i samme samtale
