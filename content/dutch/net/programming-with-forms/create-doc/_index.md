---
title: Document maken
linktitle: Document maken
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig een document met keuzerondjes met Aspose.PDF voor .NET.
type: docs
weight: 40
url: /nl/net/programming-with-forms/create-doc/
---
In deze tutorial laten we je zien hoe je een document met keuzerondjes maakt met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om je door dit proces te leiden.

##Stap 1: Voorbereiding

Controleer eerst of u de benodigde bibliotheken hebt geïmporteerd en stel het pad naar de documentenmap in:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document

Maak een nieuw Document-object om het PDF-document in op te slaan:

```csharp
Document doc = new Document();
```

## Stap 3: Een pagina toevoegen

Voeg een nieuwe pagina toe aan het document:

```csharp
Page page = doc.Pages.Add();
```

## Stap 4: Een keuzerondje toevoegen

Maak een keuzerondjeveld en stel de positie en grootte ervan in:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Stap 5: Voeg keuzerondje-opties toe

Voeg de gewenste opties toe aan het radioknopveld. U kunt de coördinaten en grootte van elke optie naar wens instellen:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Stap 6: Voeg het keuzerondje toe aan het formulier

Voeg het keuzerondje toe aan de verzameling Documentformuliervelden:

```csharp
doc.Form.Add(field);
```

## Stap 7: Sla het document op

Sla het PDF-document op:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor Create Doc met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Een nieuw document maken
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Keuzerondjeveld toevoegen
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Voeg opties voor keuzerondjes toe. Let op: deze opties bevinden zich
	// Noch horizontaal, noch verticaal.
	// U kunt proberen om de gewenste coördinaten (en zelfs de grootte) in te stellen.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Sla het PDF-document op
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe je een document met keuzerondjes maakt met Aspose.PDF voor .NET. Door deze stappen te volgen, kun je eenvoudig keuzerondjes toevoegen aan je PDF-documenten met Aspose.PDF.

### Veelgestelde vragen

#### V: Kan ik het uiterlijk van de keuzerondjes in het document aanpassen met Aspose.PDF voor .NET?

A: Ja, u kunt het uiterlijk van de keuzerondjes in het document aanpassen met Aspose.PDF voor .NET. U kunt eigenschappen instellen zoals grootte, kleur, randstijl en meer om het uiterlijk van de keuzerondjes aan te passen.

#### V: Hoe kan ik groepen keuzerondjes toevoegen met opties die elkaar uitsluiten?

A: Om wederzijds exclusieve opties te creëren, kunt u meerdere radioknopvelden met dezelfde naam toevoegen. Dit zorgt ervoor dat wanneer één optie wordt geselecteerd, de andere opties met dezelfde naam automatisch worden gedeselecteerd.

#### V: Is het mogelijk om een standaard geselecteerde optie voor de keuzerondjes in te stellen?

A: Ja, u kunt een standaard geselecteerde optie voor de keuzerondjes instellen met Aspose.PDF voor .NET. U kunt de`Selected` eigendom van de`RadioButtonOptionField` object om een optie als standaard geselecteerd te markeren.

#### V: Kan ik gebeurtenis-handlers toevoegen aan de keuzerondjes?

 A: Ja, u kunt event handlers toevoegen aan de keuzerondjes met Aspose.PDF voor .NET. U kunt JavaScript-acties koppelen, zoals`OnValueChanged`, naar de keuzerondjes om specifieke acties uit te voeren wanneer de gebruiker een optie selecteert.

#### V: Hoe kan ik de geselecteerde optie uit de keuzerondjesgroep ophalen nadat de gebruiker een selectie heeft gemaakt?

 A: U kunt de geselecteerde optie ophalen uit de radioknopgroep met Aspose.PDF voor .NET. Nadat de gebruiker een selectie heeft gemaakt, kunt u de`Selected` eigendom van de`RadioButtonOptionField` object om te controleren welke optie is geselecteerd.