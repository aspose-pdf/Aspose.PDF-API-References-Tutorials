---
title: Marges of opvulling
linktitle: Marges of opvulling
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u marges of opvulling in een tabel instelt met Aspose.PDF voor .NET.
type: docs
weight: 140
url: /nl/net/programming-with-tables/margins-or-padding/
---
In deze zelfstudie begeleiden we u stapsgewijs door het gebruik van Aspose.PDF voor .NET om marges of opvulling in een tabel in te stellen. We geven uitleg en codefragmenten om u te helpen deze functionaliteit te begrijpen en te implementeren in uw C#-broncode.

## Stap 1: Het document en de pagina instellen
Om te beginnen moet u het document en de pagina instellen met behulp van de volgende code:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer het Document-object door de lege constructor ervan aan te roepen
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Stap 2: Een tabel maken
Vervolgens gaan we een tabelobject maken met behulp van de klasse Aspose.Pdf.Table:

```csharp
// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
page.Paragraphs.Add(tab1);
```

## Stap 3: Kolombreedten en standaard celrand instellen
Gebruik de volgende code om de kolombreedte en de standaardcelrand van de tabel in te stellen:

```csharp
// Stel de kolombreedten van de tabel in
tab1. ColumnWidths = "50 50 50";
// Stel de standaardcelrand in met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Stap 4: Tabelrand en celopvulling instellen
Om de tabelrand en celopvulling in te stellen, maakt u een MarginInfo-object en stelt u de eigenschappen ervan in:

```csharp
// Maak een MarginInfo-object en stel de linker-, onder-, rechter- en bovenmarges in
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Stel de standaardcelopvulling in op het MarginInfo-object
tab1. DefaultCellPadding = margin;

// Stel de tabelrand in met een ander aangepast BorderInfo-object
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Stap 5: Rijen en cellen toevoegen
Laten we nu rijen en cellen aan de tabel toevoegen. We zullen een nieuwe rij maken en er cellen aan toevoegen:

```csharp
// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Stap 6: Tekst aan cellen toevoegen
Om tekst aan een cel toe te voegen, maakt u een TextFragment-object en voegt u dit toe aan de gewenste cel:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Stap 7: De PDF opslaan
Gebruik de volgende code om het PDF-document op te slaan:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Sla de pdf op
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Voorbeeldbroncode voor marges of opvulling met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Start het Document-object door de lege constructor ervan aan te roepen
Document doc = new Document();
Page page = doc.Pages.Add();
// Een tabelobject instantiëren
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
page.Paragraphs.Add(tab1);
// Ingesteld met kolombreedtes van de tabel
tab1.ColumnWidths = "50 50 50";
// Stel de standaardcelrand in met het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Stel de tabelrand in met een ander aangepast BorderInfo-object
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Maak een MarginInfo-object en stel de linker-, onder-, rechter- en bovenmarges in
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Stel de standaardcelopvulling in op het MarginInfo-object
tab1.DefaultCellPadding = margin;
// Maak rijen in de tabel en vervolgens cellen in de rijen
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 met grote tekstreeks die in de cel moet worden geplaatst");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Rij1.Cellen[2].Paragrafen[0].Vaste breedte= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Bewaar de pdf
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u marges of opvulling in een tabel kunt instellen met Aspose.PDF voor .NET. Deze kennis zal u helpen uw documentopmaakmogelijkheden te verbeteren en uw tabellen visueel aantrekkelijk te maken.

### Veelgestelde vragen

#### Vraag: Kan ik verschillende marges of opvulling instellen voor individuele cellen in een tabel?

A: Ja, u kunt verschillende marges of opvulling instellen voor individuele cellen in een tabel met Aspose.PDF voor .NET. In het gegeven voorbeeld stellen we de standaard celopvulling voor de hele tabel in met behulp van de`DefaultCellPadding` eigendom. Om verschillende opvullingen voor specifieke cellen in te stellen, kunt u toegang krijgen tot het`MarginInfo` van elke cel afzonderlijk en wijzig hun marges.

#### Vraag: Hoe kan ik de randkleur of -stijl van de tabel wijzigen?

 A: Om de randkleur of stijl van de tabel te wijzigen, kunt u de`Color` En`Width` eigenschappen van de`BorderInfo` voorwerp. In het gegeven voorbeeld stellen we de randkleur in op zwart en een breedte van 1F (één punt) met behulp van`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. U kunt de kleur en breedte aanpassen aan uw wensen.

#### Vraag: Is het mogelijk om kop- of voetteksten aan de tabel toe te voegen?

A: Ja, u kunt kop- en voetteksten aan de tabel toevoegen met Aspose.PDF voor .NET. Kop- en voetteksten zijn doorgaans afzonderlijke rijen die aanvullende informatie bevatten, zoals kolomlabels, tabeltitels of samenvattingsgegevens. U kunt extra rijen maken, deze anders opmaken en ze boven of onder de tabelinhoud toevoegen.

#### Vraag: Hoe pas ik de tekstuitlijning binnen een tabelcel aan?

 A: Om de tekstuitlijning binnen een tabelcel aan te passen, kunt u de`HorizontalAlignment` En`VerticalAlignment` eigenschappen van de`TextFragment` voorwerp. Als u de tekst bijvoorbeeld horizontaal wilt centreren, kunt u dit instellen`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Op dezelfde manier kunt u instellen`mytext.VerticalAlignment` om de verticale uitlijning te controleren.

#### Vraag: Kan ik afbeeldingen aan de tabelcellen toevoegen in plaats van tekst?

 A: Ja, u kunt afbeeldingen aan de tabelcellen toevoegen met Aspose.PDF voor .NET. In plaats van het creëren van een`TextFragment` object, kunt u een`Image` object, laad het afbeeldingsbestand en voeg het toe aan de gewenste cel met behulp van de`cell.Paragraphs.Add(image);` methode. Hierdoor kunt u naast tekstinhoud afbeeldingen in de tabel invoegen.