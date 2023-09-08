---
title: Göm sidnummer i innehållsförteckningen
linktitle: Göm sidnummer i innehållsförteckningen
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du döljer sidnummer i en innehållsförteckning med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 220
url: /sv/net/programming-with-document/hidepagenumbersintoc/
---
I den här artikeln kommer vi att diskutera implementeringen av funktionen Hide Page Numbers In TOC i Aspose.PDF för .NET med C#. Vi kommer att börja med en kort introduktion till Aspose.PDF för .NET och sedan dyka in i steg-för-steg-guiden för att implementera denna funktion. 

## Introduktion till Aspose.PDF för .NET

Aspose.PDF för .NET är en kraftfull PDF-manipuleringskomponent som låter utvecklare skapa, redigera och manipulera PDF-filer programmatiskt. Den tillhandahåller ett brett utbud av funktioner och funktioner som gör det enkelt att arbeta med PDF-dokument. Aspose.PDF för .NET stöder både 32-bitars och 64-bitars operativsystem och kan användas med .NET Framework, .NET Core och Xamarin-plattformar. 

## Vad är funktionen Hide Page Numbers in TOC?

Innehållsförteckning (TOC) är en viktig del av ett PDF-dokument som ger användarna en snabb överblick över innehållet. Ibland kanske användare vill dölja sidnummer i innehållsförteckningen för att göra den mer användarvänlig. Aspose.PDF för .NET har en inbyggd funktion för att dölja sidnummer i innehållsförteckningen. Den här funktionen kan användas för att skapa mer användarvänliga PDF-dokument. 

## Förutsättningar

För att följa denna handledning behöver du följande:

- Visual Studio 2010 eller senare
- Aspose.PDF för .NET installerat på ditt system
- Grundläggande kunskaper i programmeringsspråket C#

## Steg-för-steg-guide för att implementera Hide Page Numbers in TOC-funktionen

Följ stegen nedan för att implementera funktionen Dölj sidnummer i innehållsförteckning med Aspose.PDF för .NET:

## Steg 1: Skapa en ny C#-konsolapplikation i Visual Studio

Öppna Visual Studio och skapa en ny C#-konsolapplikation.

## Steg 2: Lägg till referens till Aspose.PDF för .NET

Högerklicka på mappen Referenser i ditt projekt och välj Lägg till referens. Bläddra till platsen där Aspose.PDF för .NET är installerat på ditt system och lägg till en referens till den.

## Steg 1: Skapa ett nytt PDF-dokument

Skapa ett nytt PDF-dokument med följande kod:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Steg 2: Skapa en innehållsförteckningssida

Skapa en ny sida för innehållsförteckningen och lägg till den i PDF-dokumentet med följande kod:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Steg 3: Lägg till listsektion till sektionssamlingen av PDF-dokument

Lägg till listsektionen till sektionssamlingen i PDF-dokumentet med följande kod:

```csharp
tocPage.TocInfo = tocInfo;
```

## Steg 4: Definiera formatet för listan med fyra nivåer

Definiera formatet för listan med fyra nivåer genom att ställa in vänstermarginalerna och textformatinställningarna för varje nivå med följande kod:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Steg 5: Lägg till fyra rubriker i avsnittet

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Exempel på källkod för Hide Page Numbers i TOC med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Lägg till listsektionen till sektionssamlingen i PDF-dokumentet
tocPage.TocInfo = tocInfo;
//Definiera formatet för listan med fyra nivåer genom att ställa in vänstermarginalerna och
//textformatinställningar för varje nivå

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Lägg till fyra rubriker i avsnittet
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Slutsats

I den här handledningen undersökte vi hur man arbetar med XMP-metadata i ett PDF-dokument med Aspose.PDF för .NET. XMP-metadata ger värdefull information om PDF-dokumentet, inklusive dess titel, författare, skapandedatum och mer. Aspose.PDF för .NET tillåter utvecklare att komma åt och manipulera denna metadata, vilket ger ett flexibelt och kraftfullt API för att arbeta med PDF-dokument.

### FAQ's

#### F: Vad är XMP-metadata i ett PDF-dokument?

S: XMP-metadata (Extensible Metadata Platform) i ett PDF-dokument är ett standardformat för att lagra metadatainformation om dokumentet. Den innehåller detaljer som dokumenttitel, författare, skapelsedatum, nyckelord och mer. XMP-metadata tillhandahåller ett strukturerat och standardiserat sätt att lagra och dela information om PDF-dokumentet.

#### F: Kan jag ändra XMP-metadata för ett PDF-dokument med Aspose.PDF för .NET?

 S: Ja, du kan modifiera XMP-metadata för ett PDF-dokument programmatiskt med Aspose.PDF för .NET. Du kan komma åt`Info` egendom av`Document` objekt, som ger dig tillgång till egenskaperna för XMP-metadata. Du kan sedan uppdatera värdena för dessa egenskaper för att ändra XMP-metadata för PDF-dokumentet.

#### F: Kan jag extrahera anpassade XMP-metadataegenskaper från ett PDF-dokument med Aspose.PDF för .NET?

 S: Ja, du kan extrahera anpassade XMP-metadataegenskaper från ett PDF-dokument med Aspose.PDF för .NET. Du kan använda`Metadata` egendom av`Document`objekt, som ger tillgång till alla XMP-metadataegenskaper i PDF-dokumentet. Du kan sedan extrahera anpassade egenskaper och använda deras värden efter behov.