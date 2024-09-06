---
title: Logga in digitalt PDF-fil
linktitle: Logga in digitalt PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du loggar in en PDF-fil digitalt med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-security-and-signatures/digitally-sign/
---
I den här handledningen går vi igenom processen att digitalt logga in en PDF-fil med Aspose.PDF för .NET. Den digitala signaturen garanterar dokumentets äkthet och integritet genom att lägga till ett unikt elektroniskt fingeravtryck.

## Steg 1: Förutsättningar

Innan du börjar, se till att du har följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#
- Installera Visual Studio på din dator
- Aspose.PDF-bibliotek för .NET installerat

## Steg 2: Miljöinställning

För att komma igång, följ dessa steg för att konfigurera din utvecklingsmiljö:

1. Öppna Visual Studio och skapa ett nytt C#-projekt.
2. Importera de nödvändiga namnrymden till din kodfil:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Steg 3: Digital signatur

Det första steget är att digitalt signera PDF-filen. Den medföljande koden visar hur man gör en digital signatur med Aspose.PDF för .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Den här koden laddar en PDF-fil, skapar en digital signatur med ett specificerat utseende och sparar sedan PDF-filen med den tillagda signaturen.

## Steg 4: Signaturverifiering

När du har lagt till den digitala signaturen kan du kontrollera om PDF-filen innehåller en giltig signatur.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Gör något
                     }
                 }
             }
         }
     }
}
```

Den här koden verifierar PDF-filens första signatur och utför ytterligare åtgärder om signaturen är certifierad och har specifika behörigheter.

### Exempel på källkod för digital signering med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Använd PKCS7/PKCS7Fristående objekt
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Ställ in signaturutseende
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Skapa någon av de tre signaturtyperna
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Spara utdata PDF-fil
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Några signaturer?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verifiera den första
				{
					if (signature.IsCertified) // Auktoriserad?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Få åtkomstbehörighet
						{
							// Gör något
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

Grattis! Du har framgångsrikt utfört en digital signatur på en PDF-fil med Aspose.PDF för .NET. Denna handledning täckte steg-för-steg-processen, från att lägga till den digitala signaturen till att verifiera dess giltighet. Du kan nu använda den här funktionen för att säkra dina PDF-filer med digitala signaturer.

### FAQ's

#### F: Vad är syftet med denna handledning?

S: Denna handledning guidar dig genom processen att digitalt signera en PDF-fil med Aspose.PDF för .NET. Digitala signaturer lägger till ett elektroniskt fingeravtryck för att säkerställa dokumentets äkthet och integritet.

#### F: Vilka förutsättningar krävs innan start?

S: Innan du börjar, se till att du har en grundläggande förståelse för programmeringsspråket C#, har Visual Studio installerat och har Aspose.PDF-biblioteket för .NET installerat.

#### F: Hur ställer jag in utvecklingsmiljön?

S: Följ de medföljande stegen för att ställa in din utvecklingsmiljö, inklusive att skapa ett nytt C#-projekt i Visual Studio och importera de nödvändiga namnområdena.

#### F: Hur lägger jag till en digital signatur i en PDF-fil?

 S: Den medföljande exempelkoden visar hur man laddar en PDF-fil, skapar en digital signatur, anger utseende och sparar den signerade PDF-filen. Den digitala signaturen läggs till med hjälp av`Certify` metod för`PdfFileSignature` objekt.

#### F: Hur verifierar jag giltigheten av en digital signatur?

S: När du har lagt till den digitala signaturen kan du använda exempelkoden för att verifiera signaturens giltighet. Den kontrollerar om signaturen är certifierad och har specifika åtkomstbehörigheter.

####  F: Vad betyder`PKCS7` object represent?

 A: Den`PKCS7` objekt används för att tillhandahålla den kryptografiska funktionen för digitala signaturer. Den används för att skapa den digitala signaturen i den medföljande exempelkoden.

#### F: Kan jag anpassa utseendet på den digitala signaturen?

 S: Ja, du kan anpassa utseendet på den digitala signaturen genom att ange sökvägen till en bild i`SignatureAppearance` egendom av`PdfFileSignature` objekt.

#### F: Vad händer om signaturen inte är giltig?

S: Om signaturen inte är giltig kommer verifieringsprocessen att misslyckas, och motsvarande åtgärder inom verifieringskodblocket kommer inte att utföras.

#### F: Hur kan jag säkerställa säkerheten för mina digitala signaturer?

S: Digitala signaturer är säkra genom design och använder kryptografiska tekniker för att säkerställa autenticitet och integritet. Se till att du håller din privata nyckel säker och följer bästa praxis för hantering av digitala signaturer.

#### F: Kan jag lägga till flera digitala signaturer i en PDF?

 S: Ja, du kan lägga till flera digitala signaturer till en PDF-fil med hjälp av`PdfFileSignature` föremålets`Sign` eller`Certify` metoder. Varje signatur kommer att ha sitt eget utseende och konfiguration.