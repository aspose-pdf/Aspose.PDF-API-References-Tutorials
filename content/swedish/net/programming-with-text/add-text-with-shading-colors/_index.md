---
title: Lägg till text med skuggande färger i PDF-fil
linktitle: Lägg till text med skuggande färger i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du lägger till text med skuggfärger i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-text/add-text-with-shading-colors/
---
Denna handledning guidar dig genom processen att lägga till text med skuggfärger i PDF-filen med Aspose.PDF för .NET. Den medföljande C#-källkoden visar de nödvändiga stegen.

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
 Skapa en ny`Color` objekt med en mönsterfärgrymd och ange toningsskuggningsfärgerna. Tilldela denna färg till`ForegroundColor` egendom av`TextState` av`TextFragment` objekt.

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

### FAQ's

#### F: Vad är huvudfokus för denna handledning?

S: Denna handledning guidar dig genom processen att lägga till text med skuggfärger till en PDF-fil med Aspose.PDF för .NET-biblioteket. Den medföljande C#-källkoden visar de nödvändiga stegen för att uppnå detta.

#### F: Vilka namnutrymmen behöver jag importera för den här handledningen?

S: I kodfilen där du vill lägga till text med skuggfärger, importera följande namnområden i början av filen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.Drawing;
```

#### F: Hur anger jag dokumentkatalogen?

 S: Lokalisera raden i koden`string dataDir = "YOUR DOCUMENT DIRECTORY";` och byt ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

#### F: Hur laddar jag ett befintligt PDF-dokument?

 S: I steg 4 laddar du ett befintligt PDF-dokument med hjälp av`Document` konstruktor och tillhandahåller sökvägen till dokumentfilen:

```csharp
using(Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
     // Koden kommer här...
}
```

#### F: Hur hittar och ändrar jag specifik text i PDF-dokumentet?

 S: I steg 5 kommer du att använda`TextFragmentAbsorber`för att hitta önskad text i dokumentet. Sedan kan du ändra dess egenskaper:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
TextFragment textFragment = absorber.TextFragments[1];
```

#### F: Hur kan jag ställa in skuggfärger för texten?

 S: I steg 6 skapar du en ny`Color` objekt med en mönsterfärgrymd och ange toningsskuggningsfärgerna. Tilldela denna färg till`ForegroundColor` egendom av`TextState` av`TextFragment` objekt:

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
     PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

#### F: Kan jag använda ytterligare textformatering på den ändrade texten?

 S: Ja, i steg 7 kan du använda ytterligare textformatering som understrykning genom att ändra egenskaperna för`TextState` objekt:

```csharp
textFragment.TextState.Underline = true;
```

#### F: Hur sparar jag det ändrade PDF-dokumentet?

 S: I steg 8 sparar du det ändrade PDF-dokumentet med hjälp av`Save` metod för`Document` objekt:

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

#### F: Vad är det viktigaste med den här handledningen?

S: Genom att följa den här handledningen har du framgångsrikt lärt dig hur du förbättrar ditt PDF-dokument genom att lägga till text med skuggfärger med Aspose.PDF för .NET. Detta kan vara särskilt användbart för att markera och framhäva specifikt textinnehåll i dina PDF-filer.