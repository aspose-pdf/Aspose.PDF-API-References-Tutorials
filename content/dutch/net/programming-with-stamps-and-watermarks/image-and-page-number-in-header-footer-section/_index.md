---
title: Afbeelding en paginanummer in koptekst-voettekstsectie
linktitle: Afbeelding en paginanummer in koptekst-voettekstsectie
second_title: Aspose.PDF voor .NET API-referentie
description: Ontdek hoe u met Aspose een afbeelding en een paginanummer toevoegt aan de kop- en voettekst van een PDF-document.
type: docs
weight: 110
url: /nl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
In deze tutorial laten we je stap voor stap zien hoe je een afbeelding en paginanummer toevoegt aan de header- en footersectie van een PDF-document met Aspose.PDF voor .NET. We laten je zien hoe je de meegeleverde C#-broncode gebruikt om een pagina te maken, header en footer in te stellen, een afbeelding toe te voegen aan de header en tekst met paginanummer aan de PDF-documentfooter.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET is gedownload en wordt in uw project gebruikt.

## Stap 2: Het PDF-document en de pagina maken

De eerste stap is het maken van een nieuw Document-object en een pagina in het PDF-document. Dit doet u als volgt:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Een nieuw Document-object maken
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Een pagina in het document maken
Aspose.Pdf.Page page = doc.Pages.Add();
```

De bovenstaande code maakt een nieuw Document-object en een lege pagina in het PDF-document.

## Stap 3: De header met een afbeelding toevoegen

Nu de pagina is gemaakt, kunnen we een headersectie met een afbeelding toevoegen. Dit is hoe:

```csharp
// Een headersectie maken
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// De paginakoptekst instellen
page. Header = header;

// Een afbeeldingsobject maken
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Afbeeldingspad instellen
image1.File = dataDir + "aspose-logo.jpg";

// Voeg de afbeelding toe aan de paginakoptekst van het PDF-document
header.Paragraphs.Add(image1);
```

Met de bovenstaande code wordt een headersectie gemaakt, wordt de paginaheader met deze sectie ingesteld en wordt er een afbeelding aan de header toegevoegd.

## Stap 4: De voettekst met het paginanummer toevoegen

Nu de header is toegevoegd, kunnen we een footersectie met een paginanummer toevoegen. Dit is hoe:

```csharp
// Maak een voettekstsectie
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Definieer de voettekst van het PDF-document
page. Footer = footer;

// Een TextFragment-object maken
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Voeg de tekst met het paginanummer toe aan de voettekst van het PDF-document
footer.Paragraphs.Add(txt);
```

De bovenstaande code maakt een voettekstsectie, stelt de voettekst van de pagina in met deze sectie en voegt een TextFragment toe met de tekst "Pagina: ($p van $P )"

  die het paginanummer weergeeft.

## Stap 5: Het gewijzigde PDF-document opslaan

Zodra de header en footer zijn toegevoegd, kunnen we het aangepaste PDF-document opslaan. Dit is hoe:

```csharp
// Sla het gewijzigde PDF-document op
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor Afbeelding en Paginanummer in Koptekst Voettekstsectie met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Een pagina maken in het documentobject
Aspose.Pdf.Page page = doc.Pages.Add();

// Maak een koptekstsectie van het document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de koptekst voor het PDF-bestand in
page.Header = header;

// Een afbeeldingsobject op de pagina maken
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Stel het pad van het afbeeldingsbestand in
image1.File = dataDir + "aspose-logo.jpg";

// Afbeelding toevoegen aan de headerpagina van het PDF-bestand
header.Paragraphs.Add(image1);

//Maak een voettekstsectie van het document
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Stel de voettekst van het PDF-bestand in
page.Footer = footer;

// Een tekstobject maken
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Voeg tekst toe aan de koptekstsectie van het PDF-bestand
footer.Paragraphs.Add(txt);

// Sla het PDF-bestand op
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een afbeelding en paginanummer toevoegt aan de kop- en voettekstsectie van een PDF-document met Aspose.PDF voor .NET. U kunt deze methode nu gebruiken om de kop- en voettekst in uw PDF-documenten aan te passen.

### Veelgestelde vragen

#### V: Wat is het doel van het toevoegen van een afbeelding en een paginanummer in de kop- en voettekst van een PDF-document?

A: Het toevoegen van een afbeelding en paginanummer in de kop- en voettekstsectie van een PDF-document kan de visuele aantrekkingskracht, branding en navigatie-elementen ervan verbeteren. Een afbeelding kan een logo, watermerk of een grafisch element vertegenwoordigen, terwijl een paginanummer gebruikers helpt hun voortgang bij te houden en specifieke pagina's te vinden.

#### V: Hoe helpt de meegeleverde C#-broncode bij het toevoegen van een afbeelding en een paginanummer aan de kop- en voettekst van een PDF-document?

A: De meegeleverde code laat zien hoe u een PDF-document maakt, een pagina toevoegt en vervolgens de header- en footersecties aanpast. Het laat zien hoe u een afbeelding aan de header toevoegt en een tekstfragment met paginanummering aan de footer.

#### V: Kan ik elk afbeeldingsformaat gebruiken voor de header en hoe geef ik het pad op?

 A: Ja, u kunt verschillende afbeeldingsformaten (zoals JPEG, PNG, GIF, etc.) gebruiken voor de headerafbeelding. Het pad van de afbeelding wordt opgegeven met behulp van de`File` eigendom van de`Aspose.Pdf.Image` voorwerp.

#### V: Hoe pas ik het uiterlijk en de positie van de afbeelding in de headersectie aan?

 A: U kunt het uiterlijk en de positionering van de afbeelding aanpassen door de eigenschappen van de afbeelding aan te passen.`Aspose.Pdf.Image` object voordat u het toevoegt aan de headersectie. U kunt bijvoorbeeld de afmetingen, uitlijning, rotatie, dekking, etc. van de afbeelding instellen.

####  V: Wat is het doel van de`TextFragment` object used for the footer?

 A: De`TextFragment` object wordt gebruikt om tekst te maken en op te maken die in de voettekstsectie wordt weergegeven. In de meegeleverde code wordt het gebruikt om het paginanummer en het totale aantal pagina's weer te geven.

#### V: Kan ik de voettekst aanpassen om extra informatie of opmaak toe te voegen?

 A: Ja, u kunt de voettekst wijzigen door de inhoud van de`TextFragment` object. U kunt extra tekst toevoegen, lettertypen, kleuren en opmaak wijzigen volgens uw vereisten.

#### V: Kan ik verschillende kop- en voettekstinhoud toepassen op verschillende pagina's van het PDF-document?

 A: Ja, u kunt verschillende kop- en voettekstinhoud op verschillende pagina's toepassen door afzonderlijke`HeaderFooter` objecten en deze toewijzen aan specifieke pagina's met behulp van de`Header` En`Footer` eigenschappen van de`Aspose.Pdf.Page` voorwerp.

#### V: Hoe kan ik de kop- en voettekst verder aanpassen, bijvoorbeeld door het lettertype te wijzigen of extra elementen toe te voegen?

A: U kunt de header en footer aanpassen met behulp van verschillende klassen en eigenschappen die worden geleverd door Aspose.PDF voor .NET. U kunt bijvoorbeeld verschillende tekstopmaakopties gebruiken, meer alinea's, afbeeldingen of zelfs tabellen toevoegen aan de header- en footersecties.

#### V: Kan ik de kop- en voettekstsecties indien nodig verwijderen of wissen?

A: Ja, u kunt de kop- en voettekstsecties verwijderen of wissen door de`Header` En`Footer` eigenschappen van de`Aspose.Pdf.Page` bezwaar maken tegen`null`.

#### V: Hoe kan ik ervoor zorgen dat de toegevoegde afbeelding en het paginanummer consistent blijven op verschillende apparaten en kijkers?

A: Aspose.PDF voor .NET biedt functionaliteit voor het maken van gestandaardiseerde en consistente PDF-documenten. Zo weet u zeker dat de toegevoegde afbeelding en het paginanummer consistent worden weergegeven op verschillende apparaten en PDF-viewers.