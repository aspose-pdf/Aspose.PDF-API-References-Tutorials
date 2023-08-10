---
title: Skaffa XMP-metadata
linktitle: Skaffa XMP-metadata
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder GetXmpMetadata-funktionen i Aspose.PDF för .NET för att extrahera XMP-metadata från ett PDF-dokument med C#-källkod.
type: docs
weight: 200
url: /sv/net/programming-with-document/getxmpmetadata/
---
 Aspose.PDF för .NET är ett populärt PDF-manipuleringsbibliotek som gör det möjligt för utvecklare att skapa, redigera och konvertera PDF-filer i sina .NET-applikationer. En av funktionerna som erbjuds av detta bibliotek är möjligheten att extrahera XMP-metadata från ett PDF-dokument. Denna handledning guidar dig genom stegen för att använda`GetXmpMetadata` funktion i Aspose.PDF för .NET för att extrahera XMP-metadata från ett PDF-dokument.

## Steg 1: Installera Aspose.PDF för .NET

 För att använda Aspose.PDF för .NET i dina .NET-applikationer måste du först installera biblioteket. Du kan ladda ner den senaste versionen av biblioteket från[Aspose.PDF för .NET nedladdningssida](https://releases.aspose.com/pdf/net).

När du har laddat ner biblioteket, extrahera innehållet i ZIP-filen till en mapp på din dator. Du måste sedan lägga till en referens till Aspose.PDF för .NET DLL i ditt .NET-projekt.

## Steg 2: Ladda PDF-dokumentet

 När du har installerat Aspose.PDF för .NET och lagt till en referens till DLL-filen i ditt .NET-projekt kan du börja använda`GetXmpMetadata` funktion för att extrahera XMP-metadata från ett PDF-dokument.

Det första steget i att använda den här funktionen är att ladda PDF-dokumentet som du vill extrahera XMP-metadata från. För att göra detta kan du använda följande kod:

```csharp
// Sökvägen till PDF-dokumentet
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Öppna PDF-dokumentet
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 I koden ovan, ersätt`"YOUR DOCUMENT DIRECTORY"`med sökvägen till katalogen där ditt PDF-dokument finns. Denna kod kommer att ladda PDF-dokumentet i en`Document` objekt, som du sedan kan använda för att extrahera XMP-metadata.

## Steg 3: Extrahera XMP-metadata

För att extrahera XMP-metadata från ett PDF-dokument kan du använda följande kod:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 I ovanstående kod,`xmp:CreateDate`, `xmp:Nickname` , och`xmp:CustomProperty` är exempel på XMP-metadataegenskaper som du kan extrahera från ett PDF-dokument. Du kan ersätta dessa egenskapsnamn med namnen på alla andra XMP-metadataegenskaper som du vill extrahera.

### Exempel på källkod för Hämta XMP-metadata med Aspose.PDF för .NET

 Här är den fullständiga källkoden för att extrahera XMP-metadata från ett PDF-dokument med hjälp av`GetXmpMetadata` funktion i Aspose.PDF för .NET:

```csharp
// Sökvägen till PDF-dokumentet
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Öppna PDF-dokumentet
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extrahera XMP-metadata
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 I koden ovan, ersätt`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där ditt PDF-dokument finns. Den här koden extraherar XMP-metadata från PDF-dokumentet och matar ut det till konsolen.

## Slutsats

den här handledningen har vi diskuterat hur man använder Aspose.PDF för .NET för att extrahera XMP-metadata från ett PDF-dokument. XMP-metadata ger värdefull information om ett dokument, och Aspose.PDF för .NET tillåter utvecklare att komma åt denna information och använda den i sina applikationer efter behov. Genom att extrahera XMP-metadata kan utvecklare få insikter om ett dokuments skapandedatum, författare och andra beskrivande data. Denna information kan användas för att förbättra funktionaliteten och användarupplevelsen av PDF-applikationer. Aspose.PDF för .NET tillhandahåller ett enkelt och okomplicerat API för att komma åt XMP-metadata, vilket gör det enkelt att integrera den här funktionen i .NET-applikationer.

### FAQ's

#### F: Vad är XMP-metadata i ett PDF-dokument?

S: XMP-metadata i ett PDF-dokument hänvisar till XMP-information (Extensible Metadata Platform) som är inbäddad i dokumentet. XMP-metadata tillhandahåller ett standardsätt att lagra information om dokumentet, såsom författare, skapelsedatum, nyckelord och annan beskrivande data. Det möjliggör enkel hämtning och utbyte av metadata mellan olika system och applikationer.

#### F: Vilken typ av information kan extraheras med funktionen GetXmpMetadata?

 S: GetXmpMetadata-funktionen låter utvecklare extrahera olika XMP-metadataegenskaper från ett PDF-dokument. Några exempel på XMP-metadataegenskaper som kan extraheras är`xmp:CreateDate`, `xmp:Nickname` , och`xmp:CustomProperty`. Utvecklare kan komma åt dessa egenskaper och använda dem i sina applikationer efter behov.

#### F: Kan jag extrahera anpassade XMP-metadataegenskaper med Aspose.PDF för .NET?

S: Ja, du kan extrahera anpassade XMP-metadataegenskaper med Aspose.PDF för .NET. Anpassade XMP-metadataegenskaper kan inkluderas i ett PDF-dokument för att lagra ytterligare information som är specifik för din applikation eller dina krav. Du kan extrahera och använda dessa anpassade egenskaper efter behov.

#### F: Kan Aspose.PDF för .NET extrahera annan metadatainformation från ett PDF-dokument?

S: Ja, Aspose.PDF för .NET tillhandahåller olika funktioner för att extrahera metadatainformation från ett PDF-dokument. Förutom XMP-metadata kan du också extrahera information som dokumentinformation (titel, författare, ämne, nyckelord), PDF-version, krypteringsdetaljer och mer.