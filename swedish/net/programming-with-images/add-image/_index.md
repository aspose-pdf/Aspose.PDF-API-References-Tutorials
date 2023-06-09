---
title: Lägg till bild
linktitle: Lägg till bild
second_title: Aspose.PDF för .NET API Referens
description: Lägg enkelt till en bild i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-images/add-image/
---

Den här guiden tar dig steg för steg hur du lägger till en bild i ett PDF-dokument med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Steg 3: Ställ in bildkoordinater

 Ställ in koordinaterna för bilden du vill lägga till. Variablerna`lowerLeftX`, `lowerLeftY`, `upperRightX` och`upperRightY` representerar koordinaterna för det nedre vänstra hörnet respektive det övre högra hörnet av bilden.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Steg 4: Skaffa sidan där bilden ska läggas till

För att lägga till bilden på en specifik sida i PDF-dokumentet måste vi först hämta den sidan. I det här exemplet lägger vi till bilden på den andra sidan (index 1) i dokumentet.

```csharp
Page page = pdfDocument.Pages[1];
```

## Steg 5: Ladda bilden från en ström

Vi kommer nu att ladda bilden vi vill lägga till i PDF-dokumentet. Det här exemplet förutsätter att du har en bildfil som heter`aspose-logo.jpg` i samma katalog som ditt dokument. Byt ut filnamnet om det behövs.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Steg 6: Lägg till bilden på sidtillgångar

För att använda bilden i PDF-dokumentet måste vi lägga till den i sidans resursbildsamling.

```csharp
page.Resources.Images.Add(imageStream);
```

## Steg 7: Spara aktuell grafikstatus

 Innan vi ritar bilden måste vi spara det aktuella grafikläget med hjälp av`GSave` operatör. Detta säkerställer att ändringar i grafiktillståndet kan återställas senare.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Steg 8: Skapa rektangel- och matrisobjekt

 Vi kommer nu att skapa en`Rectangle` föremål och ett`Matrix` objekt. Rektangeln representerar bildens position och storlek, medan matrisen definierar hur bilden ska placeras.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Steg 9: Sammanfoga matris för bildplacering

 För att specificera hur bilden ska placeras i rektangeln använder vi`ConcatenateMatrix`operatör. Denna operator definierar transformationsmatrisen som mappar bildens koordinatutrymme till sidans koordinatutrymme.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Steg 10: Rita bilden

 I det här steget kommer vi att rita bilden på sidan med hjälp av`Do` operatör. De`Do` operatorn tar bildnamnet från resurserna och ritar det till sidan.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Steg 11: Återställ grafikstatus

 Efter att ha ritat bilden måste vi återställa det tidigare grafiktillståndet med hjälp av`GRestore` operatör.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Steg 12: Spara det uppdaterade dokumentet

 Slutligen sparar vi det uppdaterade dokumentet i en ny fil. Uppdatera`dataDir` variabel med önskad utdatakatalog och filnamn.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Lägg till bild med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Ställ in koordinater
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Skaffa sidan där bilden behöver läggas till
Page page = pdfDocument.Pages[1];
// Ladda bilden i stream
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
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
dataDir = dataDir + "AddImage_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Slutsats

I den här handledningen lärde vi oss hur man lägger till en bild i ett PDF-dokument med Aspose.PDF för .NET. Vi har täckt varje steg i detalj, från att öppna dokumentet till att spara den uppdaterade versionen. Genom att följa den här guiden bör du nu kunna bädda in bilder i dina PDF-filer programmatiskt med C# och Aspose.PDF.