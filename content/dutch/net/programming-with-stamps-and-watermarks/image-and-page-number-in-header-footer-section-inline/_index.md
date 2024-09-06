---
title: Afbeelding en paginanummer in koptekst-voettekstsectie inline
linktitle: Afbeelding en paginanummer in koptekst-voettekstsectie inline
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeelding en paginanummer toevoegt aan de kop- en voettekst met behulp van inline-alinea's met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
In deze tutorial laten we u stap voor stap zien hoe u een afbeelding en paginanummer toevoegt aan de header- en footersectie van een PDF-document met Aspose.PDF voor .NET. We gebruiken de meegeleverde C#-broncode om een pagina te maken, header en footer in te stellen, afbeeldingen en tekst toe te voegen met behulp van inline-paragrafen in de header van het PDF-document.

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Een pagina in het document maken
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

De bovenstaande code maakt een nieuw Document-object en een lege pagina in het PDF-document.

## Stap 3: De header toevoegen met een afbeelding en inline tekst

Nu de pagina is gemaakt, kunnen we een headersectie met een afbeelding en tekst toevoegen met behulp van inline-paragrafen. Dit is hoe:

```csharp
// Een headersectie maken
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// De paginakoptekst instellen
page. Header = header;

// Maak een TextFragment-object voor de eerste inline-tekst
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Geef tekstkleur op
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Maak een Image-object voor de afbeelding
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Afbeeldingspad instellen
image1.File = dataDir + "aspose-logo.jpg";

// Definieer de afmetingen van de afbeelding
image1.FixWidth = 50;
image1.FixHeight = 20;

// Geef aan dat de eerste inline tekst een afbeelding is
image1.IsInLineParagraph = true;

// Maak een tweede inline tekst
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Items toevoegen aan header
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

De bovenstaande code maakt een headersectie, stelt de paginaheader in met deze sectie, voegt een TextFragment toe met inline tekst en een inline Image-object.

## Stap 4: Het gewijzigde PDF-document opslaan

Zodra de header met de afbeelding en inline tekst is toegevoegd, kunnen we het aangepaste PDF-document opslaan. Dit is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor Afbeelding en Paginanummer in Koptekst Voettekstsectie Inline met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer een Document-object door de lege constructor aan te roepen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Een pagina maken in het Pdf-object
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Maak een koptekstsectie van het document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de koptekst voor het PDF-bestand in
page.Header = header;

// Een tekstobject maken
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Geef de kleur op
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Maak een afbeeldingsobject in de sectie
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Stel het pad van het afbeeldingsbestand in
image1.File = dataDir + "aspose-logo.jpg";

//Stel de afbeeldingbreedte in Informatie
image1.FixWidth = 50;
image1.FixHeight = 20;

// Geeft aan dat de InlineParagraph van seg1 een afbeelding is.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// PDF opslaan
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een afbeelding en paginanummer toevoegt aan de kop- en voettekstsectie van een PDF-document met behulp van inline-paragrafen met Aspose.PDF voor .NET. U kunt nu de kop- en voettekst van uw PDF-documenten flexibel aanpassen.

### Veelgestelde vragen

#### V: Wat is het voordeel van het gebruik van inline-alinea's voor het toevoegen van een afbeelding en tekst aan de koptekst van een PDF-document?

A: Met inline-paragrafen kunt u afbeeldingen en tekst naadloos integreren in dezelfde paragraaf, waardoor u nauwkeurige controle hebt over hun plaatsing en opmaak. Deze methode is vooral handig voor het maken van aangepaste headers met visuele elementen.

#### V: Hoe worden met de meegeleverde C#-broncode inline-paragrafen voor de koptekst in een PDF-document gemaakt?

A: De meegeleverde code laat zien hoe u een PDF-document maakt, een pagina toevoegt en de header aanpast met behulp van inline-paragrafen. Het voegt een TextFragment toe met inline-tekst, een inline-afbeelding en nog een inline TextFragment.

#### V: Hoe geef ik de kleur van de inline tekst in de koptekst op?

 A: De kleur van de inline tekst wordt gespecificeerd met behulp van de`ForegroundColor` eigendom van de`TextState` van de`TextFragment` voorwerp.

#### V: Kan ik de afmetingen van de inline-afbeelding in de header aanpassen?

 A: Ja, u kunt de afmetingen van de inline-afbeelding aanpassen met behulp van de`FixWidth` En`FixHeight` eigenschappen van de`Image` object. Hiermee kunt u de breedte en hoogte van de afbeelding in de header regelen.

#### V: Kan ik extra inline-elementen, zoals hyperlinks of verschillende lettertypen, in de koptekst opnemen?

 A: Ja, u kunt extra inline-elementen in de header opnemen door meer`TextFragment` of`Image` objecten met de gewenste eigenschappen. Hiermee kunt u de header verder aanpassen, inclusief hyperlinks, verschillende lettertypes of andere visuele elementen.

#### V: Hoe kan ik ervoor zorgen dat de inline-afbeelding en tekst op verschillende apparaten en schermen goed uitgelijnd en opgemaakt blijven?

A: Aspose.PDF voor .NET zorgt ervoor dat inline afbeeldingen en tekst correct worden uitgelijnd en opgemaakt, wat resulteert in een consistente weergave op verschillende apparaten en PDF-viewers.

#### V: Kan ik inline-alinea's ook op de voettekst toepassen?

 A: Ja, u kunt dezelfde techniek van het gebruik van inline-alinea's toepassen op de voettekstsectie door een`Footer` object en het toevoegen van inline-elementen zoals tekst en afbeeldingen.

#### V: Is het mogelijk om inline-alinea's te combineren met andere aanpassingsmethoden voor kop- of voetteksten?

A: Ja, u kunt inline-alinea's combineren met andere aanpassingsmethoden voor kop- of voetteksten die Aspose.PDF voor .NET biedt om complexere en op maat gemaakte kop- of voettekstontwerpen te maken.

#### V: Kan ik indien nodig de inline-elementen uit de header verwijderen of wissen?

 A: Ja, u kunt de inline-elementen verwijderen of wissen door de inhoud van de`HeaderFooter`object en het verwijderen van de betreffende inline-alinea's.

#### V: Hoe kan ik inline-alinea's toepassen op specifieke pagina's van het PDF-document?

 A: Om inline-alinea's op specifieke pagina's toe te passen, kunt u afzonderlijke alinea's maken`HeaderFooter` objecten voor elke pagina en wijs ze toe met behulp van de`Header` eigendom van de respectievelijke`Aspose.Pdf.Page` objecten.