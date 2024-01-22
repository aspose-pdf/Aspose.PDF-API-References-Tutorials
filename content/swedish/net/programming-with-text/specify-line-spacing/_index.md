---
title: Ange radavstånd i PDF-fil
linktitle: Ange radavstånd i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du anger radavstånd i PDF-filen med Aspose.PDF för .NET.
type: docs
weight: 510
url: /sv/net/programming-with-text/specify-line-spacing/
---
Denna handledning förklarar hur man anger radavstånd i PDF-fil med Aspose.PDF för .NET. Den medföljande C#-källkoden demonstrerar processen steg för steg.

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
using System.IO;
```

## Steg 3: Ställ in sökvägen till dokumentkatalogen

 Ställ in sökvägen till din dokumentkatalog med hjälp av`dataDir` variabel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 4: Ladda in PDF-filen

 Ladda in PDF-filen med hjälp av`Document` klass:

```csharp
Document doc = new Document();
```

## Steg 5: Skapa TextFormattingOptions

 Skapa en`TextFormattingOptions` objekt och ställ in radavståndsläget till`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Steg 6: Skapa ett TextFragment

 Skapa en`TextFragment` objekt och ange textinnehållet:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Steg 7: Ladda teckensnittsfilen (valfritt)

 Om du vill använda ett specifikt teckensnitt för texten, ladda TrueType-teckensnittsfilen i en`FileStream` objekt:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Byta ut`"HPSimplified.TTF"` med det faktiska teckensnittsfilnamnet.

## Steg 8: Ange textposition och radavstånd

 Ställ in positionen för textfragmentet och tilldela`TextFormattingOptions` till`TextState.FormattingOptions` fast egendom:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Steg 9: Lägg till texten i dokumentet

 Lägg till textfragmentet i dokumentet, antingen genom att lägga till det i en`TextBuilder` eller direkt till en sida`Paragraphs` samling:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Steg 10: Spara det resulterande PDF-dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Se till att byta ut`"SpecifyLineSpacing_out.pdf"` med önskat utdatafilnamn.

### Exempel på källkod för Specificera radavstånd med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Ladda inmatad PDF-fil
Document doc = new Document();
//Skapa TextFormattingOptions med LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Skapa textbyggarobjekt för första sidan i dokumentet
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Skapa textfragment med exempelsträng
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Ladda TrueType-teckensnittet i strömobjektet
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Ställ in teckensnittsnamnet för textsträngen
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Ange positionen för textfragment
		textFragment.Position = new Position(100, 600);
		//Ställ in TextFormattingOptions för aktuellt fragment till fördefinierat (vilket pekar på LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Lägg till texten i TextBuilder så att den kan placeras över PDF-filen
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Spara det resulterande PDF-dokumentet
	doc.Save(dataDir);
}
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du anger radavstånd i ett PDF-dokument med Aspose.PDF för .NET. Denna handledning gav en steg-för-steg-guide, från att ställa in projektet till att spara det ändrade dokumentet. Du kan nu infoga den här koden i dina egna C#-projekt för att anpassa radavståndet för text i PDF-filer.

### FAQ's

#### F: Vad är syftet med handledningen "Ange radavstånd i PDF-fil"?

S: Handledningen "Ange radavstånd i PDF-fil" syftar till att vägleda användare om hur man använder Aspose.PDF-biblioteket för .NET för att anpassa radavståndet för text i ett PDF-dokument. Handledningen innehåller steg-för-steg-instruktioner och C#-kodexempel för att demonstrera processen.

#### F: Hur hjälper den här handledningen att ange radavstånd i ett PDF-dokument?

S: Denna handledning hjälper användare att förstå hur man använder funktionerna i Aspose.PDF för .NET för att ange radavstånd för text i ett PDF-dokument. Genom att följa de medföljande stegen och kodexemplen kan användare justera radavståndet enligt deras preferenser.

#### F: Vilka förutsättningar krävs för att följa denna handledning?

S: Innan du startar handledningen bör du ha en grundläggande förståelse för programmeringsspråket C#. Dessutom måste du ha Aspose.PDF för .NET-biblioteket installerat. Du kan hämta det från Asposes webbplats eller installera det i ditt projekt med NuGet.

#### F: Hur ställer jag in mitt projekt för att följa denna handledning?

S: För att komma igång, skapa ett nytt C#-projekt i din föredragna integrerade utvecklingsmiljö (IDE) och lägg till en referens till Aspose.PDF för .NET-biblioteket. Detta gör att du kan utnyttja bibliotekets funktioner för att arbeta med PDF-dokument och anpassa radavstånd.

#### F: Kan jag använda den här handledningen för att ange radavstånd för alla typer av text?

S: Ja, den här handledningen ger instruktioner om hur man anger radavstånd för textinnehåll i ett PDF-dokument med Aspose.PDF för .NET. Du kan använda de medföljande kodexemplen för att justera textens radavstånd efter dina behov.

#### F: Hur anger jag radavståndsläget i handledningen?

 S: Handledningen visar hur man skapar en`TextFormattingOptions` objekt och ställ in dess`LineSpacing` egendom till`TextFormattingOptions.LineSpacingMode.FullSize`. Detta läge anger fullständigt radavstånd för textinnehållet.

#### F: Hur kan jag ladda ett specifikt teckensnitt för texten?

 S: Om du vill använda ett specifikt teckensnitt för textinnehållet, ger handledningen vägledning om hur du laddar en TrueType-teckensnittsfil i en`FileStream` objekt och ställ in det som teckensnitt för`TextFragment`. Detta gör att du kan anpassa textens teckensnitt tillsammans med dess radavstånd.

#### F: Hur anpassar jag positionen för texten i PDF-dokumentet?

 S: För att anpassa textens position, skapa en`TextFragment` objekt och ställ in dess`Position`egenskapen till de önskade koordinaterna (X och Y). Detta låter dig styra var texten placeras i PDF-dokumentet.

#### F: Kan jag tillämpa dessa radavståndsändringar på befintliga PDF-dokument?

 S: Ja, du kan ändra radavstånd för text i befintliga PDF-dokument. Handledningen visar hur man skapar en`TextFragment` med angivet radavstånd och position, och lägg sedan till det på en sidas`Paragraphs` samling.