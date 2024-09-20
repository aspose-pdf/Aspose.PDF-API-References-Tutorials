---
title: Sök och hämta text allt
linktitle: Sök och hämta text allt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker och hämtar text från alla sidor i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 420
url: /sv/net/programming-with-text/search-and-get-text-all/
---
## Introduktion

Har du någonsin behövt extrahera specifik text från en PDF men tyckt att det var svårt? PDF-filer kan ibland kännas som låsta behållare, vilket gör det svårt att få den information du behöver. Men här är de goda nyheterna: med Aspose.PDF för .NET kan du enkelt söka och hämta text från vilken PDF-fil som helst. Detta kraftfulla bibliotek ger allt du behöver för att arbeta med PDF-filer i dina .NET-program, vilket gör textextraktion till en lek. I den här handledningen går vi igenom processen att söka och extrahera text från en PDF-fil med Aspose.PDF för .NET. Oavsett om du bygger ett textanalysverktyg eller bara behöver automatisera datautvinning från PDF-rapporter, så är du på rätt plats!

## Förutsättningar

Innan vi går in i koden, låt oss se till att du har allt konfigurerat:

1. Aspose.PDF för .NET: Du måste ladda ner och installera Aspose.PDF för .NET. Du kan hämta det från nedladdningssidan[här](https://releases.aspose.com/pdf/net/).
2. .NET-miljö: Se till att du har konfigurerat .NET Framework eller .NET Core på din utvecklingsmaskin.
3. Grundläggande C##-kunskaper: Viss förtrogenhet med C# och arbete med .NET-projekt rekommenderas.
4.  PDF-dokument: Ett exempel på PDF-fil som vi kommer att extrahera text från. I det här exemplet kommer vi att använda`SearchAndGetTextFromAll.pdf`.

## Importera paket

Innan du skriver någon kod måste du importera de nödvändiga namnrymden till ditt projekt för att arbeta med Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Dessa namnrymder ger tillgång till dokumentobjektmodellen för PDF:en och tillåter oss att manipulera text i filen.

Låt oss dela upp processen i enkla steg så att du enkelt kan följa med.

## Steg 1: Ställ in dokumentkatalogen

Först och främst måste du ange sökvägen till katalogen där din PDF-fil finns. Detta hjälper programmet att hitta filen som du ska extrahera texten från.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  De`dataDir` variabel bör peka till katalogen där din`SearchAndGetTextFromAll.pdf` filen lagras.
-  Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen på din maskin.

## Steg 2: Öppna PDF-dokumentet

Därefter öppnar vi PDF-dokumentet med Aspose.PDF:s`Document` objekt.

```csharp
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Vi skapar en ny instans av`Document` klass genom att skicka hela sökvägen till PDF-filen.
- Detta kommer att ladda PDF:en i minnet, vilket gör den redo för bearbetning.

## Steg 3: Skapa en textabsorberare

 De`TextFragmentAbsorber` objekt används för att söka efter specifik text i PDF:en. I det här fallet kommer vi att leta efter ordet "text".

```csharp
// Skapa TextAbsorber-objekt för att hitta alla instanser av den inmatade sökfrasen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  De`TextFragmentAbsorber` initieras med strängen`"text"`. Det betyder att det kommer att leta efter alla förekomster av ordet "text" i PDF-dokumentet.

## Steg 4: Acceptera Absorbern för alla sidor

Nu kommer vi att instruera PDF-dokumentet att acceptera absorbenten och söka efter texten på alla dess sidor.

```csharp
// Acceptera absorbenten för alla sidor
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  De`Accept` metod tillämpas på dokumentets sidor. Detta kommer att söka på alla sidor efter den angivna texten.

## Steg 5: Extrahera textfragment

När absorbatorn har skannat dokumentet kan vi hämta de extraherade textfragmenten.

```csharp
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  De`TextFragments` egendom av`TextFragmentAbsorber` returnerar en samling av alla textfragment som matchar söktermen.

## Steg 6: Gå igenom textfragmenten

Nu när vi har samlingen av textfragment går vi igenom dem och extraherar detaljerna.

```csharp
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  De`foreach` loop itererar genom varje`TextFragment` i samlingen.
- Vi skriver ut olika egenskaper för varje fragment, som den faktiska texten, dess placering på sidan, teckensnittsdetaljer och teckenstorlek.
-  De`XIndent` och`YIndent` egenskaper ger de exakta koordinaterna för textfragmentet i PDF-filen.

## Slutsats

Och där har du det! Med bara några rader kod har vi framgångsrikt sökt och extraherat text från en PDF med Aspose.PDF för .NET. Flexibiliteten hos Aspose.PDF låter dig manipulera PDF-filer på många sätt, vilket gör det till ett utmärkt val för utvecklare som behöver robusta PDF-lösningar i .NET-miljöer. Du kan enkelt utöka det här exemplet för att söka efter andra ord, extrahera fler detaljer eller till och med manipulera PDF-innehållet baserat på dina behov. Förhoppningsvis har den här guiden gett dig ett tydligt och enkelt sätt att arbeta med PDF-filer. Varsågod och prova det med dina egna PDF-filer!

## FAQ's

### Kan jag söka efter flera ord samtidigt?  
 Ja, du kan ändra`TextFragmentAbsorber` för att söka efter flera fraser genom att justera söksträngen därefter.

### Vad händer om texten sträcker sig över flera rader?  
Aspose.PDF kommer fortfarande att känna igen och extrahera text även om den sträcker sig över flera rader. Du kan hantera dessa fragment individuellt.

### Hur sparar jag den extraherade texten till en fil?  
 Du kan skriva den extraherade texten till en fil med vanliga C#-fil I/O-operationer, som t.ex`StreamWriter`.

### Stöder Aspose.PDF extrahering av text från skannade PDF-filer?  
Aspose.PDF stöder inte OCR. För skannade PDF-filer skulle du behöva ett OCR-verktyg för att känna igen texten.

### Hur hanterar jag krypterade PDF-filer?  
Om din PDF är lösenordsskyddad kan du låsa upp den med Aspose.PDF genom att ange lösenordet när du laddar dokumentet.