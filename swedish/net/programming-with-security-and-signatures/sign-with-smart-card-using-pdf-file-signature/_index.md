---
title: Signera med smartkort med pdf-filsignatur
linktitle: Signera med smartkort med pdf-filsignatur
second_title: Aspose.PDF för .NET API Referens
description: Signera dina PDF-filer säkert med ett smartkort med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---

Digital signering med ett smartkort är ett säkert sätt att signera PDF-filer. Med Aspose.PDF för .NET kan du enkelt signera en PDF-fil med ett smartkort genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är de nödvändiga importdirektiven:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill signera. Byta ut`"YOUR DOCUMENTS DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 3: Ladda PDF-dokumentet

Nu kommer vi att ladda PDF-dokumentet som ska signeras med följande kod:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Steg 4: Utför signaturen med smartkortet

 I det här steget kommer vi att utföra signaturen med smartkortet med hjälp av`PdfFileSignature` klass från`Facades` bibliotek. Vi väljer smartkortcertifikatet från Windows certifikatarkiv och anger nödvändig signeringsinformation. Här är motsvarande kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Välj certifikatet i butiken
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Steg 5: Verifiera signaturen

 Slutligen verifierar vi signaturen för den signerade PDF-filen med hjälp av`PdfFileSignature` klass. Vi tar fram signaturnamnen och kontrollerar dem en efter en. Om en signatur misslyckas med verifiering skapas ett undantag. Här är motsvarande kod:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### Exempel på källkod för Sign With Smart Card med Pdf-filsignatur med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Signera med certifikatval i Windows certifikatbutik
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Välj certifikat manuellt i butiken
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

Grattis! Du har nu en steg-för-steg-guide för att signera en PDF-fil med ett smartkort med Aspose.PDF för .NET. Du kan använda den här koden för att lägga till säkra digitala signaturer till dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade funktioner för digital signatur och certifikathantering.