---
title: Horizontaal en verticaal keuzerondjes
linktitle: Horizontaal en verticaal keuzerondjes
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig horizontale en verticale keuzerondjes in uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 180
url: /nl/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
In deze zelfstudie laten we u zien hoe u horizontaal en verticaal gerangschikte keuzerondjes in een PDF-document kunt maken met behulp van Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

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
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Randkleur van keuzerondjes
```

## Stap 4: Voeg horizontale keuzerondjes toe

Voeg keuzerondjes toe die horizontaal zijn gerangschikt door de opties en positie van het veld op te geven:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Stap 5: Voeg verticale keuzerondjes toe

Voeg keuzerondjes toe die verticaal zijn gerangschikt door de opties en positie van het veld op te geven:

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

### Voorbeeldbroncode voor horizontale en verticale keuzerondjes met Aspose.PDF voor .NET 
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
	// Horizontaal keuzerondje toevoegen
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize als de grootte van het keuzerondje-item.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Voeg een ander keuzerondje toe dat verticaal is geplaatst
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

In deze zelfstudie hebben we geleerd hoe u horizontaal en verticaal gerangschikte keuzerondjes in een PDF-document kunt maken met behulp van Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig de lay-out van keuzerondjes aanpassen en deze met Aspose.PDF aan uw PDF-documenten toevoegen.

### Veelgestelde vragen

#### Vraag: Wat zijn horizontaal en verticaal gerangschikte keuzerondjes in een PDF-document?

A: Horizontaal en verticaal geplaatste keuzerondjes in een PDF-document verwijzen naar de lay-outoriëntatie van keuzerondjes. Bij de horizontale lay-out worden de keuzerondjes naast elkaar geplaatst, zodat gebruikers van links naar rechts een selectie kunnen maken. Bij een verticale lay-out worden de keuzerondjes op elkaar gestapeld, zodat gebruikers van boven naar beneden een selectie kunnen maken.

#### Vraag: Hoe pas ik het uiterlijk van de keuzerondjes in Aspose.PDF voor .NET aan?

A: U kunt het uiterlijk van de keuzerondjes in Aspose.PDF voor .NET aanpassen door verschillende eigenschappen aan te passen. De API biedt opties om de afstand tussen twee keuzerondjes in te stellen (`RadioGap`), de lay-outoriëntatie (`RadioHoriz`), de grootte van keuzerondje-items (`RadioButtonItemSize`), de randbreedte en kleur van keuzerondjes, en meer.

#### Vraag: Kan ik zowel horizontale als verticale keuzerondjes aan hetzelfde PDF-document toevoegen?

A: Ja, u kunt zowel horizontale als verticale keuzerondjes aan hetzelfde PDF-document toevoegen met Aspose.PDF voor .NET. De voorbeeldbroncode in de zelfstudie laat zien hoe u eerst horizontaal gerangschikte keuzerondjes toevoegt en vervolgens nog een reeks verticaal gerangschikte keuzerondjes aan hetzelfde PDF-document toevoegt.

#### Vraag: Kan ik voor elke groep keuzerondjes verschillende keuzerondjes instellen?

 A: Ja, u kunt voor elke groep keuzerondjes verschillende opties voor keuzerondjes instellen. Elke groep moet een uniek exemplaar hebben`RadioButtonField` voorwerp, en de`RadioButtonOptionField` objecten binnen elke groep moeten dezelfde pagina en unieke namen voor hun opties delen. Dit zorgt ervoor dat de keuzerondjes binnen elke groep correct functioneren en dat de selecties elkaar uitsluiten.

#### Vraag: Worden de lay-out- en weergave-instellingen van keuzerondjes ondersteund in alle PDF-viewers en -toepassingen?

A: Ja, de lay-out- en weergave-instellingen van keuzerondjes worden ondersteund in alle standaard-compatibele PDF-viewers en -toepassingen. De PDF-specificatie definieert keuzerondjes en hun verschillende attributen, waardoor ze universeel worden herkend in het PDF-formaat. Het is echter essentieel om het uiterlijk en het gedrag van keuzerondjes in verschillende PDF-viewers te testen om consistente weergave op verschillende platforms te garanderen.