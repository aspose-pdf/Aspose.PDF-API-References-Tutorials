---
title: PDF-operatörer
linktitle: PDF-operatörer
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att använda PDF-operatörer med Aspose.PDF för .NET. Lägg till en bild på en PDF-sida och ange dess position.
type: docs
weight: 20
url: /sv/net/programming-with-operators/pdf-operators/
---
I den här handledningen kommer vi att ge dig en steg-för-steg-guide om hur du använder PDF-operatörer med Aspose.PDF för .NET. PDF-operatorer låter dig manipulera och lägga till innehåll i PDF-dokument på ett exakt och kontrollerat sätt. Med hjälp av operatorerna som tillhandahålls av Aspose.PDF kan du lägga till en bild på en PDF-sida och ange dess position exakt.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Visual Studio installerat med .NET framework.
2. Aspose.PDF-biblioteket för .NET.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt projekt i Visual Studio och lägg till en referens till Aspose.PDF för .NET-biblioteket. Du kan ladda ner biblioteket från Asposes officiella webbplats och installera det på din maskin.

## Steg 2: Importera de nödvändiga namnrymden

I din C#-kodfil, importera de namnutrymmen som krävs för att komma åt klasserna och metoderna som tillhandahålls av Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Steg 3: Laddar PDF-dokumentet

Använd följande kod för att ladda PDF-dokumentet:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document pdfDocument = new Document(dataDir + "PDFOperators.pdf");
```

Var noga med att ange den faktiska sökvägen till PDF-filen på din maskin.

## Steg 4: Laddar bilden och lägger till den på sidan

Använd följande kod för att ladda en bild från en fil och lägga till den på PDF-sidan:

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;

Page page = pdfDocument.Pages[1];

FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream);

page. Contents. Add(new GSave());

Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });

page.Contents.Add(new ConcatenateMatrix(matrix));

XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Do(ximage.Name));

page. Contents. Add(new GRestore());
```

 Var noga med att ange de faktiska sökvägarna för PDF- och bildfiler på din maskin. Du kan också justera`lowerLeftX`, `lowerLeftY`, `upperRightX` och`upperRightY` koordinater för att placera bilden efter behov.

### Exempel på källkod för PDF-operatörer som använder Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "PDFOperators.pdf");
// Ställ in koordinater
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Skaffa sidan där bilden behöver läggas till
Page page = pdfDocument.Pages[1];
// Ladda bilden i stream
FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
// Lägg till bild i bildsamlingen av sidresurser
page.Resources.Images.Add(imageStream);
// Använda GSave-operatorn: denna operatör sparar aktuell grafikstatus
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Skapa rektangel- och matrisobjekt
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//Använda operatorn ConcatenateMatrix (sammanfoga matris): definierar hur bilden ska placeras
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Använda Gör-operatorn: denna operator ritar en bild
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Använda GRestore-operatorn: denna operator återställer grafiktillstånd
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "PDFOperators_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
```

## Slutsats

I den här handledningen lärde du dig hur du använder PDF-operatorer med Aspose.PDF för .NET. Genom att följa stegen som beskrivs kommer du att kunna lägga till en bild på en PDF-sida och ange dess position exakt. PDF-operatörer ger detaljerad kontroll över manipuleringen av PDF-dokument, vilket gör att du kan anpassa ditt innehåll.
