---
title: Digitaal ondertekenen met tijdstempel in PDF-bestand
linktitle: Digitaal ondertekenen met tijdstempel in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een digitale handtekening met tijdstempel in een PDF-bestand kunt uitvoeren met Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
In deze zelfstudie leiden we u door het proces van het digitaal ondertekenen van een PDF-bestand met tijdstempel met behulp van Aspose.PDF voor .NET. De digitale handtekening met tijdstempel garandeert de authenticiteit en integriteit van het document, door toevoeging van een elektronische vingerafdruk met tijdstempel.

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
```

## Stap 3: Digitale handtekening met tijdstempel

De eerste stap is het uitvoeren van de digitale handtekening met tijdstempel op het PDF-bestand. De meegeleverde code laat zien hoe u deze handtekening kunt bereiken met Aspose.PDF voor .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Deze code laadt een PDF-bestand, creëert een digitale handtekening met tijdstempel met behulp van een PFX-bestand (privésleutel) en de opgegeven tijdstempelparameters. De handtekening wordt vervolgens aan het PDF-bestand toegevoegd en opgeslagen met het achtervoegsel "_uit".

### Voorbeeldbroncode voor digitaal ondertekenen met tijdstempel met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // Gebruiker/wachtwoord kan worden weggelaten
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Maak een van de drie handtekeningtypen
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Sla het uitvoer-PDF-bestand op
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusie

Gefeliciteerd! U hebt met succes een digitale handtekening met tijdstempel op een PDF-bestand uitgevoerd met behulp van Aspose.PDF voor .NET. In deze zelfstudie werd het stapsgewijze proces behandeld, van het maken van de handtekening tot het opslaan van het bijgewerkte PDF-bestand. U kunt deze functie nu gebruiken om digitale handtekeningen met tijdstempel aan uw PDF-bestanden toe te voegen.

### Veelgestelde vragen over digitaal ondertekenen met tijdstempel in PDF-bestand

#### Vraag: Wat is het doel van digitaal ondertekenen met een tijdstempel?

A: Digitaal ondertekenen met een tijdstempel voegt een elektronische vingerafdruk met een tijdstempel toe aan een PDF-bestand, waardoor de authenticiteit en integriteit van het document op een specifiek tijdstip wordt gegarandeerd.

#### Vraag: Welke vereisten zijn nodig om deze zelfstudie te starten?

A: Zorg ervoor dat u, voordat u begint, een basiskennis heeft van de programmeertaal C#, dat Visual Studio is geïnstalleerd en dat de Aspose.PDF-bibliotheek voor .NET is geïnstalleerd.

#### Vraag: Hoe kan ik mijn ontwikkelomgeving instellen?

A: Volg de aangegeven stappen om uw ontwikkelomgeving in te stellen, inclusief het maken van een nieuw C#-project in Visual Studio en het importeren van de benodigde naamruimten.

#### Vraag: Hoe voeg ik een digitale handtekening met een tijdstempel toe aan een PDF?

A: De meegeleverde voorbeeldcode laat zien hoe u een PDF-bestand laadt, een digitale handtekening met een tijdstempel maakt met behulp van een PFX-bestand (privésleutel) en gespecificeerde tijdstempelinstellingen, de handtekening aan het PDF-bestand toevoegt en het bijgewerkte bestand opslaat.

#### Vraag: Wat is een PFX-bestand en waarom wordt het in het voorbeeld gebruikt?

A: Een PFX-bestand (Personal Exchange Format) bevat een privésleutel en certificaat. Het wordt hier gebruikt om cryptografische functionaliteit voor digitale handtekeningen te bieden. Zorg ervoor dat u de tijdelijke aanduiding vervangt door uw PFX-bestand en wachtwoord.

#### Vraag: Wat zijn tijdstempelinstellingen?

A: TimestampSettings definieert de instellingen voor de tijdstempelserver die wordt gebruikt om de elektronische tijdstempel aan de handtekening toe te voegen. Het bevat de tijdstempelserver-URL en optionele gebruikersreferenties.

#### Vraag: Kan ik een andere tijdstempelserver gebruiken dan die in het voorbeeld?
 A: Ja, u kunt elke compatibele tijdstempelserver gebruiken. Vervang de URL en geef, indien nodig, de juiste gebruikersreferenties op in het`TimestampSettings` voorwerp.

#### Vraag: Wat is het doel van het specificeren van de handtekeningrechthoek?

A: De handtekeningrechthoek definieert de positie en afmetingen van de weergave van de digitale handtekening op de PDF-pagina. Pas deze waarden aan om de handtekening naar wens te positioneren.

#### Vraag: Wat gebeurt er als de tijdstempelserver niet beschikbaar is tijdens het ondertekenen?

A: Als de tijdstempelserver tijdens het ondertekenen niet beschikbaar is, kan het proces mislukken of langer duren. Zorg ervoor dat uw tijdstempelserver betrouwbaar en toegankelijk is.

#### Vraag: Hoe kan ik de aanwezigheid van een tijdstempel in de ondertekende PDF verifiëren?

 A: U kunt de ondertekende PDF bekijken met behulp van de meegeleverde voorbeeldcode. De`TimestampSettings` die u tijdens het ondertekenen hebt gebruikt, moet beschikbaar zijn in de handtekeninggegevens.

#### Vraag: Zijn digitale handtekeningen met tijdstempels juridisch bindend?

A: Digitale handtekeningen met tijdstempels hebben in veel rechtsgebieden juridische waarde en worden vaak als betrouwbaarder beschouwd dan eenvoudige digitale handtekeningen. Raadpleeg juridische experts in uw rechtsgebied voor specifieke regelgeving.

#### Vraag: Kan ik meerdere digitale handtekeningen met tijdstempels aan een PDF toevoegen?

A: Ja, u kunt meerdere digitale handtekeningen met tijdstempels aan een PDF-bestand toevoegen door het proces voor het maken van handtekeningen meerdere keren aan te roepen. Elke handtekening heeft zijn eigen tijdstempel.