---
title: Extrahera signaturinformation
linktitle: Extrahera signaturinformation
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar digitala signaturer och certifikatinformation från PDF-dokument med Aspose.PDF för .NET. En komplett steg-för-steg-guide för C#-utvecklare.
type: docs
weight: 80
url: /sv/net/programming-with-security-and-signatures/extract-signature-info/
---
## Introduktion

dagens digitala värld är det avgörande att säkerställa dokumentens säkerhet och integritet. En av de vanligaste metoderna som används för att säkra PDF-filer är att lägga till en digital signatur. Men att hämta och verifiera signaturens detaljer kan ibland vara en utmaning, särskilt när du har att göra med olika certifikat. I den här guiden går vi igenom processen att extrahera signaturinformation från PDF-dokument med Aspose.PDF för .NET, vilket gör uppgiften till en lek. Du kommer att lära dig hur du kommer åt signaturfält, extraherar certifikatinformation och sparar den i en fil.

## Förutsättningar

Innan vi börjar, låt oss se till att du har allt redo för att komma igång.

-  Aspose.PDF för .NET Library: Om du inte har det ännu kan du ladda ner det från[Aspose.PDF för .NET nedladdningssida](https://releases.aspose.com/pdf/net/). 
- .NET-utvecklingsmiljö: Du behöver en IDE som Visual Studio.
- Grundläggande C#-kunskaper: Bekantskap med C# är till hjälp för att förstå kodavsnitten i denna handledning.
- PDF-dokument med en digital signatur: För teständamål, se till att du har en PDF-fil som innehåller minst en digital signatur.

## Importera nödvändiga namnområden

Innan du hoppar in i koden är det viktigt att importera de nödvändiga namnrymden. Dessa namnrymder ger dig tillgång till Aspose.PDF-funktionaliteten och arbetar med PDF-dokument.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Nu när du har ställt in det väsentliga, låt oss gå vidare till den faktiska processen att extrahera signaturinformation från en PDF.

## Steg 1: Konfigurera dokumentkatalogen

 Innan du arbetar med ett PDF-dokument måste du ange platsen för filen du ska använda. Du kan byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där dina PDF-filer lagras.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Här anger vi katalogen som innehåller PDF-filen och själva filnamnet. Se till att filen finns i den katalogen!

## Steg 2: Ladda PDF-dokumentet

 Nu när du har ställt in din katalog är nästa steg att ladda PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Bearbeta PDF-filen här.
}
```

 Denna kodrad initierar en`Document`objekt som representerar PDF-filen. De`using` statement säkerställer att resurser rensas upp efter att dokumentet har bearbetats.

## Steg 3: Åtkomst till formulärfält

I det här steget går vi igenom alla formulärfält i PDF-dokumentet. Eftersom signaturer vanligtvis lagras som formulärfält hjälper det här steget oss att identifiera signaturfälten.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Identifiera signaturfält här.
}
```

 Genom att iterera genom`Form` egendom av`Document` objekt kan vi undersöka varje formulärfält för att kontrollera om det är ett signaturfält.

## Steg 4: Identifiera signaturfält

 När du har kommit åt formulärfälten är nästa steg att identifiera vilka som är signaturfält. Vi kan göra detta genom att kasta varje fält till en`SignatureField` objekt.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Extrahera signaturinformation.
}
```

 Här använder vi`as` nyckelord för att försöka casta varje formulärfält till en`SignatureField`. Om skådespelaren är framgångsrik vet vi att fältet är en signatur.

## Steg 5: Extrahera certifikatet

Nu när du har identifierat signaturfältet är nästa uppgift att extrahera certifikatet från signaturen. Certifikaten innehåller avgörande information om undertecknaren och signaturens giltighet.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 De`ExtractCertificate` metod returnerar en`Stream` objekt som innehåller certifikatdata. Denna ström kan användas för att spara certifikatet för vidare analys eller lagring.

## Steg 6: Spara certifikatet till en fil

 När du har extraherat certifikatet är det sista steget att spara det i en fil. I det här fallet sparar vi certifikatet som ett`.cer` fil.

```csharp
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

I det här kodblocket:

1. Kontrollera om certifikatströmmen inte är null.
2. Läs certifikatdata till en byte-array.
3.  Skriv byte-arrayen till a`.cer` filen i dokumentkatalogen.

## Slutsats

Att extrahera digitala signaturer och deras relaterade certifikatinformation från PDF-dokument med Aspose.PDF för .NET är ganska enkelt när det delas upp i enkla steg. Oavsett om du granskar dokument, verifierar signaturer eller bara lagrar certifikat för förvaring, förser den här handledningen dig med kunskapen för att få det gjort effektivt. Kom ihåg att säkra och verifiera dokument är avgörande i dagens digitala värld, och att använda verktyg som Aspose.PDF för .NET gör det mycket lättare att hantera.

## FAQ's

### Kan jag extrahera flera signaturer från en PDF med Aspose.PDF för .NET?
Ja, koden går igenom alla formulärfält i dokumentet, så att du kan extrahera flera signaturer om de finns.

### Vad händer om ingen signatur hittas i PDF-filen?
Om inga signaturfält finns, kommer koden helt enkelt att hoppa över dem utan att skapa ett fel.

### Kan jag använda detta tillvägagångssätt för att verifiera giltigheten av en signatur?
Även om du kan extrahera certifikatet kräver verifiering av giltigheten av en signatur ytterligare steg, som att kontrollera certifikatets förtroendekedja.

### Är det möjligt att extrahera andra formulärfältsdata med Aspose.PDF för .NET?
Ja, Aspose.PDF låter dig komma åt och manipulera olika typer av formulärfält i en PDF, inte bara signaturfält.

### Hur kan jag se detaljerna i det extraherade certifikatet?
 När certifikatet har sparats som en`.cer` fil kan du öppna den med valfri certifikatvisare eller importera den till ett systemcertifikatlager för ytterligare inspektion.