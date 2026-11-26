# Giv agenten filer

Agenten kan selv finde og læse filerne i dit projekt. Men du får bedre resultater, når du fortæller den præcis, hvilke filer opgaven handler om.

## Tre måder at give agenten en fil

**1. Nævn filen ved navn**

```text
Læs referat-marts.txt og find alle beslutninger.
```

**2. Peg på filen med @**

Skriv `@` i tekstfeltet. Så kommer der en liste over filerne i projektet, og du vælger den rigtige. Det sikrer, at agenten får præcis den fil, og ikke en med et lignende navn.

**3. Vedhæft eller træk filen ind**

Klik på knappen til at vedhæfte en fil, sæt en fil ind med Ctrl+V (Cmd+V på Mac), eller træk den direkte ind i tekstfeltet. Det er praktisk til filer, der ligger uden for projektmappen, f.eks. et skærmbillede.

## Hvilke filer kan agenten læse?

| Filtype | Kan agenten bruge den? |
| --- | --- |
| Tekst: `.txt`, `.md`, `.csv`, `.json`, `.html` | Ja, altid |
| Billeder: `.png`, `.jpg`, `.gif`, `.webp` | Ja, hvis modellen kan se billeder |
| PDF | Ja, hvis modellen kan læse PDF'er |
| Word (`.docx`), Excel (`.xlsx`), PowerPoint (`.pptx`) | Ikke direkte. Se nedenfor |
| Lyd og video | Nej |

Ikke alle gratis modeller kan se billeder eller læse PDF'er. Får du at vide, at agenten ikke kan se din fil, så prøv en anden model eller lav filen om til tekst.

## Word, Excel og PowerPoint

Office-filer er ikke almindelig tekst, så det sikreste er at gemme en kopi i et format, agenten kan læse:

| Du har | Gem en kopi som |
| --- | --- |
| Word-dokument | **PDF** eller **Almindelig tekst (.txt)** |
| Excel-ark | **CSV (semikolonsepareret)** for hvert ark |
| PowerPoint | **PDF** |

Du gør det med **Filer** og **Gem som** i Office-programmet.

Nogle gange klarer agenten det selv ved at skrive et lille program, der læser filen. Det kræver, at den må køre kommandoer på din computer, og det virker ikke altid. Se [Kontorfiler og data](../spor/kontorfiler.md).

!!! tip "Store filer"
    Hver vedhæftet fil må højst fylde 20 MB. Men agenten arbejder bedst med små filer. Har du en rapport på 200 sider, så giv den kun de kapitler, opgaven handler om.

!!! example "Øvelse"
    1. Gem et ufarligt Word-dokument som PDF og læg det i din øvelsesmappe.
    2. Skriv `@` og vælg PDF-filen.
    3. Bed agenten om et resumé på fem punkter.
    4. Virker det ikke, så skift model og prøv igen, eller gem dokumentet som `.txt` i stedet.
