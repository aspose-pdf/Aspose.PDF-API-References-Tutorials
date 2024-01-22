---
title: Extrahera signaturinformation
linktitle: Extrahera signaturinformation
second_title: Aspose.PDF för .NET API-referens
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

### FAQ's

#### F: Varför skulle jag behöva extrahera signaturinformation från ett PDF-dokument?

S: Att extrahera signaturinformation från ett PDF-dokument är användbart för att validera äktheten av ett signerat dokument och analysera certifikatet som används för signaturen. Denna process hjälper till att säkerställa integriteten hos det signerade innehållet och kan vara avgörande för juridiska och säkerhetsmässiga ändamål.

#### F: Vad är Aspose.PDF för .NET?

S: Aspose.PDF för .NET är ett bibliotek som gör det möjligt för utvecklare att arbeta med PDF-dokument i .NET-applikationer. Det ger ett brett utbud av funktioner för att skapa, ändra och interagera med PDF-filer programmatiskt.

#### F: Vilka är förutsättningarna för att extrahera signaturinformation med Aspose.PDF för .NET?

S: För att extrahera signaturinformation behöver du grundläggande kunskaper i programmeringsspråket C#, Aspose.PDF för .NET-biblioteket installerat på ditt system och ett giltigt PDF-dokument som innehåller ett eller flera signaturfält.

#### F: Hur importerar jag de nödvändiga biblioteken för extraktionsprocessen?

S: Du kan importera de nödvändiga biblioteken genom att lägga till`using` direktiv för`Aspose.Pdf` och`System.IO` i början av din C#-fil. Dessa direktiv gör det möjligt för dig att använda de klasser och metoder som krävs för att extrahera signaturinformation.

#### F: Hur anger jag PDF-dokumentet för att extrahera signaturinformation?

 S: Du kan ställa in sökvägen till PDF-dokumentet genom att ersätta det`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till ditt dokument i det medföljande kodavsnittet. Den här sökvägen används för att ladda PDF-dokumentet som du vill extrahera signaturinformation från.

#### F: Vad är processen för att extrahera signaturinformation från ett PDF-dokument?

S: Extraheringsprocessen innefattar att iterera genom formulärfälten i PDF-dokumentet, kontrollera om varje fält är ett signaturfält och i så fall extrahera det tillhörande certifikatet. Det extraherade certifikatet kan sparas som en fil för vidare analys eller validering.

#### F: Hur extraheras certifikatet från ett signaturfält?

S: Certifikatet extraheras från ett signaturfält med hjälp av`ExtractCertificate()` metod som tillhandahålls av`SignatureField` klass i Aspose.PDF för .NET. Denna metod returnerar en ström som innehåller certifikatdata.

#### F: Hur sparar jag det extraherade certifikatet som en fil?

 S: Du kan spara det extraherade certifikatet som en fil genom att läsa certifikatströmmen och skriva dess innehåll till en fil med hjälp av`FileStream` klass. Koden som tillhandahålls i handledningen visar denna process.

#### F: Kan jag använda detta extraherade certifikat för signaturvalidering?

S: Ja, det extraherade certifikatet kan användas för signaturvalidering. Du kan analysera certifikatets detaljer och verifiera dess äkthet för att säkerställa integriteten hos det undertecknade dokumentet.

#### F: Hur kan jag integrera den här koden i mina egna applikationer?

S: Du kan integrera den medföljande koden i dina egna C#-applikationer genom att följa steg-för-steg-guiden. Ändra sökvägarna och filnamnen efter behov, och infoga koden i dina befintliga projekt.

#### F: Finns det andra funktioner i Aspose.PDF för .NET relaterade till signaturhantering?

S: Ja, Aspose.PDF för .NET tillhandahåller en rad funktioner för att arbeta med digitala signaturer, inklusive att signera dokument, verifiera signaturer och lägga till tidsstämpelinformation. Du kan utforska den officiella dokumentationen för mer information om dessa funktioner.

#### F: Var kan jag hitta ytterligare resurser för att använda Aspose.PDF för .NET?

 S: För mer information, handledning och resurser om att använda Aspose.PDF för .NET,[Aspose.PDF för .NET](https://reference.aspose.com/pdf/net/).

#### F: Är det möjligt att extrahera signaturer från krypterade PDF-dokument?

S: Möjligheten att extrahera signaturer från krypterade PDF-dokument kan bero på dokumentets krypteringsinställningar och behörigheter. Du kan behöva se till att du har nödvändiga behörigheter för att komma åt och extrahera signaturinformation.

#### F: Kan jag extrahera flera signaturer från ett enda PDF-dokument?

S: Ja, du kan modifiera den tillhandahållna koden så att den går igenom alla signaturfält i PDF-dokumentet och extraherar signaturinformation från var och en. Detta gör att du kan extrahera information om flera signaturer som finns i dokumentet.

#### F: Vilka är några praktiska användningsfall för att extrahera signaturinformation?

S: Några praktiska användningsfall för att extrahera signaturinformation inkluderar validering av äktheten av digitalt signerade dokument, analys av certifikatdetaljer för efterlevnadsändamål och upprätthållande av ett register över signaturer och undertecknare för revisionsändamål.

#### F: Finns det några juridiska överväganden när man extraherar signaturinformation?

S: Att extrahera signaturinformation kan ha juridiska konsekvenser, särskilt vid hantering av juridiskt bindande dokument. Se till att du följer relevanta regler och lagar relaterade till elektroniska signaturer och dokumentäkthet i din jurisdiktion.