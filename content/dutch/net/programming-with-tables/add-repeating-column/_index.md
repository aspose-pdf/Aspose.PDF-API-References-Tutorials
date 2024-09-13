---
title: Herhalende kolom toevoegen in PDF-document
linktitle: Herhalende kolom toevoegen in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een herhalende kolom toevoegt aan een PDF-document met Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-tables/add-repeating-column/
---
In deze tutorial gaan we leren hoe je een herhalende kolom toevoegt aan een PDF-document met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet je hoe je een tabel met een herhalende kolom maakt in een PDF-document. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg er eerst voor dat u uw C#-ontwikkelomgeving hebt ingesteld met Aspose.PDF voor .NET. Voeg de referentie toe aan de bibliotheek en importeer de benodigde naamruimten.

## Stap 2: Het PDF-document maken
In deze stap maken we een nieuw PDF-document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

We hebben een leeg PDF-document gemaakt waar we inhoud aan kunnen toevoegen.

## Stap 3: De tabellen aanmaken
In deze stap maken we een hoofdtabel (`outerTable`) en een geneste tabel (`mytable`) die in de kolom herhaald wordt.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

We hebben tabeleigenschappen gespecificeerd, zoals kolombreedte en geneste tabelonderbrekingsmodus.

## Stap 4: De tabellen aan het document toevoegen
Nu voegen we de gemaakte tabellen toe aan het PDF-document.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

We voegen eerst de hoofdtabel toe (`outerTable`) aan het PDF-document. Vervolgens voegen we de geneste tabel (`mytable` ) als een alinea in een cel in de hoofdtabel. We specificeren ook het aantal herhaalde kolommen voor`mytable` (in dit voorbeeld 5 kolommen).

## Stap 5: Kopteksten en regels toevoegen
Nu voegen we de kopteksten en rijen toe aan de tabel.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//Voeg hier andere headers toe

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Voeg hier de andere kolommen toe
}
```

We voegen eerst de headers toe aan de eerste rij van de tabel (`headerRow`). Vervolgens voegen we de rijen met gegevens uit een lus toe. In dit voorbeeld voegen we 6 rijen met gegevens toe.

## Stap 6: Het PDF-document opslaan
Ten slotte slaan we het PDF-document op in het opgegeven bestand.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Zorg ervoor dat u de juiste map en bestandsnaam opgeeft om het PDF-uitvoerbestand op te slaan.

### Voorbeeldbroncode voor het toevoegen van een herhalende kolom met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Een nieuw document maken
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Instantieer een buitenste tabel die de hele pagina beslaat
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Instantieer een tabelobject dat genest zal worden binnen outerTable dat zal breken binnen dezelfde pagina
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Voeg de outerTable toe aan de pagina-alinea's
// Voeg mytable toe aan outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Koptekstrij toevoegen
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Maak rijen in de tabel en vervolgens cellen in de rijen
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Conclusie
In deze tutorial hebben we geleerd hoe je een herhalende kolom toevoegt aan een PDF-document met Aspose.PDF voor .NET. Je kunt deze stapsgewijze handleiding gebruiken om tabellen met herhalende kolommen te maken in je eigen C#-projecten.

### FAQ's voor het toevoegen van een herhalende kolom in een PDF-document

#### V: Kan ik het aantal herhaalde kolommen in de geneste tabel aanpassen?

 A: Ja, u kunt het aantal herhaalde kolommen in de geneste tabel aanpassen. In het gegeven voorbeeld stellen we in`mytable.RepeatingColumnsCount = 5;`, wat betekent dat er 5 herhaalde kolommen zullen zijn. U kunt deze waarde wijzigen naar elk gewenst nummer.

#### V: Is het mogelijk om dynamisch meer rijen aan de geneste tabel toe te voegen?

A: Ja, u kunt dynamisch meer rijen toevoegen aan de geneste tabel op dezelfde manier als getoond in de tutorial. U kunt lussen of andere logica gebruiken om rijen toe te voegen op basis van uw gegevens.

#### V: Kan ik stijlen en opmaak toepassen op de tabel en de cellen daarin?

A: Ja, u kunt stijlen en opmaak toepassen op de tabel en de cellen met Aspose.PDF voor .NET. De bibliotheek biedt verschillende eigenschappen en methoden om het uiterlijk van de tabel en de inhoud ervan aan te passen.

#### V: Is Aspose.PDF voor .NET compatibel met .NET Core?

A: Ja, Aspose.PDF voor .NET is compatibel met .NET Core. U kunt het gebruiken in zowel .NET Framework als .NET Core-applicaties.

#### V: Kan ik deze aanpak gebruiken om herhalende kolommen toe te voegen aan een bestaand PDF-document?

A: Ja, u kunt deze aanpak gebruiken om herhalende kolommen toe te voegen aan een bestaand PDF-document. Laad het bestaande document eenvoudigweg met Aspose.PDF voor .NET en volg dezelfde stappen om de herhalende kolom te maken en toe te voegen.