---
title: Waarde ophalen uit veld in PDF-document
linktitle: Waarde ophalen uit veld in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig de waarde van een formulierveld op in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 140
url: /nl/net/programming-with-forms/get-value-from-field/
---
In deze tutorial laten we je zien hoe je de waarde van een formulierveld kunt ophalen met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om je door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het document

Open het PDF-document:

```csharp
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
```

## Stap 3: Veld ophalen

Haal het gewenste formulierveld op (in dit voorbeeld gebruiken we het veld "textbox1"):

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Stap 4: Veldwaarde ophalen

 Haal de veldwaarde op met behulp van de`Value` eigendom:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Voorbeeldbroncode voor Get Value From Field met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Krijg een veld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Veldwaarde ophalen
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusie

In deze tutorial hebben we geleerd hoe je de waarde van een formulierveld kunt ophalen met Aspose.PDF voor .NET. Door deze stappen te volgen, kun je eenvoudig de waarde van een specifiek formulierveld in je PDF-documenten ophalen met Aspose.PDF.

### Veelgestelde vragen

#### V: Kan ik de waarde van een formulierveld opvragen zonder dat ik de naam ervan vooraf weet?

 A: Nee, u moet de naam of een deel van de naam van het formulierveld weten om de waarde ervan te verkrijgen met Aspose.PDF voor .NET.`pdfDocument.Form["fieldname"]` De syntaxis vereist de exacte naam of een gedeeltelijke naam van het formulierveld om toegang te krijgen tot de eigenschappen ervan, inclusief de waarde.

#### V: Wat als het formulierveld niet in het PDF-document staat?

 A: Als het formulierveld niet in het PDF-document voorkomt,`pdfDocument.Form["fieldname"]` syntaxis zal terugkeren`null` Het is essentieel om dergelijke gevallen te behandelen door te controleren op`null` voordat u de eigenschappen van het formulierveld benadert, om uitzonderingen te voorkomen.

#### V: Hoe kan ik verschillende typen formuliervelden (bijv. selectievakjes, keuzerondjes) verwerken om de waarden op te halen?

 A: Om verschillende typen formuliervelden te verwerken, kunt u de juiste veldklassen gebruiken die beschikbaar zijn in Aspose.PDF voor .NET. Gebruik bijvoorbeeld`CheckBoxField` om met selectievakjes te werken en`RadioButtonField`om met keuzerondjes te werken. Zodra u het juiste veldobject hebt, kunt u de eigenschappen ervan openen, inclusief de waarde.

#### V: Kan ik de waarden van meerdere formuliervelden tegelijk opvragen?

A: Ja, u kunt de waarden van meerdere formuliervelden tegelijk ophalen door de formulierveldenverzameling te doorlopen met behulp van een lus of LINQ-query's. Op deze manier kunt u programmatisch toegang krijgen tot de waarde van elk formulierveld in het PDF-document.

#### V: Is het mogelijk om de waarde van een formulierveld te wijzigen en de wijzigingen op te slaan in het PDF-document?

 A: Ja, u kunt de waarde van een formulierveld wijzigen met Aspose.PDF voor .NET en de wijzigingen opslaan in het PDF-document. Nadat u de`Value` eigenschap van het formulierveld, kunt u de`pdfDocument.Save()` Methode om de wijzigingen in het originele PDF-document op te slaan.