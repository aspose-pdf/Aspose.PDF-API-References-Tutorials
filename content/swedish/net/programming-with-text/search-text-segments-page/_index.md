---
title: Sök textsegmentsida i PDF-fil
linktitle: Sök textsegmentsida i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du söker efter textsegment på en sida i PDF-fil och hämtar deras egenskaper med Aspose.PDF för .NET.
type: docs
weight: 470
url: /sv/net/programming-with-text/search-text-segments-page/
---
Denna handledning förklarar hur man använder Aspose.PDF för .NET för att söka efter specifika textsegment på en sida med PDF-fil och hämta deras egenskaper. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Ladda PDF-dokumentet

 Ladda PDF-dokumentet med hjälp av`Document` klass:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Byta ut`"SearchTextSegmentsPage.pdf"` med det faktiska namnet på din PDF-fil.

## Steg 5: Skapa en TextFragmentAbsorber

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av den inmatade sökfrasen:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Byta ut`"text"` med önskad sökfras.

## Steg 6: Acceptera absorbenten för en specifik sida

Acceptera absorbenten för önskad sida i dokumentet:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Byta ut`2` med önskat sidnummer (1-baserat index).

## Steg 7: Hämta de extraherade textsegmenten

 Hämta de extraherade textsegmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Steg 8: Gå igenom textsegmenten

Gå igenom de hämtade textsegmenten och få tillgång till deras egenskaper:

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

Ändra koden i slingan för att utföra ytterligare åtgärder på varje textsegment om det behövs.

### Exempel på källkod för söktextsegmentsida med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Skapa TextAbsorber-objekt för att hitta alla instanser av den inmatade sökfrasen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Acceptera absorbenten för alla sidor
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Hämta de extraherade textfragmenten
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Gå igenom fragmenten
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du söker efter specifika textsegment på en sida i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ladda dokumentet till att komma åt de extraherade textsegmenten. Du kan nu infoga den här koden i dina egna C#-projekt för att utföra avancerade textsegmentsökningar i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Sök textsegment i PDF-fil"?

S: Handledningen "Sök textsegment i PDF-fil" ger en omfattande guide om hur du använder Aspose.PDF-biblioteket för .NET för att söka efter specifika textsegment på en viss sida i ett PDF-dokument. Den täcker processen att sätta upp ett projekt, ladda ett PDF-dokument, söka efter textsegment och hämta deras egenskaper med C#-kod.

#### F: Hur hjälper den här handledningen vid sökning efter specifika textsegment i ett PDF-dokument?

S: Den här handledningen visar processen att hitta och extrahera specifika textsegment på en viss sida i ett PDF-dokument. Genom att följa stegen och kodexemplen kan användare effektivt söka efter önskade textsegment och hämta information om deras egenskaper.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du startar handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller installera det i ditt projekt med NuGet.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: För att komma igång, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta gör att du kan använda bibliotekets funktioner för att söka och arbeta med PDF-dokument.

#### F: Kan jag använda den här handledningen för att söka efter specifika textsegment på vilken sida som helst i en PDF?

S: Ja, den här handledningen ger instruktioner om hur du söker efter specifika textsegment på en vald sida i ett PDF-dokument. Den guidar användare om att sätta upp ett projekt, ladda en PDF och använda Aspose.PDF-biblioteket för att hitta och hämta egenskaper för de önskade textsegmenten.

#### F: Hur anger jag texten jag vill söka efter i denna handledning?

 S: För att ange texten du vill söka efter, skapa en`TextFragmentAbsorber` objekt och ställ in dess sökparameter med hjälp av`Text` fast egendom. Ersätt standard`"text"` i handledningens kod med önskad sökfras.

#### F: Hur hämtar jag egenskaperna för de extraherade textsegmenten?

Efter att ha accepterat`TextFragmentAbsorber` för en specifik sida i PDF:en kan du hämta de extraherade textsegmenten med hjälp av`TextFragments` absorbatorobjektets egenskap. Detta ger tillgång till en samling textfragment, som var och en innehåller flera textsegment.

#### F: Kan jag anpassa koden för att utföra ytterligare åtgärder på varje textsegment?

A: Absolut. Handledningens exempelkod ger en loop för att iterera genom de hämtade textsegmenten. Du kan anpassa koden inom denna loop för att utföra ytterligare åtgärder på varje textsegment, baserat på dina projektkrav.

#### F: Hur sparar jag det ändrade PDF-dokumentet efter att ha extraherat textsegment?

S: Denna handledning fokuserar främst på att söka efter textsegment och hämta deras egenskaper. Om du tänker göra ändringar i PDF:en kan du hänvisa till annan Aspose.PDF-dokumentation för att lära dig hur du manipulerar och sparar dokumentet baserat på dina specifika behov.