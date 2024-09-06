---
title: PDF-formulierveldcoördinaten ophalen
linktitle: PDF-formulierveldcoördinaten ophalen
second_title: Aspose.PDF voor .NET API-referentie
description: Haal eenvoudig PDF-formulierveldcoördinaten op in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-forms/get-coordinates/
---
In deze tutorial laten we u zien hoe u PDF-formulierveldcoördinaten kunt verkrijgen met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en stel het pad naar de documentenmap in:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het uitvoerdocument

Laad het uitvoer-PDF-document:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Stap 3: Zoek toegevoegde velden

Zoek de toegevoegde formuliervelden (in dit voorbeeld gebruiken we de velden "Item1", "Item2" en "Item3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Stap 4: Sub-itemposities voor elk veld weergeven

Blader door de opties voor elk veld en bekijk de coördinaten voor elk subitem:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Voorbeeldbroncode voor Coördinaten ophalen met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laad het uitvoerdocument
	Document doc1 = new Document( dataDir + "input.pdf");
	// Vind toegevoegde velden
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// En toon de posities van de subitems voor elk van hen.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe u formulierveldcoördinaten kunt ophalen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de coördinaten van de subelementen van uw formuliervelden ophalen in uw PDF-documenten met Aspose.PDF.

### Veelgestelde vragen

#### V: Kan ik deze methode gebruiken om coördinaten te verkrijgen voor elk type formulierveld in Aspose.PDF voor .NET?

A: Ja, u kunt deze methode gebruiken om coördinaten te verkrijgen voor verschillende typen formuliervelden in Aspose.PDF voor .NET. De meegeleverde C#-broncode laat zien hoe u coördinaten voor RadioButton-velden kunt verkrijgen, maar u kunt dezelfde aanpak toepassen op andere typen formuliervelden, zoals TextBox, CheckBox, ListBox en meer.

#### V: Hoe kan ik de coördinaten van een formulierveld wijzigen of aanpassen?

A: Formulierveldcoördinaten zijn gebaseerd op het coördinatensysteem van het PDF-document, waarbij de oorsprong (0,0) zich in de linkerbenedenhoek van de pagina bevindt. Om de formulierveldcoördinaten te wijzigen of aan te passen, kunt u de`Rect` eigenschap van het betreffende formulierveld of de subitems daarvan, zoals RadioButtonOptionField.

#### V: Kan ik de coördinaten van formuliervelden programmatisch aan een PDF-document toevoegen?

A: Ja, u kunt de coördinaten van formuliervelden ophalen die programmatisch aan een PDF-document zijn toegevoegd. Met Aspose.PDF voor .NET kunt u formuliervelden dynamisch toevoegen en nadat ze zijn toegevoegd, kunt u hun coördinaten ophalen met behulp van de aanpak die in deze tutorial wordt gedemonstreerd.

#### V: Wat is het doel van het ophalen van formulierveldcoördinaten?

A: Het ophalen van formulierveldcoördinaten kan handig zijn wanneer u specifieke lay-outgerelateerde bewerkingen of validaties op formuliervelden in een PDF-document moet uitvoeren. Hiermee kunt u formuliervelden nauwkeurig positioneren en uitlijnen op basis van hun coördinaten, zodat ze correct in het document worden weergegeven en een naadloze gebruikerservaring bieden.

#### V: Worden de coördinaten van het formulierveld uitgedrukt in punten of een andere eenheid?

A: De formulierveldcoördinaten in Aspose.PDF voor .NET worden uitgedrukt in punten. Eén punt is gelijk aan 1/72 inch, waardoor het een standaard meeteenheid is in het PDF-formaat.