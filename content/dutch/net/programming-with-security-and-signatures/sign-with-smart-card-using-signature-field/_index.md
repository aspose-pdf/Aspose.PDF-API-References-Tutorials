---
title: Ondertekenen met smartcard met behulp van handtekeningveld
linktitle: Ondertekenen met smartcard met behulp van handtekeningveld
second_title: Aspose.PDF voor .NET API-referentie
description: Onderteken uw PDF-bestanden veilig met een smartcard met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
Digitaal ondertekenen met een smartcard is een veilige manier om PDF-bestanden te ondertekenen. Met Aspose.PDF voor .NET kunt u eenvoudig een PDF-bestand ondertekenen met een handtekeningveld en een smartcard door de volgende broncode te volgen:

## Stap 1: Importeer de vereiste bibliotheken

Voordat u begint, moet u de benodigde bibliotheken voor uw C#-project importeren. Dit zijn de benodigde importrichtlijnen:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Stap 2: Stel het pad naar de documentenmap in

 In deze stap moet u het pad opgeven naar de map met het PDF-bestand dat u wilt ondertekenen. Vervangen`"YOUR DOCUMENTS DIRECTORY"` in de volgende code met het daadwerkelijke pad naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 3: Kopieer en open het PDF-document

Nu gaan we het PDF-document kopiëren en openen dat ondertekend moet worden met behulp van de volgende code:

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Een handtekeningveld maken
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Selecteer het certificaat in de winkel
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Maak een externe handtekening met de benodigde informatie
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

## Stap 4: Handtekening verifiëren

 Ten slotte verifiëren we de handtekening van het ondertekende PDF-bestand met behulp van de`PdfFileSignature` klasse. We krijgen de handtekeningnamen en controleren ze één voor één. Als een handtekening de verificatie niet doorstaat, wordt er een uitzondering gegenereerd. Hier is de bijbehorende code:

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

### Voorbeeldbroncode voor Sign With Smart Card Using Signature Field met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Ondertekenen met certificaatselectie in het Windows-certificaatarchief
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Handmatig het certificaat in de winkel gekozen
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

## Conclusie

Gefeliciteerd! U hebt nu een stapsgewijze handleiding voor het ondertekenen van een PDF-bestand met een smartcard met behulp van een handtekeningveld met Aspose.PDF voor .NET. U kunt deze code gebruiken om veilige digitale handtekeningen toe te voegen aan uw PDF-documenten.

Raadpleeg de officiële Aspose.PDF-documentatie voor meer informatie over geavanceerde functies voor digitale handtekeningen en certificaatbeheer.

### Veelgestelde vragen

#### V: Wat is het voordeel van het gebruik van een handtekeningveld voor digitale ondertekening met een smartcard?

A: Het gebruik van een handtekeningveld voor digitale ondertekening met een smartcard biedt een aangewezen gebied binnen de PDF waar de handtekening wordt toegepast. Dit verbetert de duidelijkheid van het document en garandeert de authenticiteit van de handtekening.

#### V: Hoe faciliteert de Aspose.PDF voor .NET-bibliotheek digitale ondertekening op basis van smartcards met een handtekeningveld?

A: Aspose.PDF voor .NET vereenvoudigt het proces van het maken van een handtekeningveld, het selecteren van een smartcardcertificaat en het toepassen van een digitale handtekening op een specifiek gebied in het PDF-document.

#### V: Waarom is het selecteren van een specifiek certificaat belangrijk voor smartcard-gebaseerde ondertekening?

A: Door een specifiek certificaat te selecteren, kunt u de ondertekenaar op unieke wijze identificeren en de integriteit van de handtekening garanderen. Dit helpt vertrouwen en naleving van digitale ondertekeningsnormen te creëren.

#### V: Hoe verwerkt de meegeleverde broncode het op smartcards gebaseerde ondertekeningsproces met een handtekeningveld?

A: De broncode laat zien hoe u een handtekeningveld maakt, een smartcardcertificaat selecteert en een digitale handtekening met specifieke ondertekeningsinformatie toepast. Het laat ook zien hoe u de geldigheid van de handtekening verifieert.

#### V: Kan ik het uiterlijk van het handtekeningveld aanpassen?

A: Ja, u kunt het uiterlijk van het handtekeningveld aanpassen, zoals de grootte, positie en visuele weergave, zodat het aansluit bij de lay-out van uw document.

#### V: Wat gebeurt er als een handtekening tijdens de verificatiestap niet wordt geverifieerd?

A: Als een handtekening de verificatie niet doorstaat, wordt er een uitzondering gegenereerd die aangeeft dat de handtekening niet geldig is. Dit zorgt ervoor dat alleen geldige en vertrouwde handtekeningen worden geaccepteerd.

#### V: Kan ik meerdere handtekeningvelden en smartcard-gebaseerde handtekeningen op één PDF-document toepassen?

A: Absoluut. U kunt meerdere handtekeningvelden en smartcard-gebaseerde handtekeningen toepassen op verschillende delen van hetzelfde PDF-document, waardoor u meerdere beveiligingslagen creëert.

#### V: Hoe verbetert het gebruik van een handtekeningveld het algehele documentondertekeningsproces?

A: Door een handtekeningveld te gebruiken, wordt het ondertekeningsproces van documenten gestroomlijnd. Het veld helpt de ondertekenaar bij het plaatsen van zijn handtekening op een aangewezen plek. Hierdoor wordt het ondertekeningsproces overzichtelijker en gebruiksvriendelijker.

#### V: Zijn er beperkingen aan het gebruik van handtekeningvelden bij het ondertekenen met smartcards?

A: Er zijn geen inherente beperkingen aan het gebruik van handtekeningvelden met smartcard-gebaseerde ondertekening. Het is echter belangrijk om ervoor te zorgen dat de gekozen locatie van het handtekeningveld geen belangrijke documentinhoud verbergt.

#### V: Waar kan ik verdere hulp of ondersteuning vinden voor het implementeren van smartcard-gebaseerde ondertekening met een handtekeningveld?

A: Voor aanvullende begeleiding en ondersteuning kunt u terecht in de officiële Aspose.PDF-documentatie en communityforums. Deze bieden waardevolle inzichten en oplossingen voor het implementeren van veilige digitale handtekeningen.