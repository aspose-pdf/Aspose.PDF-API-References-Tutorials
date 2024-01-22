---
title: Paginarichting volgens afbeeldingsafmetingen
linktitle: Paginarichting volgens afbeeldingsafmetingen
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het instellen van de paginarichting op basis van afbeeldingsafmetingen met Aspose.PDF voor .NET.
type: docs
weight: 80
url: /nl/net/document-conversion/page-orientation-according-image-dimensions/
---
In deze zelfstudie begeleiden we u bij het instellen van de paginarichting op basis van de afmetingen van een afbeelding met behulp van Aspose.PDF voor .NET. We doorlopen een lijst met JPG-afbeeldingen in een bepaalde map en passen de paginarichting automatisch aan op basis van de breedte van elke afbeelding. Volg de onderstaande stappen om dit te bereiken.

## Vereisten
Zorg ervoor dat u aan de volgende vereisten voldoet voordat u begint:

- Basiskennis van de programmeertaal C#.
- Aspose.PDF-bibliotheek voor .NET geïnstalleerd op uw systeem.
- Een ontwikkelomgeving zoals Visual Studio.

## Stap 1: Blader door JPG-afbeeldingen
Bij deze stap bladeren we door alle JPG-afbeeldingen in een bepaalde map. Volg de onderstaande code:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak een nieuw PDF-document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Haal de namen op van alle JPG-bestanden in een bepaalde map
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Zeker vervangen`"YOUR DOCUMENTS DIRECTORY"` met de daadwerkelijke map waar uw JPG-afbeeldingen zich bevinden.

## Stap 2: Creatie van de pagina en de afbeelding
Nadat we door de JPG-bestanden hebben gebladerd, maken we voor elk bestand een pagina en een afbeelding. Gebruik de volgende code:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Maak een Pagina-object
Aspose.Pdf.Page page = doc.Pages.Add();

// Maak een afbeeldingsobject
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Stap 3: Afbeeldingsafmetingen controleren
Laten we nu de afmetingen van elke afbeelding controleren om de paginarichting te bepalen. Gebruik de volgende code:

```csharp
// Maak een BitMap-object om informatie uit het afbeeldingsbestand te halen
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Controleer of de breedte van de afbeelding groter is dan de breedte van de pagina of niet
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Als de breedte van de afbeelding kleiner is dan de breedte van de pagina, stelt u de afdrukstand van de pagina in op staand
page.PageInfo.IsLandscape = false;
```

## Stap 4: De afbeelding toevoegen aan het PDF-document
Nadat we de afmetingen van de afbeelding hebben gecontroleerd, voegen we de afbeelding toe aan de alineaverzameling van het PDF-document. Gebruik de volgende code:

```csharp
// Voeg de afbeelding toe aan de alineaverzameling van het PDF-document
page.Paragraphs.Add(image1);
```

## Stap 5: Het PDF-bestand opslaan
Nadat we alle afbeeldingen aan het PDF-document hebben toegevoegd, kunnen we nu het resulterende PDF-bestand opslaan. Hier is de laatste stap:

```csharp
// Sla het PDF-bestand op
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met de gewenste map waarin u het uitgevoerde PDF-bestand wilt opslaan.

### Voorbeeldbroncode voor paginaoriëntatie volgens afbeeldingsafmetingen met Aspose.PDF voor .NET

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Haal de namen op van alle JPG-bestanden in een bepaalde map
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Maak een paginaobject
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Maak een afbeeldingsobject
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Maak een BitMap-object om de informatie van het afbeeldingsbestand op te halen
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Controleer of de breedte van het afbeeldingsbestand groter is dan Paginabreedte of niet
	if (myimage.Width > page.PageInfo.Width)
		// Als de afbeeldingsbreedte groter is dan de paginabreedte, stelt u de paginarichting in op Liggend
		page.PageInfo.IsLandscape = true;
	else
		// Als de afbeeldingsbreedte kleiner is dan de paginabreedte, stelt u de paginarichting in op Staand
		page.PageInfo.IsLandscape = false;
	// Voeg de afbeelding toe aan de alineaverzameling van het PDF-document
	page.Paragraphs.Add(image1);
}
// Sla het pdf-bestand op
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces besproken van het instellen van de paginarichting op basis van de afmetingen van een afbeelding met behulp van Aspose.PDF voor .NET. Door de hierboven beschreven instructies te volgen, zou u nu een PDF-document moeten kunnen maken met de juiste paginarichting voor elke afbeelding. Deze functie is handig als u afbeeldingen van verschillende formaten heeft en deze in een PDF-document wilt insluiten.

### Veelgestelde vragen

#### Vraag: Kan ik andere afbeeldingsformaten gebruiken in plaats van JPG om de paginarichting in te stellen op basis van de afmetingen van de afbeelding?

A: Ja, u kunt naast JPG ook andere afbeeldingsformaten gebruiken, zoals PNG, BMP of GIF, om de paginarichting in te stellen op basis van de afmetingen van de afbeelding. De meegeleverde code loopt door alle afbeeldingsbestanden met de extensie ".JPG", maar u kunt deze wijzigen om ook andere afbeeldingsformaten op te nemen.

#### Vraag: Wat gebeurt er als de afmetingen van een afbeelding exact gelijk zijn aan de paginabreedte?

A: Als de breedte van een afbeelding exact gelijk is aan de paginabreedte, wordt de paginarichting ingesteld op staand. In de verstrekte code wordt de paginarichting alleen ingesteld op liggend als de breedte van de afbeelding groter is dan de paginabreedte.

#### Vraag: Kan ik de logica van de paginarichting aanpassen op basis van specifieke vereisten?

A: Ja, u kunt de paginaoriëntatielogica aanpassen op basis van specifieke vereisten. U kunt bijvoorbeeld een drempelwaarde instellen om te bepalen wanneer de paginarichting moet worden ingesteld op liggend of staand. Bovendien kunt u rekening houden met factoren zoals de hoogte van de afbeelding of de beeldverhouding om de paginarichting te bepalen.

#### Vraag: Kan ik naast de afbeeldingen ook andere inhoud, zoals tekst of tabellen, aan het PDF-document toevoegen?

A: Ja, u kunt samen met de afbeeldingen andere inhoud, zoals tekst of tabellen, aan het PDF-document toevoegen. Aspose.PDF voor .NET biedt een uitgebreide reeks functies voor het manipuleren van PDF-documenten, inclusief het toevoegen van tekst, afbeeldingen, tabellen en andere elementen aan de pagina's.