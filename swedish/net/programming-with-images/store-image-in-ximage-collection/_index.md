---
title: Lagra bild i XImage Collection
linktitle: Lagra bild i XImage Collection
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att lagra en bild i XImage-samlingen med Aspose.PDF för .NET.
type: docs
weight: 290
url: /sv/net/programming-with-images/store-image-in-ximage-collection/
---

I den här handledningen går vi igenom hur du lagrar en bild i XImage-samlingen med Aspose.PDF för .NET. Följ dessa steg för att enkelt utföra denna operation.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan utvecklingsmiljö installerad och konfigurerad.
- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat. Du kan ladda ner den från Asposes officiella webbplats.

## Steg 1: Initiering av PDF-dokument

För att komma igång använder du följande kod för att initiera ett nytt PDF-dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Initiera dokumentet
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## Steg 2: Lägga till bilden i XImage-samlingen

Därefter lägger vi till bilden i XImage-samlingen av PDF-dokumentet. Använd följande kod:

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

Se till att ange rätt sökväg till bildkällfilen.

## Steg 3: Placering av bilden på sidan

Låt oss nu placera bilden på sidan i PDF-dokumentet. Använd följande kod:

```csharp
page. Contents. Add(new GSave());

// Ställ in koordinater
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//Använd operatorn ConcatenateMatrix: definiera hur bilden ska placeras
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

Detta kommer att placera bilden vid de angivna koordinaterna på sidan.

## Steg 4: Spara PDF-dokumentet

Slutligen sparar vi det uppdaterade PDF-dokumentet. Använd följande kod:

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

Var noga med att ange önskad sökväg och filnamn för det slutliga PDF-dokumentet.

### Exempel på källkod för Store Image In XImage Collection med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initiera dokument
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// Ställ in koordinater
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//Använda operatorn ConcatenateMatrix (sammanfoga matris): definierar hur bilden ska placeras
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## Slutsats

Grattis! Du har lyckats lagra en bild i XImage-samlingen med Aspose.PDF för .NET. Du kan nu tillämpa den här metoden på dina egna projekt för att manipulera och anpassa bilder i PDF-filer.