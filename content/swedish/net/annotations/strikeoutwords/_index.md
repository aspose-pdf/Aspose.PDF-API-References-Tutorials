---
title: Stryk ut ord
linktitle: Stryk ut ord
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du stryker ut ord i en PDF med Aspose.PDF för .NET med den här omfattande steg-för-steg-guiden. Förbättra dina färdigheter i dokumentredigering.
type: docs
weight: 150
url: /sv/net/annotations/strikeoutwords/
---
## Introduktion

Har du någonsin märkt att du behöver betona specifik text i en PDF genom att stryka över den? Oavsett om du granskar dokument, markerar text eller helt enkelt behöver markera vissa avsnitt, kan strykning av ord vara ett värdefullt verktyg. I den här handledningen kommer vi att utforska hur man gör just det med Aspose.PDF för .NET. Den här omfattande guiden leder dig genom varje steg och säkerställer att du har all information som behövs för att effektivt implementera den här funktionen i dina .NET-applikationer. 

## Förutsättningar

Innan vi hoppar in i koden finns det några förutsättningar som du måste uppfylla för att följa med den här handledningen:

1.  Aspose.PDF for .NET Library: Se till att du har Aspose.PDF för .NET-biblioteket installerat. Du kan[ladda ner den här](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Se till att du har .NET Framework installerat på din dator. Denna handledning är utformad för .NET-applikationer.

3. Utvecklingsmiljö: Du behöver en IDE som Visual Studio för att skriva och köra din kod.

4. PDF-dokument: Ha ett exempel på en PDF-fil redo som du vill arbeta med. Detta kommer att vara dokumentet där vi stryker texten.

5. Grundläggande C#-kunskaper: Bekantskap med C#-programmering är nödvändig för att förstå och implementera stegen i denna handledning.

## Importera paket

Innan vi kan börja koda måste vi importera de nödvändiga namnrymden i vårt .NET-projekt. Detta ger oss tillgång till de klasser och metoder som krävs för att manipulera PDF-filer med Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Dessa namnrymder är viktiga för att arbeta med PDF-dokument, hantera text och lägga till anteckningar som strykningar.

det här avsnittet kommer vi att dela upp processen att stryka ut ord i ett PDF-dokument i enkla, hanterbara steg. Varje steg kommer att åtföljas av en detaljerad förklaring för att säkerställa att du förstår hur allt fungerar.

## Steg 1: Ladda PDF-dokumentet

Det första steget är att ladda PDF-dokumentet som du vill redigera. Detta dokument kommer att vara det där du kommer att stryka ut specifika ord eller fraser.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna PDF-dokumentet
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Denna variabel innehåller sökvägen till din dokumentkatalog. Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där din PDF-fil finns.
- `Document` : Den`Document` klass representerar ett PDF-dokument. Genom att skicka filsökvägen till dess konstruktor öppnar vi PDF-filen för bearbetning.

## Steg 2: Skapa en TextFragment Absorber för att hitta specifik text

 Därefter skapar vi en instans av`TextFragmentAbsorber` för att söka efter ett specifikt textfragment i PDF-dokumentet. Detta gör att vi kan hitta den text vi vill stryka ut.

```csharp
// Skapa TextFragment Absorber-instans för att söka efter ett specifikt textfragment
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Den här klassen används för att hitta och arbeta med specifika textfragment i PDF-dokumentet. I det här exemplet söker vi efter ordet "Estoque". Ersätt "Estoque" med ordet eller frasen du vill hitta i ditt dokument.

## Steg 3: Iterera genom sidorna i PDF-dokumentet

 Nu när vi har vår`TextFragmentAbsorber`, måste vi iterera genom varje sida i PDF-dokumentet för att hitta den angivna texten.

```csharp
// Iterera genom sidorna i PDF-dokumentet
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Hämta den aktuella sidan i PDF-dokumentet
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Denna loop itererar genom varje sida i PDF-dokumentet.
- `document.Pages[i]`: Hämtar den aktuella sidan som bearbetas.
- `page.Accept(textFragmentAbsorber)` : Denna metod tillämpar`TextFragmentAbsorber` till den aktuella sidan och söker efter den angivna texten.

## Steg 4: Samla in och bearbeta textfragmenten

Efter att ha gått igenom sidorna samlar vi in de textfragment som hittats och förbereder dem för vidare bearbetning.

```csharp
// Skapa en samling av absorberade textfragment
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Den här samlingen lagrar alla textfragment som hittades i dokumentet. Vi använder den här samlingen i nästa steg för att stryka över texten.

## Steg 5: Iterera genom textfragmenten och stryk ut dem

I det här steget går vi igenom varje textfragment i vår samling och lägger till en överstruken kommentar på det.

```csharp
// Iterera över samlingen av textfragment
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Få de rektangulära dimensionerna för TextFragment-objektet
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Instantiera StrikeOut Annotation-instans
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Ställ in egenskaper för överstruken kommentar
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Lägg till anteckningen i anteckningssamlingen på textfragmentets sida
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Den här raden hämtar det aktuella textfragmentet.
- `Aspose.Pdf.Rectangle`: Vi beräknar de rektangulära dimensionerna för textfragmentet för att avgöra var strykningen ska tillämpas.
- `StrikeOutAnnotation`: Den här klassen representerar den genomstrukna kommentaren. Vi instansierar det med den beräknade rektangeln och den aktuella sidan.
- `strikeOut.Opacity`: Den här egenskapen ställer in opaciteten för genomstruken, vilket gör den 80 % synlig.
- `strikeOut.Color`Vi ställer in färgen på strykningen till röd. Du kan ändra detta till vilken färg du föredrar.
- `textFragment.Page.Annotations.Add(strikeOut)`: Detta lägger till en överstruken kommentar på sidan.

## Steg 6: Spara det modifierade PDF-dokumentet

Det sista steget är att spara det ändrade PDF-dokumentet med strykningarna tillämpade.

```csharp
// Spara det uppdaterade PDF-dokumentet
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Detta skapar ett nytt filnamn för det ändrade dokumentet. Originalfilen förblir oförändrad.
- `document.Save(dataDir)`: Sparar PDF-dokumentet med strykningarna till den angivna platsen.

## Slutsats

Grattis! Du har lyckats stryka ut specifika ord i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa denna steg-för-steg-guide kan du nu anpassa PDF-dokument genom att markera eller stryka ut text, vilket gör dem mer dynamiska och skräddarsydda efter dina behov. Oavsett om du kommenterar juridiska dokument, förbereder rapporter eller bara markerar text för granskning, har den här handledningen utrustat dig med färdigheter för att göra det effektivt.

## FAQ's

### Kan jag ändra färgen på strykningen?

 Ja, du kan ändra färgen genom att ändra`strikeOut.Color`egendom. Du kan till exempel ställa in den på`Aspose.Pdf.Color.Blue` för en blå överstrykning.

### Är det möjligt att stryka ut flera ord samtidigt?

 Absolut! De`TextFragmentAbsorber` kan användas för att söka efter valfritt ord eller fras i dokumentet. Du kan tillämpa överstruken på flera instanser genom att iterera genom`TextFragmentCollection`.

### Vad händer om jag bara vill stryka text på specifika sidor?

 Du kan ändra slingan som itererar genom sidorna så att den bara inkluderar de sidor du vill ändra. Till exempel,`for (int i = 1; i <= 3; i++)` skulle tillämpa strykningen endast på de tre första sidorna.

### Hur kan jag justera tjockleken på strecklinjen?

 Du kan justera tjockleken på strecklinjen genom att ändra`Border` egendom av`StrikeOutAnnotation`. Detta möjliggör anpassning av överstruket utseende.

### Finns det något sätt att ångra strykningen efter att ha sparat dokumentet?

När dokumentet har sparats är överstruken permanent. Om du behöver behålla originaltexten utan överstrykning, överväg att spara en säkerhetskopia av originaldokumentet innan du gör några ändringar.