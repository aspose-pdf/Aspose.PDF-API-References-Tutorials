---
title: Tekstuitlijning voor tabelrijinhoud
linktitle: Tekstuitlijning voor tabelrijinhoud
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u rijinhoud in een PDF-tabel uitlijnt met Aspose.PDF voor .NET.
type: docs
weight: 210
url: /nl/net/programming-with-tables/text-alignment-for-table-row-content/
---
In deze tutorial begeleiden we u stap voor stap bij het uitlijnen van de inhoud van een rij in een tabel van een PDF-document met behulp van Aspose.PDF voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze implementeert.

## Stap 1: Het PDF-document maken
Eerst maken we het PDF-document:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Stap 2: Initialisatie van de tabel
Vervolgens initialiseren we de tabel:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Stap 3: De kleur van de tabelrand instellen
We configureren de kleur van de tabelrand:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Stap 4: De tabelcelrand configureren
We gaan de rand van de tabelcel configureren:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Stap 5: Herhaal de lus om 10 rijen aan de tabel toe te voegen
We gaan nu een lus gebruiken om 10 rijen aan de tabel toe te voegen:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Stap 6: De verticale lijnuitlijning configureren
We gaan de verticale uitlijning van de rijen van de tabel configureren:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Stap 7: Inhoud toevoegen aan rijcellen
We gaan inhoud toevoegen aan de rijcellen:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Stap 8: De tabel toevoegen aan de documentpagina
Laten we nu de tabel aan de documentpagina toevoegen:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Stap 9: Het PDF-document opslaan
Ten slotte slaan we het PDF-document op:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Voorbeeldbroncode voor tekstuitlijning voor tabelrijinhoud met behulp van Aspose.PDF voor .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF-document maken
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Initialiseert een nieuw exemplaar van de tabel
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Stel de kleur van de tabelrand in als Lichtgrijs
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// de rand voor tabelcellen instellen
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// maak een lus om 10 rijen toe te voegen
for (int row_count = 0; row_count < 10; row_count++)
{
	// rij toevoegen aan tabel
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Tabelobject toevoegen aan de eerste pagina van het invoerdocument
tocPage.Paragraphs.Add(table);
// Opslaan bijgewerkt document met tabelobject
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Conclusie
Gefeliciteerd! U hebt nu geleerd hoe u de inhoud van een rij in een tabel in een PDF-document kunt uitlijnen met Aspose.PDF voor .NET. Deze stapsgewijze handleiding liet u zien hoe u een document kunt maken, een tabel kunt initialiseren, de rand en uitlijning kunt configureren, inhoud kunt toevoegen en het PDF-document kunt opslaan. Nu kunt u deze kennis toepassen op uw eigen projecten.

### Veelgestelde vragen

#### V: Hoe kan ik de inhoud van de tabelcellen horizontaal uitlijnen?

 A: U kunt de inhoud van de tabelcellen horizontaal uitlijnen door de`HorizontalAlign` eigenschap van de cel`TextState` object. Om de tekst bijvoorbeeld te centreren, gebruikt u`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Je kunt het ook instellen op`HorizontalAlignment.Left` of`HorizontalAlignment.Right` voor respectievelijk links- en rechtsuitlijning.

#### V: Kan ik verschillende randstijlen en kleuren toepassen op afzonderlijke cellen in de tabel?

 A: Ja, u kunt verschillende randstijlen en kleuren toepassen op afzonderlijke cellen in de tabel. Om de rand voor een specifieke cel aan te passen, stelt u de`cell.Border` eigendom naar een nieuwe`BorderInfo`object met de gewenste instellingen, zoals randzijden, breedte en kleur.

#### V: Hoe kan ik de verticale uitlijning van de tabelinhoud binnen de cellen aanpassen?

 A: U kunt de verticale uitlijning van de tabelinhoud binnen de cellen aanpassen door de`VerticalAlignment` eigenschap van de rij naar`VerticalAlignment.Center`, `VerticalAlignment.Top` , of`VerticalAlignment.Bottom`. Deze eigenschap bepaalt de verticale uitlijning van alle cellen in die rij.

#### V: Is het mogelijk om dynamisch meer kolommen of rijen aan de tabel toe te voegen?

 A: Ja, u kunt dynamisch meer kolommen en rijen aan de tabel toevoegen met behulp van de`table.Rows.Add()` methode om nieuwe rijen toe te voegen en de`row.Cells.Add()` methode om nieuwe cellen aan de rijen toe te voegen. U kunt dit doen binnen lussen of op basis van uw specifieke vereisten.

#### V: Hoe kan ik een achtergrondkleur instellen voor specifieke cellen of voor de hele tabel?

 A: Om een achtergrondkleur voor specifieke cellen of de hele tabel in te stellen, gebruikt u de`BackgroundColor` eigendom van de`Cell` of`Table` object. Om bijvoorbeeld de achtergrondkleur van een cel in te stellen, gebruikt u`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.