# Kontorfiler og data

Her er agenter for alvor stærkere end en chat. Agenten kan arbejde med mange filer på én gang, og den kan skrive og køre små programmer, der regner, sorterer og laver nye filer. Du skal ikke selv kunne kode. Du skal bare kunne beskrive, hvad du vil have, og tjekke resultatet.

## Forberedelse

Lav en mappe, `spor-kontor`. Læg denne `opencode.json` i den, så agenten spørger, før den kører kommandoer og retter i filer:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "permissions": [
    { "action": "edit", "resource": "*", "effect": "ask" },
    { "action": "shell", "resource": "*", "effect": "ask" }
  ]
}
```

!!! info "Når agenten vil køre en kommando"
    I dette spor vil agenten ofte bede om lov til at køre en kommando, f.eks. `python` eller `node`. Det er de små programmer, den skriver for at løse opgaven. Hvis du er i tvivl, så skriv: "Forklar kort, hvad kommandoen gør, før jeg godkender."

    Har du ikke Python installeret, siger agenten det typisk. Bed den så om at løse opgaven uden programmer, eller spørg underviseren.

## Projekt 1: Ryd op i en mappe

Lav en undermappe, `rod`, med 10 til 15 tomme eller små filer med rodede navne, f.eks. `Faktura marts FINAL.txt`, `faktura_april.txt`, `referat 3.txt`, `Referat-Juni-v2.txt`.

Brug **Plan** først:

```text
Se på filerne i mappen rod. Foreslå en ny mappestruktur og et fast navneformat, f.eks. 2026-03-faktura.txt. Vis forslaget som en tabel med gammelt og nyt navn. Flyt ikke noget endnu.
```

Ret forslaget, skift til **Build**, og skriv:

```text
Kopiér filerne over i den nye struktur i en ny mappe, ryddet. Lad mappen rod være uændret.
```

Ved at kopiere i stedet for at flytte har du stadig originalerne.

## Projekt 2: Fra data til rapport

Bed agenten lave øvelsesdata:

```text
Lav en fil, salg.csv, med 200 rækker opdigtede salgsdata: dato i 2026, sælger (5 navne), region (Nord, Syd, Øst, Vest), produkt (4 produkter) og beløb i kroner. Brug semikolon som skilletegn, så filen kan åbnes i dansk Excel.
```

Åbn filen i Excel og se, at den ser rigtig ud. Skriv derefter:

```text
Analysér @salg.csv. Lav en rapport, salgsrapport.md, med:
1. Samlet salg pr. måned og pr. region i tabeller
2. De tre bedste sælgere
3. Tre ting, der springer i øjnene, i almindeligt sprog
Skriv til sidst, hvordan du har regnet tallene ud.
```

!!! warning "Tjek tallene"
    Åbn `salg.csv` i Excel og tjek mindst ét tal selv, f.eks. det samlede salg for én måned med en pivottabel eller SUM.HVIS. Passer det ikke, så sig det til agenten og bed den regne igen.

## Projekt 3: Excel-filer ind og ud

Agenten kan ikke læse `.xlsx` direkte som tekst, men den kan ofte skrive et lille program, der gør det. Gem `salg.csv` som `salg.xlsx` i Excel, og prøv:

```text
Læs @salg.xlsx. Lav en ny Excel-fil, salg-pr-region.xlsx, med ét ark pr. region og en sum nederst på hvert ark.
```

Virker det ikke, så brug omvejen: Gem arket som CSV, lad agenten arbejde på CSV-filen, og bed om resultatet som CSV, som du åbner i Excel.

!!! tip "Genbrug programmet"
    Bed agenten om at gemme programmet, den skrev, f.eks. som `lav-rapport.py`, og om at lave en kort `LAES-MIG.md`, der forklarer, hvordan man kører det igen næste måned. Så har du en lille automatisering.

!!! example "Tjekliste"
    - [ ] Jeg har fået ryddet op i en mappe uden at miste originalerne
    - [ ] Jeg har fået en rapport ud fra en CSV-fil og selv tjekket et tal
    - [ ] Jeg har prøvet at få agenten til at arbejde med en Excel-fil
