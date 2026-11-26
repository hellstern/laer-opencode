# Terminal og andre modeller

Denne side er til dig, der vil videre end kurset. Intet her er nødvendigt for at gennemføre det.

## Terminalversionen

OpenCode findes også som terminalprogram. Agenterne, skills og kommandoerne er de samme som i skrivebordsprogrammet, men du styrer alt med tekstkommandoer som `/models` og `/agents`.

### Windows

Brug **PowerShell**. Curl-kommandoen fra OpenCodes hjemmeside kræver bash, som Windows ikke har. Installationen sker i stedet med npm, som følger med Node.js.

1. Tjek, om du har Node.js, med `node --version`. Får du en fejl, så installér det med `winget install OpenJS.NodeJS.LTS` og genstart PowerShell.
2. Installér OpenCode. Det ekstra flag er nødvendigt, fordi nyere npm ellers blokerer det script, der henter Windows-programmet:

    ```
    npm install -g --allow-scripts=@opencode/cli @opencode/cli
    ```

3. Luk PowerShell, åbn et nyt vindue, og tjek med `opencode --version`.
4. Får du fejlen "running scripts is disabled on this system", så kør `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, svar `Y`, og prøv igen.

### macOS og Linux

Åbn Terminal og kør:

```
curl -fsSL https://opencode.ai/v2/install | bash
```

Luk terminalen, åbn den igen, og tjek installationen med `opencode --version`.

### Kom i gang i terminalen

```
cd Documents/opencode-kursus
opencode
```

| I terminalen | Det gør |
| --- | --- |
| ++shift+tab++ | Skift mellem agenter, f.eks. Plan og Build |
| `/models` | Vælg model |
| `/connect` | Forbind en udbyder med en API-nøgle |
| `/new` og `/sessions` | Ny samtale og tidligere samtaler |
| ++ctrl+p++ | Kommandopaletten med alle handlinger |

## EU-model med Mistral

Mistral er en fransk AI-udbyder. Før du sender rigtige data, så tjek behandlingssted og vilkår for netop den tjeneste og plan, du bruger, i Mistrals vilkår og databehandleraftale. Den gratis plan giver ikke adgang til API'et, så det kræver et betalt abonnement. Mistral Pro indeholder et månedligt beløb i API-credits.

1. Opret en konto på [console.mistral.ai](https://console.mistral.ai/) og vælg en plan med API-adgang.
2. Åbn **API keys**, klik på **New key**, og kopiér nøglen. Du kan kun se den én gang.
3. Forbind OpenCode til Mistral:
    - **Skrivebordsprogrammet:** Find knappen til at forbinde en udbyder på startskærmen eller under indstillingerne, søg efter **Mistral**, og indsæt nøglen.
    - **Terminalen:** Skriv `/connect`, vælg **Mistral**, og indsæt nøglen.
4. Vælg en Mistral-model i modelvælgeren eller med `/models`.

!!! warning "Pas på din nøgle"
    En API-nøgle er som en adgangskode til din betalingskonto. Del den aldrig, og læg den ikke i en fil, du sender videre.

## Helt lokalt med Ollama

Med Ollama kører selve modellen på din egen computer, så dine opgaver og filer sendes ikke til en modeludbyder. Andre værktøjer kan stadig gå på nettet: Websøgning sender søgeord til en ekstern søgetjeneste, og hentning af websider kontakter de sider, agenten henter. Sæt `websearch` og `webfetch` til `deny` i `opencode.json`, hvis intet må forlade computeren. Det kræver mindst 16 GB RAM, og små modeller er dårligere til at bruge værktøjer end de store modeller i skyen. Regn med, at det går langsommere.

1. Installér Ollama fra [ollama.com](https://ollama.com/).
2. Hent en model, der kan bruge værktøjer, f.eks. `ollama pull qwen3:8b`.
3. Start OpenCode med Ollama: `ollama launch opencode`.
4. Vælg Ollama-modellen i modelvælgeren eller med `/models`.

## Kilder

- [OpenCode: installation og /connect](https://opencode.ai/docs/)
- [OpenCode: terminalens kommandoer og genveje](https://opencode.ai/docs/cli/tui/)
- [Mistral: priser og planer](https://mistral.ai/pricing)
- [Ollama: integration med OpenCode](https://docs.ollama.com/integrations/opencode)
