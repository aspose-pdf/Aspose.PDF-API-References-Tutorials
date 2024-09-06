---
title: Digitaal ondertekenen met tijdstempel in PDF-bestand
linktitle: Digitaal ondertekenen met tijdstempel in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een digitale handtekening met tijdstempel in een PDF-bestand kunt maken met Aspose.PDF voor .NET.
type: docs
weight: 50
url: /nl/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
In deze tutorial leiden we u door het proces van het digitaal ondertekenen van een PDF-bestand met tijdstempel met behulp van Aspose.PDF voor .NET. De digitale handtekening met tijdstempel garandeert de authenticiteit en integriteit van het document door een elektronische vingerafdruk met een tijdstempel toe te voegen.

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
```

## Stap 3: Digitale handtekening met tijdstempel

De eerste stap is om de digitale handtekening met tijdstempel op het PDF-bestand uit te voeren. De meegeleverde code laat zien hoe u deze handtekening kunt bereiken met Aspose.PDF voor .NET.

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

Deze code laadt een PDF-bestand, maakt een digitale handtekening met tijdstempel met behulp van een PFX-bestand (private key) en de opgegeven tijdstempelparameters. De handtekening wordt vervolgens toegevoegd aan het PDF-bestand en opgeslagen met het achtervoegsel "_uit".

### Voorbeeldbroncode voor Digitaal ondertekenen met tijdstempel met behulp van Aspose.PDF voor .NET 
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
		// Opslaan uitvoer PDF-bestand
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusie

Gefeliciteerd! U hebt met succes een digitale handtekening met tijdstempel op een PDF-bestand uitgevoerd met Aspose.PDF voor .NET. Deze tutorial behandelde het stapsgewijze proces van het maken van de handtekening tot het opslaan van het bijgewerkte PDF-bestand. U kunt deze functie nu gebruiken om digitale handtekeningen met tijdstempel toe te voegen aan uw PDF-bestanden.

### FAQ's voor digitaal ondertekenen met tijdstempel in PDF-bestand

#### V: Wat is het doel van digitaal ondertekenen met een tijdstempel?

A: Als u digitaal ondertekent met een tijdstempel, wordt er een elektronische vingerafdruk met tijdstempel aan een PDF-bestand toegevoegd. Zo wordt de authenticiteit en integriteit van het document op een bepaald moment gegarandeerd.

#### V: Welke vereisten zijn er nodig om met deze tutorial te kunnen beginnen?

A: Voordat u begint, moet u ervoor zorgen dat u een basiskennis hebt van de programmeertaal C#, dat u Visual Studio hebt geïnstalleerd en dat u de Aspose.PDF-bibliotheek voor .NET hebt geïnstalleerd.

#### V: Hoe kan ik mijn ontwikkelomgeving instellen?

A: Volg de onderstaande stappen om uw ontwikkelomgeving in te stellen, waaronder het maken van een nieuw C#-project in Visual Studio en het importeren van de benodigde naamruimten.

#### V: Hoe voeg ik een digitale handtekening met tijdstempel toe aan een PDF?

A: De meegeleverde voorbeeldcode laat zien hoe u een PDF-bestand laadt, een digitale handtekening met een tijdstempel maakt met behulp van een PFX-bestand (privésleutel) en opgegeven tijdstempelinstellingen, de handtekening aan het PDF-bestand toevoegt en het bijgewerkte bestand opslaat.

#### V: Wat is een PFX-bestand en waarom wordt het in het voorbeeld gebruikt?

A: Een PFX-bestand (Personal Exchange Format) bevat een privésleutel en certificaat. Het wordt hier gebruikt om cryptografische functionaliteit te bieden voor digitale handtekeningen. Zorg ervoor dat u de tijdelijke aanduiding vervangt door uw PFX-bestand en wachtwoord.

#### V: Wat zijn TimestampSettings?

A: TimestampSettings definieert de instellingen voor de timestampserver die wordt gebruikt om de elektronische timestamp toe te voegen aan de handtekening. Het omvat de timestampserver-URL en optionele gebruikersreferenties.

#### V: Kan ik een andere tijdstempelserver gebruiken dan die in het voorbeeld?
 A: Ja, u kunt elke compatibele timestamp-server gebruiken. Vervang de URL en geef indien nodig de juiste gebruikersreferenties op in de`TimestampSettings` voorwerp.

#### V: Wat is het doel van het specificeren van de handtekeningrechthoek?

A: De handtekeningrechthoek definieert de positie en afmetingen van de digitale handtekeningweergave op de PDF-pagina. Pas deze waarden aan om de handtekening naar wens te positioneren.

#### V: Wat gebeurt er als de tijdstempelserver niet beschikbaar is tijdens het ondertekenen?

A: Als de timestampserver niet beschikbaar is tijdens het ondertekenen, kan het proces mislukken of langer duren. Zorg ervoor dat uw timestampserver betrouwbaar en toegankelijk is.

#### V: Hoe kan ik controleren of er een tijdstempel in het ondertekende PDF-bestand staat?

 A: U kunt de ondertekende PDF bekijken met behulp van de meegeleverde voorbeeldcode.`TimestampSettings` De gegevens die u tijdens het ondertekenen hebt gebruikt, moeten beschikbaar zijn in de handtekeningdetails.

#### V: Zijn digitale handtekeningen met tijdstempels juridisch bindend?

A: Digitale handtekeningen met tijdstempels hebben juridische waarde in veel rechtsgebieden en worden vaak als betrouwbaarder beschouwd dan eenvoudige digitale handtekeningen. Raadpleeg juridische experts in uw rechtsgebied voor specifieke regelgeving.

#### V: Kan ik meerdere digitale handtekeningen met tijdstempels aan een PDF toevoegen?

A: Ja, u kunt meerdere digitale handtekeningen met tijdstempels toevoegen aan een PDF-bestand door het handtekeningcreatieproces meerdere keren aan te roepen. Elke handtekening heeft zijn eigen tijdstempel.