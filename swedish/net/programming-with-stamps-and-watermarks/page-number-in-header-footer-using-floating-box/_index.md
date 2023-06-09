---
title: Sidnummer i sidhuvud med flytande låda
linktitle: Sidnummer i sidhuvud med flytande låda
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till sidnumret i sidhuvudet och sidfoten i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 150
url: /sv/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
I den här handledningen guidar vi dig steg för steg om hur du lägger till sidnummer i sidhuvud och sidfot i ett PDF-dokument med FloatingBox med Aspose.PDF för .NET. Vi kommer att använda den medföljande C#-källkoden för att skapa ett PDF-dokument, lägga till en sida, skapa en FloatingBox, ställa in dess position och lägga till sidnumret till den, spara sedan det modifierade PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Skapa PDF-dokumentet och lägga till en sida

Det första steget är att skapa en instans av PDF-dokumentet och lägga till en sida till det. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instantiera PDF-dokumentet
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Lägg till en sida i PDF-dokumentet
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

## Steg 3: Skapa FloatingBox och lägg till sidnumret

Nu när sidan har lagts till i PDF-dokumentet kan vi skapa en FloatingBox, ställa in dess position och lägga till sidnumret till den. Här är hur:

```csharp
// Skapa en FloatingBox med en bredd på 140 och en höjd på 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Ställ in styckets vänstra position
box1. Left = 2;

// Ställ in styckets översta position
box1. Top = 10;

// Lägg till sidnumret i FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Lägg till FloatingBox på sidan
page.Paragraphs.Add(box1);
```

Koden ovan skapar en FloatingBox med en bredd på 140 och en höjd på 80. Därefter ställer vi in dess position genom att ange de vänstra och övre värdena. Slutligen lägger vi till sidnumret i FloatingBox med hjälp av ett TextFragment som innehåller syntaxen "($p/ $P )" som kommer att ersättas med det aktuella sidnumret och det totala antalet sidor.

## Steg 4: Spara det ändrade PDF-dokumentet

När sidnumret har lagts till i sidhuvudet eller sidfoten med FloatingBox kan vi spara det modifierade PDF-dokumentet. Här är hur:

```csharp
// Spara det ändrade PDF-dokumentet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Ovanstående kod sparar det redigerade PDF-dokumentet i den angivna katalogen.

### Exempel på källkod för sidnummer i sidhuvud med sidfot med flytande box med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantiera dokumentinstans
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Lägg till en sida i pdf-dokumentet
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initierar en ny instans av FloatingBox-klassen
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Flytande värde som anger styckets vänstra position
box1.Left = 2;

// Flytande värde som anger styckets topposition
box1.Top = 10;

// Lägg till makron till styckesamlingen i FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Lägg till en floatingBox på sidan
page.Paragraphs.Add(box1);

// Spara dokumentet
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till sidnummer i sidhuvud och sidfot i PDF-dokument med FloatingBox med Aspose.PDF för .NET. Du kan nu anpassa dina sidhuvuden och sidfötter genom att lägga till dynamisk information som sidnummer.
