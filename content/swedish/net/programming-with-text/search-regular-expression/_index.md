---
title: Sök efter reguljära uttryck i PDF-fil
linktitle: Sök efter reguljära uttryck i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du söker och hämtar text med reguljära uttryck i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 440
url: /sv/net/programming-with-text/search-regular-expression/
---
Denna handledning förklarar hur du använder Aspose.PDF för .NET för att söka och hämta text som matchar ett reguljärt uttryck i PDF-filen. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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

### FAQ's

#### F: Vad är syftet med handledningen "Sök regelbundet uttryck i PDF-fil"?

S: Handledningen "Sök regelbundet uttryck i PDF-fil" syftar till att visa hur man använder Aspose.PDF-biblioteket för .NET för att söka efter och extrahera text som matchar ett specificerat reguljärt uttrycksmönster i en PDF-fil. Handledningen ger omfattande vägledning och exempel på C#-kod för att demonstrera processen.

#### F: Hur hjälper den här handledningen vid sökning efter text med reguljära uttryck i ett PDF-dokument?

S: Den här handledningen ger ett steg-för-steg tillvägagångssätt för att använda Aspose.PDF-biblioteket för att utföra textsökningar i ett PDF-dokument baserat på ett reguljärt uttrycksmönster. Den beskriver hur man ställer in projektet, laddar PDF-dokumentet, definierar ett reguljärt uttrycksmönster och hämtar matchande textfragment.

#### F: Vilka är förutsättningarna för att följa denna handledning?

S: Innan du börjar med den här handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan få det från Asposes webbplats eller använda NuGet för att integrera det i ditt projekt.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: Till att börja, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta gör att du kan utnyttja bibliotekets kapacitet i ditt projekt.

#### F: Kan jag använda reguljära uttryck för att söka efter text i ett PDF-dokument?

 S: Ja, den här handledningen visar hur man använder reguljära uttryck för att söka efter och extrahera text från ett PDF-dokument. Det handlar om att använda`TextFragmentAbsorber` klass och ange ett reguljärt uttrycksmönster för att hitta fraser som matchar det angivna mönstret.

#### F: Hur definierar jag det reguljära uttrycksmönstret för textsökning?

 S: För att definiera ett reguljärt uttrycksmönster för textsökning, skapa en`TextFragmentAbsorber` objekt och ställ in dess mönster med hjälp av`Text` parameter. Byt ut standardmönstret`"\\d{4}-\\d{4}"` i handledningens kod med ditt önskade reguljära uttrycksmönster.

#### F: Hur kan jag aktivera användning av reguljära uttryck för textsökning?

 S: Användning av reguljära uttryck aktiveras genom att skapa en`TextSearchOptions` objekt och ställer in dess värde till`true` . Tilldela detta objekt till`TextSearchOptions` egendom av`TextFragmentAbsorber` exempel. Detta säkerställer att det reguljära uttrycksmönstret tillämpas under textsökning.

#### F: Kan jag hämta textfragment som matchar det reguljära uttrycksmönstret?

 A: Absolut. Efter att ha tillämpat sökningen med reguljära uttryck på PDF-dokumentet kan du hämta de extraherade textfragmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt. Dessa textfragment innehåller textsegmenten som matchar det angivna reguljära uttrycksmönstret.

#### F: Vad kan jag komma åt från de hämtade textfragmenten?

S: Från de hämtade textfragmenten kan du komma åt olika egenskaper som matchat textinnehåll, position (X- och Y-koordinater), teckensnittsinformation (namn, storlek, färg) med mera. Exempelkoden i handledningens loop visar hur man kommer åt och visar dessa egenskaper.

#### F: Hur kan jag anpassa åtgärder på de extraherade textfragmenten?

S: När du har de extraherade textfragmenten kan du anpassa koden i slingan för att utföra ytterligare åtgärder på varje textfragment. Detta kan inkludera att spara den extraherade texten, analysera mönster eller implementera formateringsändringar baserat på dina krav.