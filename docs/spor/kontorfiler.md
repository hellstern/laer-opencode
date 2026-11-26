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

Alle på holdet bruger det samme datasæt. Så kan I sammenligne resultater på tværs af modeller, og det er let at se, om en afvigelse skyldes beregningen, eller måden filen blev læst på.

1. Hent [salg.csv](../filer/salg.csv) og læg den i mappen `spor-kontor`.
2. Åbn filen i Excel og se, at den ser rigtig ud: 200 rækker med kolonnerne Dato, Sælger, Region, Produkt, Antal og Beløb.

Alle data er opdigtede. Filen bruger semikolon som skilletegn, så den kan åbnes direkte i dansk Excel.

Skriv derefter:

```text
Analysér @salg.csv. Lav en rapport, salgsrapport.md, med:
1. Samlet salg pr. måned og pr. region i tabeller
2. De tre bedste sælgere
3. Tre ting, der springer i øjnene, i almindeligt sprog
Skriv til sidst, hvordan du har regnet tallene ud.
```

### Kontrollér med facit

Find salget i **marts** for region **Nord** i agentens rapport, og sammenlign med facit. Regn også gerne tallet ud selv i Excel med en pivottabel eller SUM.HVISER.

??? success "Facit: marts, region Nord"
    | | Facit |
    | --- | --- |
    | Antal salg (rækker) | 5 |
    | Antal solgte enheder | 15 |
    | **Samlet beløb** | **42.000 kr.** |

    Fordelt på produkter: Kontorstol 19.200 kr., Hæve-sænkebord 15.600 kr., Skærm 7.200 kr., Headset 0 kr.

    De fem rækker:

    | Dato | Sælger | Produkt | Antal | Beløb |
    | --- | --- | --- | --- | --- |
    | 2026-03-06 | Peter Lund | Kontorstol | 6 | 14.400 |
    | 2026-03-10 | Peter Lund | Kontorstol | 2 | 4.800 |
    | 2026-03-19 | Jonas Krag | Hæve-sænkebord | 3 | 15.600 |
    | 2026-03-21 | Søren Bæk | Skærm | 3 | 5.400 |
    | 2026-03-28 | Mette Holm | Skærm | 1 | 1.800 |

### Hvis tallet ikke passer

Spørg først, hvordan agenten har læst filen. Typiske fejl:

| Tegn på fejlen | Sandsynlig årsag |
| --- | --- |
| Alle tal er meget forkerte, eller der kun er én kolonne | Filen er læst med komma i stedet for semikolon som skilletegn |
| Marts har for mange eller for få salg | Datoerne er læst forkert, f.eks. med dag og måned byttet om |
| Region Øst eller sælgeren Søren Bæk mangler | Æ, ø og å er læst forkert |
| Beløbet er tæt på, men ikke ens | Agenten har regnet i hovedet i stedet for at bruge et program, eller har sprunget rækker over |

Skriv f.eks.: "Dit tal for marts i Nord er forkert. Fortæl, hvordan du har læst filen, og regn det igen med et lille program."

!!! example "Sammenlign modeller"
    Giv den samme opgave til to forskellige gratis modeller i hver sin samtale. Får de samme tal for marts i Nord? Skriv jeres resultater i Teams-kanalen, så holdet kan se, hvilke modeller der regner rigtigt.

??? example "Ekstraopgave: lad agenten lave sine egne data"
    Bed agenten om at lave et nyt datasæt:

    ```text
    Lav en fil, salg-egen.csv, med 200 rækker opdigtede salgsdata: dato i 2026, sælger (5 navne), region (Nord, Syd, Øst, Vest), produkt (4 produkter), antal og beløb i kroner. Brug semikolon som skilletegn, så filen kan åbnes i dansk Excel.
    ```

    Kør den samme analyse på den nye fil. Her er der intet facit, så du skal selv kontrollere mindst ét tal i Excel.

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
    - [ ] Jeg har fået en rapport ud fra salg.csv og tjekket marts i Nord mod facit
    - [ ] Jeg har prøvet at få agenten til at arbejde med en Excel-fil
