---
title: Waarden ophalen uit alle velden in PDF-document
linktitle: Waarden ophalen uit alle velden in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig de waarden van alle formuliervelden op in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 150
url: /nl/net/programming-with-forms/get-values-from-all-fields/
---
In deze tutorial laten we u zien hoe u de waarden van alle formuliervelden in een PDF-document kunt ophalen met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Open het document

Open het PDF-document:

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Stap 3: Waarden voor alle velden ophalen

Doorloop alle formuliervelden in het document en haal hun namen en waarden op:

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Voorbeeldbroncode voor Waarden ophalen uit alle velden met Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document openen
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Waarden uit alle velden ophalen
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe u de waarden van alle formuliervelden in een PDF-document kunt ophalen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de waarden van alle formuliervelden uit uw PDF-documenten extraheren met Aspose.PDF.

### Veelgestelde vragen

#### V: Kan ik de waarden van formuliervelden wijzigen terwijl ik ze ophaal met Aspose.PDF voor .NET?

 A: Ja, u kunt de waarden van formuliervelden wijzigen terwijl u ze ophaalt met Aspose.PDF voor .NET. Zodra u de`Field` object dat een formulierveld vertegenwoordigt, kunt u de`Value`eigenschap met de gewenste waarde. Nadat u de nodige wijzigingen hebt aangebracht, kunt u het bijgewerkte PDF-document opslaan om de wijzigingen weer te geven.

#### V: Hoe kan ik specifieke formuliervelden filteren en ophalen op basis van hun type (bijvoorbeeld tekstvelden, selectievakjes)?

 A: Om specifieke formuliervelden op te halen op basis van hun typen, kunt u voorwaardelijke statements of LINQ-query's gebruiken om de velden van interesse te filteren. U kunt het type van elk formulierveld controleren met behulp van de veldnaam.`FieldType` eigenschap en haal vervolgens de waarden dienovereenkomstig op.

#### V: Wat gebeurt er als het PDF-document geen formuliervelden heeft?

 A: Als het PDF-document geen formuliervelden bevat,`pdfDocument.Form` property retourneert een lege verzameling. In dergelijke gevallen wordt de lus om waarden op te halen niet uitgevoerd en worden er geen waarden weergegeven.

#### V: Kan ik de waarden van de formuliervelden in een specifieke volgorde ophalen of alfabetisch sorteren?

A: De volgorde waarin de formuliervelden worden opgehaald, is afhankelijk van de onderliggende structuur van het PDF-document. Aspose.PDF voor .NET retourneert de formuliervelden in de volgorde waarin ze aan het document zijn toegevoegd. Als u de formuliervelden in een specifieke volgorde wilt weergeven of verwerken, kunt u aangepaste sorteerlogica implementeren op basis van uw vereisten.

#### V: Hoe kan ik omgaan met versleutelde PDF-documenten met wachtwoordbeveiligde formuliervelden?

 A: Aspose.PDF voor .NET biedt functies om te werken met gecodeerde PDF-documenten en met wachtwoord beveiligde formuliervelden. Voordat u het document laadt, kunt u het wachtwoord instellen met behulp van de`pdfDocument.Password` eigenschap om toegang te krijgen tot het beveiligde PDF-document en de bijbehorende formuliervelden.