---
title: Extrahera kolumntext i PDF-fil
linktitle: Extrahera kolumntext i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar kolumner med text från PDF-filer med Aspose.PDF för .NET. Den här guiden bryter ner varje steg med kodexempel och förklaringar.
type: docs
weight: 150
url: /sv/net/programming-with-text/extract-columns-text/
---
## Introduktion

Arbetar du med PDF-filer och behöver extrahera text i ett specifikt kolumnformat? Oavsett om du behandlar fakturor, rapporter eller strukturerade dokument kan det vara svårt att extrahera text från en PDF-fil. Det är här Aspose.PDF för .NET går in för att förenkla processen. I den här handledningen går vi igenom hur du enkelt extraherar kolumner med text från en PDF-fil. 

## Förutsättningar

Innan vi dyker in i koden, låt oss täcka de väsentliga sakerna du behöver:

-  Aspose.PDF för .NET: Se till att du har den senaste versionen av Aspose.PDF för .NET installerad. Om inte, kan du[ladda ner den här](https://releases.aspose.com/pdf/net/).
- Utvecklingsmiljö: Du behöver Visual Studio eller annan .NET-utvecklingsmiljö för att arbeta med koden.
- PDF-dokument: Ha ett exempel på PDF-dokument till hands, helst ett med textkolumner, eftersom vi kommer att extrahera text från det.

 Om du inte har installerat Aspose.PDF för .NET än, kan du ta en[gratis provperiod](https://releases.aspose.com/) eller[köpa en licens](https://purchase.aspose.com/buy) för alla funktioner. Du kan också ansöka om en[tillfällig licens](https://purchase.aspose.com/temporary-license) om det behövs.

## Importera namnområden

För att använda Aspose.PDF för .NET i ditt projekt måste du importera följande namnrymder:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Steg-för-steg-guide: Extrahera textkolumner från en PDF

Låt oss nu dela upp varje del av koden för att bättre förstå hur den fungerar. Följ med när vi går steg för steg och förklarar varje segment av processen.

## Steg 1: Ladda PDF-dokumentet

 Det första du behöver göra är att ladda din PDF-fil i`Document`objekt. Så här interagerar Aspose.PDF med ditt dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 I det här steget definierar vi helt enkelt katalogen där ditt PDF-dokument lagras. Ersätta`"YOUR DOCUMENT DIRECTORY"` med sökvägen till din lokala PDF-fil. De`Document` objekt laddar PDF:en i minnet, vilket gör den tillgänglig för vidare bearbetning.

## Steg 2: Ställ in Text Fragment Absorber

 Därefter använder vi en`TextFragmentAbsorber` för att absorbera eller fånga all text från PDF-filen. Denna absorberklass är designad för att extrahera textfragment från specifika områden i din PDF, vilket gör den idealisk för att extrahera textkolumner.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Här skapar vi en instans av`TextFragmentAbsorber` och tillämpa den på alla sidor i PDF-filen med`Accept()` . De`TextFragmentCollection` lagrar den extraherade texten, och från denna samling kan vi manipulera eller extrahera text efter behov.

## Steg 3: Justera teckenstorleken för den extraherade texten

När du har fångat textfragmenten kanske du vill minska deras teckenstorlek, särskilt när originaltexten är för stor. I det här exemplet minskar vi teckensnittsstorleken med 70 %.

```csharp
foreach (TextFragment tf in tfc)
{
    // Minska teckenstorleken med 70 %
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Denna kod går igenom var och en`TextFragment` i samlingen och minskar dess teckenstorlek med 70 %. Att justera teckenstorleken kan göra den extraherade texten lättare att hantera, särskilt om du formaterar den för olika ändamål.

## Steg 4: Spara dokumentet i en minnesström

 Efter att ha modifierat texten sparar vi PDF-filen i en`MemoryStream`. Detta gör att vi kan behålla dokumentet i minnet för vidare bearbetning utan att behöva skriva tillbaka det till disken.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Här sparar vi PDF:en i en minnesström och laddar sedan om dokumentet. Den här metoden är användbar när du arbetar med stora filer och vill undvika onödiga diskoperationer.

## Steg 5: Extrahera all text med Text Absorber

 Nu när vi har förberett PDF:en är det dags att extrahera texten. Vi använder`TextAbsorber` för att hämta all text från dokumentet.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 I detta steg,`TextAbsorber` absorberar all text från PDF:en och den extraherade texten lagras i`extractedText` sträng. Det är här magin händer - dina textkolumner är nu i vanlig textformat!

## Steg 6: Spara den extraherade texten till en fil

 Slutligen sparar vi den extraherade texten i en`.txt` fil för enkel åtkomst och vidare användning.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Denna kod skriver den extraherade texten till en ny`.txt` filen och sparar den i din angivna katalog. Ett meddelande visas i konsolen för att bekräfta att processen lyckades.

## Slutsats

Där har du det! Att extrahera kolumner med text från en PDF-fil med Aspose.PDF för .NET är enklare än du kanske tror. Med bara några rader kod kan du ladda en PDF, extrahera specifik text, justera formateringen och spara resultaten i en textfil.

Den här tekniken är otroligt användbar för att bearbeta strukturerade dokument som tabeller, rapporter eller annat innehåll organiserat i kolumner. Oavsett om du behöver automatisera datautvinning eller bearbeta bulkdokument, tillhandahåller Aspose.PDF verktygen för att få det att hända effektivt.

## FAQ's

### Kan jag extrahera text från specifika sidor i en PDF?  
 Ja! Du kan ändra`TextFragmentAbsorber` för att rikta in sig på specifika sidor med hjälp av`pdfDocument.Pages[pageIndex].Accept(tfa);` metod.

### Är det möjligt att extrahera text från endast en kolumn i en PDF med flera kolumner?  
 Ja, men du måste arbeta med koordinaterna för textfragmenten med hjälp av`TextFragment.Rectangle` för att rikta in sig på specifika områden i dokumentet.

### Hur kan jag förbättra noggrannheten i textextraktion?  
 För bättre noggrannhet, se till att PDF-filens struktur är väldefinierad och undvik dokument med komplexa layouter. Du kan också finjustera`TextFragmentAbsorber` för att extrahera text baserat på teckensnittsstilar, storlekar eller regioner.

### Stöder Aspose.PDF textextraktion från skannade dokument?  
Ja, men du måste använda OCR-teknik (Optical Character Recognition). Aspose tillhandahåller verktyg för detta också.

### Hur hanterar jag stora PDF-filer med tusentals sidor?  
För stora PDF-filer, bearbeta dokumentet i bitar genom att extrahera text från några sidor åt gången för att undvika hög minnesanvändning.