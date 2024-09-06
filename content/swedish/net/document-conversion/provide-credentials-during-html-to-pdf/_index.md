---
title: Ge referenser under HTML till PDF
linktitle: Ge referenser under HTML till PDF
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du konverterar HTML till PDF med Aspose.PDF för .NET med denna steg-för-steg-guide. Perfekt för utvecklare som vill effektivisera dokumentgenereringen.
type: docs
weight: 240
url: /sv/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## Introduktion

I en värld av mjukvaruutveckling är konvertering av HTML till PDF ett vanligt krav. Oavsett om du genererar rapporter, fakturor eller något annat dokument, kan du spara mycket tid och ansträngning att ha ett tillförlitligt bibliotek för att hantera denna uppgift. Gå in i Aspose.PDF för .NET, ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument med lätthet. I den här handledningen går vi igenom processen med att använda Aspose.PDF för att konvertera HTML till PDF samtidigt som du tillhandahåller autentiseringsuppgifter för säker åtkomst. Så ta tag i din kodningshatt och låt oss dyka in!

## Förutsättningar

Innan vi sätter igång finns det några saker du måste ha på plats:

1. Visual Studio: Se till att du har Visual Studio installerat på din dator. Det här blir vår utvecklingsmiljö.
2.  Aspose.PDF för .NET: Du kan ladda ner biblioteket från[webbplats](https://releases.aspose.com/pdf/net/) . Om du vill prova först kan du också få en[gratis provperiod](https://releases.aspose.com/).
3. Grundläggande kunskaper i C#: Bekantskap med C#-programmering hjälper dig att förstå exemplen bättre.
4. Internetåtkomst: Eftersom vi kommer att hämta HTML-innehåll från en URL, se till att du har en aktiv internetanslutning.

## Importera paket

För att komma igång med Aspose.PDF måste du importera de nödvändiga paketen till ditt projekt. Så här kan du göra det:

1. Öppna ditt Visual Studio-projekt.
2. Högerklicka på ditt projekt i Solution Explorer och välj "Hantera NuGet-paket."
3. Sök efter "Aspose.PDF" och installera den senaste versionen.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
Nu när vi har allt installerat, låt oss dela upp processen att konvertera HTML till PDF med referenser i hanterbara steg.

## Steg 1: Konfigurera din dokumentkatalog

Innan vi kan konvertera HTML till PDF måste vi ange var vår utdata PDF ska sparas. Detta görs genom att definiera en sökväg till dokumentkatalogen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen där du vill spara din PDF-fil. Detta kan vara en mapp på skrivbordet eller någon annan plats på ditt system.

## Steg 2: Skapa en webbförfrågan

 Därefter måste vi skapa en begäran för att hämta HTML-innehållet från en specifik URL. Det är här vi kommer att använda`WebRequest` klass.

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

Här skapar vi en begäran till webbadressen som innehåller HTML-koden vi vill konvertera. Se till att ersätta URL:en med den du tänker använda.

## Steg 3: Ange inloggningsuppgifter (om det behövs)

Om servern kräver autentiseringsuppgifter för att komma åt innehållet måste vi ställa in dem. Detta görs med hjälp av`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

 Den här raden säkerställer att begäran använder standardinloggningsuppgifterna för den aktuella användaren. Om du behöver ange specifika referenser kan du skapa en ny`NetworkCredential` objekt.

## Steg 4: Få svar

Nu när vi har ställt in vår begäran är det dags att få svar från servern.

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

Den här raden skickar begäran och väntar på att servern ska svara. Om allt går bra får vi det HTML-innehåll vi behöver.

## Steg 5: Läs svarsströmmen

 När vi har fått svaret måste vi läsa innehållet som returneras av servern. Detta görs med hjälp av en`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

 Här läser vi in hela innehållet i svarsströmmen till en strängvariabel som kallas`responseFromServer`. Glöm inte att stänga läsaren och strömmen för att frigöra resurser.

## Steg 6: Konvertera HTML till PDF

Nu kommer den spännande delen! Vi konverterar HTML-innehållet till ett PDF-dokument med Aspose.PDF.

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

 det här steget skapar vi en`MemoryStream` från HTML-innehållet och inställningarna`HtmlLoadOptions`. Detta gör att vi kan ange basadressen för externa resurser (som bilder eller stilmallar) som HTML-koden kan referera till.

## Steg 7: Spara PDF-dokumentet

Slutligen måste vi spara det genererade PDF-dokumentet i den angivna katalogen.

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Denna rad sparar PDF-filen med namnet`ProvideCredentialsDuringHTMLToPDF_out.pdf` i katalogen vi angav tidigare.

## Slutsats

Och där har du det! Du har framgångsrikt konverterat HTML till PDF med Aspose.PDF för .NET samtidigt som du har tillhandahållit autentiseringsuppgifter för säker åtkomst. Detta kraftfulla bibliotek gör det enkelt att hantera PDF-dokument, och med bara några rader kod kan du skapa proffsiga PDF-filer från HTML-innehåll. 

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument i .NET-applikationer.

### Hur installerar jag Aspose.PDF?
 Du kan installera Aspose.PDF via NuGet Package Manager i Visual Studio eller ladda ner det från[webbplats](https://releases.aspose.com/pdf/net/).

### Kan jag använda Aspose.PDF gratis?
Ja, Aspose erbjuder en gratis testversion som du kan använda för att utvärdera biblioteket innan du köper.

### Vilka typer av dokument kan jag skapa med Aspose.PDF?
Du kan skapa ett brett utbud av dokument, inklusive rapporter, fakturor och formulär, med Aspose.PDF.

### Var kan jag hitta support för Aspose.PDF?
 Du kan hitta support och ställa frågor på[Aspose supportforum](https://forum.aspose.com/c/pdf/10).