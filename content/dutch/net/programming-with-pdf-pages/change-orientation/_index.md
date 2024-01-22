---
title: Verander de oriëntatie
linktitle: Verander de oriëntatie
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding om de paginarichting van een PDF te wijzigen met Aspose.PDF voor .NET. Gemakkelijk te volgen en te implementeren in uw projecten.
type: docs
weight: 10
url: /nl/net/programming-with-pdf-pages/change-orientation/
---
In deze zelfstudie leiden we u stapsgewijs door het proces om de paginarichting van een PDF-document te wijzigen met Aspose.PDF voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u de paginarichting van uw PDF-documenten kunt wijzigen met Aspose.PDF voor .NET.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een basiskennis van de programmeertaal C#
- Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar uw invoer-PDF-bestand zich bevindt en waar u uw gewijzigde uitvoer-PDF-bestand wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het PDF-document
 Vervolgens kunt u het PDF-document vanuit het invoerbestand laden met behulp van de`Document` klasse van Aspose.PDF. Zorg ervoor dat u het juiste pad naar het PDF-bestand opgeeft.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Stap 3: Wijzig de paginarichting
Nu gaan we elke pagina van het document doornemen en de richting ervan wijzigen. Voor elke pagina passen we de afmetingen van de mediabox aan (`MediaBox`) door de breedte en hoogte om te wisselen, passen we de coördinaten van het mediavak aan om de positie van de pagina te behouden. Ten slotte stellen we de paginarotatie in op 90 graden.

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
 Ten slotte kunt u het gewijzigde PDF-document opslaan in een uitvoerbestand met behulp van de`Save()` werkwijze van de`Document`klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Change Orientation met Aspose.PDF voor .NET 

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
	// We moeten de pagina naar boven verplaatsen om het veranderende paginaformaat te compenseren
	// (onderrand van de pagina is 0,0 en informatie wordt meestal geplaatst vanuit de
	// Bovenkant van de pagina. Daarom verplaatsen we de minnaar naar boven op het verschil tussen
	// Oude en nieuwe hoogte.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Soms moeten we ook CropBox instellen (als dit in het originele bestand was ingesteld)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Rotatiehoek van de pagina instellen
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Sla het uitvoerbestand op
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de paginarichting van een PDF-document kunt wijzigen met Aspose.PDF voor .NET. Door de hierboven beschreven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw eigen projecten implementeren. Voel je vrij om de Aspose.PDF-documentatie verder te verkennen om andere handige functies voor het werken met PDF-bestanden te ontdekken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het wijzigen van de paginarichting in een PDF-document?

A: Door de paginarichting in een PDF-document te wijzigen, kunt u de inhoud van de pagina 90 graden draaien. Dit kan handig zijn in scenario's waarin de originele inhoud in een andere richting moet worden weergegeven of afgedrukt, zoals bij het overschakelen van portret- naar landschapsmodus of omgekeerd.

#### Vraag: Kan ik de richting van specifieke pagina's in het PDF-document wijzigen?

 A: Ja, u kunt de richting van specifieke pagina's in het PDF-document wijzigen. In de meegeleverde C#-broncode wordt de`foreach` lus wordt gebruikt om door elke pagina van het document te gaan en de richting ervan te wijzigen. Als u alleen de richting van specifieke pagina's wilt wijzigen, kunt u de lus aanpassen om die pagina's te targeten op basis van hun paginanummers of andere criteria.

#### Vraag: Heeft het wijzigen van de paginarichting invloed op de lay-out van de inhoud op de pagina?

A: Ja, het wijzigen van de paginarichting heeft invloed op de lay-out van de inhoud op de pagina. De inhoud wordt 90 graden gedraaid en de breedte en hoogte van de pagina worden verwisseld. Als gevolg hiervan kan de plaatsing en uitlijning van de inhoud op de pagina veranderen.

#### Vraag: Kan ik de pagina in een andere hoek dan 90 graden draaien?

 A: In de meegeleverde C#-broncode is de paginarotatie ingesteld op 90 graden met behulp van`page.Rotate = Rotate.on90;` . U kunt de rotatiehoek echter indien nodig naar andere waarden wijzigen. U kunt bijvoorbeeld gebruiken`Rotate.on180` om de pagina 180 graden te draaien of`Rotate.on270` om hem 270 graden te draaien.

#### Vraag: Hoe ga ik om met de pagina-inhoud die overloopt na het wijzigen van de richting?

A: Wanneer u de paginarichting wijzigt, kunnen de afmetingen van de pagina veranderen, wat kan resulteren in een overloop van de inhoud. Om dit te verhelpen, moet u mogelijk de lay-out en opmaak van de inhoud op de pagina aanpassen. U kunt de functies van Aspose.PDF voor .NET gebruiken, zoals het wijzigen van de grootte van elementen, het aanpassen van marges of het reorganiseren van inhoud, om ervoor te zorgen dat de pagina-inhoud goed past na de wijziging van de richting.