---
title: Få bokmärkes sidnummer
linktitle: Få bokmärkes sidnummer
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt bokmärkessidnummer från dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-bookmarks/get-bookmark-page-number/
---

Att hämta sidnummer associerade med bokmärken i ett PDF-dokument kan vara användbart för navigering. Med Aspose.PDF för .NET kan du enkelt få sidnumret för bokmärken genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf.Facades;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill extrahera bokmärkets sidnummer från. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

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