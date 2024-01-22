---
title: Ontvang PDF-paginaafmetingen
linktitle: Ontvang PDF-paginaafmetingen
second_title: Aspose.PDF voor .NET API-referentie
description: In deze zelfstudie leggen we uit hoe u PDF-paginaafmetingen kunt verkrijgen en manipulaties kunt uitvoeren met Aspose.PDF voor .NET. Er worden gedetailleerde stappen gegeven om u door het proces te begeleiden.
type: docs
weight: 60
url: /nl/net/programming-with-pdf-pages/get-dimensions/
---
In deze zelfstudie leiden we u stapsgewijs door het proces voor het ophalen van paginaafmetingen in een PDF-bestand met Aspose.PDF voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze tutorial weet je hoe je de afmetingen van een pagina in een PDF-bestand kunt krijgen met Aspose.PDF voor .NET.

## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Een basiskennis van de programmeertaal C#
- Aspose.PDF voor .NET geïnstalleerd in uw ontwikkelomgeving

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar uw PDF-bestand zich bevindt. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het PDF-document
 Vervolgens kunt u het PDF-bestand openen met behulp van de`Document` klasse van Aspose.PDF. Zorg ervoor dat u het juiste pad naar het PDF-bestand opgeeft.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Stap 3: Voeg een lege pagina toe (indien nodig)
 Als het PDF-document al pagina's bevat, kunt u met behulp van de index naar een bestaande pagina springen`1` (de eerste pagina heeft een index van 1). Anders kunt u een nieuwe pagina aan het document toevoegen.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Stap 4: Haal pagina-afmetingen op
 U kunt nu de paginaafmetingen verkrijgen met behulp van de`GetPageRect()` werkwijze van de`Page` voorwerp. Deze methode retourneert a`Rectangle` object dat de afmetingen van de pagina bevat. U kunt toegang krijgen tot de breedte en hoogte met behulp van de`Width` En`Height` eigenschappen.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Stap 5: Draai de pagina
 Als u de pagina wilt roteren, kunt u de`Rotate` eigendom van de`Page`voorwerp. In dit voorbeeld wordt de pagina 90 graden gedraaid.

```csharp
page. Rotate = Rotate. on90;
```

## Stap 6: Haal de paginaafmetingen opnieuw op
 Na paginarotatie kunt u de paginaafmetingen opnieuw verkrijgen met behulp van de`GetPageRect()` methode.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Voorbeeldbroncode voor Get Dimensions met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Voegt een lege pagina toe aan een pdf-document
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Krijg informatie over de paginahoogte en -breedte
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Roteer de pagina in een hoek van 90 graden
page.Rotate = Rotation.on90;
// Krijg informatie over de paginahoogte en -breedte
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de afmetingen van een pagina in een PDF-bestand kunt verkrijgen met behulp van Aspose.PDF voor .NET. Door de gegeven stappen te volgen, kunt u eenvoudig pagina-afmetingen extraheren en andere PDF-manipulatiebewerkingen uitvoeren. Aspose.PDF voor .NET biedt grote flexibiliteit bij het werken met PDF-bestanden en stelt u in staat krachtige en op maat gemaakte oplossingen te ontwikkelen.

Voel je vrij om de documentatie van Aspose.PDF verder te verkennen om alle functies van deze bibliotheek te ontdekken.

### Veelgestelde vragen over het verkrijgen van PDF-paginaafmetingen

#### Vraag: Hoe kan ik de afmetingen van een specifieke pagina in een PDF-bestand krijgen?

A: Om de afmetingen van een specifieke pagina in een PDF-bestand te krijgen, kunt u de`GetPageRect()` werkwijze van de`Page` object in Aspose.PDF voor .NET. Deze methode retourneert a`Rectangle` object dat de afmetingen (breedte en hoogte) van de pagina bevat.

####  Vraag: Wat doet de`GetPageRect(true)` method do in the provided C# source code?

 EEN: De`GetPageRect(true)` methode in de meegeleverde C#-broncode retourneert de afmetingen van de pagina na toepassing van eventuele rotaties. Als de pagina wordt geroteerd, retourneert de methode de afmetingen van de geroteerde pagina, die kunnen afwijken van de oorspronkelijke afmetingen.

#### Vraag: Kan ik de afmetingen van alle pagina's in het PDF-document opvragen met Aspose.PDF voor .NET?

 A: Ja, u kunt de afmetingen van alle pagina's in het PDF-document verkrijgen door de`Pages` verzameling van de`Document` object en het gebruik van de`GetPageRect(true)` methode voor elke pagina.

#### Vraag: Hoe kan ik de richting van een pagina (staand of liggend) bepalen op basis van de afmetingen?

A: Om de oriëntatie van een pagina te bepalen op basis van de afmetingen, kunt u de breedte en hoogte van de pagina vergelijken. Als de breedte groter is dan de hoogte, bevindt de pagina zich in de liggende richting, en als de hoogte groter is dan de breedte, bevindt de pagina zich in de staande richting.

#### Vraag: Kan ik de afmetingen van een pagina wijzigen met Aspose.PDF voor .NET?

 A: Ja, u kunt de afmetingen van een pagina wijzigen in Aspose.PDF voor .NET. Na het verkrijgen van de`Rectangle` object dat de pagina-afmetingen vertegenwoordigt, kunt u de breedte en hoogte aanpassen aan uw vereisten en vervolgens de wijzigingen op de pagina toepassen.