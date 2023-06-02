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

 I koden ovan, ersätt`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där ditt PDF-dokument finns. Denna kod kommer att ladda PDF-dokumentet i en`Document` objekt, som du sedan kan använda för att extrahera XMP-metadata.

## Steg 3: Extrahera XMP-metadata

För att extrahera XMP-metadata från ett PDF-dokument kan du använda följande kod:

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 I ovanstående kod,`xmp:CreateDate`, `xmp:Nickname` , och`xmp:CustomProperty`är exempel på XMP-metadataegenskaper som du kan extrahera från ett PDF-dokument. Du kan ersätta dessa egenskapsnamn med namnen på alla andra XMP-metadataegenskaper som du vill extrahera.

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