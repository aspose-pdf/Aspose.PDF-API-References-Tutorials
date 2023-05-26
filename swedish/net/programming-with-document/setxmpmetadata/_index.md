---
title: Ställ in XMPMetadata
linktitle: Ställ in XMPMetadata
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du ställer in XMPMetadata i PDF-filer med Aspose.PDF för .NET. Följ denna steg-för-steg-guide.
type: docs
weight: 330
url: /sv/net/programming-with-document/setxmpmetadata/
---
I den här artikeln ger vi en steg-för-steg-guide om hur du använder Aspose.PDF för .NET för att ställa in XMP-metadata i en PDF-fil. Vi kommer att tillhandahålla ett fullständigt exempel på källkod i slutet av artikeln.

## Steg 1: Ställ in sökvägen till dokumentkatalogen

Innan vi börjar måste vi ställa in sökvägen till katalogen där vårt PDF-dokument finns. Vi kommer att lagra denna sökväg i en variabel som heter "dataDir".

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Se till att byta ut`YOUR DOCUMENT DIRECTORY` med den faktiska sökvägen till din PDF-fil.

## Steg 2: Öppna PDF-filen

Det första steget är att öppna PDF-filen du vill ställa in XMP-metadata för. För att göra detta måste du skapa en ny`Document` objekt och skicka in sökvägen till din PDF-fil.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Steg 3: Ställ in egenskaper för XMP-metadata

Nu när du har din PDF-fil öppen kan du börja ställa in XMP-metadataegenskaper. Vilka egenskaper du anger beror på dina specifika behov, men här är några vanliga egenskaper som du kanske vill ställa in:

- `xmp:CreateDate`: Skapandet av PDF-filen.
- `xmp:Nickname`: Ett smeknamn eller alias för PDF-filen.
- `xmp:CustomProperty`: En anpassad egenskap med ett värde som du anger.

 För att ställa in dessa egenskaper kan du använda`Metadata` egendom av`Document` objekt. Här är ett exempel:

```csharp
// Ställ in egenskaper
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

I den här handledningen ställer vi in skapelsedatumet till det aktuella datumet och tiden, smeknamnet till "Smetnamn" och en anpassad egenskap till "Anpassat värde". Du kan ersätta dessa värden med dina egna.

## Steg 4: Spara PDF-filen

 När du har ställt in egenskaperna för XMP-metadata måste du spara PDF-filen. För att göra detta kan du använda`Save` metod för`Document` objekt och skicka in sökvägen till där du vill spara den uppdaterade PDF-filen.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//Spara dokument
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Set XMPMetadata med Aspose.PDF för .NET

Här är den kompletta källkoden för att ställa in XMPMetadata med Aspose.PDF för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Öppna dokumentet
	Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

	// Ställ in egenskaper
	pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
	pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
	pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

	dataDir = dataDir + "SetXMPMetadata_out.pdf";
	//Spara dokument
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);

```
