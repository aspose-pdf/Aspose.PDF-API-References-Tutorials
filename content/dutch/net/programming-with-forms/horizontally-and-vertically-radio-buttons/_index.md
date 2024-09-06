---
title: Horizontale en verticale keuzerondjes
linktitle: Horizontale en verticale keuzerondjes
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig horizontale en verticale keuzerondjes in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
In deze tutorial laten we u zien hoe u horizontaal en verticaal gerangschikte radioknoppen in een PDF-document kunt maken met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document

Laad het bestaande PDF-document:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Stap 3: Pas de opties voor keuzerondjes aan

Pas de opties voor keuzerondjes aan door de volgende eigenschappen in te stellen:

```csharp
formEditor. RadioGap = 4; // Afstand tussen twee keuzerondjes
formEditor. RadioHoriz = true; //Horizontale indeling van keuzerondjes
formEditor.RadioButtonItemSize = 20; // Grootte van keuzerondjes
formEditor.Facade.BorderWidth = 1; // Breedte van de rand van de keuzerondjes
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Kleur van de rand van de keuzerondjes
```

## Stap 4: Horizontale keuzerondjes toevoegen

Voeg horizontaal gerangschikte keuzerondjes toe door de opties en de positie van het veld op te geven:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Stap 5: Verticale keuzerondjes toevoegen

Voeg verticaal gerangschikte keuzerondjes toe door de opties en de positie van het veld op te geven:

```csharp
formEditor. RadioHoriz = false; // Verticale indeling van keuzerondjes
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Stap 6: Sla het document op

Sla het gewijzigde PDF-document op:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Voorbeeldbroncode voor horizontale en verticale keuzerondjes met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Laad het eerder opgeslagen document
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap is de afstand tussen twee keuzerondjes.
	formEditor.RadioGap = 4;
	// Horizontale radioknop toevoegen
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize is de grootte van het keuzerondje.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Voeg een andere keuzerond toe die verticaal is geplaatst
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Sla het PDF-document op
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze tutorial hebben we geleerd hoe u horizontaal en verticaal gerangschikte keuzerondjes in een PDF-document kunt maken met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de lay-out van keuzerondjes aanpassen en ze toevoegen aan uw PDF-documenten met Aspose.PDF.

### Veelgestelde vragen

#### V: Wat zijn horizontaal en verticaal gerangschikte keuzerondjes in een PDF-document?

A: Horizontaal en verticaal gerangschikte radioknoppen in een PDF-document verwijzen naar de lay-outoriëntatie van radioknopopties. Horizontale lay-out plaatst de radioknopopties naast elkaar, zodat gebruikers van links naar rechts een selectie kunnen maken. Verticale lay-out daarentegen stapelt de radioknopopties boven op elkaar, zodat gebruikers van boven naar beneden een selectie kunnen maken.

#### V: Hoe pas ik het uiterlijk van keuzerondjes in Aspose.PDF voor .NET aan?

A: U kunt het uiterlijk van radioknopopties in Aspose.PDF voor .NET aanpassen door verschillende eigenschappen aan te passen. De API biedt opties om de afstand tussen twee radioknopopties in te stellen (`RadioGap`), de lay-outoriëntatie (`RadioHoriz`), de grootte van de items in de keuzerondjes (`RadioButtonItemSize`), de randbreedte en kleur van keuzerondjes, en meer.

#### V: Kan ik zowel horizontale als verticale keuzerondjes aan hetzelfde PDF-document toevoegen?

A: Ja, u kunt zowel horizontale als verticale radioknoppen toevoegen aan hetzelfde PDF-document met Aspose.PDF voor .NET. De voorbeeldbroncode in de tutorial laat zien hoe u eerst horizontaal gerangschikte radioknoppen toevoegt en vervolgens een andere set verticaal gerangschikte radioknoppen toevoegt aan hetzelfde PDF-document.

#### V: Kan ik voor elke groep keuzerondjes verschillende opties voor keuzerondjes instellen?

 A: Ja, u kunt verschillende radioknopopties instellen voor elke groep radioknoppen. Elke groep moet een unieke`RadioButtonField` object, en de`RadioButtonOptionField` objecten binnen elke groep moeten dezelfde pagina en unieke namen voor hun opties delen. Dit zorgt ervoor dat de keuzerondjes binnen elke groep correct functioneren en de selecties elkaar uitsluiten.

#### V: Worden de lay-out- en weergave-instellingen van keuzerondjes in alle PDF-viewers en -toepassingen ondersteund?

A: Ja, de lay-out en weergave-instellingen van keuzerondjes worden ondersteund in alle standaard-compatibele PDF-viewers en -toepassingen. De PDF-specificatie definieert keuzerondjes en hun verschillende kenmerken, waardoor ze universeel worden herkend in het PDF-formaat. Het is echter essentieel om het uiterlijk en gedrag van keuzerondjes in verschillende PDF-viewers te testen om consistente weergave op verschillende platforms te garanderen.