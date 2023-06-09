---
title: Ställ in bildstorlek
linktitle: Ställ in bildstorlek
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ställa in storleken på en bild i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 270
url: /sv/net/programming-with-images/set-image-size/
---

den här handledningen går vi igenom hur du ställer in storleken på en bild i ett PDF-dokument med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan utvecklingsmiljö installerad och konfigurerad.
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat. Du kan ladda ner den från Asposes officiella webbplats.

## Steg 1: Skapa PDF-dokumentet

För att komma igång använder du följande kod för att skapa ett nytt PDF-dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Instantiera ett dokumentobjekt
Document doc = new Document();

// Lägg till en sida till samlingen av sidor i PDF-filen
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Steg 2: Lade till bild

Därefter lägger vi till en bild på sidan i PDF-dokumentet. Använd följande kod:

```csharp
// Skapa en bildinstans
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Ställ in bildens bredd och höjd i punkter
img. FixWidth = 100;
img. FixHeight = 100;

// Ställ in bildtyp till okänd (Okänd)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Sökväg till bildens källfil
img.File = dataDir + "aspose-logo.jpg";

// Lägg till bilden i sidans styckesamling
page.Paragraphs.Add(img);
```

Se till att ange rätt sökväg till bildkällfilen.

## Steg 3: Ställa in sidegenskaper

Slutligen ställer vi in egenskaperna för sidan, inklusive dess bredd och höjd. Använd följande kod:

```csharp
// Ställ in sidegenskaper
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Exempel på källkod för Set Image Size med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instantiera dokumentobjekt
Document doc = new Document();
//lägg till sida till sidor samling av PDF-fil
Aspose.Pdf.Page page = doc.Pages.Add();
// Skapa en bildinstans
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Ställ in bildbredd och höjd i punkter
img.FixWidth = 100;
img.FixHeight = 100;
// Ställ in bildtyp som SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Sökväg för källfil
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Ställ in sidegenskaper
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// spara den resulterande PDF-filen
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har framgångsrikt angett storleken på en bild i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu tillämpa den här metoden på dina egna projekt för att justera storleken på bilder i PDF-filer.