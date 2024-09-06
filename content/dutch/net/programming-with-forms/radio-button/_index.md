---
title: Keuzerondje
linktitle: Keuzerondje
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig keuzerondjes toe aan uw PDF-documenten met Aspose.PDF voor .NET.
type: docs
weight: 220
url: /nl/net/programming-with-forms/radio-button/
---
In deze tutorial laten we je zien hoe je een radioknop toevoegt aan een PDF-document met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om je door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentobject instantiëren

Instantieer een Document-object om een nieuw PDF-document te maken:

```csharp
Document pdfDocument = new Document();
```

## Stap 3: Een pagina toevoegen

Voeg een pagina toe aan het PDF-document:

```csharp
pdfDocument.Pages.Add();
```

## Stap 4: Instantieer een RadioButtonField-object

Instantieer een RadioButtonField-object door het paginanummer als argument op te geven:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Stap 5: Voeg keuzerondje-opties toe

Voeg keuzerondjes toe aan het RadioButtonField-object door de coördinaten van elke optie op te geven met een Rectangle-object:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Stap 6: Voeg de keuzerondje toe aan het formulier

Voeg de keuzerondje toe aan het Form-object van het document:

```csharp
pdfDocument.Form.Add(radio);
```

## Stap 7: Sla het PDF-document op

Sla het gemaakte PDF-document op:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Voorbeeldbroncode voor keuzerondje met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantieer Document object
	Document pdfDocument = new Document();
	// Een pagina toevoegen aan een PDF-bestand
	pdfDocument.Pages.Add();
	// RadioButtonField-object met paginanummer als argument instellen
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Voeg de eerste optie voor een keuzerondje toe en geef ook de oorsprong ervan op met behulp van het Rectangle-object
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Tweede keuzerondje toevoegen
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Keuzerondje toevoegen aan formulierobject van Documentobject
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

In deze tutorial hebben we geleerd hoe je een keuzerondje toevoegt aan een PDF-document met Aspose.PDF voor .NET. Door deze stappen te volgen, kun je eenvoudig een keuzerondje maken en deze op een specifieke pagina in je PDF-document plaatsen.


### Veelgestelde vragen

#### V: Kan ik het uiterlijk van de keuzerondje aanpassen, bijvoorbeeld de grootte en kleur?

 A: Ja, u kunt het uiterlijk van de keuzerondje aanpassen met behulp van de`Rectangle` coördinaten van het object om de grootte en positie ervan te definiëren. Met Aspose.PDF voor .NET kunt u het uiterlijk van de radioknop aanpassen aan uw behoeften.

#### V: Kan ik meerdere keuzerondjes met verschillende groepen op dezelfde pagina toevoegen?

A: Ja, u kunt meerdere radioknoppen met verschillende groepen op dezelfde pagina toevoegen. Elke groep radioknoppen kan een unieke naam hebben en er kan slechts één optie binnen elke groep tegelijk worden geselecteerd.

#### V: Hoe kan ik een label of tekstbeschrijving toevoegen aan de keuzerondjes?

 A: Om een label of tekstbeschrijving toe te voegen aan de opties van de keuzerondjes, kunt u de`TextStamp`klasse van Aspose.PDF voor .NET om tekst op specifieke coördinaten over het PDF-document te leggen.

#### V: Is Aspose.PDF voor .NET compatibel met alle versies van .NET Framework?

A: Ja, Aspose.PDF voor .NET is compatibel met alle versies van .NET Framework, inclusief .NET Core en .NET Standard.

#### V: Kan ik de selectie van een keuzerondje in het PDF-document programmatisch regelen?

 A: Ja, u kunt de selectie van een keuzerondje programmatisch regelen met behulp van de`IsSelected` eigendom van de`RadioButtonOption` klasse. Met deze eigenschap kunt u een specifieke optie als geselecteerd instellen.