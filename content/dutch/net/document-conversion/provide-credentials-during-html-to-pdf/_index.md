---
title: Geef referenties op tijdens HTML naar PDF
linktitle: Geef referenties op tijdens HTML naar PDF
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het converteren van HTML naar PDF door inloggegevens op te geven bij Aspose.PDF voor .NET.
type: docs
weight: 240
url: /nl/net/document-conversion/provide-credentials-during-html-to-pdf/
---
In deze zelfstudie leiden we u door het proces van het converteren van een HTML-bestand naar PDF, terwijl we inloggegevens verstrekken bij het openen van een beveiligde URL met Aspose.PDF voor .NET. Door de onderstaande stappen te volgen, kunt u HTML-inhoud naar PDF converteren met de juiste inloggegevens.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: Haal beveiligde HTML-inhoud op
In deze stap halen we beveiligde HTML-inhoud op van een URL met behulp van de juiste inloggegevens. Gebruik de volgende code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak een verzoek voor de URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Stel indien nodig voor de server de inloggegevens in.
request.Credentials = CredentialCache.DefaultCredentials;
// Ontvang het antwoord.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Haal de stream op met de inhoud die door de server wordt geretourneerd.
Stream dataStream = response. GetResponseStream();
// Open de stream met een StreamReader voor gemakkelijke toegang.
StreamReader reader = new StreamReader(dataStream);
// Lees de inhoud.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waarin u het resulterende PDF-bestand wilt opslaan.

## Stap 2: Converteer HTML naar PDF door inloggegevens op te geven
Nu zullen we de opgehaalde HTML-inhoud laden en deze naar PDF-formaat converteren, terwijl we de juiste inloggegevens opgeven. Gebruik de volgende code:

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://Mijn.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Laad het HTML-bestand
Document pdfDocument = new Document(stream, options);
```

## Stap 3: Het resulterende PDF-bestand opslaan
Ten slotte slaan we het resulterende PDF-bestand op. Gebruik de volgende code:

```csharp
// Sla het resulterende PDF-bestand op
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 De bovenstaande code slaat het resulterende PDF-bestand op met de bestandsnaam`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Voorbeeldbroncode voor het verstrekken van referenties tijdens HTML naar PDF met behulp van Aspose.PDF voor .NET

```csharp
try
{
	
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Maak een verzoek voor de URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Indien vereist door de server, stelt u de inloggegevens in.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Ontvang het antwoord.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Haal de stream met inhoud op die door de server wordt geretourneerd.
	Stream dataStream = response.GetResponseStream();
	// Open de stream met een StreamReader voor gemakkelijke toegang.
	StreamReader reader = new StreamReader(dataStream);
	// Lees de inhoud.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// Mijn.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// HTML-bestand laden
	Document pdfDocument = new Document(stream, options);
	// Sla het resulterende bestand op
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces besproken van het converteren van een HTML-bestand naar PDF, terwijl we inloggegevens verstrekten bij het openen van een beveiligde URL met Aspose.PDF voor .NET. Door de hierboven beschreven instructies te volgen, kunt u HTML-inhoud met succes naar PDF converteren terwijl u de juiste inloggegevens verstrekt.

### Veelgestelde vragen

#### Vraag: Wat is Aspose.PDF voor .NET?

A: Aspose.PDF voor .NET is een robuuste bibliotheek waarmee ontwikkelaars met PDF-documenten in C#-toepassingen kunnen werken. Het biedt een breed scala aan functionaliteiten, waaronder conversie van HTML naar PDF.

#### Vraag: Hoe kan ik beveiligde HTML-inhoud ophalen van een URL?

 A: Om beveiligde HTML-inhoud van een URL op te halen, kunt u de`WebRequest` klasse in C#. Zorg ervoor dat u de juiste inloggegevens instelt met behulp van de`Credentials` eigendom.

#### Vraag: Wat zijn de vereisten voor deze zelfstudie?

A: Voordat u doorgaat met de zelfstudie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

#### Vraag: Hoe gaat Aspose.PDF voor .NET om met externe bronnen tijdens het converteren van HTML naar PDF?

 A: Aspose.PDF voor .NET biedt de`HtmlLoadOptions`klasse om externe bronnen te verwerken tijdens de conversie van HTML naar PDF. U kunt de referenties voor externe bronnen instellen met behulp van de`ExternalResourcesCredentials` eigendom.

#### Vraag: Kan ik de bestandsnaam voor het resulterende PDF-bestand aanpassen?

 A: Ja, u kunt de bestandsnaam voor het resulterende PDF-bestand aanpassen door de code te wijzigen waarmee het PDF-document wordt opgeslagen. Wijzig eenvoudig de gewenste bestandsnaam in het`pdfDocument.Save()` methode.