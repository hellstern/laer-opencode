# Skriv gode opgaver

En agent er kun så god som opgaven, den får. Den kender ikke din arbejdsplads, din chef eller dine kunder. Alt, hvad den skal vide, skal stå i opgaven eller i filerne.

## De fire byggesten: MMFA

En god opgave har fire dele. Husk dem som **MMFA**:

| Byggesten | Spørgsmål | Eksempel |
| --- | --- | --- |
| **Mål** | Hvad skal resultatet bruges til, og af hvem? | "En nyhedsmail til kolleger, der ikke kender AI" |
| **Materiale** | Hvilke filer eller kilder skal agenten bruge? | "Brug notaterne i @mødenoter.md" |
| **Format** | Hvordan skal resultatet se ud, og hvor skal det gemmes? | "Højst 200 ord, tre afsnit, gem som nyhedsmail.md" |
| **Afgrænsning** | Hvad må agenten ikke? | "Ret ikke i mødenoterne. Opfind ikke tal." |

## Fra dårlig til god

**Dårlig:**

```text
Skriv noget om vores møde.
```

**God:**

```text
Mål: Skriv en kort opsummering af gårsdagens teammøde til kolleger, der ikke var med.
Materiale: Brug kun @referat-teammøde.txt.
Format: Højst 150 ord. Først de tre vigtigste beslutninger som punkter, derefter én linje om næste møde. Gem som opsummering.md.
Afgrænsning: Ret ikke i referatet. Står noget ikke i referatet, så skriv det ikke.
```

## Flere gode råd

- **Én opgave ad gangen.** Store opgaver deler du op, eller du beder agenten lave en plan først (se [Plan og Build](../arbejdsgange/plan-og-build.md)).
- **Bed agenten stille spørgsmål.** Skriv "Stil mig de spørgsmål, du har brug for, før du går i gang."
- **Bed om at se ræsonnementet.** "Fortæl kort, hvilke kilder du har brugt, og hvor du er usikker."
- **Ret med præcise beskeder.** Ikke "det er ikke godt", men "afsnit 2 er for teknisk, skriv det, så en ny medarbejder forstår det."
- **Saml rettelser i én besked.** Tre rettelser i én besked giver bedre resultat end tre beskeder i træk.

!!! warning "Tjek fakta"
    En AI kan skrive noget, der lyder rigtigt, men er forkert. Det gælder især tal, datoer, navne og citater. Bed agenten om kilder, og tjek dem selv, før du sender noget videre.

## Gem det, der går igen

Se på din MMFA-opgave. Mål, materiale og format skifter fra opgave til opgave. Men en del af **afgrænsningen** er den samme hver gang, f.eks. "Opfind ikke tal" eller "Ret ikke i originalerne". Det samme gælder tone og sprog.

Det, der går igen, hører hjemme i `regler-kladde.md`. Så skal du kun skrive det, der er særligt for den enkelte opgave. I del 3 lærer du at gøre kladden til en AGENTS.md, så agenten følger reglerne uden at du nævner dem.

!!! example "Øvelse"
    Tag en af de tre opgaver, du skrev ned i del 1. Skriv den som en MMFA-opgave og giv den til agenten. Var resultatet brugbart i første forsøg? Hvad manglede i opgaven? Tilføj de dele af afgrænsningen, der altid gælder, til `regler-kladde.md`.
