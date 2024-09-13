---
title: Tabel weergeven in PDF-document
linktitle: Tabel weergeven in PDF-document
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabel in een PDF-document kunt weergeven met Aspose.PDF voor .NET.
type: docs
weight: 170
url: /nl/net/programming-with-tables/render-table/
---
In deze tutorial begeleiden we u stap voor stap bij het weergeven van een tabel in een PDF-document met Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten zien hoe u deze implementeert.

## Stap 1: Het document maken
Eerst maken we een nieuw PDF-document:

```csharp
// Pad naar de documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Een nieuw document maken
Document doc = new Document();
```

## Stap 2: Paginamarges en -oriëntatie configureren
Vervolgens configureren we de paginamarges en stellen we de afdrukstand in op liggend:

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

## Stap 4: Rijen en cellen toevoegen aan de tabel
Vervolgens voegen we rijen en cellen toe aan de tabel met behulp van een lus:

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
Laten we nu de tabel aan de documentpagina toevoegen:

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
// Ik wil graag tabel 1 op de volgende pagina houden...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u een tabel in een PDF-document kunt weergeven met Aspose.PDF voor .NET. Deze stapsgewijze handleiding liet u zien hoe u een document kunt maken, paginamarges en -oriëntatie kunt configureren, een tabel kunt toevoegen en een tabel op een nieuwe pagina kunt weergeven. Nu kunt u deze kennis toepassen op uw eigen projecten.

### FAQ's voor rendertabel in PDF-document

#### V: Hoe kan ik het uiterlijk van de tabel aanpassen, bijvoorbeeld door celkleuren te wijzigen of randen toe te voegen?

 A: Om het uiterlijk van de tabel te wijzigen, kunt u verschillende eigenschappen van de tabel instellen.`Aspose.Pdf.Table` en de cellen ervan. U kunt bijvoorbeeld de`BackgroundColor` eigenschap van cellen om hun achtergrondkleur te veranderen. U kunt ook de`Border` eigenschap van de tabel of afzonderlijke cellen om randen toe te voegen. Daarnaast kunt u het lettertype, de tekstkleur en de uitlijning van de tabelinhoud aanpassen door de`TextState` van de`TextFragment` objecten die aan de cellen zijn toegevoegd.

#### V: Kan ik kop- of voetteksten aan de tabel toevoegen?

A: Ja, u kunt kop- of voetteksten toevoegen aan de tabel door extra rijen aan het begin of einde van de tabel te maken en de juiste inhoud in de cellen in te stellen. U kunt de kop- of voetteksten onafhankelijk van de rest van de tabelinhoud aanpassen door verschillende stijlen of inhoud toe te voegen aan deze specifieke rijen.

#### V: Hoe kan ik de positie van de tabel op de pagina bepalen?

A: Om de positie van de tabel op de pagina te bepalen, kunt u de`MarginInfo` van de`PageInfo` voorwerp. Het`MarginInfo` kunt u de linker-, rechter-, boven- en ondermarges van de pagina instellen, wat invloed heeft op de beschikbare ruimte voor de tabel. U kunt ook de`PositioningType` eigendom van de`Aspose.Pdf.Table` om de horizontale en verticale uitlijning binnen het inhoudsgebied van de pagina te regelen.

#### V: Kan ik de tabel exporteren naar verschillende bestandsformaten, zoals Excel of CSV?

A: Aspose.PDF voor .NET is primair ontworpen voor het werken met PDF-documenten. Hoewel het PDF-document kan worden geëxporteerd als een afbeelding of XPS, ondersteunt het niet rechtstreeks het exporteren van tabellen naar formaten zoals Excel of CSV. Om de tabelgegevens te exporteren naar verschillende bestandsformaten, moet u mogelijk extra bibliotheken of methoden gebruiken om de PDF-inhoud te converteren naar het gewenste formaat.

#### V: Hoe kan ik hyperlinks toevoegen aan de tabelcellen?

 A: Om hyperlinks aan de tabelcellen toe te voegen, kunt u de`Aspose.Pdf.WebHyperlink` klasse om een hyperlink te maken en deze vervolgens als anker toe te voegen aan de`TextFragment`binnen de cel. Hiermee kunt u een URL of linkdoel koppelen aan specifieke tekst of content binnen de cel, waardoor klikbare hyperlinks ontstaan.