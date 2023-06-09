---
title: Signera digitalt
linktitle: Signera digitalt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du signerar en PDF-fil digitalt med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-security-and-signatures/digitally-sign/
---

den här handledningen går vi igenom processen att digitalt signera en PDF-fil med Aspose.PDF för .NET. Den digitala signaturen garanterar dokumentets äkthet och integritet genom att lägga till ett unikt elektroniskt fingeravtryck.

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
                         // Göra någonting
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
			//Skapa någon av de tre signaturtyperna
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
							// Göra någonting
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