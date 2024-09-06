---
title: Velden uit regio ophalen in PDF-bestand
linktitle: Velden uit regio ophalen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig velden uit een specifieke regio op in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 130
url: /nl/net/programming-with-forms/get-fields-from-region/
---
In deze tutorial laten we je zien hoe je de velden van een specifieke regio in een PDF-bestand krijgt met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om je door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

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

## Stap 5: Haal de velden in het rechthoekige gebied

Haal de velden op die zich in het opgegeven rechthoekige gebied bevinden:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## Stap 6: Veldnamen en waarden weergeven

Loop door de resulterende velden en geef hun namen en waarden weer:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Voorbeeldbroncode voor het ophalen van velden uit regio met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PDF-bestand openen
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Maak een rechthoekig object om velden in dat gebied te krijgen
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Ontvang het PDF-formulier
Aspose.Pdf.Forms.Form form = doc.Form;
// Velden in het rechthoekige gebied ophalen
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Veldnamen en waarden weergeven
foreach (Field field in fields)
{
	// Weergave van de eigenschappen van de afbeeldingsplaatsing voor alle plaatsingen
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe we de velden van een specifieke regio in een PDF-document kunnen ophalen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de velden extraheren die zich in een bepaald rechthoekig gebied van uw PDF-document bevinden met Aspose.PDF.

### Veelgestelde vragen

#### V: Kan ik deze methode gebruiken om velden uit een niet-rechthoekig gebied in een PDF-document te halen?

 A: Nee, de verstrekte methode`GetFieldsInRect` is speciaal ontworpen om velden op te halen die zich binnen een rechthoekige regio in een PDF-document bevinden. Als u velden uit een niet-rechthoekige regio wilt extraheren, moet u aangepaste logica implementeren om de velden te identificeren en te extraheren op basis van andere criteria, zoals veldcoördinaten of namen.

#### V: Hoe kan ik de grootte of positie van de rechthoek aanpassen om velden uit een ander gebied te krijgen?

 A: Om velden uit een andere regio te krijgen, kunt u de`Aspose.Pdf.Rectangle` parameters van het object die worden gebruikt om de begrenzende rechthoek te definiëren.`Rectangle` constructor heeft vier parameters:`x`, `y`, `width` , En`height`die de coördinaten van de linkerbovenhoek en de afmetingen van de rechthoek vertegenwoordigen. Door deze parameters aan te passen, verandert u de regio waaruit velden worden geëxtraheerd.

#### V: Wat als er geen velden binnen het opgegeven rechthoekige gebied zijn?

 A: Als er geen velden binnen het opgegeven rechthoekige gebied zijn,`GetFieldsInRect` methode retourneert een lege array. U kunt de lengte van de array controleren om te bepalen of er velden in de regio zijn.

#### V: Kan ik velden uit overlappende regio's in een PDF-document ophalen?

 A: Ja, u kunt velden uit overlappende regio's in een PDF-document ophalen door meerdere velden te maken.`Aspose.Pdf.Rectangle` objecten en het aanroepen van de`GetFieldsInRect` methode voor elk van hen. Overlappende regio's worden onafhankelijk behandeld en u ontvangt afzonderlijke arrays van velden voor elke regio.

#### V: Is het mogelijk om velden van een specifieke pagina of meerdere pagina's in het PDF-document op te halen?

A: Ja, u kunt velden van een specifieke pagina of meerdere pagina's in een PDF-document ophalen. Om dit te bereiken, kunt u het PDF-document laden, de gewenste pagina's openen met behulp van de`doc.Pages` verzameling en pas vervolgens de`GetFieldsInRect` methode voor de specifieke regio van elke pagina.