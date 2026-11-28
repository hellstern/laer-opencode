# Tre agenter, ét team

På siden [Hjælpeagenter](hjaelpeagenter.md) så du, at en hovedagent kan sende delopgaver videre. Her får du et færdigt team af tre agenter, som du kan køre, læse og ændre. Du behøver ikke kunne programmere. Agenterne er almindelige tekstfiler, og du kan åbne dem i Notesblok, TextEdit eller VS Code. Tænk på dem som tre jobbeskrivelser til tre kolleger.

![Tre agenter, ét team. Du giver projektlederen opgaven. Projektlederen sender en opgave til researcher, som finder fakta med kilder. Projektlederen gemmer et udkast i mappen, sender det til redaktøren, som giver feedback, retter udkastet og svarer dig. Projektlederen må skrive filer og starte hjælpere, men ikke gå på nettet. Researcher må gå på nettet, men ikke skrive filer. Redaktøren må kun læse.](../billeder/tre-agenter.svg)

!!! warning "Om dine data"
    Researcher henter websider, og de gratis modeller kører på servere uden for EU. Brug kun opgaver uden personoplysninger og fortrolige data. Se [Modeller og dine data](../start/modeller-og-data.md).

## Hent teamet

1. Hent [agent-eksempler.zip](../filer/agent-eksempler.zip), og pak den ud, f.eks. i `Dokumenter/opencode-kursus`.
2. Tjek, at mappen indeholder dette:

    ```text
    agent-eksempler/
      opencode.json
      .opencode/
        agents/
          projektleder.md
          researcher.md
          redaktoer.md
    ```

3. Åbn mappen `agent-eksempler` som projekt i OpenCode, som du lærte i [Din første opgave](../start/foerste-opgave.md).

!!! info "Skjulte mapper"
    Mappen `.opencode` begynder med et punktum og er derfor skjult. På Mac viser du den med Cmd+Shift+punktum i Finder. På Windows slår du **Skjulte elementer** til under **Vis** i Stifinder. OpenCode finder agenterne selv, også selvom du ikke kan se mappen.

## Prøv teamet

Vælg agenten **projektleder** i menuen ved tekstfeltet, og skriv:

```text
Skriv en kort nyhedsmail til kollegerne om, hvad Microsoft Copilot er, og hvad de skal være opmærksomme på. Brug researcher til fakta og redaktoer til feedback.
```

!!! example "Tjekliste"
    - [ ] Projektlederen gentager opgaven og laver en plan
    - [ ] Researcher starter og henter fakta med kilder
    - [ ] Projektlederen skriver et udkast og gemmer det som en .md-fil i mappen
    - [ ] Redaktøren giver feedback i tre afsnit
    - [ ] Projektlederen retter udkastet og fortæller, hvilken fil det ligger i

Mangler der flueben, så se [Fejlfinding](../opslag/fejlfinding.md).

## Forskellen på projektlederen og de to andre

Projektlederen er den eneste, du taler med. Researcher og redaktør er hjælpere, som projektlederen sender opgaver til. Du skriver aldrig direkte til dem.

| | Projektleder | Researcher | Redaktør |
| --- | --- | --- | --- |
| **Fil** | `projektleder.md` | `researcher.md` | `redaktoer.md` |
| **Rolle** | Hovedagent (`mode: primary`). Den, du taler med | Hjælper (`mode: subagent`). Kaldes af projektlederen | Hjælper (`mode: subagent`). Kaldes af projektlederen |
| **Opgave** | Planlægger, uddelegerer, skriver udkastet og gemmer filen | Finder fakta på nettet med kilder | Læser udkastet og giver feedback |
| **Må oprette og ændre filer** (`edit`) | Ja | Nej | Nej |
| **Må hente websider** (`webfetch`) | Nej | Ja | Nej |
| **Må starte andre agenter** (`subagent`) | Ja | Nej | Nej |
| **Må køre kommandoer** (`shell`) | Nej | Nej | Nej |

Ingen af de tre kan alt. Projektlederen kan skrive filer, men ikke gå på nettet. Researcher kan gå på nettet, men ikke skrive filer. Redaktøren kan kun læse. Det er med vilje: hvis en agent gør noget forkert, er skaden begrænset til det, den har lov til.

### Sådan arbejder de sammen

1. Du giver projektlederen en opgave.
2. Projektlederen gentager opgaven og laver en plan.
3. Projektlederen sender en del af opgaven til researcher, som finder fakta med kilder og sender dem tilbage.
4. Projektlederen skriver et udkast og gemmer det som en fil i mappen.
5. Projektlederen sender udkastet til redaktøren, som sender feedback tilbage.
6. Projektlederen retter udkastet og fortæller dig, hvilken fil det ligger i.

Det er det samme, som når en projektleder på en arbejdsplads beder en kollega om at finde tal og en anden om at læse korrektur.

## Inde i en agentfil

En agent er én Markdown-fil med to dele: indstillingerne mellem de to `---` og instruktionerne under. Her er redaktøren i kort udgave:

```markdown
---
description: Læser et udkast og giver konkret feedback
mode: subagent
permissions:
  - action: edit
    resource: "*"
    effect: deny
---

Du er redaktør. Du giver feedback, men du retter ikke selv i teksten.
```

| Felt | Betydning |
| --- | --- |
| `description` | Fortæller hovedagenten, hvad agenten kan. Den bruges til at vælge den rigtige hjælper |
| `mode` | `primary` er en hovedagent, du taler med. `subagent` er en hjælper, som hovedagenten kalder |
| `model` | Valgfrit. Udelades feltet, bruger agenten den model, du har valgt |
| `permissions` | Hvad agenten må. `effect` er `allow` (må) eller `deny` (må ikke) |

De vigtigste handlinger i `permissions`:

| Handling | Betyder |
| --- | --- |
| `edit` | Oprette og ændre filer |
| `shell` | Køre kommandoer på computeren |
| `webfetch` | Hente websider |
| `subagent` | Starte andre agenter |

### Hvad står der i hver fil?

Instruktionerne er skrevet som almindelig dansk tekst, præcis som du ville skrive en opgavebeskrivelse til en kollega.

**projektleder.md**

- **Indstillinger:** `mode: primary`, så det er den, du taler med. Må oprette filer og starte de to hjælpere. Må ikke gå på nettet eller køre kommandoer.
- **Instruktioner:** syv trin fra "gentag opgaven" til "fortæl, hvilken fil det ligger i". Den skal sende fakta-spørgsmål til researcher og udkastet til redaktøren.
- **Regler:** skriv på dansk, opfind aldrig fakta, og spørg brugeren, hvis opgaven er uklar.

**researcher.md**

- **Indstillinger:** `mode: subagent`, så den bliver kaldt af projektlederen. Må hente websider. Må ikke oprette filer eller køre kommandoer.
- **Instruktioner:** find oplysningerne, svar med højst fem punkter, og skriv kilden efter hvert punkt.
- **Regler:** gæt aldrig. Hellere "ikke fundet" end et forkert svar.

**redaktoer.md**

- **Indstillinger:** `mode: subagent`. Må ingenting andet end at læse det, den får. Ingen filer, intet net og ingen kommandoer.
- **Instruktioner:** svar med præcis tre afsnit: "Det virker godt", "Det skal rettes" og "Samlet vurdering".
- **Regler:** tænk på målgruppen, som er kontoransatte uden teknisk baggrund, og ret aldrig selv i teksten.

## Skru på rettighederne

!!! example "Øvelse"
    Gæt først, test bagefter. Start en ny samtale efter hver ændring. Virker en ændring ikke, så luk OpenCode og åbn det igen.

    | Ændring | Dit gæt | Det skete |
    | --- | --- | --- |
    | **A.** I `redaktoer.md`: skift `effect: deny` til `effect: allow` for `webfetch`. Kør testopgaven igen. Begynder redaktøren at hente websider? | | |
    | **B.** I `projektleder.md`: skift `effect: allow` til `effect: deny` for `edit`. Kør testopgaven igen. Hvad gør projektlederen med udkastet? | | |
    | **C.** Sæt begge filer tilbage, og tjek, at testopgaven virker igen | | |

    Hvorfor fik redaktøren ikke lov til nettet fra starten? Hvad er risikoen ved en agent, der både må hente websider og skrive filer?

## Byg din egen hjælper: en faktatjekker

Et svar med kilder er ikke rigtigt, før nogen har åbnet kilderne. Nu skal en agent gøre det.

!!! example "Øvelse"
    1. Opret filen `faktatjekker.md` i `.opencode/agents`. Start med skabelonen herunder.
    2. Udfyld de tre rettigheder: sæt hver `???` til `allow` eller `deny`. Hvad skal den kunne, og hvad må den aldrig?
    3. Skriv dine egne regler færdige.
    4. Åbn `projektleder.md`, og tilføj et trin: udkastet sendes til faktatjekker, før det sendes til redaktoer.
    5. Kør testopgaven igen i en ny samtale.

    ```markdown
    ---
    description: Åbner kilderne i et udkast og tjekker, om de siger det, udkastet påstår
    mode: subagent
    permissions:
      - action: edit
        resource: "*"
        effect: ???
      - action: shell
        resource: "*"
        effect: ???
      - action: webfetch
        resource: "*"
        effect: ???
    ---

    Du er faktatjekker. Du tjekker kilder, men du retter ikke selv i teksten.

    Sådan arbejder du:

    1. Find hver påstand i udkastet, der har en kilde.
    2. Åbn kilden.
    3. Svar for hver påstand: Holder, Holder delvist eller Holder ikke, og skriv én linje om hvorfor.

    Regler:

    - Skriv på dansk.
    - ???
    ```

    Hvad fangede faktatjekkeren? Hvad slap igennem?

??? tip "Forslag til rettighederne"
    `edit` er `deny`, fordi den ikke skal rette i teksten. `shell` er `deny`, fordi den ikke har brug for det. `webfetch` er `allow`, fordi den skal kunne åbne kilderne.

## Når du selv vil ændre en agent

- **Vil du ændre, hvad agenten gør?** Ret teksten under de to `---`. Skriv det på almindeligt dansk.
- **Vil du ændre, hvad agenten må?** Ret `allow` til `deny` eller omvendt under `permissions`. Ret kun ordet, ikke mellemrummene foran. Indrykningen betyder noget.
- **Vil du lave en ny hjælper?** Kopiér `redaktoer.md`, giv kopien et nyt navn, f.eks. `oversaetter.md`, og ret beskrivelsen og instruktionerne. Bed projektlederen bruge den.
- **Gik noget galt?** Pak `agent-eksempler.zip` ud igen, så har du de oprindelige filer.

Gem filen, og start en ny samtale, når du har ændret en agent. Slår ændringen ikke igennem, så luk OpenCode og åbn det igen.

!!! example "Tjekliste"
    - [ ] Teamet har løst testopgaven med alle fem flueben
    - [ ] Jeg kan forklare forskellen på projektlederen og de to hjælpere
    - [ ] Jeg har ændret en rettighed og set, hvad der skete
    - [ ] Jeg har bygget en faktatjekker og sat den ind hos projektlederen

!!! tip "Næste skridt"
    Hvornår skal faktatjekkeren være en agent, og hvornår er en skill nok? Se [Skill eller agent?](skill-eller-agent.md).

## Kilder

- [OpenCode: Agenter i Markdown](https://opencode.ai/v2/docs/agents/)
- [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
