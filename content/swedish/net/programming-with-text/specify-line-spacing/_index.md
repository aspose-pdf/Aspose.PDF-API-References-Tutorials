---
title: Ange radavstånd i PDF-fil
linktitle: Ange radavstånd i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du anger radavstånd i en PDF med Aspose.PDF för .NET med denna steg-för-steg-guide. Perfekt för utvecklare som söker exakt textformatering.
type: docs
weight: 510
url: /sv/net/programming-with-text/specify-line-spacing/
---
## Introduktion

Har du någonsin kämpat med att kontrollera radavståndet i en PDF-fil? Kanske har du haft text som ser för fullproppad ut eller som bara inte ser så snygg ut som du skulle vilja. I den här handledningen kommer vi att gå igenom hur du enkelt kan ange radavstånd i en PDF med Aspose.PDF för .NET. Vi kommer att använda en enkel, steg-för-steg-guide för att ta dig från en tom PDF-fil till en som inkluderar anpassat radavstånd. Detta är perfekt om du behöver precision i din textlayout för dokument som rapporter, fakturor eller certifikat.

## Förutsättningar

Innan vi hoppar in i koden, låt oss se till att du har allt du behöver:

1.  Aspose.PDF för .NET installerat. Om du inte har det, ta det från[Aspose.PDF nedladdningssida](https://releases.aspose.com/pdf/net/).
2. En .NET-utvecklingsmiljö (som Visual Studio).
3. En TrueType-teckensnittsfil (`.ttf` ) som vi kommer att använda i exemplet. Du kan använda vilket typsnitt som helst, men för den här guiden kommer vi att använda`HPSimplified.TTF` font.
4. Grundläggande kunskaper i C# och PDF-manipulation.

Om du är redo, låt oss gå vidare till att importera de nödvändiga paketen.

## Importera paket

ditt C#-projekt måste du importera Aspose.PDF-namnområdena för att fungera med PDF-funktionerna. Så här gör du det:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Dessa namnutrymmen låter dig skapa och manipulera PDF-dokument, samt arbeta med textformatering och teckensnittsalternativ.

Vi delar upp detta i lagom stora steg, så att du enkelt kan följa med. Varje steg kommer att fokusera på en viktig del av processen, från att ställa in din PDF till att specificera radavstånd.

## Steg 1: Konfigurera ditt projekt och definiera dokumentkatalogen

Det första vi behöver göra är att definiera var våra filer finns. Detta hjälper programmet att veta var man hittar typsnittet och var man ska spara den resulterande PDF-filen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 I det här steget byter du ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till var du lagrar dina filer. Det är här du placerar din teckensnittsfil (`HPSimplified.TTF`) och där PDF:en kommer att sparas.

## Steg 2: Ladda ett PDF-dokument

Nu måste vi skapa ett nytt PDF-dokument. För den här guiden börjar vi med ett tomt dokument, men du kan också ladda en befintlig PDF om det behövs.

```csharp
Document doc = new Document();
```

Detta skapar ett nytt, tomt PDF-dokument. Lätt, eller hur?

## Steg 3: Ställ in textformateringsalternativ

 Här händer magin. Vi anger radavståndsläget för texten vi vill lägga till i PDF-filen. Aspose.PDF ger oss flera alternativ, men i den här guiden kommer vi att använda`LineSpacingMode.FullSize`, vilket säkerställer att radavståndet respekteras fullt ut.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Denna kod ställer in radavståndsläget till`FullSize` , vilket säkerställer att texten kommer att visas med rätt mellanrum. Det finns andra alternativ som`Proportional` om du vill ha olika mellanrumsbeteenden, men för nu, låt oss hålla oss till`FullSize`.

## Steg 4: Skapa ett textfragment

Nu ska vi skapa den faktiska texten som kommer att placeras i PDF:en. Den här texten kommer att respektera radavståndet vi har definierat.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Vi har skapat ett textfragment med strängen`"Hello world"`. Du kan naturligtvis anpassa denna text till vad du vill.

## Steg 5: Ladda och använd ett anpassat teckensnitt

För att få texten att sticka ut kommer vi att ladda ett anpassat TrueType-teckensnitt från en fil. Det här steget är valfritt, men det kan ge dina PDF-filer en professionell touch.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Här laddar vi teckensnittsfilen och applicerar den på textfragmentet. Om filsökvägen är giltig används typsnittet. Annars tillämpas standardteckensnittet.

## Steg 6: Ställ in textposition och formatering

Därefter måste vi placera texten på PDF-filen. Vi kommer också att tillämpa de formateringsalternativ vi skapade tidigare.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 De`Position` metod ställer in koordinaterna där texten kommer att visas på sidan (i detta fall 100 enheter från vänster och 600 enheter från botten). Formateringsalternativen, inklusive radavståndsläget, tillämpas här.

## Steg 7: Lägg till text på PDF-sidan

Nu när vår text är formaterad och placerad är det dags att lägga till den i PDF-dokumentet.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Denna kod skapar en ny sida i PDF-dokumentet och lägger till textfragmentet till det.

## Steg 8: Spara PDF-filen

Vi har nått det sista steget! Nu när allt är inställt, låt oss spara PDF:en.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Detta sparar PDF-filen med angivet radavstånd, och din fil är klar!

## Slutsats

Och det är det! Du har precis skapat ett PDF-dokument med anpassat radavstånd med Aspose.PDF för .NET. Det är ett kraftfullt verktyg som låter dig kontrollera alla aspekter av dina PDF-filer, och det här är bara ett exempel på vad du kan uppnå. Från textplacering till formatering, möjligheterna är oändliga.

Om du funderar på att dyka djupare in i PDF-manipulation, erbjuder Aspose.PDF en mängd funktioner att utforska. Tveka inte att experimentera och tänja på gränserna för vad du kan göra med dina dokument!

## FAQ's

### Kan jag justera radavståndet till andra lägen?  
 Ja, du kan använda andra lägen som`Proportional` eller`Fixed` beroende på dina behov.

### Är det möjligt att ladda typsnitt från systemet istället för en fil?  
 Ja, du kan ladda systeminstallerade teckensnitt med hjälp av`FontRepository`.

### Kan jag använda Aspose.PDF för .NET med andra filformat?  
Absolut! Aspose.PDF för .NET stöder en mängd olika format som XML, HTML och mer.

### Behöver jag en licens för att använda Aspose.PDF för .NET?  
Ja, för full funktionalitet behöver du en licens som du kan få[här](https://purchase.aspose.com/buy).

### Hur ställer jag in radavståndet för flera stycken?  
 Du kan ansöka`TextFormattingOptions` till var och en`TextFragment` eller`TextParagraph` för att styra avståndet för flera rader eller stycken.