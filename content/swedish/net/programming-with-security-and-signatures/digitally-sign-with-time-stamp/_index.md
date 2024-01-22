---
title: Signera digitalt med tidsstämpel i PDF-fil
linktitle: Signera digitalt med tidsstämpel i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du utför en digital signatur med tidsstämpel i PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 50
url: /sv/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
I den här handledningen går vi igenom processen att digitalt logga in PDF-fil med tidsstämpel med Aspose.PDF för .NET. Den digitala signaturen med tidsstämpel garanterar dokumentets äkthet och integritet, genom att lägga till ett elektroniskt fingeravtryck med en tidsstämpel.

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
		// Skapa någon av de tre signaturtyperna
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Spara utdata-PDF-fil
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Slutsats

Grattis! Du har framgångsrikt utfört en digital signatur med tidsstämpel på en PDF-fil med Aspose.PDF för .NET. Denna handledning täckte steg-för-steg-processen från att skapa signaturen till att spara den uppdaterade PDF-filen. Du kan nu använda den här funktionen för att lägga till digitala signaturer med tidsstämpel till dina PDF-filer.

### Vanliga frågor om digital signering med tidsstämpel i PDF-fil

#### F: Vad är syftet med digital signering med en tidsstämpel?

S: Digital signering med en tidsstämpel lägger till ett elektroniskt fingeravtryck med en tidsstämpel till en PDF-fil, vilket säkerställer dokumentets autenticitet och integritet vid en specifik tidpunkt.

#### F: Vilka förutsättningar krävs för att starta den här handledningen?

S: Innan du börjar, se till att du har en grundläggande förståelse för programmeringsspråket C#, har Visual Studio installerat och har Aspose.PDF-biblioteket för .NET installerat.

#### F: Hur kan jag ställa in min utvecklingsmiljö?

S: Följ de medföljande stegen för att ställa in din utvecklingsmiljö, inklusive att skapa ett nytt C#-projekt i Visual Studio och importera de nödvändiga namnområdena.

#### F: Hur lägger jag till en digital signatur med en tidsstämpel i en PDF?

S: Den medföljande exempelkoden visar hur man laddar en PDF-fil, skapar en digital signatur med en tidsstämpel med hjälp av en PFX-fil (privat nyckel) och angivna tidsstämpelinställningar, lägger till signaturen i PDF-filen och sparar den uppdaterade filen.

#### F: Vad är en PFX-fil och varför används den i exemplet?

S: En PFX-fil (Personal Exchange Format) innehåller en privat nyckel och ett certifikat. Den används här för att tillhandahålla kryptografisk funktionalitet för digitala signaturer. Se till att du ersätter platshållaren med din PFX-fil och ditt lösenord.

#### F: Vad är tidsstämpelinställningar?

S: TimestampSettings definierar inställningarna för tidsstämpelservern som används för att lägga till den elektroniska tidsstämpeln till signaturen. Den inkluderar tidsstämpelserverns URL och valfria användaruppgifter.

#### F: Kan jag använda en annan tidsstämpelserver än den i exemplet?
 S: Ja, du kan använda vilken som helst kompatibel tidsstämpelserver. Byt ut URL:en och, om det behövs, ange lämpliga användaruppgifter i`TimestampSettings` objekt.

#### F: Vad är syftet med att specificera signaturrektangeln?

S: Signaturrektangeln definierar positionen och dimensionerna för den digitala signaturens utseende på PDF-sidan. Justera dessa värden för att placera signaturen efter önskemål.

#### F: Vad händer om tidsstämpelservern inte är tillgänglig under signering?

S: Om tidsstämpelservern inte är tillgänglig under signering kan processen misslyckas eller ta längre tid. Se till att din tidsstämpelserver är pålitlig och tillgänglig.

#### F: Hur kan jag verifiera närvaron av en tidsstämpel i den signerade PDF-filen?

 S: Du kan granska den signerade PDF-filen med hjälp av exempelkoden som tillhandahålls. De`TimestampSettings` du använde under signeringen bör finnas tillgänglig i signaturinformationen.

#### F: Är digitala signaturer med tidsstämplar juridiskt bindande?

S: Digitala signaturer med tidsstämplar har juridiskt värde i många jurisdiktioner och anses ofta vara mer tillförlitliga än enkla digitala signaturer. Rådfråga juridiska experter i din jurisdiktion för specifika bestämmelser.

#### F: Kan jag lägga till flera digitala signaturer med tidsstämplar till en PDF?

S: Ja, du kan lägga till flera digitala signaturer med tidsstämplar till en PDF-fil genom att anropa processen för att skapa signaturer flera gånger. Varje signatur kommer att ha sin egen tidsstämpel.