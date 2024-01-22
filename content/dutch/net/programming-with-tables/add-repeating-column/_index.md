---
title: Voeg een herhalende kolom toe aan een PDF-document
linktitle: Voeg een herhalende kolom toe aan een PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een herhalende kolom aan een PDF-document toevoegt met Aspose.PDF voor .NET.
type: docs
weight: 20
url: /nl/net/programming-with-tables/add-repeating-column/
---
In deze zelfstudie leren we hoe u een herhalende kolom aan een PDF-document kunt toevoegen met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet u hoe u een tabel met een herhalende kolom in een PDF-document kunt maken. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg er eerst voor dat u uw C#-ontwikkelomgeving hebt ingesteld met Aspose.PDF voor .NET. Voeg de verwijzing naar de bibliotheek toe en importeer de benodigde naamruimten.

## Stap 2: Het PDF-document maken
In deze stap maken we een nieuw PDF-document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

We hebben een leeg PDF-document gemaakt waar we inhoud kunnen toevoegen.

## Stap 3: De tabellen maken
In deze stap maken we een hoofdtabel (`outerTable`) en een geneste tabel (`mytable`) die in de kolom wordt herhaald.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

We hebben tabeleigenschappen opgegeven, zoals kolombreedte en geneste tabelafbrekingsmodus.

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

We voegen eerst de hoofdtabel toe (`outerTable`) naar het PDF-document. Vervolgens voegen we de geneste tabel toe (`mytable` ) als alinea in een cel in de hoofdtabel. We specificeren ook het aantal herhaalde kolommen voor`mytable` (in dit voorbeeld 5 kolommen).

## Stap 5: Kopteksten en regels toevoegen
Nu voegen we de kopteksten en rijen toe aan de tabel.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Voeg hier andere headers toe

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Voeg hier de overige kolommen toe
}
```

We voegen eerst de kopteksten toe aan de eerste rij van de tabel (`headerRow`). Vervolgens voegen we de rijen met gegevens uit een lus toe. In dit voorbeeld voegen we zes rijen met gegevens toe.

## Stap 6: Het PDF-document opslaan
Ten slotte slaan we het PDF-document op in het opgegeven bestand.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Zorg ervoor dat u de juiste map en bestandsnaam opgeeft om het uitgevoerde PDF-bestand op te slaan.

### Voorbeeldbroncode voor het toevoegen van herhalende kolommen met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Maak een nieuw document
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Creëer een buitenste tabel die de hele pagina beslaat
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Instantieer een tabelobject dat wordt genest in outsideTable en dat op dezelfde pagina wordt afgebroken
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Voeg de buitenste tabel toe aan de paginaparagrafen
// Voeg mijntabel toe aan buitensteTabel
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Voeg koprij toe
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
In deze zelfstudie hebben we geleerd hoe u een herhalende kolom aan een PDF-document kunt toevoegen met Aspose.PDF voor .NET. U kunt deze stapsgewijze handleiding gebruiken om tabellen met herhalende kolommen te maken in uw eigen C#-projecten.

### Veelgestelde vragen over het toevoegen van herhalende kolommen aan een PDF-document

#### Vraag: Kan ik het aantal herhaalde kolommen in de geneste tabel aanpassen?

 A: Ja, u kunt het aantal herhaalde kolommen in de geneste tabel aanpassen. In het gegeven voorbeeld stellen we in`mytable.RepeatingColumnsCount = 5;`, wat betekent dat er vijf herhaalde kolommen zijn. U kunt deze waarde wijzigen in elk gewenst getal.

#### Vraag: Is het mogelijk om dynamisch meer rijen aan de geneste tabel toe te voegen?

A: Ja, u kunt dynamisch meer rijen toevoegen aan de geneste tabel, op dezelfde manier als getoond in de tutorial. U kunt lussen of andere logica gebruiken om rijen toe te voegen op basis van uw gegevens.

#### Vraag: Kan ik stijlen en opmaak toepassen op de tabel en de cellen ervan?

A: Ja, u kunt stijlen en opmaak toepassen op de tabel en de cellen ervan met behulp van Aspose.PDF voor .NET. De bibliotheek biedt verschillende eigenschappen en methoden om het uiterlijk van de tabel en de inhoud ervan aan te passen.

#### Vraag: Is Aspose.PDF voor .NET compatibel met .NET Core?

A: Ja, Aspose.PDF voor .NET is compatibel met .NET Core. U kunt het gebruiken in zowel .NET Framework- als .NET Core-toepassingen.

#### Vraag: Kan ik deze aanpak gebruiken om herhalende kolommen toe te voegen aan een bestaand PDF-document?

A: Ja, u kunt deze aanpak gebruiken om herhalende kolommen toe te voegen aan een bestaand PDF-document. Laad eenvoudigweg het bestaande document met Aspose.PDF voor .NET en volg dezelfde stappen om de herhalende kolom te maken en toe te voegen.