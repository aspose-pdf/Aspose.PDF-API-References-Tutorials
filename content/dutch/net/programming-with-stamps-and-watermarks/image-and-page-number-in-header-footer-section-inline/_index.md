---
title: Afbeelding en paginanummer in koptekst-voettekstsectie Inline
linktitle: Afbeelding en paginanummer in koptekst-voettekstsectie Inline
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een afbeelding en paginanummer kunt toevoegen aan de kop- en voettekst met behulp van inline alinea's met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
In deze zelfstudie begeleiden we u stap voor stap bij het toevoegen van een afbeelding en paginanummer in het kop- en voettekstgedeelte van een PDF-document met behulp van Aspose.PDF voor .NET. We zullen de meegeleverde C#-broncode gebruiken om een pagina te maken, de kop- en voettekst in te stellen, afbeeldingen en tekst toe te voegen met behulp van inline alinea's in de kop van het PDF-document.

## Stap 1: De omgeving instellen

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een geïnstalleerde .NET-ontwikkelomgeving.
- De Aspose.PDF-bibliotheek voor .NET gedownload en waarnaar wordt verwezen in uw project.

## Stap 2: Het PDF-document en de pagina maken

De eerste stap is het maken van een nieuw documentobject en een pagina in het PDF-document. Hier is hoe:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak een nieuw Document-object
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Maak een pagina in het document
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Met de bovenstaande code wordt een nieuw documentobject en een lege pagina in het PDF-document gemaakt.

## Stap 3: De header toevoegen met een afbeelding en inline tekst

Nu de pagina is gemaakt, kunnen we een koptekstgedeelte toevoegen met een afbeelding en tekst met behulp van inline alinea's. Hier is hoe:

```csharp
// Maak een kopsectie
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de paginakop in
page. Header = header;

// Maak een TextFragment-object voor de eerste inlinetekst
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

// Maak een tweede inlinetekst
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Voeg items toe aan de kop
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

De bovenstaande code maakt een koptekstsectie, stelt de paginakop in met deze sectie, voegt een TextFragment toe met inline tekst en een inline Image-object.

## Stap 4: Het gewijzigde PDF-document opslaan

Zodra de koptekst met de afbeelding en inline tekst is toegevoegd, kunnen we het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het gewijzigde PDF-document op
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor afbeelding en paginanummer in koptekst-voettekstsectie Inline met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer een Document-object door de lege constructor ervan aan te roepen
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Maak een pagina in het Pdf-object
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Maak een koptekstsectie van het document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de koptekst voor het PDF-bestand in
page.Header = header;

// Maak een tekstobject
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Geef de kleur op
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Maak een afbeeldingsobject in de sectie
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Stel het pad van het afbeeldingsbestand in
image1.File = dataDir + "aspose-logo.jpg";

// Stel de afbeeldingsbreedte in. Informatie
image1.FixWidth = 50;
image1.FixHeight = 20;

// Geef aan dat de InlineParagraph van seg1 een afbeelding is.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Bewaar de pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een afbeelding en paginanummer kunt toevoegen aan de kop- en voettekst van een PDF-document met behulp van inline alinea's met Aspose.PDF voor .NET. U kunt nu de kop- en voettekst van uw PDF-documenten flexibel aanpassen.

### Veelgestelde vragen

#### Vraag: Wat is het voordeel van het gebruik van inline alinea's voor het toevoegen van een afbeelding en tekst aan de koptekst van een PDF-document?

A: Door inline alinea's te gebruiken, kunt u afbeeldingen en tekst naadloos in dezelfde alinea integreren, waardoor u nauwkeurige controle krijgt over de plaatsing en opmaak ervan. Deze methode is vooral handig voor het maken van aangepaste kopteksten met visuele elementen.

#### Vraag: Hoe zorgt de meegeleverde C#-broncode voor inline alinea's voor de koptekst in een PDF-document?

A: De meegeleverde code laat zien hoe u een PDF-document kunt maken, een pagina kunt toevoegen en de koptekst kunt aanpassen met behulp van inline-paragrafen. Het voegt een TekstFragment toe met inline tekst, een inline afbeelding en nog een inline TekstFragment.

#### Vraag: Hoe geef ik de kleur van de inlinetekst in de koptekst op?

 A: De kleur van de inlinetekst wordt opgegeven met behulp van de`ForegroundColor` eigendom van de`TextState` van de`TextFragment` voorwerp.

#### Vraag: Kan ik de afmetingen van de inline afbeelding in de header aanpassen?

 A: Ja, u kunt de afmetingen van de inline afbeelding aanpassen met behulp van de`FixWidth` En`FixHeight` eigenschappen van de`Image` voorwerp. Hiermee kunt u de breedte en hoogte van de afbeelding binnen de koptekst bepalen.

#### Vraag: Kan ik extra inline-elementen, zoals hyperlinks of verschillende lettertypestijlen, in de koptekst opnemen?

 A: Ja, u kunt extra inline-elementen in de koptekst opnemen door er meer te maken`TextFragment` of`Image` objecten met de gewenste eigenschappen. Hiermee kunt u de koptekst verder aanpassen, inclusief hyperlinks, verschillende lettertypestijlen of andere visuele elementen.

#### Vraag: Hoe kan ik ervoor zorgen dat de inline afbeelding en tekst correct uitgelijnd en opgemaakt blijven op verschillende apparaten en kijkers?

A: Aspose.PDF voor .NET zorgt ervoor dat inline afbeeldingen en tekst correct worden uitgelijnd en opgemaakt, wat resulteert in een consistente weergave op verschillende apparaten en PDF-viewers.

#### Vraag: Kan ik inline alinea's ook op de voettekst toepassen?

 A: Ja, u kunt dezelfde techniek van het gebruik van inline-paragrafen toepassen op de voettekstsectie door een`Footer` object en voeg er inline-elementen zoals tekst en afbeeldingen aan toe.

#### Vraag: Is het mogelijk om inline alinea's te combineren met andere aanpassingsmethoden voor kop- of voetteksten?

A: Ja, u kunt inline alinea's combineren met andere aanpassingsmethoden voor kop- of voetteksten die worden aangeboden door Aspose.PDF voor .NET om complexere en op maat gemaakte kop- of voettekstontwerpen te maken.

#### Vraag: Kan ik indien nodig de inline-elementen uit de header verwijderen of wissen?

 A: Ja, u kunt de inline-elementen verwijderen of wissen door de inhoud van het`HeaderFooter` object en verwijder de respectieve inline-paragrafen.

#### Vraag: Hoe kan ik inline alinea's toepassen op specifieke pagina's van het PDF-document?

 A: Als u inline-paragrafen op specifieke pagina's wilt toepassen, kunt u afzonderlijke paragrafen maken`HeaderFooter` objecten voor elke pagina en wijs ze toe met behulp van de`Header` eigendom van de betreffende`Aspose.Pdf.Page` voorwerpen.