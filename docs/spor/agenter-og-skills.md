# Agenter og skills

Indtil nu har du brugt de agenter, der følger med OpenCode. I dette spor bygger du dine egne. Det kræver ingen kode. Agenter, skills og kommandoer er almindelige tekstfiler i Markdown.

| Byg | Det er | Brug det når |
| --- | --- | --- |
| **Agent** | En AI med sin egen rolle, sine egne instruktioner og sine egne rettigheder | Du vil have en fast "medarbejder", f.eks. en redaktør |
| **Skill** | En opskrift på en arbejdsgang, som agenten henter, når den har brug for den | Agenten skal kunne en bestemt metode, f.eks. jeres skabelon til tilbud |
| **Kommando** | En gemt opgave, du starter med `/navn` | Du giver tit den samme opgave |

Alle tre lægges i en skjult mappe, `.opencode`, i dit projekt:

```text
spor-agenter/
  AGENTS.md
  .opencode/
    agents/
      redaktoer.md
    skills/
      tilbud/
        SKILL.md
    commands/
      kundeanalyse.md
```

!!! info "Skjulte mapper"
    Mapper, der begynder med punktum, er skjulte. På Mac viser du dem med Cmd+Shift+punktum i Finder. På Windows slår du **Skjulte elementer** til under **Vis** i Stifinder. Du kan også bare bede agenten om at oprette filerne for dig.

## Projekt 1: Din første agent

Lav filen `.opencode/agents/redaktoer.md`:

```markdown
---
description: Læser et udkast og giver konkret feedback på sprog, struktur og målgruppe
mode: subagent
permissions:
  - action: edit
    resource: "*"
    effect: deny
---

Du er en erfaren dansk redaktør. Du giver feedback, men du retter aldrig selv i teksten.

Giv altid feedback i tre afsnit:
1. Det der virker
2. Tre konkrete forbedringer med eksempler
3. Én sætning om, hvorvidt teksten rammer målgruppen
```

Delen mellem de to `---` er indstillingerne. Teksten under er agentens instruktioner.

| Felt | Betydning |
| --- | --- |
| `description` | Fortæller hovedagenten, hvad agenten kan. Bruges til at vælge den rigtige hjælpeagent |
| `mode` | `primary` er en hovedagent, du taler med. `subagent` er en hjælpeagent |
| `permissions` | Hvad agenten må. Her må redaktøren ikke rette i filer (`edit` er `deny`) |

Start en ny samtale og skriv:

```text
Skriv et kort opslag til intranettet om vores nye cykelordning. Brug redaktoer til at få feedback, og ret teksten bagefter.
```

### Ekstra: Tre agenter, der arbejder sammen

Hent [agent-eksempler.zip](../filer/agent-eksempler.zip) og pak mappen ud. Den indeholder et lille team:

| Agent | Type | Må | Opgave |
| --- | --- | --- | --- |
| projektleder | hovedagent | skrive filer, starte hjælpeagenter | Planlægger og uddelegerer |
| researcher | hjælpeagent | hente websider | Finder fakta med kilder |
| redaktoer | hjælpeagent | kun læse | Giver feedback på udkast |

Åbn mappen `agent-eksempler` som projekt, vælg **projektleder** som agent, og skriv:

```text
Skriv en kort nyhedsmail til kollegerne om, hvad Microsoft Copilot er, og hvad de skal være opmærksomme på. Brug researcher til fakta og redaktoer til feedback.
```

Læs agentfilerne i `.opencode/agents` og se, hvordan rettighederne er sat op. Prøv derefter at give redaktøren lov til at hente websider, eller lav en fjerde agent, f.eks. en oversætter.

## Projekt 2: Din første skill

En skill er en opskrift. Agenten ser kun skillens navn og beskrivelse og henter selve opskriften, når opgaven passer. Så kan du have mange skills uden at fylde agentens hukommelse.

Lav filen `.opencode/skills/tilbud/SKILL.md`:

```markdown
---
name: Tilbud
description: Skriver et kort tilbud til en kunde efter Azantas faste skabelon. Brug den, når brugeren beder om et tilbud.
---

Sådan skriver du et tilbud:

1. Spørg om kundens navn, opgaven og budgettet, hvis det ikke står i opgaven
2. Skriv tilbuddet med disse overskrifter: Baggrund, Vores forslag, Tidsplan, Pris, Næste skridt
3. Højst én side
4. Gem som tilbud-[kundenavn].md
```

Test den:

```text
Lav et tilbud til Bageriet Solstrejf på et halvt dags kursus i Copilot for 8 medarbejdere.
```

Agenten henter selv skillen. Du kan også pege direkte på den ved at skrive `@tilbud` i opgaven.

## Projekt 3: Din første kommando

En kommando er en gemt opgave. Lav filen `.opencode/commands/kundeanalyse.md`:

```markdown
---
description: Laver en kort kundeanalyse til et første møde
agent: plan
---

Jeg skal til et første møde med $ARGUMENTS om, hvordan de kan bruge AI.
Lav en kort kundeanalyse med disse afsnit: Kort om virksomheden, Tre mulige AI-muligheder, Fem spørgsmål til mødet.
Angiv kilder. Skriv "ikke fundet", hvis du mangler oplysninger.
```

Nu skriver du bare:

```text
/kundeanalyse Bageriet Solstrejf
```

`$ARGUMENTS` bliver erstattet af det, du skriver efter kommandoen. Linjen `agent: plan` gør, at kommandoen kører i Plan, så agenten gennemgår og beskriver i stedet for at gå i gang med at ændre filer. Vil du være helt sikker, så sæt `edit` til `ask` i projektets `opencode.json`.

## Byg dit eget

Tag en af de tre opgaver fra din liste i del 1. Er den bedst løst som agent, skill eller kommando? Byg den, og test den på en opdigtet opgave.

!!! tip "Lad agenten hjælpe"
    Du kan bede OpenCode om at lave filerne: "Lav en hjælpeagent i .opencode/agents, der oversætter tekster til engelsk og aldrig må rette i originalfilen." Læs filen igennem bagefter, og ret instruktionerne til.

!!! tip "Gælder for alle projekter"
    Vil du bruge en agent, skill eller kommando i alle dine projekter, så læg den i OpenCodes fælles mappe i stedet: `~/.config/opencode/agents`, `~/.config/opencode/skills` eller `~/.config/opencode/commands`. På Windows er `~` din brugermappe, f.eks. `C:\Users\dit-navn`.

!!! example "Tjekliste"
    - [ ] Jeg har lavet en hjælpeagent med begrænsede rettigheder
    - [ ] Jeg har lavet en skill, som agenten selv henter
    - [ ] Jeg har lavet en kommando, jeg starter med `/`
    - [ ] Jeg har bygget mindst én ting til mit eget arbejde
