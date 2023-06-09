---
title: Lägg till bildstämpel
linktitle: Lägg till bildstämpel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt lägger till en bildstämpel i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 20
url: /sv/net/programming-with-stamps-and-watermarks/add-image-stamp/
---
den här handledningen tar vi dig steg för steg om hur du lägger till en bildbuffert till ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att lägga till en anpassad bildbuffert på en specifik sida i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddImageStamp.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skapa rambufferten

Nu när du har laddat upp PDF-dokumentet kan du skapa bildstämpeln att lägga till. Så här gör du:

```csharp
// Skapa rambufferten
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
```

Koden ovan skapar en ny bildbuffert med hjälp av filen "aspose-logo.jpg". Se till att sökvägen till bildfilen är korrekt.

## Steg 4: Konfigurera bildbuffertegenskaper

Innan du lägger till bildstämpeln i PDF-dokumentet kan du konfigurera olika egenskaper för stämpeln, såsom opacitet, storlek, position, etc. Så här gör du:

```csharp
// Konfigurera bildbuffertegenskaper
imageStamp. Background = true;
imageStamp. XIndent = 100;
imageStamp. YIndent = 100;
imageStamp. Height = 300;
imageStamp. Width = 300;
imageStamp.Rotate = Rotate.on270;
imageStamp. Opacity = 0.5;
```

Du kan anpassa dessa egenskaper efter dina behov.

## Steg 5: Lägga till bildstämpeln till PDF:en

Nu när bildstämpeln är klar kan du lägga till den på en specifik sida i PDF-dokumentet. Här är hur:

```csharp
// Lägg till rambufferten på den specifika sidan
pdfDocument.Pages[1].AddStamp(imageStamp);
```

Koden ovan lägger till bildbufferten på första sidan i PDF-dokumentet. Du kan ange en annan sida om det behövs.

## Steg 6: Spara utdatadokumentet

När du har lagt till bildbufferten kan du spara det ändrade PDF-dokumentet. Här är hur:

```csharp
// Spara utdatadokumentet
pdfDocument.Save(dataDir);
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för Lägg till bildstämpel med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "AddImageStamp.pdf");

// Skapa bildstämpel
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");
imageStamp.Background = true;
imageStamp.XIndent = 100;
imageStamp.YIndent = 100;
imageStamp.Height = 300;
imageStamp.Width = 300;
imageStamp.Rotate = Rotation.on270;
imageStamp.Opacity = 0.5;

// Lägg till stämpel på en viss sida
pdfDocument.Pages[1].AddStamp(imageStamp);
dataDir = dataDir + "AddImageStamp_out.pdf";

// Spara utdatadokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage stamp added successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Du har lärt dig hur du lägger till en bildbuffert med Aspose.PDF för .NET. Nu kan du tillämpa denna kunskap på dina egna projekt för att lägga till anpassade bildstämplar till PDF-dokument.
