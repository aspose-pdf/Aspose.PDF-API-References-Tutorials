---
title: Tabel renderen in PDF-document
linktitle: Tabel renderen in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabel in een PDF-document kunt weergeven met Aspose.PDF voor .NET.
type: docs
weight: 170
url: /nl/net/programming-with-tables/render-table/
---
In deze zelfstudie begeleiden we u stap voor stap bij het weergeven van een tabel in een PDF-document met Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze kunt implementeren.

## Stap 1: Het document aanmaken
Eerst maken we een nieuw PDF-document:

```csharp
// Pad naar de documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak een nieuw document
Document doc = new Document();
```

## Stap 2: Paginamarges en oriëntatie configureren
Vervolgens configureren we de paginamarges en stellen we de oriëntatie in op de liggende modus:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Stap 3: De tabel en kolommen maken
Laten we nu een tabel maken en de kolombreedtes instellen:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Stap 4: Voeg rijen en cellen toe aan de tabel
Vervolgens voegen we rijen en cellen aan de tabel toe met behulp van een lus:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Stap 5: De tabel aan de pagina toevoegen
Laten we nu de tabel toevoegen aan de documentpagina:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Stap 6: De tabel op een nieuwe pagina weergeven
Vervolgens maken we een nieuwe tabel en stellen we de eigenschap "IsInNewPage" in op "true" om de tabel op een nieuwe pagina weer te geven:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Stap 7: PDF opslaan
Ten slotte slaan we het PDF-document op:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Voorbeeldbroncode voor Render Table met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Pagina toegevoegd.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Ik wil tabel 1 behouden op de volgende pagina, alstublieft...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u een tabel in een PDF-document kunt weergeven met Aspose.PDF voor .NET. In deze stapsgewijze handleiding werd uitgelegd hoe u een document maakt, de paginamarges en -richting configureert, een tabel toevoegt en een tabel op een nieuwe pagina weergeeft. Nu kunt u deze kennis toepassen op uw eigen projecten.

### Veelgestelde vragen over de rendertabel in PDF-document

#### Vraag: Hoe kan ik het uiterlijk van de tabel wijzigen, zoals het wijzigen van de celkleuren of het toevoegen van randen?

A: Om het uiterlijk van de tabel te wijzigen, kunt u verschillende eigenschappen van de tabel instellen`Aspose.Pdf.Table` en zijn cellen. U kunt bijvoorbeeld de`BackgroundColor` eigenschap van cellen om hun achtergrondkleur te veranderen. U kunt ook de`Border` eigenschap van de tabel of individuele cellen om randen toe te voegen. Bovendien kunt u het lettertype, de tekstkleur en de uitlijning van de tabelinhoud aanpassen door de`TextState` van de`TextFragment` objecten die aan de cellen zijn toegevoegd.

#### Vraag: Kan ik kop- of voetteksten aan de tabel toevoegen?

A: Ja, u kunt kop- en voetteksten aan de tabel toevoegen door extra rijen aan het begin of einde van de tabel te maken en de juiste inhoud in de cellen in te stellen. U kunt de kop- en voetteksten onafhankelijk van de rest van de tabelinhoud aanpassen door verschillende stijlen of inhoud aan deze specifieke rijen toe te voegen.

#### Vraag: Hoe kan ik de positie van de tabel op de pagina bepalen?

 A: Om de positie van de tabel op de pagina te bepalen, kunt u de`MarginInfo` van de`PageInfo` voorwerp. De`MarginInfo`Hiermee kunt u de linker-, rechter-, boven- en ondermarges van de pagina instellen, wat van invloed is op de beschikbare ruimte voor de tabel. Je kunt ook gebruik maken van de`PositioningType` eigendom van de`Aspose.Pdf.Table` om de horizontale en verticale uitlijning binnen het inhoudsgebied van de pagina te bepalen.

#### Vraag: Kan ik de tabel exporteren naar verschillende bestandsformaten, zoals Excel of CSV?

A: Aspose.PDF voor .NET is voornamelijk ontworpen voor het werken met PDF-documenten. Hoewel het het PDF-document als afbeelding of XPS kan exporteren, ondersteunt het niet direct het exporteren van tabellen naar formaten zoals Excel of CSV. Als u de tabelgegevens naar verschillende bestandsindelingen wilt exporteren, moet u mogelijk extra bibliotheken of methoden gebruiken om de PDF-inhoud naar de gewenste indeling te converteren.

#### Vraag: Hoe kan ik hyperlinks naar de tabelcellen toevoegen?

 A: Om hyperlinks naar de tabelcellen toe te voegen, kunt u de`Aspose.Pdf.WebHyperlink` klasse om een hyperlink te maken en deze vervolgens toe te voegen als anker aan de`TextFragment`binnen de cel. Hierdoor kunt u een URL of linkdoel koppelen aan specifieke tekst of inhoud in de cel, waardoor klikbare hyperlinks ontstaan.