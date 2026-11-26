# Modeller og dine data

OpenCode er selve programmet. Modellen er den AI, der svarer. Når du skriver en opgave, sendes din tekst og de filer, agenten læser, til den model, du har valgt. Derfor er valget af model også et valg om, hvor dine data ender.

## De gratis modeller

OpenCode har en række gratis modeller indbygget, som du kan bruge uden konto. Navnene skifter ofte, og de fleste er kun gratis i en periode. Det er helt normalt, at en model forsvinder fra listen.

Reglerne for data er forskellige fra model til model. Ifølge OpenCodes egen oversigt gælder for eksempel:

| Type gratis model | Hvad sker der med dine data |
| --- | --- |
| Nogle modeller | Gemmes ikke og bruges ikke til træning |
| Nogle modeller | Gemmes i 30 dage af sikkerhedshensyn |
| Flere modeller | **Gemmes og kan bruges til at forbedre modellen**, mens den er gratis |
| Prøvemodeller | Udbyderen beder dig om ikke at sende personlige eller fortrolige data |

Den aktuelle oversigt finder du på [opencode.ai/docs/console/models](https://opencode.ai/docs/console/models/).

!!! warning "Reglen på kurset"
    Behandl alt, hvad du skriver i en gratis model, som om det bliver læst af andre. Skriv aldrig:

    - Personoplysninger, f.eks. navne, CPR-numre, adresser eller helbredsoplysninger
    - Kundedata eller oplysninger fra en virksomhed, du er i praktik hos
    - Adgangskoder, API-nøgler eller andre hemmeligheder

    Brug opdigtede eller offentlige data i øvelserne.

## Når du skal arbejde med rigtige data

Skal du senere bruge agenter på rigtige opgaver, har du tre muligheder:

| Mulighed | Fordel | Ulempe |
| --- | --- | --- |
| **Betalt model fra en udbyder** med databehandleraftale, f.eks. Anthropic, OpenAI eller Mistral | Bedre modeller og klare vilkår | Koster penge pr. brug |
| **EU-udbyder**, f.eks. Mistral (Frankrig) | Data bliver i EU | Kræver betalt API-adgang |
| **Lokal model** via Ollama | Intet forlader din computer | Kræver en kraftig computer, og små modeller er dårligere til at bruge værktøjer |

Du forbinder en udbyder ved at indsætte en API-nøgle i OpenCodes indstillinger. Fremgangsmåden står i [Terminal og andre modeller](../opslag/terminal-og-modeller.md).

!!! tip "Når agenten opfører sig mærkeligt"
    De gratis modeller er gode, men ikke lige gode til alt. Kalder agenten ikke sine værktøjer, svarer den på engelsk, eller går den i stå, så prøv en anden gratis model, før du konkluderer, at opgaven er umulig.

!!! example "Øvelse"
    Åbn modelvælgeren og find to forskellige gratis modeller. Giv dem samme opgave i hver sin samtale, f.eks. "Skriv tre gode råd til et kort møde". Hvilken svarer bedst på dansk?
