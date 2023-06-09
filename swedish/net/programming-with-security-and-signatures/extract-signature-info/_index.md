---
title: Extrahera signaturinformation
linktitle: Extrahera signaturinformation
second_title: Aspose.PDF för .NET API Referens
description: Extrahera signaturinformation med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-security-and-signatures/extract-signature-info/
---

Processen att extrahera signaturinformation från ett PDF-dokument kan vara ganska användbar i olika scenarier. Oavsett om du behöver validera äktheten av ett signerat dokument eller analysera certifikatet som används för signaturen, erbjuder Aspose.PDF för .NET-biblioteket en bekväm lösning. I den här handledningen guidar vi dig genom steg-för-steg-processen för att extrahera signaturinformation med hjälp av den medföljande C#-källkoden.

## Krav

Innan vi börjar, se till att du har följande förutsättningar på plats:

1. Grundläggande kunskaper i programmeringsspråket C#.
2. Aspose.PDF för .NET-biblioteket installerat på ditt system.
3. Ett giltigt PDF-dokument med ett eller flera signaturfält.

Låt oss nu dyka in i implementeringsdetaljerna.

## Steg 1: Importera de obligatoriska biblioteken

 För att komma igång måste du importera de nödvändiga biblioteken till ditt C#-projekt. I det här fallet måste vi importera`Aspose.Pdf` och`System.IO` namnrymder. Detta kan göras genom att lägga till följande kod i början av din C#-fil:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Steg 2: Ställa in dokumentsökvägen

 Därefter måste du ställa in sökvägen till PDF-dokumentet som du vill extrahera signaturinformationen från. Byta ut`"YOUR DOCUMENTS DIRECTORY"` i följande kodavsnitt med den faktiska sökvägen till ditt dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

## Steg 3: Extrahera signaturinformation

Låt oss nu gå vidare till huvuddelen av koden där vi extraherar signaturinformationen från PDF-dokumentet. Vi itererar igenom varje fält i dokumentets formulär och kontrollerar om det är ett signaturfält. Om ett signaturfält hittas fortsätter vi med att extrahera certifikatet. Lägg till följande kodavsnitt:

```csharp
using (Document pdfDocument = new Document(input))
{
     foreach(Field field in pdfDocument.Form)
     {
         SignatureField sf = field as SignatureField;
         if (sf != null)
         {
             // Ta ut certifikatet
             Stream cerStream = sf.ExtractCertificate();
             if (cerStream != null)
             {
                 using (cerStream)
                 {
                     byte[] bytes = new byte[cerStream.Length];
                     using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
                     {
                         cerStream.Read(bytes, 0, bytes.Length);
                         fs.Write(bytes, 0, bytes.Length);
                     }
                 }
             }
         }
     }
}
```

## Steg 4: Extrahera certifikatet

I det här steget extraherar vi certifikatet från signaturfältet och sparar det som en fil. Det extraherade certifikatet kan analyseras ytterligare eller användas för valideringsändamål. Kodavsnittet nedan visar utvinnings- och sparprocessen:

```csharp
Stream cerStream = sf.ExtractCertificate();
if (cerStream != null)
{
     using (cerStream)
     {
         byte[] bytes = new byte[cerStream.Length];
         using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
         {
             cerStream.Read(bytes, 0, bytes.Length);
             fs.Write(bytes, 0, bytes.Length);
         }
     }
}
```

## Steg 5

: Sparar certifikatet

Slutligen sparar vi det extraherade certifikatet som en fil. I det här exemplet sparas certifikatet med namnet "input.cer" i den angivna katalogen. Du kan ändra koden så att den passar dina krav. Här är kodavsnittet för att spara certifikatet:

```csharp
using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
{
     fs.Write(bytes, 0, bytes.Length);
}
```

Det är allt! Du har framgångsrikt extraherat signaturinformation med Aspose.PDF för .NET. Integrera den här koden i dina egna applikationer eller modifiera den efter dina behov.

### Exempel på källkod för att extrahera signaturinformation med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string input = dataDir + "ExtractSignatureInfo.pdf";
	using (Document pdfDocument = new Document(input))
	{
		foreach (Field field in pdfDocument.Form)
		{
			SignatureField sf = field as SignatureField;
			if (sf != null)
			{
				Stream cerStream = sf.ExtractCertificate();
				if (cerStream != null)
				{
					using (cerStream)
					{
						byte[] bytes = new byte[cerStream.Length];
						using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
						{
							cerStream.Read(bytes, 0, bytes.Length);
							fs.Write(bytes, 0, bytes.Length);
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

I den här handledningen gick vi igenom en steg-för-steg-guide om hur man extraherar signaturinformation från ett PDF-dokument med hjälp av Aspose.PDF för .NET-biblioteket. Vi täckte processen med att importera de nödvändiga biblioteken, ställa in dokumentsökvägen, extrahera signaturinformation, extrahera certifikatet och spara det i en fil. Genom att följa dessa steg kan du enkelt hämta signaturdetaljer och arbeta med dem efter behov.