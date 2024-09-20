---
title: Sign Med Smart Card Använder Signaturfältet
linktitle: Sign Med Smart Card Använder Signaturfältet
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du säkert signerar PDF-filer med ett smartkort med Aspose.PDF för .NET. Följ vår steg-för-steg-guide för enkel implementering.
type: docs
weight: 120
url: /sv/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## Introduktion

dagens digitala värld är det viktigare än någonsin att säkra dokument. Oavsett om du är en utvecklare, en företagsägare eller bara någon som hanterar känslig information, kan du spara tid och se till att dina dokument är autentiserade genom att veta hur man signerar PDF-filer elektroniskt. I den här guiden går vi igenom processen att signera en PDF-fil med ett smartkort och ett signaturfält med Aspose.PDF för .NET. 

## Förutsättningar

Innan vi fördjupar oss i undertecknandeprocessen, låt oss se till att du har allt du behöver för att komma igång. Här är en checklista med förutsättningar:

1. Aspose.PDF för .NET: Se till att du har Aspose.PDF-biblioteket installerat i din .NET-miljö. Du kan ladda ner den från[plats](https://releases.aspose.com/pdf/net/).

2. Visual Studio: Du behöver en IDE för att skriva och köra din .NET-kod. Visual Studio Community Edition är ett fantastiskt gratisalternativ.

3. Ett smartkort: Detta är viktigt för att signera din PDF. Se till att du har en smartkortläsare och de nödvändiga certifikaten installerade på din maskin.

4. Grundläggande C#-kunskaper: Bekantskap med C#-programmering hjälper dig att förstå kodavsnitten vi kommer att använda.

5. Exempel på PDF-dokument: Ha ett exempel på PDF-dokument redo för testning. Du kan skapa en tom PDF eller använda en befintlig.

## Importera paket

Innan vi börjar koda, låt oss importera de nödvändiga paketen. Du måste inkludera följande namnområden i din C#-fil:

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Dessa namnrymder ger dig tillgång till de klasser och metoder som krävs för att arbeta med PDF-filer och hantera digitala signaturer.

## Steg-för-steg-guide för att signera en PDF-fil med ett smartkort

Nu när vi har klarat våra förutsättningar, låt oss dela upp signeringsprocessen i hanterbara steg. Vi går igenom varje steg i detalj, så att du förstår vad som händer under huven.

### Steg 1: Konfigurera din dokumentkatalog

Vad du ska göra: Definiera sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Förklaring: Byt ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen där dina PDF-filer finns. Det är här vi läser den tomma PDF-filen och sparar det signerade dokumentet.

### Steg 2: Kopiera den tomma PDF-filen

Vad du ska göra: Skapa en kopia av din tomma PDF att arbeta med.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 Förklaring: Den här raden kopierar`blank.pdf`fil till en ny fil med namnet`externalSignature1.pdf` . De`true` parametern tillåter överskrivning om filen redan finns.

### Steg 3: Öppna PDF-dokumentet

Vad du ska göra: Öppna den kopierade PDF-filen för att läsa och skriva.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // Ytterligare steg kommer att gå här
    }
}
```

 Förklaring: Vi använder en`FileStream` för att öppna vår PDF-fil. De`Document` klass från Aspose.PDF tillåter oss att manipulera PDF-innehållet.

### Steg 4: Skapa ett signaturfält

Vad du ska göra: Definiera ett signaturfält i PDF:en där signaturen ska placeras.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 Förklaring: Här skapar vi en`SignatureField` på den andra sidan (sidindex börjar från 1) i PDF-filen. De`Rectangle` definierar positionen och storleken på signaturfältet.

### Steg 5: Gå till Smart Card Certificate Store

Vad du ska göra: Öppna certifikatarkivet för att välja ditt smartkortcertifikat.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

Förklaring: Vi kommer åt certifikatarkivet för den aktuella användaren. Det är här dina smartkortscertifikat lagras.

### Steg 6: Välj certifikatet

Vad du ska göra: Be användaren att välja ett certifikat från butiken.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

Förklaring: Den här raden öppnar en dialogruta där du kan välja ett certifikat. Du kan välja det certifikat som är kopplat till ditt smartkort.

### Steg 7: Skapa en extern signatur

 Vad du ska göra: Skapa en instans av`ExternalSignature` med det valda certifikatet.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 Förklaring: Vi initierar`ExternalSignature` med det valda certifikatet. Du kan också ställa in behörighet, skäl för signering och kontaktinformation.

### Steg 8: Lägg till signaturfältet i dokumentet

Vad du ska göra: Lägg till signaturfältet i dokumentet.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

Förklaring: Vi ger signaturfältet ett namn och lägger till det på första sidan i dokumentet. Detta förbereder PDF-filen för signering.

### Steg 9: Signera dokumentet

Vad du ska göra: Använd den externa signaturen för att signera PDF:en.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

Förklaring: Den här raden signerar dokumentet med den externa signaturen och sparar ändringarna i PDF-filen. Ditt dokument är nu signerat!

### Steg 10: Verifiera signaturen

Vad du ska göra: Kontrollera om signaturen är giltig.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

Förklaring: Vi skapar en instans av`PdfFileSignature` för att verifiera signaturerna i dokumentet. Om signaturen inte är giltig görs ett undantag.

## Slutsats

Grattis! Du har precis lärt dig hur du signerar ett PDF-dokument med ett smartkort och ett signaturfält med Aspose.PDF för .NET. Denna process säkrar inte bara dina dokument utan säkerställer också autenticitet, vilket gör det till en viktig färdighet i dagens digitala landskap. Oavsett om du undertecknar kontrakt, fakturor eller andra viktiga dokument, kan du spara tid och känna dig trygg genom att veta hur du implementerar digitala signaturer.

## FAQ's

### Vad är Aspose.PDF för .NET?
Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, manipulera och konvertera PDF-dokument i .NET-applikationer.

### Behöver jag ett smartkort för att signera PDF-filer?
Ja, ett smartkort krävs för att säkert signera PDF-filer med ett digitalt certifikat.

### Kan jag använda Aspose.PDF gratis?
 Aspose.PDF erbjuder en gratis testversion, som du kan ladda ner[här](https://releases.aspose.com/).

### Hur kan jag verifiera en signerad PDF?
 Du kan använda`PdfFileSignature` klass i Aspose.PDF för att verifiera signaturerna i ditt PDF-dokument.

### Var kan jag hitta mer dokumentation om Aspose.PDF?
 Du kan kontrollera[Aspose.PDF-dokumentation](https://reference.aspose.com/pdf/net/) för mer information och exempel.