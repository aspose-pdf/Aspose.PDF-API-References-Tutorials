---
title: Få bokmärkesidnummer i PDF-fil
linktitle: Få bokmärkesidnummer i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Få enkelt bokmärkes sidnummer i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-bookmarks/get-bookmark-page-number/
---
Att hämta sidnummer associerade med bokmärken i PDF-fil kan vara användbart för navigering. Med Aspose.PDF för .NET kan du enkelt få sidnumret för bokmärken genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf.Facades;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill extrahera bokmärkets sidnummer från. Byta ut`"YOUR DOCUMENT DIRECTORY"` följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Skapa bokmärkesredigeraren

 Nu ska vi skapa en`PdfBookmarkEditor` objekt för att manipulera dokumentets bokmärken. Använd följande kod:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Steg 4: Öppna PDF-filen

 I det här steget öppnar vi PDF-filen med hjälp av`BindPdf` metod för bokmärkesredigeraren. Här är motsvarande kod:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Steg 5: Extrahera bokmärken

 Nu kommer vi att extrahera bokmärkena från dokumentet med hjälp av`ExtractBookmarks` metod för bokmärkesredigeraren. Här är motsvarande kod:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Steg 6: Bläddra i bokmärken och få sidnummer

 Slutligen går vi igenom de extraherade bokmärkena och får sidnumren som är associerade med varje bokmärke med hjälp av en`foreach` slinga. Här är motsvarande kod:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Exempel på källkod för Get Bookmark Page Number med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Skapa PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Öppna PDF-fil
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Extrahera bokmärken
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att få bokmärkessidnummer med Aspose.PDF för .NET. Du kan använda den här koden för att hämta navigeringsinformationen som är kopplad till varje bokmärke i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.

### Vanliga frågor för att få bokmärkes sidnummer i PDF-fil

#### F: Vad är bokmärken i en PDF-fil?

S: Bokmärken i en PDF-fil är navigeringshjälpmedel som gör att användare snabbt kan hoppa till specifika avsnitt eller sidor i dokumentet. De förbättrar användarupplevelsen genom att tillhandahålla genvägar till relevant innehåll.

#### F: Varför skulle jag vilja hämta bokmärkessidnummer från en PDF-fil?

S: Att hämta sidnummer för bokmärken hjälper användare att navigera genom ett dokument mer effektivt, vilket ger en tydlig indikation på vart varje bokmärke leder. Detta är särskilt användbart för längre dokument med flera avsnitt.

#### F: Hur importerar jag de nödvändiga biblioteken för mitt C#-projekt?

S: För att importera det nödvändiga biblioteket för ditt C#-projekt, använd följande importdirektiv:

```csharp
using Aspose.Pdf.Facades;
```

Detta direktiv låter dig använda klasserna och metoderna som tillhandahålls av Aspose.PDF för .NET.

#### F: Hur anger jag sökvägen till dokumentmappen?

 S: I den medföljande källkoden, ersätt`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till mappen som innehåller PDF-filen från vilken du vill extrahera sidnummer för bokmärken. Detta säkerställer att koden kan hitta mål-PDF-filen.

#### F: Hur skapar jag en bokmärkesredigerare?

S: För att skapa en bokmärkesredigerare, använd följande kod:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### F: Hur öppnar jag en PDF-fil för bokmärkesmanipulation?

S: För att öppna en PDF-fil för att extrahera bokmärkesinformation, använd följande kod:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Byta ut`"GetBookmarks.pdf"` med det faktiska filnamnet.

#### F: Hur extraherar jag bokmärken från PDF-filen?

 S: För att extrahera bokmärken från PDF-filen, använd`ExtractBookmarks` metod för bokmärkesredigeraren:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### F: Hur hämtar och visar jag sidnummer för bokmärken?

 S: Gå igenom de extraherade bokmärkena med hjälp av en`foreach` loop och få tillgång till`PageNumber` egenskapen för varje bokmärke för att hämta och visa dess tillhörande sidnummer:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### F: Kan jag ändra bokmärkesegenskaper med den här metoden?

 S: Även om den här handledningen fokuserar på att hämta bokmärkes sidnummer, kan du ändra andra bokmärkesegenskaper med samma`Bookmark`objekt och tillhörande egenskaper.

#### F: Hur sparar jag den uppdaterade PDF-filen efter att ha extraherat bokmärkesinformation?

S: Bokmärkesextraktion ändrar inte den ursprungliga PDF-filen. Om du vill spara några ändringar kan du göra det med andra metoder som tillhandahålls av Aspose.PDF för .NET.