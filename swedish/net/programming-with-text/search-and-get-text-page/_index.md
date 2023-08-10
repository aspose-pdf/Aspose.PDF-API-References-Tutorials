---
title: Sök och hämta textsida
linktitle: Sök och hämta textsida
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker och hämtar text från en specifik sida i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 430
url: /sv/net/programming-with-text/search-and-get-text-page/
---

Denna handledning förklarar hur du använder Aspose.PDF för .NET för att söka och hämta text från en specifik sida i ett PDF-dokument. Den medföljande C#-källkoden demonstrerar processen steg för steg.

## Förutsättningar

Innan du fortsätter med handledningen, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller använda NuGet för att installera det i ditt projekt.

## Steg 1: Konfigurera projektet

Börja med att skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera nödvändiga namnutrymmen

Lägg till följande med hjälp av direktiv i början av din C#-fil för att importera de nödvändiga namnrymden:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Steg 3: Ladda PDF-dokumentet

 Ställ in sökvägen till din PDF-dokumentkatalog och ladda dokumentet med hjälp av`Document` klass:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Sök och extrahera text från en sida

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av den inmatade sökfrasen på en specifik sida:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Byta ut`"Figure"` med den faktiska texten du vill söka efter.

## Steg 5: Sök på en specifik sida

Acceptera absorbenten för en specifik sida i dokumentet:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Steg 6: hämta extraherade textfragment

Hämta de extraherade textfragmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Steg 7: Gå igenom textfragmenten och segmenten

Gå igenom getd-textfragmenten och deras segment och få tillgång till deras egenskaper:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Du kan ändra koden i slingan för att utföra ytterligare åtgärder på varje textsegment.

### Exempel på källkod för Sök och hämta textsida med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//Skapa TextAbsorber-objekt för att hitta alla instanser av den inmatade sökfrasen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Acceptera absorbenten för alla sidor
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker och hämtar text från en specifik sida i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ladda dokumentet till att komma åt de extraherade textsegmenten. Du kan nu införliva