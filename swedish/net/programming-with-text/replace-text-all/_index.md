---
title: Ersätt text alla
linktitle: Ersätt text alla
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du ersätter all text i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 350
url: /sv/net/programming-with-text/replace-text-all/
---

I den här handledningen kommer vi att förklara hur man ersätter all text i ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Vi kommer att tillhandahålla en steg-för-steg-guide tillsammans med den nödvändiga C#-källkoden.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- Grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Ställ in sökvägen till katalogen där du har den inmatade PDF-filen. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till din PDF-fil.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Steg 3: Sök och ersätt text

 Skapa en`TextFragmentAbsorber`objekt för att hitta alla instanser av den inmatade sökfrasen. Acceptera absorbenten för alla sidor i PDF-dokumentet för att extrahera textfragmenten.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Steg 4: Ersätt text

Gå igenom de extraherade textfragmenten och ersätt texten efter behov. Uppdatera texten och andra egenskaper som typsnitt, teckenstorlek, förgrundsfärg och bakgrundsfärg.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Steg 5: Spara den modifierade PDF-filen

Spara det ändrade PDF-dokumentet till den angivna utdatafilen.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Exempel på källkod för Ersätt text Alla med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
// Skapa TextAbsorber-objekt för att hitta alla instanser av den inmatade sökfrasen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Acceptera absorbenten för alla sidor
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Uppdatera text och andra egenskaper
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Spara det resulterande PDF-dokumentet.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Slutsats

I den här handledningen har du lärt dig hur du ersätter all text i ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Genom att följa steg-för-steg-guiden och köra den medföljande C#-koden kan du ladda ett PDF-dokument, söka efter önskad text, ersätta den och spara den modifierade PDF-filen.