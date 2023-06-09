---
title: HTML till PDF
linktitle: HTML till PDF
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att konvertera HTML till PDF med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/document-conversion/html-to-pdf/
---

den här handledningen går vi igenom processen att konvertera en HTML-fil till PDF med Aspose.PDF för .NET. HTML (HyperText Markup Language) är ett märkningsspråk som används för att strukturera och presentera webbinnehåll. Genom att följa stegen nedan kommer du att kunna konvertera HTML-filer till PDF-format.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Laddar HTML-filen
I det här steget kommer vi att ladda HTML-filen med Aspose.PDF för .NET. Följ koden nedan:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din HTML-fil finns.

## Steg 2: HTML-laddningsalternativ
Nu när vi har laddat HTML-filen kan vi ange specifika laddningsalternativ. Använd följande kod:

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

Koden ovan säger till Aspose.PDF att använda en anpassad laddningsstrategi för externa resurser, såsom bilder. Du kan anpassa denna policy för att passa dina behov.

## Steg 3: HTML till PDF-konvertering
Efter att ha laddat HTML-filen och angett laddningsalternativen kan vi fortsätta med konverteringen till PDF. Använd följande kod:

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### Exempel på källkod för HTML till PDF med Aspose.PDF för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats
I den här handledningen täckte vi processen steg för steg. steg för att konvertera en HTML-fil till PDF med Aspose.PDF för .NET. Genom att följa instruktionerna ovan bör du nu kunna konvertera HTML-filer till PDF-format. Den här funktionen kan vara användbar när du behöver generera PDF-dokument från HTML-innehåll.

