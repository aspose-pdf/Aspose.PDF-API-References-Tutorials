---
title: Keuzerondje met opties
linktitle: Keuzerondje met opties
second_title: Aspose.PDF voor .NET API-referentie
description: Voeg eenvoudig een keuzerondje met opties toe aan een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 230
url: /nl/net/programming-with-forms/radio-button-with-options/
---

In deze tutorial laten we u zien hoe u een radioknop met opties toevoegt aan een PDF-document met Aspose.PDF voor .NET. We leggen de C#-broncode stap voor stap uit om u door dit proces te leiden.

## Stap 1: Voorbereiding

Zorg ervoor dat u de benodigde bibliotheken hebt geïmporteerd en het pad naar uw documentenmap hebt ingesteld:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Een documentobject instantiëren

Instantieer een Document-object om een nieuw PDF-document te maken:

```csharp
Document doc = new Document();
```

## Stap 3: Pagina en tabel toevoegen

Voeg een pagina toe aan het document en maak een tabel om de keuzerondjes in op te slaan:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## Stap 4: Instantieer een RadioButtonField-object

Instantieer een RadioButtonField-object om de keuzerondje weer te geven:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## Stap 5: Voeg keuzerondje-opties toe

Voeg de keuzerondjes toe aan het RadioButtonField-object:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## Stap 6: Pas de opties voor keuzerondjes aan

Pas de opties voor keuzerondjes aan door kenmerken in te stellen zoals rand, tekstkleur en bijschrifttekst:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Herhaal dezelfde stappen voor opt2 en opt3

```

## Stap 7: Voeg de opties voor de keuzerondjes toe aan de tabel

Voeg de keuzerondjes toe aan de tabel om ze weer te geven:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## Stap 8: Sla het PDF-document op

Sla het gemaakte PDF-document op:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Voorbeeldbroncode voor keuzerondje met opties met behulp van Aspose.PDF voor .NET 
```csharp
try
{
	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// Sla het PDF-bestand op
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusie

Gefeliciteerd! U hebt met succes een keuzerondje met opties toegevoegd aan een PDF-document met Aspose.PDF voor .NET. U kunt deze methode nu gebruiken om interactieve formulieren te maken in uw PDF-documenten.