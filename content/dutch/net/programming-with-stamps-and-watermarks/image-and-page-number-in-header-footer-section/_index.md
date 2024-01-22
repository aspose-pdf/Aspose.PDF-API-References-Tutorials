---
title: Afbeelding en paginanummer in koptekst-voettekstsectie
linktitle: Afbeelding en paginanummer in koptekst-voettekstsectie
second_title: Aspose.PDF voor .NET API-referentie
description: Ontdek hoe u met Aspose een afbeelding en een paginanummer kunt toevoegen aan de kop- en voettekst van een PDF-document.
type: docs
weight: 110
url: /nl/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
In deze zelfstudie laten we u stap voor stap zien hoe u een afbeelding en paginanummer kunt toevoegen aan de kop- en voettekst van een PDF-document met behulp van Aspose.PDF voor .NET. We laten u zien hoe u de meegeleverde C#-broncode kunt gebruiken om een pagina te maken, de kop- en voettekst in te stellen, een afbeelding toe te voegen aan de koptekst en tekst met paginanummer om de voettekst van een PDF te documenteren.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Maak een pagina in het document
Aspose.Pdf.Page page = doc.Pages.Add();
```

Met de bovenstaande code wordt een nieuw documentobject en een lege pagina in het PDF-document gemaakt.

## Stap 3: De header toevoegen met een afbeelding

Nu de pagina is gemaakt, kunnen we een koptekstgedeelte met een afbeelding toevoegen. Hier is hoe:

```csharp
// Maak een kopsectie
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de paginakop in
page. Header = header;

// Maak een afbeeldingsobject
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Afbeeldingspad instellen
image1.File = dataDir + "aspose-logo.jpg";

// Voeg de afbeelding toe aan de paginakop van het PDF-document
header.Paragraphs.Add(image1);
```

De bovenstaande code maakt een koptekstsectie, stelt de paginakoptekst in met deze sectie en voegt een afbeelding toe aan de koptekst.

## Stap 4: Voettekst met paginanummer toevoegen

Nu de koptekst is toegevoegd, kunnen we een voettekstgedeelte met een paginanummer toevoegen. Hier is hoe:

```csharp
// Maak een voettekstsectie
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Definieer de voettekst van het PDF-document
page. Footer = footer;

// Maak een TextFragment-object
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Voeg de tekst met het paginanummer toe aan de voettekst van het PDF-document
footer.Paragraphs.Add(txt);
```

De bovenstaande code maakt een voettekstsectie, stelt de voettekst van de pagina in met deze sectie en voegt een tekstfragment toe met de tekst "Pagina: ($p of $P )"

  waarin het paginanummer wordt weergegeven.

## Stap 5: Het gewijzigde PDF-document opslaan

Zodra de kop- en voettekst zijn toegevoegd, kunnen we het gewijzigde PDF-document opslaan. Hier is hoe:

```csharp
// Sla het gewijzigde PDF-document op
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

De bovenstaande code slaat het bewerkte PDF-document op in de opgegeven map.

### Voorbeeldbroncode voor afbeelding en paginanummer in de koptekst-voettekstsectie met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Maak een pagina in het documentobject
Aspose.Pdf.Page page = doc.Pages.Add();

// Maak een koptekstsectie van het document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Stel de koptekst voor het PDF-bestand in
page.Header = header;

// Maak een afbeeldingsobject op de pagina
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Stel het pad van het afbeeldingsbestand in
image1.File = dataDir + "aspose-logo.jpg";

// Voeg een afbeelding toe aan de koppagina van het pdf-bestand
header.Paragraphs.Add(image1);

//Maak een voettekstsectie van het document
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Stel de voettekst van het PDF-bestand in
page.Footer = footer;

// Maak een tekstobject
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Voeg tekst toe aan het koptekstgedeelte van het pdf-bestand
footer.Paragraphs.Add(txt);

// Sla het pdf-bestand op
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u een afbeelding en paginanummer kunt toevoegen aan de kop- en voettekst van een PDF-document met behulp van Aspose.PDF voor .NET. Nu kunt u deze methode gebruiken om de kop- en voettekst in uw PDF-documenten aan te passen.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het toevoegen van een afbeelding en paginanummer in de kop- en voettekst van een PDF-document?

A: Het toevoegen van een afbeelding en paginanummer in de kop- en voettekst van een PDF-document kan de visuele aantrekkingskracht, branding en navigatie-elementen verbeteren. Een afbeelding kan een logo, watermerk of een ander grafisch element vertegenwoordigen, terwijl een paginanummer gebruikers helpt hun voortgang bij te houden en specifieke pagina's te lokaliseren.

#### Vraag: Hoe helpt de meegeleverde C#-broncode bij het toevoegen van een afbeelding en paginanummer aan de kop- en voettekst van een PDF-document?

A: De meegeleverde code laat zien hoe u een PDF-document kunt maken, een pagina kunt toevoegen en vervolgens de kop- en voettekstsecties kunt aanpassen. Het laat zien hoe u een afbeelding aan de koptekst en een tekstfragment met paginanummering aan de voettekst kunt toevoegen.

#### Vraag: Kan ik elk afbeeldingsformaat voor de koptekst gebruiken en hoe geef ik het pad op?

 A: Ja, u kunt verschillende afbeeldingsformaten gebruiken (zoals JPEG, PNG, GIF, enz.) voor de headerafbeelding. Het pad van de afbeelding wordt opgegeven met behulp van de`File` eigendom van de`Aspose.Pdf.Image` voorwerp.

#### Vraag: Hoe pas ik het uiterlijk en de positionering van de afbeelding in het koptekstgedeelte aan?

 A: U kunt het uiterlijk en de positionering van de afbeelding aanpassen door de eigenschappen van de afbeelding aan te passen`Aspose.Pdf.Image` object voordat u het aan de koptekstsectie toevoegt. U kunt bijvoorbeeld de afmetingen, uitlijning, rotatie, dekking, enz. van de afbeelding instellen.

####  Vraag: Wat is het doel van de`TextFragment` object used for the footer?

 EEN: De`TextFragment` object wordt gebruikt om tekst te maken en op te maken die in de voettekst wordt weergegeven. In de meegeleverde code wordt deze gebruikt om het paginanummer en het totale aantal pagina's weer te geven.

#### Vraag: Kan ik de voettekst wijzigen om aanvullende informatie of opmaak toe te voegen?

 A: Ja, u kunt de voettekst wijzigen door de inhoud van het`TextFragment` voorwerp. U kunt extra tekst toevoegen, lettertypen, kleuren en opmaak wijzigen volgens uw vereisten.

#### Vraag: Kan ik verschillende kop- en voettekstinhoud toepassen op verschillende pagina's van het PDF-document?

 A: Ja, u kunt verschillende kop- en voettekstinhoud op verschillende pagina's toepassen door afzonderlijke pagina's te maken`HeaderFooter` objecten en wijs deze toe aan specifieke pagina's met behulp van de`Header` En`Footer` eigenschappen van de`Aspose.Pdf.Page` voorwerp.

#### Vraag: Hoe kan ik de kop- en voettekst verder aanpassen, zoals het wijzigen van de lettertypestijl of het toevoegen van extra elementen?

A: U kunt de kop- en voettekst aanpassen met behulp van verschillende klassen en eigenschappen van Aspose.PDF voor .NET. U kunt bijvoorbeeld verschillende tekstopmaakopties gebruiken, meer alinea's, afbeeldingen of zelfs tabellen toevoegen aan de kop- en voettekstsecties.

#### Vraag: Kan ik de kop- en voettekstsecties indien nodig verwijderen of wissen?

A: Ja, u kunt de kop- en voettekstsecties verwijderen of wissen door de`Header` En`Footer` eigenschappen van de`Aspose.Pdf.Page` bezwaar tegen`null`.

#### Vraag: Hoe kan ik ervoor zorgen dat de toegevoegde afbeelding en het paginanummer consistent blijven op verschillende apparaten en kijkers?

A: Aspose.PDF voor .NET biedt functionaliteit voor het maken van gestandaardiseerde en consistente PDF-documenten, zodat de toegevoegde afbeelding en het paginanummer consistent op verschillende apparaten en PDF-viewers verschijnen.