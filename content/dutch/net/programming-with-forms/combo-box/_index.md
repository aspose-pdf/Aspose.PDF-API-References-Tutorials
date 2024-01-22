---
title: Combinatiebox
linktitle: Combinatiebox
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig een keuzelijst met keuzelijsten in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-forms/combo-box/
---
In deze zelfstudie laten we u zien hoe u een keuzelijst met keuzelijsten kunt maken met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg er eerst voor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar de documentenmap:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een documentobject

Maak een documentobject om het PDF-formulier in te bewaren:

```csharp
Document doc = new Document();
```

## Stap 3: Voeg een pagina toe

Voeg een pagina toe aan het document:

```csharp
doc.Pages.Add();
```

## Stap 4: Instantieer een ComboBoxField-object

Instantieer een ComboBoxField-object met de gewenste afmetingen:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Stap 5: Voeg opties toe aan de vervolgkeuzelijst

Voeg de gewenste opties toe aan de vervolgkeuzelijst:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Stap 6: Voeg de keuzelijst met invoervakken toe aan het formulier

Voeg het ComboBoxField-object toe aan de Document Form Fields-collectie:

```csharp
doc.Form.Add(combo);
```

## Stap 7: Sla het document op

Sla het PDF-document op:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Combo Box met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Documentobject maken
	Document doc = new Document();
	// Pagina toevoegen aan documentobject
	doc.Pages.Add();
	// Instantieer het ComboBox Field-object
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Optie toevoegen aan ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Voeg een combobox-object toe om de veldenverzameling van het documentobject te vormen
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Sla het PDF-document op
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een keuzelijst met keuzelijsten kunt maken met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig een keuzelijst met keuzelijsten aan uw PDF-documenten toevoegen met behulp van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Kan ik het uiterlijk van de keuzelijst met invoervakken aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt het uiterlijk van de keuzelijst met invoervak aanpassen met Aspose.PDF voor .NET. U kunt eigenschappen zoals lettergrootte, kleur, achtergrondkleur, randstijl en meer instellen, zodat deze bij uw gewenste uiterlijk passen.

#### Vraag: Kan ik standaard geselecteerde opties instellen in de keuzelijst met invoervak?

 A: Ja, u kunt standaard geselecteerde opties instellen in de keuzelijst met invoervak met behulp van Aspose.PDF voor .NET. U kunt gebruik maken van de`Selected` eigendom van de`ComboBoxField` object om een of meer opties als standaard geselecteerd te markeren.

#### Vraag: Hoe kan ik de geselecteerde waarde uit de keuzelijst met keuzelijsten ophalen nadat de gebruiker een selectie heeft gemaakt?

 A: U kunt de geselecteerde waarde uit de keuzelijst met invoervakken ophalen met Aspose.PDF voor .NET. Nadat de gebruiker een selectie heeft gemaakt, krijgt u toegang tot het`Value` eigendom van de`ComboBoxField`object om de geselecteerde waarde te verkrijgen.

#### Vraag: Is het mogelijk om gebeurtenishandlers of acties toe te voegen aan de keuzelijst met invoervak?

 A: Ja, met Aspose.PDF voor .NET kunt u gebeurtenishandlers of acties toevoegen aan de keuzelijst met invoervak. U kunt JavaScript-acties koppelen, zoals`OnValueChanged`, naar de keuzelijst met invoervak om specifieke acties uit te voeren wanneer de gebruiker een optie selecteert.

#### Vraag: Kan ik tooltips of beschrijvingen toevoegen aan de opties in de keuzelijst met invoervak?

 A: Ja, u kunt tooltips of beschrijvingen toevoegen aan de opties in de keuzelijst met invoervak met behulp van Aspose.PDF voor .NET. U kunt de`AlternateName` eigenschap van elke optie om tooltip of beschrijving te bieden die wordt weergegeven wanneer de gebruiker over de optie beweegt.