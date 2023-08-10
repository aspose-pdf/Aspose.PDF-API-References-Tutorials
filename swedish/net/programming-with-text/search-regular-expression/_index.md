---
title: Sök efter reguljära uttryck
linktitle: Sök efter reguljära uttryck
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker och hämtar text med reguljära uttryck i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 440
url: /sv/net/programming-with-text/search-regular-expression/
---

Denna handledning förklarar hur du använder Aspose.PDF för .NET för att söka och hämta text som matchar ett reguljärt uttryck i ett PDF-dokument. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Sök med reguljärt uttryck

 Skapa en`TextFragmentAbsorber` objekt och ställ in det reguljära uttrycksmönstret för att hitta alla fraser som matchar mönstret:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Som 1999-2000
```

 Byta ut`"\\d{4}-\\d{4}"` med ditt önskade reguljära uttrycksmönster.

## Steg 5: Ställ in alternativ för textsökning

 Skapa en`TextSearchOptions` objekt och ställ in det på`TextSearchOptions` egendom av`TextFragmentAbsorber` objekt för att aktivera användning av reguljära uttryck:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Steg 6: Sök på alla sidor

Acceptera absorbenten för alla sidor i dokumentet:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Steg 7: Hämta extraherade textfragment

Hämta de extraherade textfragmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Steg 8: Gå igenom textfragmenten

Gå igenom de hämtade textfragmenten och få tillgång till deras egenskaper:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Du kan ändra koden i slingan för att utföra ytterligare åtgärder på varje textfragment.

### Exempel på källkod för Sök Regular Expression med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Skapa TextAbsorber-objekt för att hitta alla fraser som matchar det reguljära uttrycket
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Som 1999-2000
// Ställ in textsökningsalternativ för att ange användning av reguljära uttryck
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Acceptera absorbenten för alla sidor
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker och hämtar text som matchar ett reguljärt uttryck i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ladda dokumentet till att komma åt de extraherade textfragmenten. Du kan nu infoga den här koden i dina egna C#-projekt för att utföra avancerade textsökningar i PDF-filer.