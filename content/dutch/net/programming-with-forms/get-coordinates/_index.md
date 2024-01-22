---
title: Ontvang veldcoördinaten voor PDF-formulieren
linktitle: Ontvang veldcoördinaten voor PDF-formulieren
second_title: Aspose.PDF voor .NET API-referentie
description: Ontvang eenvoudig veldcoördinaten van PDF-formulieren in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 120
url: /nl/net/programming-with-forms/get-coordinates/
---
In deze zelfstudie laten we u zien hoe u veldcoördinaten van PDF-formulieren kunt verkrijgen met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar de documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het uitvoerdocument

Laad het uitgevoerde PDF-document:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Stap 3: Zoek toegevoegde velden

Zoek de toegevoegde formuliervelden (in dit voorbeeld gebruiken we de velden 'Item1', 'Item2' en 'Item3'):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Stap 4: Geef subitemposities voor elk veld weer

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

### Voorbeeldbroncode voor Get Coördinaten met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laad het uitvoerdocument
	Document doc1 = new Document( dataDir + "input.pdf");
	// Zoek toegevoegde velden
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// En toon de posities van subitems voor elk van hen.
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

In deze zelfstudie hebben we geleerd hoe u formulierveldcoördinaten kunt verkrijgen met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de coördinaten van de subelementen van uw formuliervelden in uw PDF-documenten ophalen met behulp van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Kan ik deze methode gebruiken om coördinaten op te halen voor elk type formulierveld in Aspose.PDF voor .NET?

A: Ja, u kunt deze methode gebruiken om coördinaten op te halen voor verschillende soorten formuliervelden in Aspose.PDF voor .NET. De meegeleverde C#-broncode laat zien hoe u coördinaten voor RadioButton-velden kunt verkrijgen, maar u kunt dezelfde aanpak aanpassen voor andere typen formuliervelden, zoals TextBox, CheckBox, ListBox en meer.

#### Vraag: Hoe kan ik de veldcoördinaten van het formulier wijzigen of aanpassen?

A: De coördinaten van formuliervelden zijn gebaseerd op het coördinatensysteem van het PDF-document, waarbij de oorsprong (0,0) zich in de linkerbenedenhoek van de pagina bevindt. Om de veldcoördinaten van het formulier te wijzigen of aan te passen, kunt u de`Rect` eigenschap van het betreffende formulierveld of de subitems ervan, zoals RadioButtonOptionField.

#### Vraag: Kan ik de coördinaten van formuliervelden programmatisch aan een PDF-document toevoegen?

A: Ja, u kunt de coördinaten opvragen van formuliervelden die programmatisch aan een PDF-document zijn toegevoegd. Met Aspose.PDF voor .NET kunt u formuliervelden dynamisch toevoegen. Eenmaal toegevoegd kunt u hun coördinaten ophalen met behulp van de aanpak die in deze zelfstudie wordt gedemonstreerd.

#### Vraag: Wat is het doel van het ophalen van formulierveldcoördinaten?

A: Het ophalen van formulierveldcoördinaten kan handig zijn als u specifieke lay-outgerelateerde bewerkingen of validaties op formuliervelden in een PDF-document moet uitvoeren. Hiermee kunt u formuliervelden nauwkeurig positioneren en uitlijnen op basis van hun coördinaten, zodat ze correct in het document verschijnen en een naadloze gebruikerservaring bieden.

#### Vraag: Worden de veldcoördinaten van het formulier uitgedrukt in punten of in een andere eenheid?

A: De formulierveldcoördinaten in Aspose.PDF voor .NET worden uitgedrukt in punten. Eén punt komt overeen met 1/72 inch, waardoor het een standaard meeteenheid is in PDF-formaat.