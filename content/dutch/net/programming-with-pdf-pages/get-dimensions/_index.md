---
title: PDF-pagina-afmetingen ophalen
linktitle: PDF-pagina-afmetingen ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: In deze tutorial leggen we uit hoe u PDF-pagina-afmetingen kunt verkrijgen en manipulaties kunt uitvoeren met Aspose.PDF voor .NET. Er worden gedetailleerde stappen gegeven om u door het proces te leiden.
type: docs
weight: 60
url: /nl/net/programming-with-pdf-pages/get-dimensions/
---
In deze tutorial leiden we u stapsgewijs door het proces om pagina-afmetingen in een PDF-bestand te krijgen met Aspose.PDF voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en te implementeren in uw eigen projecten. Aan het einde van deze tutorial weet u hoe u de afmetingen van een pagina in een PDF-bestand krijgt met Aspose.PDF voor .NET.

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

- Basiskennis van de programmeertaal C#
- Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving

## Stap 1: Definieer de documentdirectory
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar uw PDF-bestand zich bevindt. Vervang "UW DOCUMENTENMAP" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het PDF-document
 Vervolgens kunt u het PDF-bestand openen met behulp van de`Document` klasse van Aspose.PDF. Zorg ervoor dat u het juiste pad naar het PDF-bestand opgeeft.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Stap 3: Voeg een lege pagina toe (indien nodig)
 Als het PDF-document al pagina's bevat, kunt u met behulp van de index naar een bestaande pagina springen`1` (de eerste pagina heeft index 1). Anders kunt u een nieuwe pagina aan het document toevoegen.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Stap 4: Pagina-afmetingen verkrijgen
 U kunt nu de pagina-afmetingen verkrijgen met behulp van de`GetPageRect()` methode van de`Page` object. Deze methode retourneert een`Rectangle` object met de afmetingen van de pagina. U kunt de breedte en hoogte openen met behulp van de`Width` En`Height` eigenschappen.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Stap 5: Draai de pagina
 Als u de pagina wilt draaien, kunt u de`Rotate` eigendom van de`Page`object. In dit voorbeeld is de pagina 90 graden gedraaid.

```csharp
page. Rotate = Rotate. on90;
```

## Stap 6: Haal de pagina-afmetingen opnieuw op
 Na het roteren van de pagina kunt u de pagina-afmetingen opnieuw verkrijgen met behulp van de`GetPageRect()` methode.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Voorbeeldbroncode voor Get Dimensions met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Voegt een lege pagina toe aan een pdf-document
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Informatie over paginahoogte en -breedte ophalen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Draai de pagina in een hoek van 90 graden
page.Rotate = Rotation.on90;
// Informatie over paginahoogte en -breedte ophalen
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusie
In deze tutorial hebben we geleerd hoe je de afmetingen van een pagina in een PDF-bestand kunt krijgen met Aspose.PDF voor .NET. Door de gegeven stappen te volgen, kun je eenvoudig pagina-afmetingen extraheren en andere PDF-manipulatiebewerkingen uitvoeren. Aspose.PDF voor .NET biedt grote flexibiliteit voor het werken met PDF-bestanden en stelt je in staat om krachtige en aangepaste oplossingen te ontwikkelen.

U kunt de documentatie van Aspose.PDF verder doornemen om alle functies van deze bibliotheek te ontdekken.

### Veelgestelde vragen over het verkrijgen van PDF-pagina-afmetingen

#### V: Hoe kan ik de afmetingen van een specifieke pagina in een PDF-bestand krijgen?

A: Om de afmetingen van een specifieke pagina in een PDF-bestand te krijgen, kunt u de`GetPageRect()` methode van de`Page` object in Aspose.PDF voor .NET. Deze methode retourneert een`Rectangle` object dat de afmetingen (breedte en hoogte) van de pagina bevat.

####  V: Wat betekent de`GetPageRect(true)` method do in the provided C# source code?

 A: De`GetPageRect(true)` methode in de meegeleverde C# broncode retourneert de afmetingen van de pagina na het toepassen van rotaties. Als de pagina is geroteerd, retourneert de methode de afmetingen van de geroteerde pagina, die kunnen verschillen van de oorspronkelijke afmetingen.

#### V: Kan ik de afmetingen van alle pagina's in het PDF-document verkrijgen met Aspose.PDF voor .NET?

 A: Ja, u kunt de afmetingen van alle pagina's in het PDF-document verkrijgen door de`Pages` verzameling van de`Document` object en het gebruik van de`GetPageRect(true)` methode voor elke pagina.

#### V: Hoe kan ik de oriëntatie van een pagina (staand of liggend) bepalen op basis van de afmetingen?

A: Om de oriëntatie van een pagina te bepalen op basis van de afmetingen, kunt u de breedte en hoogte van de pagina vergelijken. Als de breedte groter is dan de hoogte, is de pagina in liggende oriëntatie, en als de hoogte groter is dan de breedte, is de pagina in staande oriëntatie.

#### V: Kan ik de afmetingen van een pagina wijzigen met Aspose.PDF voor .NET?

 A: Ja, u kunt de afmetingen van een pagina in Aspose.PDF voor .NET wijzigen. Nadat u de`Rectangle` object dat de pagina-afmetingen weergeeft, kunt u de breedte en hoogte naar wens aanpassen en de wijzigingen vervolgens op de pagina toepassen.