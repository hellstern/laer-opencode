# Plan og Build

OpenCode har to indbyggede hovedagenter, som du kan skifte imellem:

| Agent | Hvad den gør | Brug den når |
| --- | --- | --- |
| **Build** | Standardagenten. Den læser, skriver og retter filer og kan køre kommandoer | Du ved, hvad du vil have, og agenten skal udføre det |
| **Plan** | Undersøger og planlægger, men retter ikke i dine filer | Opgaven er stor eller uklar, og du vil se planen først |

Du vælger agent i menuen ved tekstfeltet. Det står hele tiden, hvilken agent der er aktiv.

## Arbejdsgangen: Planlæg, ret, udfør

1. **Vælg Plan** og beskriv opgaven.
2. **Læs planen.** Er der trin, der mangler, eller trin, du ikke vil have?
3. **Ret planen** i samme samtale: "Drop trin 3. Tilføj et trin, hvor du tjekker datoerne."
4. **Skift til Build** og skriv: "Udfør planen."

Det tager et par minutter ekstra, men du undgår, at agenten bruger lang tid på noget forkert.

## Eksempel

Vælg **Plan** og skriv:

```text
Jeg skal lave et kursusbevis til 25 deltagere. Navnene ligger i @deltagere.csv. Lav en plan for, hvordan du laver ét bevis pr. deltager som PDF. Gør ikke noget endnu.
```

Agenten svarer med en plan i trin. Måske foreslår den at lave en skabelon først, så du kan godkende layoutet. Ret planen, og skift derefter til **Build**.

!!! tip "Plan er også god til spørgsmål"
    Vil du bare forstå noget, f.eks. "Hvad står der i disse fem kontrakter om opsigelse?", er Plan et godt valg. Så er du sikker på, at agenten ikke kommer til at rette i filerne.

!!! example "Øvelse"
    1. Læg tre korte tekster i en mappe, f.eks. tre opslag fra en hjemmeside.
    2. Vælg **Plan** og bed om en plan for at lave et fælles nyhedsbrev ud fra teksterne.
    3. Ret mindst én ting i planen.
    4. Skift til **Build** og få planen udført.
