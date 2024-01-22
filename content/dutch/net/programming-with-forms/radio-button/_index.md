---
title: Radio knop
linktitle: Radio knop
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig keuzerondjes toe aan uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 220
url: /nl/net/programming-with-forms/radio-button/
---
In deze zelfstudie laten we u zien hoe u een keuzerondje aan een PDF-document toevoegt met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Instantie van een documentobject

Een documentobject instantiëren om een nieuw PDF-document te maken:

```csharp
Document pdfDocument = new Document();
```

## Stap 3: Voeg een pagina toe

Voeg een pagina toe aan het PDF-document:

```csharp
pdfDocument.Pages.Add();
```

## Stap 4: Instantieer een RadioButtonField-object

Instantieer een RadioButtonField-object dat het paginanummer als argument specificeert:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Stap 5: Voeg keuzerondjes toe

Voeg keuzerondjesopties toe aan het RadioButtonField-object door de coördinaten van elke optie op te geven met een Rectangle-object:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Stap 6: Voeg het keuzerondje toe aan het formulier

Voeg het keuzerondje toe aan het formulierobject van het document:

```csharp
pdfDocument.Form.Add(radio);
```

## Stap 7: Sla het PDF-document op

Sla het gemaakte PDF-document op:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Voorbeeldbroncode voor Radio Button met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantieer een documentobject
	Document pdfDocument = new Document();
	// Voeg een pagina toe aan een PDF-bestand
	pdfDocument.Pages.Add();
	// Instatiate RadioButtonField-object met paginanummer als argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Voeg de eerste keuzerondje toe en specificeer ook de oorsprong ervan met behulp van het Rectangle-object
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Voeg een tweede keuzerondje toe
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Keuzerondje toevoegen om object van documentobject te vormen
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Sla het PDF-bestand op
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een keuzerondje kunt toevoegen aan een PDF-document met Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig een keuzerondje maken en deze op een specifieke pagina in uw PDF-document plaatsen.


### Veelgestelde vragen

#### Vraag: Kan ik het uiterlijk van het keuzerondje aanpassen, zoals de grootte en kleur?

 A: Ja, u kunt het uiterlijk van het keuzerondje aanpassen met behulp van de`Rectangle` de coördinaten van het object om de grootte en positie ervan te bepalen. Met Aspose.PDF voor .NET kunt u het uiterlijk van het keuzerondje aanpassen aan uw behoeften.

#### Vraag: Kan ik meerdere keuzerondjes met verschillende groepen op dezelfde pagina toevoegen?

A: Ja, u kunt meerdere keuzerondjes met verschillende groepen op dezelfde pagina toevoegen. Elke groep keuzerondjes kan een unieke naam hebben en binnen elke groep kan slechts één optie tegelijk worden geselecteerd.

#### Vraag: Hoe kan ik een label of tekstbeschrijving toevoegen aan de keuzerondjes?

 A: Om een label of tekstbeschrijving aan de keuzerondjes toe te voegen, kunt u de`TextStamp`klasse van Aspose.PDF voor .NET om tekst op specifieke coördinaten op het PDF-document te plaatsen.

#### Vraag: Is Aspose.PDF voor .NET compatibel met alle versies van .NET Framework?

A: Ja, Aspose.PDF voor .NET is compatibel met alle versies van .NET Framework, inclusief .NET Core en .NET Standard.

#### Vraag: Kan ik de selectie van een keuzerondje in het PDF-document programmatisch beheren?

 A: Ja, u kunt de selectie van een keuzerondje programmatisch beheren met behulp van de`IsSelected` eigendom van de`RadioButtonOption` klas. Met deze eigenschap kunt u een specifieke optie instellen zoals geselecteerd.