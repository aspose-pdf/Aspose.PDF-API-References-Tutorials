---
title: Ondertekenen met smartcard met behulp van PDF-bestandshandtekening
linktitle: Ondertekenen met smartcard met behulp van PDF-bestandshandtekening
second_title: Aspose.PDF voor .NET API-referentie
description: Onderteken uw PDF-bestanden veilig met een smartcard met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Digitaal ondertekenen met een smartcard is een veilige manier om PDF-bestanden te ondertekenen. Met Aspose.PDF voor .NET kunt u eenvoudig een PDF-bestand ondertekenen met een smartcard door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Dit zijn de benodigde importrichtlijnen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand dat u wilt ondertekenen. Vervangen`"YOUR DOCUMENTS DIRECTORY"` in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 3: Laad het PDF-document

Nu laden we het PDF-document dat ondertekend moet worden met behulp van de volgende code:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Stap 4: Voer de handtekening uit met de smartcard

 In deze stap zullen we de handtekening met de smartcard uitvoeren met behulp van de`PdfFileSignature` klas van de`Facades`bibliotheek. We selecteren het smartcardcertificaat uit de Windows-certificaatopslag en specificeren de benodigde ondertekeningsinformatie. Hier is de bijbehorende code:

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Selecteer het certificaat in de winkel
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Stap 5: Handtekening verifiëren

 Ten slotte verifiëren we de handtekening van het ondertekende PDF-bestand met behulp van de`PdfFileSignature` klasse. We krijgen de handtekeningnamen en controleren ze één voor één. Als een handtekening de verificatie niet doorstaat, wordt er een uitzondering gegenereerd. Hier is de bijbehorende code:

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

### Voorbeeldbroncode voor Sign With Smart Card Using Pdf File Signature met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Ondertekenen met certificaatselectie in het Windows-certificaatarchief
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Handmatig het certificaat in de winkel gekozen
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

## Conclusie

Gefeliciteerd! U hebt nu een stapsgewijze handleiding voor het ondertekenen van een PDF-bestand met een smartcard met Aspose.PDF voor .NET. U kunt deze code gebruiken om veilige digitale handtekeningen toe te voegen aan uw PDF-documenten.

Raadpleeg de officiële Aspose.PDF-documentatie voor meer informatie over geavanceerde functies voor digitale handtekeningen en certificaatbeheer.

### Veelgestelde vragen

#### V: Waarom zou ik PDF-bestanden ondertekenen met een smartcard?

A: PDF-bestanden ondertekenen met een smartcard verbetert de beveiliging door de authenticiteit en integriteit van het document te garanderen. Smartcard-gebaseerde handtekeningen bieden een hoger niveau van vertrouwen en naleving.

#### V: Hoe werkt digitaal ondertekenen met een smartcard?

A: Smartcard-gebaseerde digitale ondertekening omvat het gebruik van een cryptografische sleutel die is opgeslagen op een smartcard om een unieke digitale handtekening te maken. Deze handtekening wordt toegevoegd aan het PDF-bestand, zodat ontvangers de oorsprong en integriteit van het document kunnen verifiëren.

#### V: Wat is de rol van Aspose.PDF voor .NET bij smartcard-gebaseerde ondertekening?

A: Aspose.PDF voor .NET biedt een uitgebreide set tools en bibliotheken om smartcard-gebaseerde digitale ondertekening van PDF-bestanden te vergemakkelijken. Het vereenvoudigt het proces en zorgt voor veilige documentondertekening.

#### V: Kan ik een specifiek smartcardcertificaat kiezen voor ondertekening?

A: Ja, u kunt een specifiek smartcardcertificaat selecteren uit de Windows-certificaatopslag voor ondertekening. Met Aspose.PDF voor .NET kunt u certificaatselectie naadloos integreren in uw toepassing.

#### V: Hoe verwerkt de meegeleverde broncode smartcard-gebaseerde ondertekening?

A: De broncode laat zien hoe u een PDF-document bindt, een smartcardcertificaat selecteert, ondertekeningsinformatie opgeeft en een digitale handtekening maakt. Het laat ook zien hoe u de geldigheid van de handtekening verifieert.

#### V: Kan ik meerdere handtekeningen met behulp van smartcards in één PDF-bestand toepassen?

A: Absoluut, u kunt meerdere smartcard-gebaseerde handtekeningen toepassen op één PDF-bestand. Elke handtekening is uniek en draagt bij aan de algehele beveiliging van het document.

#### V: Wat als een handtekening de verificatie tijdens de verificatiestap niet doorstaat?

A: Als een handtekening de verificatie niet doorstaat, wordt er een uitzondering gegenereerd die aangeeft dat de handtekening niet geldig is. Dit zorgt ervoor dat alleen geldige en vertrouwde handtekeningen worden geaccepteerd.

#### V: Is ondertekenen met smartcards compatibel met alle soorten PDF-documenten?

A: Ja, smartcard-based signing is compatibel met alle typen PDF-documenten. U kunt digitale handtekeningen toepassen op verschillende typen PDF-bestanden, waaronder formulieren, rapporten en meer.

#### V: Hoe kan ik meer leren over geavanceerd beheer van digitale handtekeningen en certificaten?

A: Bekijk de officiële Aspose.PDF-documentatie voor gedetailleerde inzichten in geavanceerde functies voor digitale handtekeningen, certificaatbeheer en best practices voor het waarborgen van de beveiliging van documenten.

#### V: Waar kan ik verdere hulp of ondersteuning vinden voor het implementeren van smartcard-gebaseerde ondertekening?

A: Voor aanvullende begeleiding en ondersteuning kunt u terecht op de Aspose.PDF communityforums of de documentatie raadplegen voor uitgebreide informatie over ondertekenen met smartcards.