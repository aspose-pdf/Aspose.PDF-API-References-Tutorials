---
title: Sign Med Smart Card Använder Signaturfältet
linktitle: Sign Med Smart Card Använder Signaturfältet
second_title: Aspose.PDF för .NET API Referens
description: Signera dina PDF-filer säkert med ett smartkort med Aspose.PDF för .NET.
type: docs
weight: 120
url: /sv/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Digital signering med ett smartkort är ett säkert sätt att signera PDF-filer. Med Aspose.PDF för .NET kan du enkelt signera en PDF-fil med ett signaturfält och ett smartkort genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är de nödvändiga importdirektiven:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill signera. Byta ut`"YOUR DOCUMENTS DIRECTORY"` följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 3: Kopiera och öppna PDF-dokumentet

Nu kommer vi att kopiera och öppna PDF-dokumentet som ska signeras med följande kod:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Skapa ett signaturfält
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Välj certifikatet i butiken
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Skapa en extern signatur med nödvändig information
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Steg 4: Verifiera signaturen

 Slutligen verifierar vi signaturen för den signerade PDF-filen med hjälp av`PdfFileSignature` klass. Vi tar fram signaturnamnen och kontrollerar dem en efter en. Om en signatur misslyckas med verifiering skapas ett undantag. Här är motsvarande kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Exempel på källkod för Sign With Smart Card som använder signaturfält med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Signera med certifikatval i Windows certifikatbutik
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Välj certifikat manuellt i butiken
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
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

## Slutsats

Grattis! Du har nu en steg-för-steg-guide för att signera en PDF-fil med ett smartkort med hjälp av ett signaturfält med Aspose.PDF för .NET. Du kan använda den här koden för att lägga till säkra digitala signaturer till dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade funktioner för digital signatur och certifikathantering.

### FAQ's

#### F: Vad är fördelen med att använda ett signaturfält för digital signering med ett smartkort?

S: Att använda ett signaturfält för digital signering med ett smartkort ger ett angivet område i PDF:en där signaturen tillämpas. Detta förbättrar dokumentets tydlighet och säkerställer signaturens äkthet.

#### F: Hur underlättar Aspose.PDF för .NET-biblioteket smartkortsbaserad digital signering med ett signaturfält?

S: Aspose.PDF för .NET förenklar processen att skapa ett signaturfält, välja ett smartkortcertifikat och tillämpa en digital signatur på ett specifikt område i PDF-dokumentet.

#### F: Varför är det viktigt att välja ett specifikt certifikat för smartkortsbaserad signering?

S: Genom att välja ett specifikt certifikat kan du unikt identifiera undertecknaren och säkerställa signaturens integritet. Detta hjälper till att skapa förtroende och överensstämmelse med standarder för digital signering.

#### F: Hur hanterar den medföljande källkoden den smartkortbaserade signeringsprocessen med ett signaturfält?

S: Källkoden visar hur man skapar ett signaturfält, väljer ett smartkortcertifikat och tillämpar en digital signatur med specifik signeringsinformation. Den visar också hur man verifierar signaturens giltighet.

#### F: Kan jag anpassa utseendet på signaturfältet?

S: Ja, du kan anpassa utseendet på signaturfältet, t.ex. dess storlek, position och visuella representation, så att det passar ditt dokuments layout.

#### F: Vad händer om en signatur misslyckas med verifiering under verifieringssteget?

S: Om en signatur misslyckas med verifiering, skapas ett undantag, vilket indikerar att signaturen inte är giltig. Detta säkerställer att endast giltiga och pålitliga signaturer accepteras.

#### F: Kan jag använda flera signaturfält och smartkortbaserade signaturer på ett enda PDF-dokument?

S: Absolut, du kan använda flera signaturfält och smartkortbaserade signaturer på olika delar av samma PDF-dokument, vilket ger flera säkerhetslager.

#### F: Hur förbättrar användningen av ett signaturfält den övergripande dokumentsigneringsprocessen?

S: Att använda ett signaturfält effektiviserar dokumentsigneringsprocessen, eftersom det vägleder undertecknaren att placera sin signatur på ett avsett område, vilket gör signeringsprocessen mer organiserad och användarvänlig.

#### F: Finns det några begränsningar för att använda signaturfält med smartkortsbaserad signering?

S: Det finns inga inneboende begränsningar för att använda signaturfält med smartkortsbaserad signering. Det är dock viktigt att se till att den valda platsen för signaturfältet inte skymmer viktigt dokumentinnehåll.

#### F: Var kan jag hitta ytterligare hjälp eller support för att implementera smartkortsbaserad signering med ett signaturfält?

S: För ytterligare vägledning och support kan du hänvisa till den officiella Aspose.PDF-dokumentationen och gemenskapsforum, som erbjuder värdefulla insikter och lösningar för att implementera säkra digitala signaturer.