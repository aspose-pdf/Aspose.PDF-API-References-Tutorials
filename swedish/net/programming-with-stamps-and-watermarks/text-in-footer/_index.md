---
title: Text i sidfot
linktitle: Text i sidfot
second_title: Aspose.PDF för .NET API Referens
description: Lär dig att lägga till text i sidfoten i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/programming-with-stamps-and-watermarks/text-in-footer/
---
den här handledningen ska vi lära oss hur du lägger till text i sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Följ stegen nedan:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Skapa sidfotstext

Skapa en ny textstämpel med texten du vill lägga till i sidfoten:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Du kan anpassa texten genom att ändra dess egenskaper som bottenmarginal, horisontell justering och vertikal justering.

## Steg 5: Lägg till sidfotstext på alla sidor

Gå igenom alla sidor i PDF-dokumentet och lägg till textstämpeln i sidfoten:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Steg 6: Spara PDF-dokumentet

När sidfoten har lagts till på alla sidor, spara det uppdaterade PDF-dokumentet:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där du vill spara PDF-dokumentet.

### Exempel på källkod för Textin Footer med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Skapa sidfot
TextStamp textStamp = new TextStamp("Footer Text");

// Ställ in egenskaper för stämpeln
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Lägg till sidfot på alla sidor
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Spara uppdaterad PDF-fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Slutsats

Grattis! Du har lärt dig hur du lägger till text i sidfoten i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu anpassa dina sidfötter genom att lägga till ytterligare text i dina PDF-dokument.
