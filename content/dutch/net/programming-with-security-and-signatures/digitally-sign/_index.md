---
title: Digitaal aanmelden PDF-bestand
linktitle: Digitaal aanmelden PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een PDF-bestand digitaal kunt ondertekenen met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-security-and-signatures/digitally-sign/
---
In deze tutorial leiden we u door het proces van het digitaal ondertekenen van een PDF-bestand met Aspose.PDF voor .NET. De digitale handtekening garandeert de authenticiteit en integriteit van het document door een unieke elektronische vingerafdruk toe te voegen.

## Stap 1: Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#
- Visual Studio op uw machine installeren
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd

## Stap 2: Omgeving instellen

Om te beginnen volgt u deze stappen om uw ontwikkelomgeving in te stellen:

1. Open Visual Studio en maak een nieuw C#-project.
2. Importeer de vereiste naamruimten in uw codebestand:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## Stap 3: Digitale handtekening

De eerste stap is het digitaal ondertekenen van het PDF-bestand. De meegeleverde code laat zien hoe u een digitale handtekening maakt met Aspose.PDF voor .NET.

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

Deze code laadt een PDF-bestand, maakt een digitale handtekening met een opgegeven uiterlijk en slaat het PDF-bestand vervolgens op met de toegevoegde handtekening.

## Stap 4: Handtekeningverificatie

Nadat u de digitale handtekening hebt toegevoegd, kunt u controleren of het PDF-bestand een geldige handtekening bevat.

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

### Voorbeeldbroncode voor Digitally Sign met Aspose.PDF voor .NET 
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
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // PKCS7/PKCS7Detached-objecten gebruiken
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Uiterlijk van handtekening instellen
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// Maak een van de drie handtekeningtypen
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Opslaan uitvoer PDF-bestand
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Zijn er handtekeningen?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Verifieer de eerste
				{
					if (signature.IsCertified) // Gecertificeerd?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Toegangsmachtiging verkrijgen
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

Gefeliciteerd! U hebt met succes een digitale handtekening op een PDF-bestand uitgevoerd met Aspose.PDF voor .NET. Deze tutorial behandelde het stapsgewijze proces, van het toevoegen van de digitale handtekening tot het verifiëren van de geldigheid ervan. U kunt deze functie nu gebruiken om uw PDF-bestanden te beveiligen met digitale handtekeningen.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial?

A: Deze tutorial begeleidt u door het proces van het digitaal ondertekenen van een PDF-bestand met Aspose.PDF voor .NET. Digitale handtekeningen voegen een elektronische vingerafdruk toe om de authenticiteit en integriteit van het document te garanderen.

#### V: Aan welke voorwaarden moet ik voldoen voordat ik kan beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u een basiskennis hebt van de programmeertaal C#, dat u Visual Studio hebt geïnstalleerd en dat u de Aspose.PDF-bibliotheek voor .NET hebt geïnstalleerd.

#### V: Hoe stel ik de ontwikkelomgeving in?

A: Volg de onderstaande stappen om uw ontwikkelomgeving in te stellen, waaronder het maken van een nieuw C#-project in Visual Studio en het importeren van de vereiste naamruimten.

#### V: Hoe voeg ik een digitale handtekening toe aan een PDF-bestand?

 A: De meegeleverde voorbeeldcode laat zien hoe u een PDF-bestand laadt, een digitale handtekening maakt, het uiterlijk specificeert en het ondertekende PDF-bestand opslaat. De digitale handtekening wordt toegevoegd met behulp van de`Certify` methode van de`PdfFileSignature` voorwerp.

#### V: Hoe verifieer ik de geldigheid van een digitale handtekening?

A: Nadat u de digitale handtekening hebt toegevoegd, kunt u de voorbeeldcode gebruiken om de geldigheid van de handtekening te verifiëren. Het controleert of de handtekening gecertificeerd is en specifieke toegangsrechten heeft.

####  V: Wat betekent de`PKCS7` object represent?

 A: De`PKCS7` object wordt gebruikt om de cryptografische functionaliteit voor digitale handtekeningen te bieden. Het wordt gebruikt om de digitale handtekening te maken in de meegeleverde voorbeeldcode.

#### V: Kan ik het uiterlijk van de digitale handtekening aanpassen?

 A: Ja, u kunt het uiterlijk van de digitale handtekening aanpassen door het pad naar een afbeelding in de`SignatureAppearance` eigendom van de`PdfFileSignature` voorwerp.

#### V: Wat gebeurt er als de handtekening niet geldig is?

A: Als de handtekening niet geldig is, mislukt het verificatieproces en worden de bijbehorende acties in het verificatiecodeblok niet uitgevoerd.

#### V: Hoe kan ik de veiligheid van mijn digitale handtekeningen garanderen?

A: Digitale handtekeningen zijn qua ontwerp veilig en gebruiken cryptografische technieken om authenticiteit en integriteit te garanderen. Zorg ervoor dat u uw privésleutel veilig houdt en volg de best practices voor het omgaan met digitale handtekeningen.

#### V: Kan ik meerdere digitale handtekeningen aan een PDF toevoegen?

 A: Ja, u kunt meerdere digitale handtekeningen aan een PDF-bestand toevoegen met behulp van de`PdfFileSignature` voorwerp`Sign` of`Certify` methoden. Elke handtekening heeft zijn eigen uiterlijk en configuratie.