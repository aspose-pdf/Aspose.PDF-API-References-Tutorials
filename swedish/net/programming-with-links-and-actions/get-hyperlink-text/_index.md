---
title: Hämta hyperlänktext
linktitle: Hämta hyperlänktext
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar hyperlänktext från en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/programming-with-links-and-actions/get-hyperlink-text/
---

Lär dig hur du extraherar text från hyperlänkar i en PDF-fil med Aspose.PDF för .NET med denna steg-för-steg-guide.

## Steg 1: Sätta upp miljön

Se till att du har konfigurerat din utvecklingsmiljö med ett C#-projekt och lämpliga Aspose.PDF-referenser.

## Steg 2: Laddar PDF-filen

Ställ in katalogsökvägen för dina dokument och ladda upp PDF-filen med följande kod:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ladda PDF-filen
Document document = new Document(dataDir + "input.pdf");
```

## Steg 3: Navigera genom dokumentets sidor

 Iterera genom varje sida i dokumentet med hjälp av en`foreach` slinga:

```csharp
foreach(Page page in document.Pages)
{
     // Visa länkkommentarer
     ShowLinkAnnotations(page);
}
```

## Steg 4: Felhantering

Lägg till felhantering för att fånga eventuella undantag och visa motsvarande felmeddelande:

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### Exempel på källkod för Get Hyperlink Text med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda PDF-filen
	Document document = new Document(dataDir + "input.pdf");
	// Iterera genom varje sida i PDF
	foreach (Page page in document.Pages)
	{
		// Visa länkkommentar
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

Grattis! Du vet nu hur man extraherar hyperlänktext från en PDF-fil med Aspose.PDF för .NET. Du kan använda denna kunskap för att hantera hyperlänkar i dina projekt och automatisera uppgifter relaterade till PDF-filer.

Nu när du har slutfört den här guiden kan du tillämpa dessa koncept på dina egna projekt och utforska funktionerna som erbjuds av Aspose.PDF för .NET.