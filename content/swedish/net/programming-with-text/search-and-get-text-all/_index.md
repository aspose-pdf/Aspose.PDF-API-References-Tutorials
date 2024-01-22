---
title: Sök och hämta text allt
linktitle: Sök och hämta text allt
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du söker och hämtar text från alla sidor i ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 420
url: /sv/net/programming-with-text/search-and-get-text-all/
---
Denna handledning förklarar hur man använder Aspose.PDF för .NET för att söka och hämta text från alla sidor i ett PDF-dokument. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Se till att byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Sök och extrahera text

 Skapa en`TextFragmentAbsorber` objekt för att hitta alla instanser av den inmatade sökfrasen:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Byta ut`"text"` med den faktiska texten du vill söka efter.

## Steg 5: Sök på alla sidor

Acceptera absorbenten för alla sidor i dokumentet:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Steg 6: hämta extraherade textfragment

Hämta de extraherade textfragmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Steg 7: Gå igenom textfragmenten

Gå igenom getd-textfragmenten och få tillgång till deras egenskaper:

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

### Exempel på källkod för Search And Get Text All med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Skapa TextAbsorber-objekt för att hitta alla instanser av den inmatade sökfrasen
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Grattis! Du har framgångsrikt lärt dig hur du söker och hämtar text från alla sidor i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ladda dokumentet till att komma åt de extraherade textfragmenten. Du kan nu infoga den här koden i dina egna C#-projekt för att analysera och bearbeta textinnehåll i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Sök och hämta text allt"?

S: Handledningen "Sök och hämta text allt" visar hur man använder Aspose.PDF-biblioteket för .NET för att söka och extrahera text från alla sidor i ett PDF-dokument. Handledningen innehåller steg-för-steg-instruktioner tillsammans med exempel på C#-kod för att utföra textsökning och hämtning.

#### F: Hur hjälper den här handledningen till att extrahera text från PDF-dokument?

S: Denna handledning guidar dig genom processen att extrahera text från alla sidor i ett PDF-dokument. Den använder Aspose.PDF-biblioteket för att hitta specifika textfraser och hämta tillhörande information, såsom position, teckensnittsegenskaper och färger.

#### F: Vilka är förutsättningarna för att följa denna handledning?

S: Innan du börjar med den här handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan få det från Asposes webbplats eller använda NuGet för att integrera det i ditt projekt.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: För att komma igång, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta ger dig tillgång till bibliotekets funktionalitet i ditt projekt.

#### F: Hur söker jag efter specifik text i ett PDF-dokument?

S: Du kan använda`TextFragmentAbsorber`klass för att hitta instanser av en specifik sökfras i PDF-dokumentet. Genom att skapa en instans av den här klassen och ange måltexten kan du fånga alla förekomster av den texten.

#### F: Kan jag söka efter text på alla sidor i PDF-dokumentet?

 S: Ja, handledningen visar hur man söker efter text på alla sidor i PDF-dokumentet. De`pdfDocument.Pages.Accept(textFragmentAbsorber)` metoden används för att acceptera absorbenten för alla sidor, så att du kan söka efter önskad text på varje sida.

#### F: Hur kommer jag åt de extraherade textfragmenten?

 S: Efter att ha sökt efter texten kan du komma åt de extraherade textfragmenten med hjälp av`TextFragments` egendom av`TextFragmentAbsorber` objekt. Denna fastighet ger tillgång till en samling av`TextFragment` objekt som innehåller den extraherade texten och relaterad information.

#### F: Vilken information kan jag hämta från de extraherade textfragmenten?

S: Du kan hämta olika detaljer från de extraherade textfragmenten, såsom det faktiska textinnehållet, position (X- och Y-koordinater), teckensnittsinformation (namn, storlek, färg, etc.) med mera. Handledningens exempelkod visar hur du kommer åt och skriver ut dessa detaljer.

#### F: Kan jag utföra ytterligare åtgärder på de extraherade textfragmenten?

A: Absolut. När du har de extraherade textfragmenten kan du modifiera koden i slingan för att utföra anpassade åtgärder på varje fragment. Detta kan inkludera att spara den extraherade texten, analysera textmönster eller tillämpa formateringsändringar.