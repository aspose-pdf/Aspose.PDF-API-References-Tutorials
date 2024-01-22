---
title: Onderteken met smartcard met behulp van PDF-bestandshandtekening
linktitle: Onderteken met smartcard met behulp van PDF-bestandshandtekening
second_title: Aspose.PDF voor .NET API-referentie
description: Onderteken uw PDF-bestanden veilig met een smartcard met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
Digitaal ondertekenen met een smartcard is een veilige manier om PDF-bestanden te ondertekenen. Met Aspose.PDF voor .NET kunt u eenvoudig een PDF-bestand ondertekenen met een smartcard door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Hier zijn de noodzakelijke importrichtlijnen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand dat u wilt ondertekenen. Vervangen`"YOUR DOCUMENTS DIRECTORY"`in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 3: Laad het PDF-document

Nu zullen we het te ondertekenen PDF-document laden met behulp van de volgende code:

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Stap 4: Voer de handtekening uit met de smartcard

 In deze stap voeren we de handtekening uit met de smartcard met behulp van de`PdfFileSignature` klasse uit de`Facades`bibliotheek. We selecteren het smartcardcertificaat uit het Windows-certificaatarchief en specificeren de benodigde ondertekeningsinformatie. Hier is de bijbehorende code:

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

 Ten slotte verifiëren we de handtekening van het ondertekende PDF-bestand met behulp van de`PdfFileSignature` klas. We krijgen de handtekeningnamen en controleren ze één voor één. Als de verificatie van een handtekening mislukt, wordt er een uitzondering gegenereerd. Hier is de bijbehorende code:

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

### Voorbeeldbroncode voor ondertekenen met smartcard met behulp van PDF-bestandshandtekening met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Onderteken met certificaatselectie in het Windows-certificaatarchief
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Handmatig het certificaat gekozen in de winkel
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

Gefeliciteerd! U beschikt nu over een stapsgewijze handleiding voor het ondertekenen van een PDF-bestand met een smartcard met behulp van Aspose.PDF voor .NET. U kunt deze code gebruiken om veilige digitale handtekeningen aan uw PDF-documenten toe te voegen.

Zorg ervoor dat u de officiële Aspose.PDF-documentatie bekijkt voor meer informatie over geavanceerde functies voor digitale handtekeningen en certificaatbeheer.

### Veelgestelde vragen

#### Vraag: Waarom zou ik overwegen om PDF-bestanden te ondertekenen met een smartcard?

A: Het ondertekenen van PDF-bestanden met een smartcard verbetert de veiligheid door de authenticiteit en integriteit van het document te garanderen. Op smartcards gebaseerde handtekeningen zorgen voor een hoger niveau van vertrouwen en compliance.

#### Vraag: Hoe werkt digitaal ondertekenen op basis van smartcards?

A: Bij digitaal ondertekenen op basis van smartcards wordt gebruik gemaakt van een cryptografische sleutel die op een smartcard is opgeslagen om een unieke digitale handtekening te creëren. Deze handtekening wordt aan het PDF-bestand toegevoegd, zodat ontvangers de oorsprong en integriteit van het document kunnen verifiëren.

#### Vraag: Wat is de rol van Aspose.PDF voor .NET bij het ondertekenen op basis van smartcards?

A: Aspose.PDF voor .NET biedt een uitgebreide set tools en bibliotheken om op smartcards gebaseerde digitale ondertekening van PDF-bestanden te vergemakkelijken. Het vereenvoudigt het proces en zorgt voor een veilige ondertekening van documenten.

#### Vraag: Kan ik een specifiek smartcardcertificaat kiezen om te ondertekenen?

A: Ja, u kunt een specifiek smartcardcertificaat uit het Windows-certificaatarchief selecteren om te ondertekenen. Met Aspose.PDF voor .NET kunt u certificaatselectie naadloos in uw toepassing integreren.

#### Vraag: Hoe verwerkt de meegeleverde broncode het ondertekenen op basis van smartcards?

A: De broncode laat zien hoe u een PDF-document kunt inbinden, een smartcardcertificaat kunt selecteren, ondertekeningsinformatie kunt opgeven en een digitale handtekening kunt maken. Het laat ook zien hoe u de geldigheid van de handtekening kunt verifiëren.

#### Vraag: Kan ik meerdere handtekeningen toepassen met behulp van smartcards in één PDF-bestand?

A: Absoluut, u kunt meerdere op smartcards gebaseerde handtekeningen op één PDF-bestand toepassen. Elke handtekening is uniek en draagt bij aan de algemene veiligheid van het document.

#### Vraag: Wat moet ik doen als de verificatie van een handtekening tijdens de verificatiestap mislukt?

A: Als de verificatie van een handtekening mislukt, wordt er een uitzondering gegenereerd, wat aangeeft dat de handtekening niet geldig is. Dit zorgt ervoor dat alleen geldige en vertrouwde handtekeningen worden geaccepteerd.

#### Vraag: Is op smartcards gebaseerde ondertekening compatibel met alle soorten PDF-documenten?

A: Ja, op smartcards gebaseerde ondertekening is compatibel met alle soorten PDF-documenten. U kunt digitale handtekeningen toepassen op verschillende soorten PDF-bestanden, waaronder formulieren, rapporten en meer.

#### Vraag: Hoe kan ik meer te weten komen over geavanceerd beheer van digitale handtekeningen en certificaten?

A: Bekijk de officiële Aspose.PDF-documentatie voor gedetailleerd inzicht in geavanceerde functies voor digitale handtekeningen, certificaatbeheer en best practices voor het garanderen van documentbeveiliging.

#### Vraag: Waar kan ik verdere hulp of ondersteuning vinden voor het implementeren van op smartcards gebaseerde ondertekening?

A: Neem voor aanvullende begeleiding en ondersteuning contact op met de Aspose.PDF-communityforums of raadpleeg de documentatie voor uitgebreide informatie over ondertekenen op basis van smartcards.