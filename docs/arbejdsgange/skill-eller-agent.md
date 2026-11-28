# Skill eller agent?

"Hvornår skal jeg bruge en skill, og hvornår skal jeg bruge en agent?" Det er et af de mest stillede spørgsmål, når man har prøvet begge dele. Svaret er kort, og du kan se det med dine egne øjne på 20 minutter. Siden bygger på [Tre agenter, ét team](agentteam.md) og faktatjekkeren, du byggede der.

## Det korte svar

| | Skill | Agent |
| --- | --- | --- |
| **Er** | En opskrift: *hvordan* en opgave løses | En medarbejder: *hvem* der løser den |
| **Har** | Metode, skabelon, tjekliste og evt. scripts | En rolle, sine egne rettigheder og en ren start |
| **Bruges** | Hentes kun, når opgaven passer | Bliver kaldt til en delopgave, eller du taler direkte med den |
| **Eksempel** | `kildetjek`: sådan tjekker du kilder | `faktatjekker`: den, der tjekker |

!!! tip "Tommelfingerregel"
    **Start med en skill.** Gå først til en agent, når du har brug for mindst én af tre ting:

    1. **En anden rolle.** Den, der tjekker, må ikke være den, der skrev.
    2. **Andre rettigheder.** F.eks. må åbne websider, men ikke rette i filer.
    3. **Ren kontekst.** Opgaven er stor, eller den skal ses med friske øjne uden hele samtalen i hovedet.

En agent er ikke "mere AI". Den er en ny rolle. Og de to arbejder sammen: **agenter bruger skills**. Den samme skill kan bruges af flere agenter, og agentfilen bliver kort, fordi metoden ligger i skill'en.

## Prøv det: fra skill til agent

### Det skal du bruge

1. Hent [skill-til-agent.zip](../filer/skill-til-agent.zip), og pak den ud, f.eks. i `Dokumenter/opencode-kursus`.
2. Mappen indeholder:

    ```text
    skill-til-agent/
      opencode.json
      .opencode/
        agents/
          projektleder.md
          researcher.md
          redaktoer.md
        skills/
          kildetjek/
            SKILL.md
      trin-3/
        faktatjekker.md
    ```

    Agenterne er de samme som i `agent-eksempler`. Det nye er skill'en `kildetjek` og agenten `faktatjekker.md`, som ligger **uden for** `.opencode` til at begynde med.

3. Åbn mappen `skill-til-agent` som projekt i OpenCode, og vælg en gratis model.

Mappen `.opencode` er skjult. På Mac viser du den med Cmd+Shift+punktum i Finder. På Windows slår du **Skjulte elementer** til under **Vis** i Stifinder.

### Trin 1: Kun en skill

Åbn `.opencode/skills/kildetjek/SKILL.md`, og læs den. Det er en opskrift i fem trin: find påstandene, åbn kilderne, giv hver en vurdering, og gæt aldrig.

Vælg **projektleder**, start en ny samtale, og skriv:

```text
Skriv en kort nyhedsmail til kollegerne om, hvad Microsoft Copilot er, på højst 150 ord. Skriv kilde ved hver oplysning.
Brug researcher til fakta. Brug derefter skill'en kildetjek på dit eget udkast, før du gemmer det.
```

!!! example "Hold øje med"
    - Henter projektlederen skill'en? Du kan se det, når den kalder værktøjet `skill`.
    - Kan den åbne kilderne? Se efter `webfetch` i sporet.
    - Hvad skriver den om kilderne til sidst?

### Trin 2: Hvorfor gik det galt?

Projektlederen har fået metoden, men den kan typisk ikke bruge den. Åbn `projektleder.md`, og find `webfetch`. Den står til `deny`. Tænk over de tre grunde fra tommelfingerreglen, før du læser videre.

??? tip "Svar"
    1. **Rettigheder.** En skill giver en metode, men ikke lov til at gå på nettet. Projektlederen kan ikke åbne kilderne, så den skriver "Ikke fundet", giver op eller vurderer kilderne ud fra det, researcher skrev. Det sidste er det farligste, fordi det ligner et tjek.
    2. **Rolle.** Projektlederen tjekker sit eget arbejde.
    3. **Kontekst.** Projektlederen har hele samtalen i hovedet, også researchers forklaringer. Den ser kilderne med de samme briller.

    Det er alle tre grunde til at lave en agent.

!!! info "Åbnede den kilderne alligevel?"
    Nogle modeller finder en vej uden om, f.eks. ved at bede researcher om at åbne kilderne for sig. Det er en god påmindelse: En instruktion er et ønske, en rettighed er en grænse. Rettigheder sætter du i agentfilen, ikke i opgaven.

### Trin 3: Så skal der en agent til

Flyt `trin-3/faktatjekker.md` ind i `.opencode/agents`. Åbn den:

```markdown
---
description: Tjekker kilderne i et udkast med skill'en kildetjek. Har ikke skrevet udkastet og må ikke rette i det
mode: subagent
permissions:
  - action: edit
    resource: "*"
    effect: deny
  - action: shell
    resource: "*"
    effect: deny
  - action: webfetch
    resource: "*"
    effect: allow
---

Du er faktatjekker. Du har ikke skrevet udkastet, og du retter ikke i det.

Brug altid skill'en kildetjek, når du får et udkast.
```

Sammenlign med den faktatjekker, du byggede i [Tre agenter, ét team](agentteam.md#byg-din-egen-hjlper-en-faktatjekker). Instruktionerne er skrumpet til to linjer, fordi metoden nu ligger i skill'en. Agentfilen siger *hvem* og *hvad den må*. Skill'en siger *hvordan*.

Start en **ny samtale** med projektleder, og skriv:

```text
Skriv en kort nyhedsmail til kollegerne om, hvad Microsoft Copilot er, på højst 150 ord. Skriv kilde ved hver oplysning.
Brug researcher til fakta. Send udkastet til faktatjekker, før du gemmer det, og ret udkastet ud fra svaret.
```

!!! example "Hold øje med"
    - Starter projektlederen faktatjekker?
    - Henter faktatjekker skill'en `kildetjek`?
    - Åbner faktatjekker kilderne med `webfetch`?
    - Hvad er forskellen på svaret om kilderne i trin 1 og trin 3?

### Trin 4: De arbejder sammen

Skill'en er ikke bundet til faktatjekkeren. Skriv i samme samtale:

```text
Bed researcher om at bruge skill'en kildetjek på sine egne kilder, før den svarer dig.
```

Researcher må gerne gå på nettet, så her virker skill'en. **Én skill, to agenter.** Retter du metoden i `SKILL.md`, gælder rettelsen for begge.

## Byg dit eget valg

Tænk på tre opgaver fra dit eget arbejde. Skriv for hver: skill, agent eller begge, og hvorfor.

| Opgave | Skill, agent eller begge? | Hvorfor? |
| --- | --- | --- |
| | | |
| | | |
| | | |

??? tip "Eksempler"
    - **Mødereferat efter fast skabelon.** Skill. Samme metode hver gang, ingen særlige rettigheder.
    - **Korrekturlæsning af en tekst, du selv har skrevet.** Agent, eller agent med skill. Den skal læse med friske øjne og må ikke rette selv.
    - **Tilbud efter firmaets regler for rabat og moms.** Skill til reglerne. Kommer der et tjek af tallene oveni, så en agent til tjekket, der bruger samme skill.

Vil du bygge selv, så finder du skabeloner til agenter, skills og kommandoer i sporet [Agenter og skills](../spor/agenter-og-skills.md). Vil du blive bedre til skills, så se kurset [Lær skills](https://hellstern.github.io/laer-skills/).

!!! example "Tjekliste"
    - [ ] Jeg kan forklare forskellen på en skill og en agent med ordene *hvordan* og *hvem*
    - [ ] Jeg har set, at en skill ikke giver rettigheder
    - [ ] Jeg har set faktatjekkeren bruge skill'en kildetjek
    - [ ] Jeg kan nævne de tre grunde til at gå fra en skill til en agent
    - [ ] Jeg har valgt mellem skill og agent for tre af mine egne opgaver

## Kilder

- [OpenCode: Agent Skills](https://opencode.ai/docs/skills/)
- [OpenCode: Agenter i Markdown](https://opencode.ai/v2/docs/agents/)
- [Anthropic: Equipping agents for the real world with Agent Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)
