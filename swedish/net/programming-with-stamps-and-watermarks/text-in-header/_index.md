---
title: Text i rubriken
linktitle: Text i rubriken
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till text i rubriken i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 190
url: /sv/net/programming-with-stamps-and-watermarks/text-in-header/
---
I den här handledningen ska vi lära oss hur man lägger till text i rubriken på ett PDF-dokument med Aspose.PDF för .NET. Följ stegen nedan:

## Steg 1: Projektförberedelser

Se till att du har installerat Aspose.PDF för .NET och skapat ett C#-projekt.

## Steg 2: Importera namnutrymmen

Lägg till följande namnområden till din C#-källfil:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Öppna dokumentet

Öppna det befintliga PDF-dokumentet med den angivna sökvägen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa rubriktext

Skapa en ny textstämpel med texten du vill lägga till i rubriken:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Du kan anpassa texten genom att ändra dess egenskaper som toppmarginal, horisontell justering och vertikal justering.

## Steg 5: Lägg till rubriktext på alla sidor

Gå igenom alla sidor i PDF-dokumentet och lägg till textstämpeln i rubriken:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Steg 6: Spara PDF-dokumentet

När rubriktexten har lagts till på alla sidor, spara det uppdaterade PDF-dokumentet:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

### Exempel på källkod för Textin Header med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Skapa rubrik
TextStamp textStamp = new TextStamp("Header Text");

// Ställ in egenskaper för stämpeln
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Lägg till rubrik på alla sidor
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Spara uppdaterat dokument
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till text i rubriken på ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa dina rubriker genom att lägga till ytterligare text i dina PDF-dokument.
