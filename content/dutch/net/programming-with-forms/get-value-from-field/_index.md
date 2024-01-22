---
title: Haal waarde uit veld in PDF-document
linktitle: Haal waarde uit veld in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Krijg eenvoudig de waarde van een formulierveld in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 140
url: /nl/net/programming-with-forms/get-value-from-field/
---
In deze zelfstudie laten we u zien hoe u de waarde van een formulierveld kunt verkrijgen met behulp van Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

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

## Stap 4: Haal de veldwaarde op

 Haal de veldwaarde op met behulp van de`Value` eigendom:

```csharp
Console.WriteLine("PartialName: {0}", textBoxField.PartialName);
Console.WriteLine("Value: {0}", textBoxField.Value);
```

### Voorbeeldbroncode voor Get Value From Field met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "GetValueFromField.pdf");
// Neem een veld
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Veldwaarde ophalen
Console.WriteLine("PartialName : {0} ", textBoxField.PartialName);
Console.WriteLine("Value : {0} ", textBoxField.Value);
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de waarde van een formulierveld kunt verkrijgen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de waarde van een specifiek formulierveld in uw PDF-documenten extraheren met behulp van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Kan ik de waarde van een formulierveld achterhalen zonder vooraf de naam ervan te kennen?

 A: Nee, u moet de naam of een gedeeltelijke naam van het formulierveld weten om de waarde ervan te achterhalen met Aspose.PDF voor .NET. De`pdfDocument.Form["fieldname"]` De syntaxis vereist de exacte naam of een gedeeltelijke naam van het formulierveld om toegang te krijgen tot de eigenschappen ervan, inclusief de waarde.

#### Vraag: Wat moet ik doen als het formulierveld niet bestaat in het PDF-document?

 A: Als het formulierveld niet bestaat in het PDF-document, wordt het`pdfDocument.Form["fieldname"]` syntaxis zal terugkeren`null` . Het is essentieel om dergelijke gevallen te behandelen door te controleren op`null` voordat u toegang krijgt tot de eigenschappen van het formulierveld om uitzonderingen te voorkomen.

#### Vraag: Hoe kan ik omgaan met verschillende soorten formuliervelden (bijvoorbeeld selectievakjes, keuzerondjes) om hun waarden op te halen?

 A: Om met verschillende soorten formuliervelden om te gaan, kunt u de juiste veldklassen gebruiken die beschikbaar zijn in Aspose.PDF voor .NET. Gebruik bijvoorbeeld`CheckBoxField` werken met selectievakjes en`RadioButtonField`werken met keuzerondjes. Zodra u over het juiste veldobject beschikt, heeft u toegang tot de eigenschappen ervan, inclusief de waarde.

#### Vraag: Kan ik de waarden van meerdere formuliervelden tegelijk opvragen?

A: Ja, u kunt de waarden van meerdere formuliervelden tegelijk verkrijgen door de verzameling formuliervelden te doorlopen met behulp van een lus of LINQ-query's. Op deze manier kunt u programmatisch toegang krijgen tot de waarde van elk formulierveld in het PDF-document.

#### Vraag: Is het mogelijk om de waarde van een formulierveld te wijzigen en de wijzigingen weer op te slaan in het PDF-document?

 A: Ja, u kunt de waarde van een formulierveld wijzigen met Aspose.PDF voor .NET en de wijzigingen opslaan in het PDF-document. Na het updaten van de`Value` eigenschap van het formulierveld, kunt u de`pdfDocument.Save()` methode om de wijzigingen in het originele PDF-document op te slaan.