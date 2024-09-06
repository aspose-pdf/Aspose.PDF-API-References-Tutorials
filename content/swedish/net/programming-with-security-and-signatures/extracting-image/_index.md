---
title: Extraherar bild
linktitle: Extraherar bild
second_title: Aspose.PDF för .NET API-referens
description: Extrahera enkelt bilder från PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 70
url: /sv/net/programming-with-security-and-signatures/extracting-image/
---
Att extrahera bilder från ett PDF-dokument kan vara användbart i många fall. Med Aspose.PDF för .NET kan du enkelt extrahera bilder med hjälp av följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är de nödvändiga importdirektiven:

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen som du vill extrahera bilden från. Ersätta`"YOUR DOCUMENTS DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## Steg 3: Extrahera bild från PDF-dokument

Nu kommer vi att extrahera bilden från PDF-dokumentet med följande kod:

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

I det här exemplet går vi igenom varje fält i formuläret i PDF-dokumentet. Om ett signaturfält hittas extraherar vi den associerade bilden och sparar den i en JPEG-fil.

### Exempel på källkod för att extrahera bild med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att extrahera bilder från ett PDF-dokument med Aspose.PDF för .NET. Du kan integrera den här koden i dina egna projekt för att extrahera bilder och använda dem efter behov.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerad bildextraktion och PDF-dokumentmanipuleringsfunktioner.


### FAQ's

#### F: Är Aspose.PDF för .NET lämplig för nybörjare?

S: Även om viss förtrogenhet med C#-programmering är till hjälp, är vår handledning utformad för att vara nybörjarvänlig och guidar dig genom varje steg.

#### F: Kan jag extrahera flera bilder samtidigt?

A: Absolut! Genom att implementera loopar och anpassa den medföljande koden kan du extrahera flera bilder från ett enda PDF-dokument.

#### F: Är Aspose.PDF för .NET den enda lösningen för bildextraktion?

S: Även om det finns andra verktyg tillgängliga, är Aspose.PDF för .NET känt för sin effektivitet och omfattande funktioner.

#### F: Kan jag använda de extraherade bilderna för kommersiella ändamål?

S: Ja, när de har extraherats är bilderna dina att använda efter behov, inklusive för kommersiella projekt.

#### F: Var kan jag hitta fler resurser om PDF-manipulation med Aspose.PDF?

S: Besök vår officiella dokumentation för en mängd resurser och insikter om avancerad PDF-manipulation med Aspose.PDF för .NET.