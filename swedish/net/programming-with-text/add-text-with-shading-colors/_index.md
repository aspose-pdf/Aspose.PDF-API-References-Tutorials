---
title: Lägg till text med skuggfärger
linktitle: Lägg till text med skuggfärger
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till text med skuggfärger i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-text/add-text-with-shading-colors/
---

Denna handledning guidar dig genom processen att lägga till text med skuggfärger med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

## Krav
Innan du börjar, se till att du har följande:

- Visual Studio eller någon annan C#-kompilator installerad på din maskin.
- Aspose.PDF för .NET-bibliotek. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda en pakethanterare som NuGet för att installera den.

## Steg 1: Konfigurera projektet
1. Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnrymder
I kodfilen där du vill lägga till text med skuggfärger, lägg till följande med hjälp av direktivet överst i filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

## Steg 3: Ställ in dokumentkatalogen
 I koden, lokalisera raden som säger`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med sökvägen till katalogen där dina dokument är lagrade.

## Steg 4: Ladda PDF-dokumentet
 Ladda det befintliga PDF-dokumentet med hjälp av`Document` konstruktor och ange sökvägen till dokumentfilen.

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Koden kommer här...
}
```

## Steg 5: Hitta texten som ska ändras
 Använda sig av`TextFragmentAbsorber` för att hitta önskad text i dokumentet. I den medföljande koden letar den efter texten "Lorem ipsum".

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorb);
TextFragment textFragment = absorb.TextFragments[1];
```

## Steg 6: Ställ in skuggfärg för texten
 Skapa en ny`Color`objekt med en mönsterfärgrymd och ange toningsskuggningsfärgerna. Tilldela denna färg till`ForegroundColor` egendom av`TextState` av`TextFragment` objekt.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

## Steg 7: Använd ytterligare textformatering (valfritt)
 Du kan använda ytterligare formatering på textfragmentet, till exempel understrykning, genom att ändra egenskaperna för`TextState` objekt.

```csharp
textFragment.TextState.Underline = true;
```

## Steg 8: Spara det ändrade PDF-dokumentet
 Spara det ändrade PDF-dokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

### Exempel på källkod för Lägg till text med skuggande färger med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
	TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
	pdfDocument.Pages.Accept(absorber);
	TextFragment textFragment = absorber.TextFragments[1];
	// Skapa ny färg med mönsterfärgrymd
	textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
	{
		PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
	};
	textFragment.TextState.Underline = true;
	pdfDocument.Save(dataDir + "text_out.pdf");
}
```

## Slutsats
Du har framgångsrikt lagt till text med skuggfärger till ditt PDF-dokument med Aspose.PDF för .NET. Den resulterande PDF-filen kan nu hittas på den angivna sökvägen för utdatafilen.