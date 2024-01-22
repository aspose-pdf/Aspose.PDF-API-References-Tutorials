---
title: Digitaal inloggen in PDF-bestand
linktitle: Digitaal inloggen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u digitaal een PDF-bestand kunt ondertekenen met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-security-and-signatures/digitally-sign/
---
In deze zelfstudie leiden we u door het proces van het digitaal ondertekenen van een PDF-bestand met Aspose.PDF voor .NET. De digitale handtekening garandeert de authenticiteit en integriteit van het document, door het toevoegen van een unieke elektronische vingerafdruk.

## Stap 1: Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#
- Visual Studio op uw computer installeren
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd

## Stap 2: Omgevingsconfiguratie

Om aan de slag te gaan, volgt u deze stappen om uw ontwikkelomgeving in te stellen:

1. Open Visual Studio en maak een nieuw C#-project.
2. Importeer de vereiste naamruimten in uw codebestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Stap 3: Digitale handtekening

De eerste stap is het digitaal ondertekenen van het PDF-bestand. De meegeleverde code laat zien hoe u een digitale handtekening kunt maken met Aspose.PDF voor .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Deze code laadt een PDF-bestand, creëert een digitale handtekening met een bepaald uiterlijk en slaat vervolgens het PDF-bestand op met de toegevoegde handtekening.

## Stap 4: Handtekeningverificatie

Na het toevoegen van de digitale handtekening kunt u controleren of het PDF-bestand een geldige handtekening bevat.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Doe iets
                     }
                 }
             }
         }
     }
}
```

Deze code verifieert de eerste handtekening van het PDF-bestand en voert aanvullende acties uit als de handtekening gecertificeerd is en specifieke machtigingen heeft.

### Voorbeeldbroncode voor digitaal ondertekenen met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Gebruik PKCS7/PKCS7Detached-objecten
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Stel het kenmerkende uiterlijk in
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Maak een van de drie handtekeningtypen
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Sla het uitvoer-PDF-bestand op
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Eventuele handtekeningen?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Controleer de eerste
				{
					if (signature.IsCertified) // Gecertificeerd?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Krijg toegangsrechten
						{
							// Doe iets
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

Gefeliciteerd! U hebt met succes een digitale handtekening op een PDF-bestand uitgevoerd met Aspose.PDF voor .NET. In deze tutorial werd het stapsgewijze proces behandeld, van het toevoegen van de digitale handtekening tot het verifiëren van de geldigheid ervan. U kunt deze functie nu gebruiken om uw PDF-bestanden te beveiligen met digitale handtekeningen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial?

A: Deze tutorial leidt u door het proces van het digitaal ondertekenen van een PDF-bestand met Aspose.PDF voor .NET. Digitale handtekeningen voegen een elektronische vingerafdruk toe om de authenticiteit en integriteit van het document te garanderen.

#### Vraag: Welke vereisten zijn vereist voordat u begint?

A: Zorg ervoor dat u, voordat u begint, een basiskennis heeft van de programmeertaal C#, dat Visual Studio is geïnstalleerd en dat de Aspose.PDF-bibliotheek voor .NET is geïnstalleerd.

#### Vraag: Hoe richt ik de ontwikkelomgeving in?

A: Volg de aangegeven stappen om uw ontwikkelomgeving in te stellen, inclusief het maken van een nieuw C#-project in Visual Studio en het importeren van de vereiste naamruimten.

#### Vraag: Hoe voeg ik een digitale handtekening toe aan een PDF-bestand?

 A: De meegeleverde voorbeeldcode laat zien hoe u een PDF-bestand laadt, een digitale handtekening maakt, het uiterlijk specificeert en het ondertekende PDF-bestand opslaat. De digitale handtekening wordt toegevoegd met behulp van de`Certify` werkwijze van de`PdfFileSignature` voorwerp.

#### Vraag: Hoe verifieer ik de geldigheid van een digitale handtekening?

A: Nadat u de digitale handtekening hebt toegevoegd, kunt u de voorbeeldcode gebruiken om de geldigheid van de handtekening te verifiëren. Het controleert of de handtekening gecertificeerd is en specifieke toegangsrechten heeft.

####  Vraag: Wat doet de`PKCS7` object represent?

 EEN: De`PKCS7` object wordt gebruikt om de cryptografische functionaliteit voor digitale handtekeningen te bieden. Het wordt gebruikt om de digitale handtekening in de meegeleverde voorbeeldcode te creëren.

#### Vraag: Kan ik het uiterlijk van de digitale handtekening aanpassen?

 A: Ja, u kunt het uiterlijk van de digitale handtekening aanpassen door het pad naar een afbeelding op te geven in het`SignatureAppearance` eigendom van de`PdfFileSignature` voorwerp.

#### Vraag: Wat gebeurt er als de handtekening niet geldig is?

A: Als de handtekening niet geldig is, mislukt het verificatieproces en worden de bijbehorende acties binnen het verificatiecodeblok niet uitgevoerd.

#### Vraag: Hoe kan ik de veiligheid van mijn digitale handtekeningen garanderen?

A: Digitale handtekeningen zijn door hun ontwerp veilig en maken gebruik van cryptografische technieken om de authenticiteit en integriteit te garanderen. Zorg ervoor dat u uw privésleutel veilig houdt en volg de best practices voor het omgaan met digitale handtekeningen.

#### Vraag: Kan ik meerdere digitale handtekeningen aan een PDF toevoegen?

 A: Ja, u kunt meerdere digitale handtekeningen toevoegen aan een PDF-bestand met behulp van de`PdfFileSignature` voorwerpen`Sign` of`Certify` methoden. Elke handtekening heeft zijn eigen uiterlijk en configuratie.