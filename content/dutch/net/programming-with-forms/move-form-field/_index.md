---
title: Formulierveld verplaatsen
linktitle: Formulierveld verplaatsen
second_title: Aspose.PDF voor .NET API-referentie
description: Verplaats eenvoudig formuliervelden in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 200
url: /nl/net/programming-with-forms/move-form-field/
---
In deze zelfstudie laten we u zien hoe u een formulierveld in een PDF-document verplaatst met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document

Laad het bestaande PDF-document:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Stap 3: Haal het formulierveld op

Haal het formulierveld op dat u wilt verplaatsen:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Stap 4: Wijzig de veldlocatie

Wijzig de locatie van het formulierveld door een nieuw rechthoekig gebied te definiëren:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Stap 5: Sla het bewerkte document op

Sla het gewijzigde PDF-document op:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Voorbeeldbroncode voor formulierveld verplaatsen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Neem een veld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Veldlocatie wijzigen
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Bewaar het gewijzigde document
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een formulierveld in een PDF-document kunt verplaatsen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig naar een specifiek veld navigeren en de locatie ervan indien nodig wijzigen.


### Veelgestelde vragen

#### Vraag: Kan ik meerdere formuliervelden binnen één PDF-document verplaatsen met Aspose.PDF voor .NET?

A: Ja, u kunt meerdere formuliervelden binnen één PDF-document verplaatsen met Aspose.PDF voor .NET. Herhaal eenvoudigweg het proces voor elk formulierveld dat u wilt verplaatsen.

#### Vraag: Heeft het verplaatsen van een formulierveld invloed op de bijbehorende gegevens of functionaliteit?

A: Nee, het verplaatsen van een formulierveld heeft geen invloed op de bijbehorende gegevens of functionaliteit. Het formulierveld behoudt al zijn eigenschappen en waarden nadat het naar een nieuwe locatie is verplaatst.

#### Vraag: Hoe kan ik de exacte coördinaten voor de nieuwe locatie van het formulierveld bepalen?

 A: U kunt de nieuwe locatie opgeven met behulp van de`Aspose.Pdf.Rectangle` klasse, waar u de X- en Y-coördinaten van de linkerbovenhoek en de X- en Y-coördinaten van de rechteronderhoek van het rechthoekige gebied definieert.

#### Vraag: Is Aspose.PDF voor .NET compatibel met zowel Windows- als Linux-omgevingen?

A: Ja, Aspose.PDF voor .NET is compatibel met zowel Windows- als Linux-omgevingen, waardoor ontwikkelaars de flexibiliteit krijgen om in hun favoriete besturingssystemen te werken.