# Din første opgave

Nu skal du give agenten en mappe at arbejde i og en lille opgave at løse. Du arbejder med casen [Lyngholt Tæpper](casen.md), hvor alt er opdigtet, så der er ingen rigtige data på spil.

**Problemet:** Teamets beslutninger står spredt i tre referater. Du skal have samlet dem ét sted.

## Før du starter: data og godkendelser

To ting skal du vide, før du giver agenten sin første opgave:

- **Alt, hvad agenten læser, sendes til modellen.** Med de gratis modeller kan dine data blive gemt og brugt til træning. Brug derfor kun opdigtede eller offentlige data på kurset. Læs mere på [Modeller og dine data](modeller-og-data.md).
- **Agenten kan ændre filer.** Case-mappen indeholder en lille indstillingsfil, `opencode.json`, der får agenten til at **spørge dig**, før den skriver i en fil, kører en kommando eller arbejder uden for mappen. Når den spørger, er det dig, der bestemmer.

## Trin 1: Hent case-mappen

1. Hent [case-lyngholt.zip](../filer/case-lyngholt.zip), hvis du ikke allerede har gjort det.
2. Pak filen ud, f.eks. i din Dokumenter-mappe. På Windows: højreklik og vælg **Udpak alle**. På Mac: dobbeltklik.
3. Tjek, at mappen `case-lyngholt` indeholder:

```text
case-lyngholt/
  referat-teammoede-2026-10-07.txt
  referat-teammoede-2026-10-21.txt
  referat-teammoede-2026-11-04.txt
  handlingsliste.md
  note-fra-webbureau.txt
  opencode.json
  LAES-MIG.txt
```

I denne øvelse bruger du kun de tre referater. De andre filer kommer i del 2 og 3.

!!! warning "Åbn kun case-mappen"
    Agenten arbejder i den mappe, du åbner. Åbn aldrig hele din Dokumenter-mappe eller dit skrivebord som projekt.

## Trin 2: Åbn mappen som projekt

I OpenCode hedder en mappe, agenten arbejder i, et **projekt**.

1. Klik på projektvælgeren (under eller ved tekstfeltet) og vælg **Add project**. På startskærmen kan knappen også hedde **Open project**.
2. Vælg mappen `case-lyngholt`.
3. Tjek, at `case-lyngholt` står som projektnavn, før du skriver noget.

## Trin 3: Vælg en gratis model

Modellen er den AI, der tænker for agenten. Ved tekstfeltet finder du **modelvælgeren**.

1. Klik på modelvælgeren.
2. Vælg en model, der er markeret som gratis. De har ofte "Free" i navnet.

De gratis modeller skifter løbende. Holder en model op med at svare, så vælg bare en anden gratis model.

## Trin 4: Giv agenten opgaven

Skriv denne opgave i tekstfeltet og tryk Enter:

```text
Læs de tre referater i mappen. Lav en ny fil, beslutninger.md, med en tabel over alle beslutninger: dato for mødet, beslutning og hvem der er ansvarlig. Ret ikke i referaterne, og brug ikke de andre filer.
```

Agenten læser først de tre referater. Når den vil oprette `beslutninger.md`, stopper den og spørger dig om lov.

## Trin 5: Godkend den første skrivning

Læs, hvad agenten vil gøre. Den skal ville **oprette filen `beslutninger.md`** i case-mappen og ikke noget andet.

Vælg **Allow once**. Det giver lov til netop denne ene handling. Næste gang agenten vil skrive, spørger den igen.

| Valg | Betyder |
| --- | --- |
| **Allow once** | Lov til netop denne ene handling. Brug det, mens du lærer |
| Allow always | Lov til denne type handling i projektet fremover |
| Reject | Nej. Du kan skrive, hvad agenten skal gøre i stedet |

Du lærer mere om valgene på [Godkend, hvad agenten må](../daglig/godkendelser.md).

## Trin 6: Kontrollér resultatet mod kilden

En agent kan tage fejl, også i små opgaver. Derfor kontrollerer du altid mindst én ting selv.

1. Åbn `beslutninger.md` i Notesblok (Windows) eller TextEdit (Mac).
2. Vælg én beslutning i tabellen, f.eks. datoen for julefrokosten.
3. Åbn det referat, beslutningen kommer fra, og find stedet.
4. Står det samme begge steder? Er det den rigtige person, der er ansvarlig?

??? success "Facit: hvad tabellen skal indeholde"
    Referaterne har elleve beslutninger i alt:

    | Møde | Beslutning | Ansvarlig |
    | --- | --- | --- |
    | 7. okt. | Nyhedsbrevet sendes den første tirsdag i måneden | Aisha |
    | 7. okt. | Alle sender favoritdesign senest 10. okt., Mette vælger | Mette |
    | 7. okt. | Datoer for julefrokost undersøges med Salg | Peter |
    | 21. okt. | Julefrokost fredag 4. december 2026, lokale bookes | Lone |
    | 21. okt. | LinkedIn-opslag tirsdag og torsdag, plan for fire uger | Jonas |
    | 21. okt. | Udkast til kundeundersøgelse med højst 8 spørgsmål | Lone |
    | 4. nov. | Kundeundersøgelsen sendes mandag 16. november | Lone |
    | 4. nov. | Design 2 og budget præsenteres for direktionen 12. november. Ikke godkendt endnu | Mette |
    | 4. nov. | Jonas skriver tirsdagsopslag, Aisha torsdagsopslag | Jonas og Aisha |
    | 4. nov. | Invitation til julefrokost, tilmelding senest 20. november | Peter |
    | 4. nov. | Decembernyhedsbrevet sendes tirsdag 8. december | Aisha |

    Kaffemaskinen er ikke en beslutning, så den bør ikke stå i tabellen. At Mette har valgt design nummer 2, er en opfølgning, men nogle modeller tager det med som en beslutning. Har agenten et andet antal, så se efter, om den har udeladt, delt eller slået punkter sammen. Det er netop den slags, du skal holde øje med.

!!! info "Hvad er en .md-fil?"
    `.md` står for Markdown. Det er almindelig tekst med enkle tegn til formatering, f.eks. `|` til tabeller. Agenter er gode til Markdown, og du kan altid bede om resultatet i et andet format bagefter.

## Trin 7: Bed om en rettelse

Skriv videre i samme samtale:

```text
Tilføj en kolonne med en frist for hver beslutning. Står der ingen frist i referatet, så skriv "ikke angivet".
```

Agenten spørger igen, før den retter i filen. Vælg **Allow once** og kontrollér én frist mod referatet.

!!! example "Tjekliste"
    - [ ] Jeg har åbnet case-mappen som projekt
    - [ ] Jeg har valgt en gratis model
    - [ ] Jeg har godkendt den første skrivning med Allow once
    - [ ] Jeg har kontrolleret mindst én beslutning mod referatet
    - [ ] Jeg har bedt om en rettelse i samme samtale
