---
title: Ersätt text på reguljärt uttryck
linktitle: Ersätt Texton Regular Expression
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ersätter text baserat på ett reguljärt uttryck i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 360
url: /sv/net/programming-with-text/replace-text-on-regular-expression/
---

I den här handledningen kommer vi att förklara hur man ersätter text baserat på ett reguljärt uttryck i ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Vi kommer att tillhandahålla en steg-för-steg-guide tillsammans med den nödvändiga C#-källkoden.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- Grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Ställ in sökvägen till katalogen där du har den inmatade PDF-filen. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir`variabel med sökvägen till din PDF-fil.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Steg 3: Sök och ersätt text med hjälp av reguljära uttryck

 Skapa en`TextFragmentAbsorber` objekt och ange det reguljära uttrycksmönstret för att hitta alla fraser som matchar mönstret. Ställ in textsökningsalternativet för att aktivera användning av reguljära uttryck.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Som 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Steg 4: Ersätt text

Gå igenom de extraherade textfragmenten och ersätt texten efter behov. Uppdatera texten och andra egenskaper som typsnitt, teckenstorlek, förgrundsfärg och bakgrundsfärg.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Steg 5: Spara den modifierade PDF-filen

Spara det ändrade PDF-dokumentet till den angivna utdatafilen.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Exempel på källkod för Ersätt Texton Regular Expression med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Skapa TextAbsorber-objekt för att hitta alla fraser som matchar det reguljära uttrycket
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Som 1999-2000
// Ställ in textsökningsalternativ för att ange användning av reguljära uttryck
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Acceptera absorbenten för en enda sida
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Uppdatera text och andra egenskaper
	textFragment.Text = "New Phrase";
	// Ställ in på en instans av ett objekt.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen har du lärt dig hur du ersätter text baserat på ett reguljärt uttryck i ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Genom att följa den steg-för-steg-guide och exekvera den medföljande C#-koden kan du ladda ett PDF-dokument, söka efter text med ett reguljärt uttryck, ersätta det och spara den modifierade PDF-filen.