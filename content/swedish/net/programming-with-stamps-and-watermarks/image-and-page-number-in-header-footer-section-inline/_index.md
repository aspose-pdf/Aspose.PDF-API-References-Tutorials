---
title: Bild och sidnummer i sidfotsavsnittet Inline
linktitle: Bild och sidnummer i sidfotsavsnittet Inline
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till en bild och sidnummer inline i rubriken i en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 120
url: /sv/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Introduktion

Aspose.PDF för .NET är ett kraftfullt verktyg som ger omfattande möjligheter för att manipulera och generera PDF-filer. Oavsett om du behöver lägga till bilder, anpassa sidhuvuden och sidfötter eller hantera text, har Aspose.PDF dig täckt. I den här självstudien kommer vi att utforska hur du lägger till en bild och ett sidnummer inline i sidhuvudet eller sidfoten i ett PDF-dokument. Låt oss dyka direkt in och bryta ner processen steg för steg.

## Förutsättningar

Innan vi går in i koden, låt oss se till att du har allt på plats för att följa med:

-  Aspose.PDF för .NET: Ladda ner den senaste versionen från[Aspose PDF-nedladdningssida](https://releases.aspose.com/pdf/net/).
- Utvecklingsmiljö: Du behöver en C# IDE som Visual Studio.
-  Licens: Om du inte har en licens ännu kan du få en[tillfällig licens här](https://purchase.aspose.com/temporary-license/) eller köp en hel från[Aspose butik](https://purchase.aspose.com/buy).

Nu när du har förutsättningarna redo, låt oss börja.

## Importera paket

Innan du börjar koda, se till att importera de nödvändiga namnrymden:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Dessa paket låter dig arbeta med PDF-filer och textmanipulering.

## Steg 1: Konfigurera dokumentkatalogen

Det första vi behöver göra är att definiera sökvägen till katalogen där vår PDF-fil ska sparas. Den här sökvägen kan anpassas till ditt projekts mapp eller valfri plats på din dator.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Denna variabel håller platsen där ditt dokument kommer att lagras. Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska vägen.

## Steg 2: Instantiera PDF-dokumentet

 I det här steget skapar vi en ny instans av`Aspose.Pdf.Document` objekt. Detta objekt kommer att fungera som ryggraden i din PDF-fil.

```csharp
// Instantiera ett dokumentobjekt genom att anropa dess tomma konstruktor
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Här skapar vi en tom PDF-fil som vi senare kan fylla med innehåll.

## Steg 3: Lägg till en sida till PDF-filen

Din PDF behöver minst en sida där du kan lägga till sidhuvuden, sidfötter och innehåll. Låt oss lägga till en tom sida i vårt dokument.

```csharp
// Skapa en sida i Pdf-objektet
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Genom att ringa`pdf1.Pages.Add()`läggs en ny sida till i dokumentet, redo för anpassning av sidhuvud och sidfot.

## Steg 4: Skapa och ställ in rubriken

Nu är det dags att skapa rubriken för dokumentet. Det är här vi lägger till text, bild och sidnummer.

```csharp
// Skapa rubriksektion för dokumentet
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Ställ in rubriken för PDF-filen
page.Header = header;
```

 Vi skapar en`HeaderFooter` objekt och tilldela det till`Header` egenskapen för sidan, vilket säkerställer att allt vi lägger till i sidhuvudet visas högst upp på sidan.

## Steg 5: Lägg till inbäddad text i rubriken

 Att lägga till text är lika enkelt som att skapa en`TextFragment` och specificera dess egenskaper. Låt oss lägga till lite färgad text i vår rubrik.

```csharp
// Skapa ett textobjekt
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Ange färg
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 I detta steg skapar vi en`TextFragment` med innehållet "Aspose.Pdf är en robust komponent av" och ställ in dess färg till blått. De`IsInLineParagraph` egenskapen säkerställer att texten är inline, vilket betyder att den kommer att visas på samma rad som de andra elementen (som bilden och ytterligare text).

## Steg 6: Infoga en inbyggd bild i rubriken

För att göra din rubrik visuellt tilltalande kan du lägga till en bild inline med texten. Detta kan vara ditt företags logotyp eller någon annan grafik.

```csharp
// Skapa ett bildobjekt i avsnittet
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Ställ in sökvägen till bildfilen
image1.File = dataDir + "aspose-logo.jpg";
// Ställ in information om bildbredden
image1.FixWidth = 50;
image1.FixHeight = 20;
// Ange att seg1s InlineParagraph är en bild.
image1.IsInLineParagraph = true;
```

 Här lägger vi till en bild i rubriken genom att skapa en`Image` objekt, ange dess bana och justera bredd och höjd. De`IsInLineParagraph` ser till att bilden är i linje med texten.

## Steg 7: Lägg till ytterligare inlinetext för att komplettera rubriken

Låt oss lägga till lite mer text för att komplettera den infogade rubriken.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 I den här delen skapar vi en annan`TextFragment` med innehållet "Pty Ltd." och ställ in dess färg till rödbrun. Både textfragment och bilden läggs till i rubriken.

## Steg 8: Spara PDF-filen

När du har ställt in rubriken är det dags att spara PDF-filen.

```csharp
// Spara pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 De`Save` metoden skriver den slutliga PDF-filen till den angivna platsen.

## Slutsats

Grattis! Du har framgångsrikt lagt till en bild och text i rubriken på ett PDF-dokument med Aspose.PDF för .NET. Den här handledningen ledde dig genom de väsentliga stegen, inklusive att skapa ett dokument, lägga till sidor, infoga rubriker och placera inlineinnehåll som text och bilder. Aspose.PDF ger dig otrolig flexibilitet att hantera dina PDF-filer, oavsett om det handlar om att manipulera sidhuvuden, sidfötter eller komplext innehåll. 

## FAQ's

### Kan jag lägga till ett sidnummer i rubriken också?
 Ja! Du kan enkelt lägga till ett sidnummer genom att använda`TextFragment` klass och formatera den efter behov. Sätt bara in det i rubriken som inlineinnehåll.

### Hur ställer jag in en bakgrundsbild i rubriken?
 Du kan använda`BackgroundImage` egendom av`HeaderFooter` klass för att ställa in en bakgrundsbild. Detta är dock inte inlineinnehåll, och det kommer att täcka hela rubrikområdet.

### Är det möjligt att använda andra bildformat än JPEG?
Absolut! Aspose.PDF stöder olika bildformat som PNG, BMP och GIF.

### Kan jag anpassa teckensnittet för texten i rubriken?
 Ja, du kan använda`TextState`objekt för att ändra teckensnitt, storlek och stil på texten.

### Behöver jag en licens för att använda Aspose.PDF för .NET?
 Ja, Aspose.PDF kräver en licens för produktionsanvändning, men du kan börja med en[gratis provperiod här](https://releases.aspose.com/).