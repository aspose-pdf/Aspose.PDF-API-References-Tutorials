---
title: Ställ in bildstorlek i PDF-fil
linktitle: Ställ in bildstorlek i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ställa in storleken på en bild i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 270
url: /sv/net/programming-with-images/set-image-size/
---
I den här handledningen går vi igenom hur du ställer in storleken på en bild i PDF-fil med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan utvecklingsmiljö installerad och konfigurerad.
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat. Du kan ladda ner den från Asposes officiella hemsida.

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

//Sökväg till bildkällfilen
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
// lägg till sida till sidor samling av PDF-fil
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

### Vanliga frågor för inställd bildstorlek i PDF-fil

#### F: Vad är syftet med att ställa in storleken på en bild i ett PDF-dokument med Aspose.PDF för .NET?

S: Syftet med att ställa in storleken på en bild i ett PDF-dokument är att kontrollera bildens mått när den läggs till i PDF-filen. Detta låter dig justera utseendet och layouten för bilder i dina PDF-filer.

#### F: Hur fungerar processen att ställa in storleken på en bild i ett PDF-dokument?

 S: Processen innebär att skapa en`Aspose.Pdf.Image` ange dess bredd och höjd med hjälp av`FixWidth` och`FixHeight` egenskaper och sedan lägga till bilden i PDF-dokumentet. Dessutom kan du ställa in måtten på själva sidan för att passa bilden.

#### F: Kan jag ställa in storleken på en bild till en viss procentandel av sidmåtten?

S: Den medföljande koden anger bildens absoluta bredd och höjd i punkter. Om du vill ställa in storleken på en bild baserat på en procentandel av sidmåtten, måste du beräkna måtten därefter och justera koden därefter.

####  F: Vad är betydelsen av`FileType` property when adding an image to the PDF document?

 A: Den`FileType`egenskapen anger typen av bilden som läggs till i PDF-dokumentet. I den angivna koden, värdet`Unknown` indikerar att typen av bild är okänd, och Aspose.PDF kommer att försöka fastställa bildtypen baserat på filtillägget.

#### F: Kan jag lägga till flera bilder på en enda sida med den här metoden?

 S: Ja, du kan lägga till flera bilder på en enda sida genom att skapa flera`Aspose.Pdf.Image` instanser och lägga till dem i sidans styckesamling. Se till att justera bildernas placering och layout efter behov.

#### F: Hur kan jag kontrollera placeringen och justeringen av den tillagda bilden på sidan?

 S: Placeringen och justeringen av den tillagda bilden kan styras genom att justera bildens koordinater och layout med hjälp av egenskaper som t.ex.`img.Left`, `img.Top`, och egenskaper för styckeformatering.

####  F: Vad är syftet med att ställa in sidegenskaperna med`page.PageInfo.Width` and `page.PageInfo.Height`?

S: Genom att ställa in sidegenskaperna kan du definiera dimensionerna för själva sidan. Detta säkerställer att sidmåtten passar den tillagda bilden och allt annat innehåll du kan ha på sidan.

#### F: Kan jag ställa in olika storlekar för olika bilder i samma PDF-dokument?

 S: Ja, du kan ställa in olika storlekar för olika bilder genom att skapa separata`Aspose.Pdf.Image` instanser och justera`FixWidth`, `FixHeight`, och placeringsegenskaper för varje bild.

#### F: Hur kan jag integrera den här metoden i mina egna projekt för att ställa in bildstorlekar i PDF-filer?

S: För att integrera den här metoden i dina projekt, följ de beskrivna stegen och modifiera koden efter behov. Du kan använda den här metoden för att lägga till bilder av specifika storlekar till dina PDF-dokument baserat på din applikations krav.