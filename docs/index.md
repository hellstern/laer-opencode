# Lær OpenCode

**Et praktisk kursus i AI-agenter for dig, der ikke er udvikler.**

Du har sikkert prøvet at chatte med en AI. Du skriver et spørgsmål, du får et svar, og så kopierer du selv svaret over i et dokument. En **AI-agent** går et skridt videre: Den kan selv åbne filer, skrive nye filer, hente websider og dele en opgave op i trin. Du beskriver, hvad du vil have, og agenten gør arbejdet, mens du holder øje.

På dette kursus lærer du at bruge **OpenCode**, et gratis open source-program, til netop det. Du skal ikke kunne kode. Alt foregår i almindeligt dansk, i et skrivebordsprogram med knapper og menuer.

[Start første øvelse](start/index.md){ .md-button .md-button--primary }
[Vælg dit forløb](forside/laeringsstier.md){ .md-button }

## Hvad du kan efter kurset

- Give en agent en opgave og en mappe med filer at arbejde i
- Styre, hvad agenten må, og godkende eller afvise dens handlinger
- Lave faste instruktioner, så agenten husker dine ønsker fra gang til gang
- Bruge agenter til tekster, kontorfiler og research
- Bygge dine egne små agenter, skills og genvejskommandoer

## Kursets opbygning

<div class="grid" markdown>

<div class="kort" markdown>
[1. Kom i gang](start/index.md)

Hvad en agent er, casen, installation og din første opgave. Ca. 55 minutter.
</div>

<div class="kort" markdown>
[2. Daglig brug](daglig/index.md)

Projekter, filer, godkendelser, fortryd og gode opgaver. Ca. 1¾ time.
</div>

<div class="kort" markdown>
[3. Arbejdsgange](arbejdsgange/index.md)

Plan og Build, faste instruktioner, hjælpeagenter, et team af tre agenter og kildekontrol. Ca. 2½ time.
</div>

<div class="kort" markdown>
[4. Praksisspor](spor/index.md)

Vælg et eller flere spor: tekst, kontorfiler, research eller egne agenter. Slut med en afsluttende opgave.
</div>

<div class="kort" markdown>
[5. Opslag](opslag/index.md)

Ordliste, genveje, fejlfinding og kilder. Til når du har brug for det.
</div>

<div class="kort" markdown>
[6. Ekstra opgaver](ekstra/index.md)

Fire agentopgaver med vejledende løsninger, til dig, der er hurtigt færdig eller vil lære mere.
</div>

</div>

Del 1 til 3 er grundforløbet og tager ca. 5 timer. Det er fælles for alle, og du følger den samme case, [Lyngholt Tæpper](start/casen.md), hele vejen. Derefter vælger du de spor, der passer til dit arbejde, og slutter med en [afsluttende opgave](spor/afsluttende-opgave.md). Se [Sådan bruger du kurset](forside/laeringsstier.md) for forslag til forløb.

!!! abstract "Den røde tråd: skriv det én gang, genbrug det altid"
    I del 1 og 2 skriver du alt direkte i opgaven, hver gang. Det er bevidst. Du skal først lære, hvad en god opgave er, og hvilke regler du gentager.

    Undervejs gemmer du de regler, du skriver igen og igen, i en kladde. I del 3 bliver kladden til en **AGENTS.md**: en fil med faste instruktioner, som agenten læser ved hver eneste opgave. Kender du projekter i Claude med projektinstruktioner, er det samme idé.

    | Del | Du gør | Det gemmer du |
    | --- | --- | --- |
    | 1 og 2 | Skriver alle regler i opgaven | Regler, du gentager, i `regler-kladde.md` |
    | 3 | Gør kladden til `AGENTS.md` | Faste regler, agenten altid følger |
    | 4 | Bygger skills, kommandoer og agenter | Hele arbejdsgange, du starter med ét ord |

!!! warning "Inden du går i gang"
    Skriv aldrig personoplysninger, kundedata eller fortrolige oplysninger ind i OpenCode, når du bruger de gratis modeller. Læs [Modeller og dine data](start/modeller-og-data.md), før du arbejder med rigtige filer.

!!! info "Om kurset"
    Kurset er skrevet af Azanta til deltagerne på vores AI-forløb. Det bygger på den officielle dokumentation på [opencode.ai/docs](https://opencode.ai/docs/) og er inspireret af opbygningen i det kinesisk-engelske [OpenCode Practical Guide](https://learnopencode.com/en/). Teksterne er skrevet fra bunden på dansk og tilpasset dig, der ikke er udvikler. OpenCode ændrer sig hurtigt, så knapper og menuer kan se lidt anderledes ud i din version.
