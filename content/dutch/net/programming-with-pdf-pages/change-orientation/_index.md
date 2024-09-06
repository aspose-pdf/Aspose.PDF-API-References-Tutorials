---
title: Verander oriëntatie
linktitle: Verander oriëntatie
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om de pagina-oriëntatie van een PDF te wijzigen met Aspose.PDF voor .NET. Gemakkelijk te volgen en te implementeren in uw projecten.
type: docs
weight: 10
url: /nl/net/programming-with-pdf-pages/change-orientation/
---
In deze tutorial leiden we u stapsgewijs door het proces om de pagina-oriëntatie van een PDF-document te wijzigen met Aspose.PDF voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en te implementeren in uw eigen projecten. Aan het einde van deze tutorial weet u hoe u de pagina-oriëntatie van uw PDF-documenten kunt wijzigen met Aspose.PDF voor .NET.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Basiskennis van de programmeertaal C#
- Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving

## Stap 1: Definieer de documentdirectory
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar uw invoer-PDF-bestand zich bevindt en waar u uw gewijzigde uitvoer-PDF-bestand wilt opslaan. Vervang "UW DOCUMENTENMAP" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het PDF-document
 Vervolgens kunt u het PDF-document vanuit het invoerbestand laden met behulp van de`Document` klasse van Aspose.PDF. Zorg ervoor dat u het juiste pad naar het PDF-bestand opgeeft.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 3: Wijzig de pagina-oriëntatie
Nu gaan we elke pagina van het document doorlopen en de oriëntatie ervan wijzigen. Voor elke pagina wijzigen we de afmetingen van de mediabox (`MediaBox`) door de breedte en hoogte om te wisselen, dan passen we de coördinaten van de mediabox aan om de positie van de pagina te behouden. Tot slot stellen we de paginarotatie in op 90 graden.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Stap 4: Sla het gewijzigde PDF-document op
 Ten slotte kunt u het gewijzigde PDF-document opslaan als een uitvoerbestand met behulp van de`Save()` methode van de`Document`klasse. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Wijzigingsoriëntatie met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// We moeten de pagina naar boven verplaatsen om de veranderende paginagrootte te compenseren
	// (onderkant van de pagina is 0,0 en informatie wordt meestal geplaatst vanaf de
	// Bovenaan de pagina. Daarom verplaatsen we lover edge upper op verschil tussen
	// Oude en nieuwe hoogte.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Soms moeten we ook CropBox instellen (als dit in het originele bestand was ingesteld)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Rotatiehoek van de pagina instellen
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Uitvoerbestand opslaan
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusie
In deze tutorial hebben we geleerd hoe u de pagina-oriëntatie van een PDF-document kunt wijzigen met Aspose.PDF voor .NET. Door de hierboven beschreven stappen te volgen, kunt u deze functionaliteit eenvoudig implementeren in uw eigen projecten. U kunt de Aspose.PDF-documentatie verder verkennen om andere handige functies voor het werken met PDF-bestanden te ontdekken.

### Veelgestelde vragen

#### V: Wat is het doel van het wijzigen van de pagina-oriëntatie in een PDF-document?

A: Door de pagina-oriëntatie in een PDF-document te wijzigen, kunt u de inhoud van de pagina 90 graden draaien. Dit kan handig zijn in scenario's waarin de originele inhoud in een andere oriëntatie moet worden weergegeven of afgedrukt, zoals het wisselen van portret- naar landschapsmodus of omgekeerd.

#### V: Kan ik de afdrukstand van specifieke pagina's in het PDF-document wijzigen?

 A: Ja, u kunt de oriëntatie van specifieke pagina's in het PDF-document wijzigen. In de meegeleverde C#-broncode staat de`foreach` loop wordt gebruikt om elke pagina van het document te doorlopen en de oriëntatie te wijzigen. Als u alleen de oriëntatie van specifieke pagina's wilt wijzigen, kunt u de loop aanpassen om die pagina's te targeten op basis van hun paginanummers of andere criteria.

#### V: Heeft het wijzigen van de paginaoriëntatie invloed op de lay-out van de inhoud op de pagina?

A: Ja, het wijzigen van de pagina-oriëntatie heeft invloed op de lay-out van de content op de pagina. De content wordt 90 graden gedraaid en de breedte en hoogte van de pagina worden verwisseld. Als gevolg hiervan kunnen de plaatsing en uitlijning van de content op de pagina veranderen.

#### V: Kan ik de pagina in een andere hoek dan 90 graden draaien?

 A: In de meegeleverde C#-broncode is de paginarotatie ingesteld op 90 graden met behulp van`page.Rotate = Rotate.on90;` . U kunt de rotatiehoek echter naar andere waarden wijzigen indien nodig. U kunt bijvoorbeeld gebruiken`Rotate.on180` om de pagina 180 graden te draaien of`Rotate.on270` om het 270 graden te draaien.

#### V: Hoe ga ik om met de pagina-inhoud die overloopt nadat ik de oriëntatie heb gewijzigd?

A: Wanneer u de pagina-oriëntatie wijzigt, kunnen de afmetingen van de pagina veranderen, wat kan leiden tot overloop van de inhoud. Om dit te verwerken, moet u mogelijk de lay-out en opmaak van de inhoud op de pagina aanpassen. U kunt functies gebruiken die worden geboden door Aspose.PDF voor .NET, zoals het wijzigen van de grootte van elementen, het aanpassen van marges of het reorganiseren van inhoud, om ervoor te zorgen dat de pagina-inhoud goed past na de wijziging van de oriëntatie.