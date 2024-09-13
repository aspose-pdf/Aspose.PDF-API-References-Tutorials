---
title: Signera digitalt med tidsstämpel i PDF-fil
linktitle: Signera digitalt med tidsstämpel i PDF-fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du digitalt signerar en PDF med en tidsstämpel med Aspose.PDF för .NET. Den här steg-för-steg-guiden täcker förutsättningar, certifikatinställningar, tidsstämpling och mer.
type: docs
weight: 50
url: /sv/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
## Introduktion

Har du någonsin behövt signera en PDF digitalt och inkludera en tidsstämpel för extra säkerhet? Oavsett om du arbetar med juridiska dokument, kontrakt eller något som kräver säker autentisering, ger en digital signatur med en tidsstämpel ett extra lager av trovärdighet. I den här handledningen kommer vi att dela upp hur du kan använda Aspose.PDF för .NET för att lägga till en digital signatur tillsammans med en tidsstämpel till dina PDF-dokument. Oroa dig inte, vi tar det steg för steg!

## Förutsättningar

Innan vi dyker in i koden finns det några saker du måste ställa in för att följa med. Här är en snabb checklista över förutsättningarna för att komma igång:

-  Aspose.PDF för .NET-bibliotek: Du behöver Aspose.PDF för .NET-biblioteket installerat i ditt projekt. Du kan[ladda ner den senaste versionen här](https://releases.aspose.com/pdf/net/) eller lägg till det i ditt projekt via NuGet.
- Ett PDF-dokument: Du behöver ett exempel på en PDF-fil för att arbeta med. Se till att ha en fil i ditt projekts katalog som du vill signera.
-  Digitalt certifikat (PFX-fil): Se till att du har ett digitalt certifikat (a`.pfx` fil) för att signera dokumentet digitalt.
- URL för tidsstämpling: Detta är en tidsstämplingstjänst online som kommer att användas för att bifoga en tidsstämpel till den digitala signaturen. 
- Grundläggande C#-kunskap: Du behöver inte vara expert, men att känna till grunderna i C# hjälper dig att förstå och anpassa koden.

När du har markerat alla dessa rutor är du redo att börja koda!

## Importera paket

För att komma igång måste du importera följande namnområden till ditt C#-projekt. Detta säkerställer att du har tillgång till relevanta Aspose.PDF-klasser och funktioner.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Collections;
```

## Steg 1: Ladda PDF-dokumentet

Det första vi behöver göra är att ladda PDF-dokumentet som vi vill signera. Så här gör du det:

```csharp
// Definiera sökvägen till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda PDF-dokumentet
Document document = new Document(dataDir + @"DigitallySign.pdf");
```

 Det här steget är ganska enkelt. Vi definierar helt enkelt vägen till dokumentet vi vill underteckna. De`Document` klass från Aspose.PDF hanterar att ladda filen.

## Steg 2: Konfigurera den digitala signaturen

Därefter skapar vi den digitala signaturen med klassen PKCS7 och laddar PFX-filen. Denna PFX-fil innehåller ditt certifikat och din privata nyckel, som är nödvändiga för att signera dokumentet.

```csharp
// Sökväg till din .pfx-fil
string pfxFile = "YOUR DOCUMENTS DIRECTORY\\certificate.pfx";

// Initiera signaturobjektet
PdfFileSignature signature = new PdfFileSignature(document);

// Ladda PFX-filen med ett lösenord
PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
```

 Vid det här laget säger du till Aspose att använda ditt digitala certifikat för att signera dokumentet. De`PKCS7`objekt hanterar allt kryptografiskt arbete åt dig, så du behöver inte oroa dig för de tråkiga detaljerna.

## Steg 3: Lägg till tidsstämpelinställningarna

En av nyckelkomponenterna i en robust digital signatur är tidsstämpeln. Detta säkerställer att dokumentets signatur kan verifieras även efter att certifikatet har gått ut. Låt oss ställa in tidsstämpeln med hjälp av en online-tidsstämplingsmyndighet.

```csharp
// Definiera tidsstämpelinställningar
TimestampSettings timestampSettings = new TimestampSettings("https://your_timestamp_url", "användare:lösenord");

// Lägg till tidsstämpelinställningar till PKCS7-objektet
pkcs.TimestampSettings = timestampSettings;
```

Här anger du URL:en för tidsstämplingstjänsten, som automatiskt ger en tid och ett datum till din signatur. Detta kan göras med eller utan autentisering.

## Steg 4: Definiera signaturens plats och utseende

Nu kommer vi att definiera var signaturen kommer att visas i PDF:en och dess dimensioner. Du kan anpassa placeringen av signaturrutan på sidan, såväl som storleken.

```csharp
//Definiera signaturens utseende och plats (sida 1, med specificerad rektangel)
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
```

Här definierar vi en rektangel som placerar signaturen vid koordinater (100, 100) på första sidan av PDF:en, med en bredd på 200 och höjd på 100. Du kan ändra dessa värden så att de passar din design.

## Steg 5: Signera PDF-dokumentet

Med allt inställt är det dags att faktiskt tillämpa den digitala signaturen på PDF:en. Detta steg kombinerar certifikatet, tidsstämpeln och positioneringen till ett enkelt kommando.

```csharp
// Signera dokumentet på första sidan
signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
```

Här är vad som händer:
- 1: Detta indikerar att signaturen ska appliceras på första sidan.
- "Signatur Reason": Det är här du kan ange varför du undertecknar dokumentet.
- "Kontakt": Ange undertecknarens kontaktinformation.
- "Plats": Ange platsen för undertecknaren.
- true: Detta booleska värde indikerar om signaturen är synlig i dokumentet.
- rect: Rektangeln vi definierade tidigare anger storleken och positionen för signaturen.
- pkcs: PKCS7-objektet innehåller det digitala certifikatet och tidsstämpelinställningarna.

## Steg 6: Spara den signerade PDF-filen

När dokumentet är signerat är det bara att spara det. Du kan välja ett nytt filnamn för att behålla både originalversionen och den signerade versionen.

```csharp
// Spara det signerade PDF-dokumentet
signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
```

Din nyligen signerade och tidsstämplade PDF sparas nu i den angivna katalogen!

## Slutsats

Och där har du det! Du har framgångsrikt signerat en PDF med en tidsstämpel digitalt med Aspose.PDF för .NET. Denna process säkerställer äktheten och integriteten hos dina dokument, vilket ger både dig och mottagaren sinnesfrid. Digitala signaturer blir mer och mer viktiga i dagens digitala värld, så att bemästra denna process är definitivt en färdighet värd att ha.

## FAQ's

### Kan jag använda ett annat filformat för certifikatet?  
Ja, men handledningen fokuserar på att använda en PFX-fil, vilket är det vanligaste formatet för digitala certifikat.

### Behöver jag en internetanslutning för att använda tidsstämpeln?  
Ja, eftersom tidsstämpeln hämtas från en online-tidsstämplingsmyndighet behöver du tillgång till internet.

### Kan jag signera flera sidor i en PDF?  
 Absolut! Du kan ändra`signature.Sign()` metod för att rikta in dig på flera sidor eller gå igenom alla sidor.

### Vad händer om PFX-filens lösenord är felaktigt?  
Du kommer att få ett undantag om lösenordet är fel, så se till att det har angetts korrekt.

### Kan jag göra signaturen osynlig?  
 Ja, du kan passera`false` till`Sign` metodens synlighetsparameter för att göra signaturen osynlig.