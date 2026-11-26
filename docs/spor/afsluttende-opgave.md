# Afsluttende opgave

Du afslutter kurset med en opgave fra dit spor, som du løser på egen hånd og afleverer i Teams. Du har **30 til 45 minutter**.

Formålet er ikke at få det perfekte resultat. Det er at vise din **arbejdsgang**: hvordan du gav agenten opgaven, og hvordan du kontrollerede resultatet. To deltagere kan sagtens ende med forskellige resultater, og begge kan have arbejdet godt.

## Sådan gør du

1. Vælg **én** opgave nedenfor fra et spor, du har gennemført.
2. Lav en ny mappe til opgaven med de filer, opgaven bruger, og en `opencode.json`, så agenten spørger, før den skriver i filer.
3. Løs opgaven med OpenCode. Brug gerne Plan først.
4. Kontrollér resultatet. Find mindst to ting, du selv tjekker mod kilden.
5. Aflever i Teams. Se [Aflevering](#aflevering) nedenfor.

Brug kun opdigtede eller offentlige data.

## Vælg din opgave

=== "Tekst og kommunikation"

    **Nyhedsmail fra Lyngholt Tæpper**

    Brug de tre referater fra [casen](../start/casen.md). Skriv en nyhedsmail til alle medarbejdere i Lyngholt Tæpper om de beslutninger fra Kommunikation, der vedrører dem: julefrokosten, kundeundersøgelsen og decembernyhedsbrevet.

    - Højst 200 ord og en fængende emnelinje
    - En kort version til Teams på højst 60 ord
    - Ingen oplysninger, der ikke står i referaterne

    **Aflever:** `nyhedsmail.md` med begge versioner.

=== "Kontorfiler og data"

    **Kvartalsrapport til ledelsen**

    Brug [salg.csv](../filer/salg.csv). Lav en rapport om første kvartal 2026 (januar til marts) til ledelsen.

    - Samlet salg pr. måned og pr. region i første kvartal
    - Hvilken region og hvilket produkt der klarede sig bedst
    - Tre korte anbefalinger i almindeligt sprog
    - Et afsnit om, hvordan tallene er regnet ud

    Brug facit for marts i region Nord fra [Kontorfiler og data](kontorfiler.md) som én af dine kontroller.

    **Aflever:** `kvartalsrapport.md`.

=== "Research og analyse"

    **Kundeanalyse til et første møde**

    Vælg en offentlig dansk virksomhed, som du ikke har brugt i sporet. Lav en kundeanalyse på højst én side til et første møde om AI, med websøgning eller links, du selv finder.

    - Kort om virksomheden
    - Tre mulige AI-muligheder, hver med en begrundelse fra kilderne
    - Fem spørgsmål til mødet
    - Kilder med link efter hver påstand

    **Aflever:** `kundeanalyse.md`.

=== "Agenter og skills"

    **Et værktøj til Lyngholt Tæpper**

    Teamet i [casen](../start/casen.md) får et nyt referat hver anden uge. Byg en agent, en skill eller en kommando, der tager et nyt referat og opdaterer handlingslisten med opgave, ansvarlig, frist, status og kildefil.

    - Værktøjet må ikke rette i referaterne
    - Det skal nævne instruktioner, det finder i filer, i stedet for at følge dem
    - Test det på referatet fra 4. november og den gamle `handlingsliste.md`

    **Aflever:** Din agent-, skill- eller kommandofil og resultatet af testen.

## Aflevering

Aflever i Teams-kanalen, som underviseren angiver. Dit indlæg skal indeholde tre ting:

1. **Resultatfilen**, vedhæftet.
2. **Den prompt eller plan, du brugte.** Kopiér din vigtigste prompt ind, eller vedhæft planen. Har du rettet undervejs, så tag den sidste version.
3. **To linjer om, hvad du selv kontrollerede.** Hvad tjekkede du, mod hvilken kilde, og hvad fandt du?

Du kan kopiere denne skabelon:

```text
Spor: [dit spor]
Opgave: [opgavens navn]
Model: [den model, du brugte]

Prompt eller plan:
[indsæt her]

Det kontrollerede jeg:
1. [hvad du tjekkede, mod hvilken kilde, og hvad du fandt]
2. [hvad du tjekkede, mod hvilken kilde, og hvad du fandt]
```

!!! example "Eksempel på de to linjer"
    1. Jeg tjekkede julefrokostens dato i nyhedsmailen mod referatet fra 21. oktober. Den passede: fredag 4. december.
    2. Jeg tjekkede, om mailen nævnte noget, der ikke står i referaterne. Agenten havde skrevet "med live musik", som ikke står nogen steder, så det bad jeg den fjerne.

## Det giver underviseren feedback på

| Område | Underviseren ser efter |
| --- | --- |
| **Opgaven** | Er prompten tydelig om mål, materiale, format og afgrænsning? |
| **Sikkerhed** | Er der kun brugt opdigtede eller offentlige data, og er rettighederne sat op? |
| **Kontrol** | Er der kontrolleret noget konkret mod en kilde, og er fejl rettet? |
| **Resultatet** | Kan det bruges, eller er det tydeligt, hvad der mangler? |

Det er fint at aflevere et resultat med fejl, hvis du selv har fundet og beskrevet dem.
