---
title: Hämta alla kommentarer från sidan
linktitle: Hämta alla kommentarer från sidan
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att hämta alla kommentarer från en PDF-sida med denna steg-för-steg-guide.
type: docs
weight: 70
url: /sv/net/annotations/getallannotationsfrompage/
---
Den här artikeln guidar dig genom processen att extrahera alla kommentarer från en PDF-sida med Aspose.PDF för .NET. Aspose.PDF för .NET är ett bibliotek som låter utvecklare skapa, redigera och konvertera PDF-dokument. Med hjälp av denna guide kommer du att kunna få alla kommentarer från en specifik PDF-sida med den medföljande C#-källkoden.

Följ stegen nedan för att få alla kommentarer för en PDF-sida med Aspose.PDF för .NET:

## Steg 1: Sökvägen till dokumentkatalogen

Det första steget för att få alla kommentarer från en PDF-sida med Aspose.PDF för .NET är att ställa in sökvägen till dokumentkatalogen där dina PDF-filer lagras. Du kan göra detta genom att ändra följande kodrad:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Steg 2: Dina PDF-filer lagras

Ersätt "DIN DOKUMENTKATOGRAF" med sökvägen till mappen där dina PDF-filer lagras. Till exempel:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Steg 3: Öppna dokument

Nästa steg är att öppna PDF-dokumentet som innehåller anteckningarna du vill extrahera. Du kan göra detta genom att lägga till följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Denna kodrad initierar en ny instans av klassen Document och laddar PDF-dokumentet "GetAllAnnotationsFromPage.pdf". Ersätt detta filnamn med namnet på din PDF-fil.

## Steg 4: Gå igenom alla kommentarer

När du har öppnat PDF-dokumentet kan du gå igenom alla kommentarer på en specifik sida. För att till exempel gå igenom alla kommentarer på första sidan i PDF-dokumentet, lägg till följande kod:

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Koden går här
}
```

Den här koden går igenom alla anteckningar på första sidan i PDF-dokumentet och tilldelar varje anteckning till variabeln "annotation".

## Steg 5: Hämta anteckningsegenskaper

För att extrahera egenskaperna för varje anteckning kan du lägga till följande kod inuti foreach loop:

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Den här koden skriver titeln, ämnet och innehållet för varje anteckning till konsolen.

### Exempel på källkod för Hämta alla kommentarer från sidan med Aspose.PDF för .NET

Här är den fullständiga källkoden för att få alla kommentarer från en PDF-sida med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Gå igenom alla kommentarer
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Få anteckningsegenskaper
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```
