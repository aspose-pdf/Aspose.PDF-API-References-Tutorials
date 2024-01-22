---
title: Gegroepeerde selectievakjes in PDF-document
linktitle: Gegroepeerde selectievakjes in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Maak eenvoudig gegroepeerde selectievakjes in een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 170
url: /nl/net/programming-with-forms/grouped-check-boxes/
---
In deze zelfstudie laten we u zien hoe u gegroepeerde selectievakjes in een PDF-document kunt maken met behulp van Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te begeleiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken heeft geïmporteerd en stel het pad in naar uw documentenmap:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Instantie van een documentobject

Een documentobject instantiëren:

```csharp
Document pdfDocument = new Document();
```

## Stap 3: Pagina toevoegen aan PDF-document

Voeg een pagina toe aan het PDF-document:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Stap 4: Instantieer een RadioButtonField-object

Instantieer een RadioButtonField-object met het paginanummer als argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Stap 5: Voeg keuzerondjes toe

Voeg keuzerondjesopties toe met behulp van het RadioButtonOptionField-object en specificeer hun positie met behulp van het Rectangle-object:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Stap 6: Pas de keuzerondjesopties aan

Pas de opties voor keuzerondjes aan door hun stijl, rand en uiterlijk in te stellen:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Stap 7: Voeg de keuzerondjes toe aan het formulier

Voeg de keuzerondjes toe aan het documentformulierobject:

```csharp
pdfDocument.Form.Add(radio);
```

## Stap 8: Sla het document op

Sla het PDF-document op:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Voorbeeldbroncode voor gegroepeerde selectievakjes met Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantieer een documentobject
	Document pdfDocument = new Document();
	// Voeg een pagina toe aan een PDF-bestand
	Page page = pdfDocument.Pages.Add();
	// Instatiate RadioButtonField-object met paginanummer als argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Voeg de eerste keuzerondje toe en specificeer ook de oorsprong ervan met behulp van het Rectangle-object
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Keuzerondje toevoegen om object van documentobject te vormen
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Sla het PDF-document op
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u gegroepeerde selectievakjes in een PDF-document kunt maken met behulp van Aspose.PDF voor .NET. Door deze stappen te volgen, kunt u eenvoudig aangepaste keuzerondjes toevoegen en deze bundelen in uw PDF-documenten met behulp van Aspose.PDF.

### Veelgestelde vragen

#### Vraag: Wat zijn gegroepeerde selectievakjes in een PDF-document?

A: Gegroepeerde selectievakjes in een PDF-document verwijzen naar een reeks keuzerondjes die bij elkaar zijn gegroepeerd. Met keuzerondjes kunnen gebruikers slechts één optie selecteren uit een groep elkaar uitsluitende keuzes. Wanneer één keuzerondje is geselecteerd, worden de andere in dezelfde groep automatisch gedeselecteerd. Dit groeperingsgedrag is handig als u gebruikers meerdere opties wilt bieden, maar hun selectie wilt beperken tot slechts één keuze.

#### Vraag: Kan ik het uiterlijk van gegroepeerde selectievakjes in Aspose.PDF voor .NET aanpassen?

A: Ja, u kunt het uiterlijk van gegroepeerde selectievakjes in Aspose.PDF voor .NET aanpassen. De API biedt verschillende opties om de stijl, rand en weergave van keuzerondjes in te stellen. U kunt de positie van elke optie definiëren, kiezen tussen verschillende kaderstijlen (bijvoorbeeld vierkant, cirkel, kruis) en de randeigenschappen aanpassen om de gewenste visuele weergave te verkrijgen.

#### Vraag: Hoe voeg ik gegroepeerde selectievakjes toe aan een specifieke pagina in een PDF-document?

A: Om gegroepeerde selectievakjes aan een specifieke pagina in een PDF-document toe te voegen, moet u een`RadioButtonField` object met het gewenste paginanummer als argument. Creëer vervolgens`RadioButtonOptionField` objecten die elke keuzerondje vertegenwoordigen en specificeer hun positie met behulp van de`Rectangle` voorwerp. Voeg ten slotte deze opties toe aan het`RadioButtonField` en pas hun uiterlijk indien nodig aan voordat u de`RadioButtonField` naar het documentformulier.

#### Vraag: Kan ik meerdere groepen selectievakjes toevoegen aan één PDF-document?

 A: Ja, u kunt meerdere groepen selectievakjes aan één PDF-document toevoegen. Elke groep moet een uniek exemplaar hebben`RadioButtonField` voorwerp, en de`RadioButtonOptionField` objecten binnen elke groep moeten dezelfde pagina en unieke namen voor hun opties delen. Dit zorgt ervoor dat de keuzerondjes binnen elke groep correct functioneren en dat de selecties elkaar uitsluiten.

#### Vraag: Worden gegroepeerde selectievakjes ondersteund in alle PDF-viewers en -toepassingen?

A: Ja, gegroepeerde selectievakjes worden ondersteund in alle standaard-compatibele PDF-viewers en -toepassingen. De PDF-specificatie definieert keuzerondjes en hun groeperingsgedrag, waardoor ze universeel worden herkend in het PDF-formaat. Het is echter essentieel om de functionaliteit in verschillende PDF-viewers te testen om consistent gedrag op verschillende platforms te garanderen.