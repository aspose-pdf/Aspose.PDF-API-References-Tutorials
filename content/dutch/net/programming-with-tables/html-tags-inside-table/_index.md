---
title: HTML-tags in tabel in PDF-bestand
linktitle: HTML-tags in tabel in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u HTML-tags in een tabel in een PDF-bestand kunt gebruiken met Aspose.PDF voor .NET.
type: docs
weight: 100
url: /nl/net/programming-with-tables/html-tags-inside-table/
---
In deze zelfstudie leren we hoe u HTML-tags in een tabel in een PDF-document kunt gebruiken met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze zelfstudie weet u hoe u HTML-inhoud in een tabel in een PDF-document kunt invoegen. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg ervoor dat u uw C#-ontwikkelomgeving hebt geconfigureerd met Aspose.PDF voor .NET. Voeg de verwijzing naar de bibliotheek toe en importeer de benodigde naamruimten.

## Stap 2: Tabelgegevens creëren
We maken een DataTable met daarin een "data"-kolom van het type String. Vervolgens voegen we rijen aan deze DataTable toe met behulp van HTML-inhoud.

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
We maken een nieuw PDF-document en voegen een pagina toe aan dit document. Vervolgens initialiseren we een exemplaar van de klasse Table en stellen we de tabeleigenschappen in.

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

## Stap 4: Gegevens in de tabel importeren
We importeren de gegevens uit de DataTable in de tabel met behulp van de "ImportDataTable" -methode. We specificeren methodeparameters om aan te geven welk bereik van rijen en kolommen van de DataTable moet worden geïmporteerd.

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

### Voorbeeldbroncode voor HTML-tags in tabel met Aspose.PDF voor .NET

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
//Stel de kolombreedte van de tabel in
tableProvider.ColumnWidths = "400 50 ";
// Stel de kleur van de tabelrand in als LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Stel de rand voor tabelcellen in
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
In deze zelfstudie hebben we geleerd hoe u HTML-tags in een tabel in een PDF-document kunt gebruiken met Aspose.PDF voor .NET. U kunt deze stapsgewijze handleiding gebruiken om HTML-inhoud in tabelcellen in een PDF-document in te voegen met behulp van C#.

### Veelgestelde vragen over HTML-tags in tabel in PDF-bestand

#### Vraag: Kan ik andere HTML-tags en attributen in de tabelcellen gebruiken?

 A: Ja, u kunt verschillende HTML-tags en attributen in de tabelcellen gebruiken, zoals`<b>`, `<i>`, `<a>`en nog veel meer. Aspose.PDF voor .NET ondersteunt een breed scala aan HTML-elementen en -stijlen die u kunt gebruiken om de inhoud in de tabelcellen op te maken.

#### Vraag: Kan ik CSS-stijlen toepassen op de HTML-inhoud in de tabelcellen?

A: Ja, u kunt CSS-stijlen toepassen op de HTML-inhoud in de tabelcellen. Aspose.PDF voor .NET biedt ondersteuning voor standaard CSS-stijlen die op de HTML-elementen kunnen worden toegepast.

#### Vraag: Is het mogelijk om afbeeldingen toe te voegen samen met HTML-inhoud in de tabelcellen?

 A: Ja, u kunt afbeeldingen en HTML-inhoud toevoegen aan de tabelcellen. U kunt HTML gebruiken`<img>` tags om afbeeldingen uit verschillende bronnen op te nemen, zoals lokale bestanden of URL's.

#### Vraag: Hoe kan ik verschillende kolombreedtes voor de tabel opgeven?

 A: U kunt verschillende kolombreedtes voor de tabel opgeven met behulp van de`ColumnWidths` eigendom van de tafel. De eigenschap heeft een tekenreeks nodig die door spaties gescheiden waarden bevat, waarbij elke waarde de breedte van een kolom in punten vertegenwoordigt.

#### Vraag: Kan ik geneste tabellen in een cel met HTML-inhoud gebruiken?

A: Ja, u kunt geneste tabellen in een cel met HTML-inhoud gebruiken. U kunt afzonderlijke tabelinstanties maken en deze toevoegen als onderdeel van de HTML-inhoud in een cel om het nesteffect te bereiken.