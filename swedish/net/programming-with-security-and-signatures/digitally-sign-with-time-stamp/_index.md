---
title: Digitalt tecken med tidsstämpel
linktitle: Digitalt tecken med tidsstämpel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du utför en digital signatur med tidsstämpel på en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

I den här handledningen går vi igenom processen att digitalt signera en PDF-fil med tidsstämpel med Aspose.PDF för .NET. Den digitala signaturen med tidsstämpel garanterar dokumentets äkthet och integritet, genom att lägga till ett elektroniskt fingeravtryck med en tidsstämpel.

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
```

## Steg 3: Digital signatur med tidsstämpel

Det första steget är att utföra den digitala signaturen med tidsstämpel på PDF-filen. Den medföljande koden visar hur man uppnår denna signatur med Aspose.PDF för .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Denna kod laddar en PDF-fil, skapar en digital signatur med tidsstämpel med hjälp av en PFX-fil (privat nyckel) och de angivna tidsstämpelparametrarna. Signaturen läggs sedan till i PDF-filen och sparas med suffixet "_ut".

### Exempel på källkod för Digital Sign With Time Stamp med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Användare/lösenord kan utelämnas
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Skapa någon av de tre signaturtyperna
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Spara utdata PDF-fil
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Slutsats

Grattis! Du har framgångsrikt utfört en digital signatur med tidsstämpel på en PDF-fil med Aspose.PDF för .NET. Denna handledning täckte steg-för-steg-processen från att skapa signaturen till att spara den uppdaterade PDF-filen. Du kan nu använda den här funktionen för att lägga till digitala signaturer med tidsstämpel till dina PDF-filer.