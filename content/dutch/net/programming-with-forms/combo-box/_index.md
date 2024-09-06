---
title: Keuzelijst
linktitle: Keuzelijst
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig een keuzelijst met invoervak in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 30
url: /nl/net/programming-with-forms/combo-box/
---
In deze tutorial laten we je zien hoe je een combo box-lijst maakt met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om je door dit proces te leiden.

## Stap 1: Voorbereiding

Controleer eerst of u de benodigde bibliotheken hebt geïmporteerd en stel het pad naar de documentenmap in:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Een documentobject maken

Maak een Document-object om het PDF-formulier vast te houden:

```csharp
Document doc = new Document();
```

## Stap 3: Een pagina toevoegen

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

## Stap 6: Voeg de keuzelijst met invoervak toe aan het formulier

Voeg het ComboBoxField-object toe aan de verzameling Document Form Fields:

```csharp
doc.Form.Add(combo);
```

## Stap 7: Sla het document op

Sla het PDF-document op:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Combo Box met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Documentobject maken
	Document doc = new Document();
	// Pagina toevoegen aan documentobject
	doc.Pages.Add();
	// Instantieer ComboBox-veldobject
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Optie toevoegen aan ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Voeg een keuzelijstobject toe aan de verzameling formuliervelden van het documentobject
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

In deze tutorial hebben we geleerd hoe u een keuzelijst met invoervak kunt maken met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig een keuzelijst met invoervak toevoegen aan uw PDF-documenten met Aspose.PDF.

### Veelgestelde vragen

#### V: Kan ik het uiterlijk van de keuzelijst met invoervak aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt het uiterlijk van de keuzelijst aanpassen met Aspose.PDF voor .NET. U kunt eigenschappen zoals lettergrootte, kleur, achtergrondkleur, randstijl en meer instellen om aan te sluiten bij uw gewenste look en feel.

#### V: Kan ik standaard geselecteerde opties in de keuzelijst met keuzelijsten instellen?

 A: Ja, u kunt standaard geselecteerde opties instellen in de keuzelijst met keuzelijsten met behulp van Aspose.PDF voor .NET. U kunt de`Selected` eigendom van de`ComboBoxField` object om een of meer opties als standaard geselecteerd te markeren.

#### V: Hoe kan ik de geselecteerde waarde uit de keuzelijst met invoervak ophalen nadat de gebruiker een selectie heeft gemaakt?

 A: U kunt de geselecteerde waarde ophalen uit de keuzelijst met keuzelijsten met Aspose.PDF voor .NET. Nadat de gebruiker een selectie heeft gemaakt, kunt u de`Value` eigendom van de`ComboBoxField`object om de geselecteerde waarde te verkrijgen.

#### V: Is het mogelijk om gebeurtenis-handlers of acties toe te voegen aan de keuzelijst met invoervak?

 A: Ja, Aspose.PDF voor .NET staat u toe om event handlers of acties toe te voegen aan de combo box lijst. U kunt JavaScript acties associëren, zoals`OnValueChanged`, naar de keuzelijst met invoervak om specifieke acties uit te voeren wanneer de gebruiker een optie selecteert.

#### V: Kan ik tooltips of beschrijvingen toevoegen aan de opties in de keuzelijst met invoervak?

 A: Ja, u kunt tooltips of beschrijvingen toevoegen aan de opties in de keuzelijst met keuzelijsten met Aspose.PDF voor .NET. U kunt de`AlternateName` eigenschap van elke optie om een tooltip of beschrijving te bieden die wordt weergegeven wanneer de gebruiker over de optie beweegt.