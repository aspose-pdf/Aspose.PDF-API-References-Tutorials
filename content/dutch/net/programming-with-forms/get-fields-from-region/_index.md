---
title: Velden uit regio ophalen in PDF-bestand
linktitle: Velden uit regio ophalen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig velden uit een specifieke regio op in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 130
url: /nl/net/programming-with-forms/get-fields-from-region/
---
In deze zelfstudie laten we u zien hoe u de velden van een specifieke regio in een PDF-bestand kunt krijgen met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het PDF-bestand

Open het PDF-bestand:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## Stap 3: Maak een rechthoekig object om de regio te begrenzen

Maak een rechthoekig object om het gebied te begrenzen waar u de velden wilt ophalen:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## Stap 4: Verkrijg het PDF-formulier

Download het PDF-formulier van het document:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## Stap 5: Haal de velden in het rechthoekige gebied op

Haal de velden op die zich in het opgegeven rechthoekige gebied bevinden:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Stap 6: Geef veldnamen en waarden weer

Doorloop de resulterende velden en geef hun namen en waarden weer:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Voorbeeldbroncode voor Get Fields From Region met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Open pdf-bestand
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Maak een rechthoekig object om velden in dat gebied te krijgen
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Download het PDF-formulier
Aspose.Pdf.Forms.Form form = doc.Form;
// Krijg velden in het rechthoekige gebied
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Veldnamen en waarden weergeven
foreach (Field field in fields)
{
	// Geef de plaatsingseigenschappen van afbeeldingen weer voor alle plaatsingen
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de velden van een specifieke regio in een PDF-document kunt ophalen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de velden in een bepaald rechthoekig gebied van uw PDF-document extraheren met behulp van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Kan ik deze methode gebruiken om velden uit een niet-rechthoekig gebied in een PDF-document op te halen?

 A: Nee, de opgegeven methode`GetFieldsInRect` is speciaal ontworpen om velden op te halen die zich binnen een rechthoekig gebied in een PDF-document bevinden. Als u velden uit een niet-rechthoekig gebied moet extraheren, moet u aangepaste logica implementeren om de velden te identificeren en te extraheren op basis van andere criteria, zoals veldcoördinaten of namen.

#### Vraag: Hoe kan ik de grootte of positie van de rechthoek wijzigen om velden uit een andere regio op te halen?

 A: Als u velden uit een andere regio wilt ophalen, kunt u de`Aspose.Pdf.Rectangle` objectparameters die worden gebruikt om de begrenzende rechthoek te definiëren. De`Rectangle` constructor neemt vier parameters:`x`, `y`, `width` , En`height`die de coördinaten in de linkerbovenhoek en de afmetingen van de rechthoek vertegenwoordigen. Als u deze parameters aanpast, verandert de regio waaruit velden worden geëxtraheerd.

#### Vraag: Wat moet ik doen als er geen velden binnen het opgegeven rechthoekige gebied zijn?

 A: Als er geen velden binnen het opgegeven rechthoekige gebied zijn, wordt de`GetFieldsInRect` methode retourneert een lege array. U kunt de lengte van de array controleren om te bepalen of er velden in de regio aanwezig zijn.

#### Vraag: Kan ik velden uit overlappende gebieden in een PDF-document ophalen?

 A: Ja, u kunt velden uit overlappende gebieden in een PDF-document verkrijgen door er meerdere te maken`Aspose.Pdf.Rectangle` objecten en het aanroepen van de`GetFieldsInRect` methode voor elk van hen. Overlappende regio's worden afzonderlijk afgehandeld en u ontvangt voor elke regio afzonderlijke reeksen velden.

#### Vraag: Is het mogelijk om velden van een specifieke pagina of meerdere pagina's in het PDF-document op te halen?

A: Ja, u kunt velden van een specifieke pagina of van meerdere pagina's in een PDF-document ophalen. Om dit te bereiken, kunt u het PDF-document laden en de gewenste pagina's openen met behulp van de`doc.Pages` verzameling en pas vervolgens de`GetFieldsInRect` methode naar de specifieke regio van elke pagina.