---
title: Formulierveld verplaatsen
linktitle: Formulierveld verplaatsen
second_title: Aspose.PDF voor .NET API-referentie
description: Verplaats eenvoudig formuliervelden in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 200
url: /nl/net/programming-with-forms/move-form-field/
---
In deze tutorial laten we u zien hoe u een formulierveld in een PDF-document verplaatst met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document

Laad het bestaande PDF-document:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Stap 3: Het formulierveld ophalen

Selecteer het formulierveld dat u wilt verplaatsen:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Stap 4: Veldlocatie wijzigen

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

### Voorbeeldbroncode voor Move Form Field met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Krijg een veld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Veldlocatie wijzigen
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Gewijzigd document opslaan
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Conclusie

In deze tutorial hebben we geleerd hoe u een formulierveld in een PDF-document verplaatst met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig naar een specifiek veld navigeren en de locatie ervan wijzigen indien nodig.


### Veelgestelde vragen

#### V: Kan ik meerdere formuliervelden binnen één PDF-document verplaatsen met Aspose.PDF voor .NET?

A: Ja, u kunt meerdere formuliervelden binnen één PDF-document verplaatsen met Aspose.PDF voor .NET. Herhaal het proces eenvoudigweg voor elk formulierveld dat u wilt verplaatsen.

#### V: Heeft het verplaatsen van een formulierveld invloed op de bijbehorende gegevens of functionaliteit?

A: Nee, het verplaatsen van een formulierveld heeft geen invloed op de bijbehorende gegevens of functionaliteit. Het formulierveld behoudt al zijn eigenschappen en waarden nadat het naar een nieuwe locatie is verplaatst.

#### V: Hoe kan ik de exacte coördinaten voor de nieuwe locatie van het formulierveld bepalen?

 A: U kunt de nieuwe locatie opgeven met behulp van de`Aspose.Pdf.Rectangle` klasse, waarin u de X- en Y-coördinaten van de linkerbovenhoek en de X- en Y-coördinaten van de rechteronderhoek van het rechthoekige gebied definieert.

#### V: Is Aspose.PDF voor .NET compatibel met zowel Windows- als Linux-omgevingen?

A: Ja, Aspose.PDF voor .NET is compatibel met zowel Windows- als Linux-omgevingen, waardoor ontwikkelaars flexibel kunnen werken in hun favoriete besturingssystemen.