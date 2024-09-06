---
title: HTML-tags in tabel in PDF-bestand
linktitle: HTML-tags in tabel in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-tags in een tabel in een PDF-bestand gebruikt met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-tables/html-tags-inside-table/
---
In deze tutorial gaan we leren hoe je HTML-tags gebruikt in een tabel in een PDF-document met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet je hoe je HTML-inhoud in een tabel in een PDF-document invoegt. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg ervoor dat u uw C#-ontwikkelomgeving hebt geconfigureerd met Aspose.PDF voor .NET. Voeg de referentie toe aan de bibliotheek en importeer de benodigde naamruimten.

## Stap 2: Tabelgegevens maken
We maken een DataTable met een "data" kolom van het type String. Vervolgens voegen we rijen toe aan deze DataTable met behulp van HTML-inhoud.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Stap 3: Het document en de tabel maken
We maken een nieuw PDF-document en voegen een pagina toe aan dit document. Vervolgens initialiseren we een instantie van de klasse Table en stellen we de tabeleigenschappen in.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Stap 4: Gegevens importeren in de tabel
We importeren de gegevens uit de DataTable in de tabel met behulp van de methode "ImportDataTable". We specificeren methodeparameters om aan te geven welk bereik van rijen en kolommen van de DataTable geïmporteerd moet worden.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Stap 5: De tabel aan het document toevoegen
We voegen de tabel toe aan de documentpagina.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Fase 6: Het document opslaan
We slaan het PDF-document op met de tabel met HTML-inhoud.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Voorbeeldbroncode voor HTML-tags in tabel met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Initialiseert een nieuw exemplaar van de tabel
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Kolombreedtes van de tabel instellen
tableProvider.ColumnWidths = "400 50 ";
// Stel de kleur van de tabelrand in als Lichtgrijs
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// De rand voor tabelcellen instellen
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Conclusie
In deze tutorial hebben we geleerd hoe je HTML-tags gebruikt in een tabel in een PDF-document met Aspose.PDF voor .NET. Je kunt deze stapsgewijze handleiding gebruiken om HTML-inhoud in tabelcellen in een PDF-document in te voegen met C#.

### Veelgestelde vragen over HTML-tags in de tabel in een PDF-bestand

#### V: Kan ik andere HTML-tags en -attributen gebruiken in de tabelcellen?

 A: Ja, u kunt verschillende HTML-tags en -attributen gebruiken in de tabelcellen, zoals`<b>`, `<i>`, `<a>`en nog veel meer. Aspose.PDF voor .NET ondersteunt een breed scala aan HTML-elementen en -stijlen die u kunt gebruiken om de inhoud in de tabelcellen op te maken.

#### V: Kan ik CSS-stijlen toepassen op de HTML-inhoud in de tabelcellen?

A: Ja, u kunt CSS-stijlen toepassen op de HTML-inhoud in de tabelcellen. Aspose.PDF voor .NET biedt ondersteuning voor basis-CSS-stijlen die kunnen worden toegepast op de HTML-elementen.

#### V: Is het mogelijk om afbeeldingen samen met HTML-inhoud toe te voegen in de tabelcellen?

 A: Ja, u kunt afbeeldingen samen met HTML-inhoud toevoegen in de tabelcellen. U kunt HTML gebruiken`<img>` tags om afbeeldingen uit verschillende bronnen op te nemen, zoals lokale bestanden of URL's.

#### V: Hoe kan ik verschillende kolombreedtes voor de tabel opgeven?

 A: U kunt verschillende kolombreedtes voor de tabel opgeven met behulp van de`ColumnWidths` eigenschap van de tabel. De eigenschap neemt een string met spatiegescheiden waarden, waarbij elke waarde de breedte van een kolom in punten vertegenwoordigt.

#### V: Kan ik geneste tabellen gebruiken in een cel met HTML-inhoud?

A: Ja, u kunt geneste tabellen gebruiken in een cel met HTML-inhoud. U kunt afzonderlijke tabelinstanties maken en deze toevoegen als onderdeel van de HTML-inhoud in een cel om het nestingeffect te bereiken.