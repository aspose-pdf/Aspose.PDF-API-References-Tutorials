---
title: Haal waarden uit alle velden in het PDF-document op
linktitle: Haal waarden uit alle velden in het PDF-document op
second_title: Aspose.PDF voor .NET API-referentie
description: Krijg eenvoudig de waarden van alle formuliervelden in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 150
url: /nl/net/programming-with-forms/get-values-from-all-fields/
---
In deze zelfstudie laten we u zien hoe u de waarden van alle formuliervelden in een PDF-document kunt ophalen met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het document

Open het PDF-document:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Stap 3: Haal waarden op voor alle velden

Loop door alle formuliervelden in het document en haal hun namen en waarden op:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Voorbeeldbroncode voor waarden uit alle velden ophalen met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Haal waarden uit alle velden op
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de waarden van alle formuliervelden in een PDF-document kunt ophalen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de waarden van alle formuliervelden uit uw PDF-documenten extraheren met behulp van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Kan ik de waarden van formuliervelden wijzigen terwijl ik ze ophaal met Aspose.PDF voor .NET?

 A: Ja, u kunt de waarden van formuliervelden wijzigen terwijl u ze ophaalt met Aspose.PDF voor .NET. Zodra je de`Field` object dat een formulierveld vertegenwoordigt, kunt u het bijwerken`Value`vastgoed met de gewenste waarde. Nadat u de nodige wijzigingen heeft aangebracht, kunt u het bijgewerkte PDF-document opslaan om de wijzigingen weer te geven.

#### Vraag: Hoe kan ik specifieke formuliervelden filteren en ophalen op basis van hun typen (bijvoorbeeld tekstvelden, selectievakjes)?

 A: Om specifieke formuliervelden op te halen op basis van hun typen, kunt u voorwaardelijke instructies of LINQ-query's gebruiken om de interessevelden te filteren. U kunt het type van elk formulierveld controleren met behulp van de velden`FieldType` eigenschap en haal vervolgens de waarden dienovereenkomstig op.

#### Vraag: Wat gebeurt er als het PDF-document geen formuliervelden heeft?

 A: Als het PDF-document geen formuliervelden bevat, wordt het`pdfDocument.Form` property retourneert een lege verzameling. In dergelijke gevallen wordt de lus voor het ophalen van waarden niet uitgevoerd en worden er geen waarden weergegeven.

#### Vraag: Kan ik de formulierveldwaarden in een specifieke volgorde extraheren of alfabetisch sorteren?

A: De volgorde waarin de formuliervelden worden opgehaald, is afhankelijk van de onderliggende structuur van het PDF-document. Aspose.PDF voor .NET retourneert de formuliervelden in de volgorde waarin ze aan het document zijn toegevoegd. Als u de formuliervelden in een specifieke volgorde wilt weergeven of verwerken, kunt u aangepaste sorteerlogica implementeren op basis van uw vereisten.

#### Vraag: Hoe kan ik omgaan met gecodeerde PDF-documenten met met een wachtwoord beveiligde formuliervelden?

 A: Aspose.PDF voor .NET biedt functies om te werken met gecodeerde PDF-documenten en met een wachtwoord beveiligde formuliervelden. Voordat u het document laadt, kunt u het wachtwoord instellen met behulp van de`pdfDocument.Password` eigenschap om toegang te krijgen tot het beveiligde PDF-document en de formuliervelden ervan.