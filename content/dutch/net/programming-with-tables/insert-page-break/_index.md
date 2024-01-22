---
title: Pagina-einde invoegen in PDF-bestand
linktitle: Pagina-einde invoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een pagina-einde invoegt in een PDF-bestand met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-tables/insert-page-break/
---
In deze zelfstudie leren we hoe u een pagina-einde in een PDF-bestand kunt invoegen met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet u hoe u een pagina-einde kunt toevoegen na een bepaald aantal regels in een tabel van een PDF-document. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg ervoor dat u uw C#-ontwikkelomgeving hebt geconfigureerd met Aspose.PDF voor .NET. Voeg de verwijzing naar de bibliotheek toe en importeer de benodigde naamruimten.

## Stap 2: Het document en de tabel maken
We maken een nieuwe documentinstantie en voegen een pagina toe aan dit document. Vervolgens maken we een tabelinstantie om onze tabel in het PDF-document weer te geven. We definiëren ook de randstijlen voor de tabel.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Stap 3: Voeg rijen toe aan de tabel
We gebruiken een lus om 200 rijen aan de array toe te voegen. Voor elke rij maken we een exemplaar van Row en voegen we twee cellen met tekstinhoud toe.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Wanneer er 10 regels worden toegevoegd, voegen we een nieuw pagina-einde in
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Stap 4: De tabel aan het document toevoegen
We voegen de tabel toe aan de alineaverzameling van de documentpagina.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Stap 5: Sla het document op
We slaan het PDF-document op met het pagina-einde ingevoegd.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Voorbeeldbroncode voor Pagina-einde invoegen met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantie van documentinstantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
doc.Pages.Add();
// Tabelinstantie maken
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Randstijl voor tabel instellen
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Stel de standaardrandstijl in voor de tabel met de randkleur als Rood
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Geef de kolombreedte van de tabel op
tab.ColumnWidths = "100 100";
// Maak een lus om 200 rijen voor de tabel toe te voegen
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Wanneer er 10 rijen zijn toegevoegd, render dan een nieuwe rij op een nieuwe pagina
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Tabel toevoegen aan alineaverzameling van PDF-bestand
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Sla het PDF-document op
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een pagina-einde in een PDF-document kunt invoegen met Aspose.PDF voor .NET. U kunt deze stapsgewijze handleiding gebruiken om met C# een pagina-einde toe te voegen na een bepaald aantal regels in een tabel in een PDF-document.

### Veelgestelde vragen over het invoegen van een pagina-einde in een PDF-bestand

#### Vraag: Hoe kan ik het paginaformaat wijzigen voor de nieuwe pagina's die na het pagina-einde zijn gemaakt?

 A: Om het paginaformaat te wijzigen voor de nieuwe pagina's die na het pagina-einde zijn gemaakt, kunt u de`PageSize` eigendom van de`Page` voorwerp. U kunt bijvoorbeeld de volgende code gebruiken om het paginaformaat in te stellen op A4:

```csharp
// Stel het paginaformaat in op A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Vraag: Kan ik de paginamarges voor de nieuwe pagina's na het pagina-einde beheren?

 A: Ja, u kunt de paginamarges voor de nieuwe pagina's na het pagina-einde bepalen. Gebruik de`Margin` eigendom van de`Page` object om de paginamarges in te stellen. Om bijvoorbeeld alle marges op 10 punten in te stellen, kunt u de volgende code gebruiken:

```csharp
// Stel alle marges in op 10 punten
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Vraag: Is het mogelijk om kop- en voetteksten toe te voegen aan de nieuwe pagina's na het pagina-einde?

 A: Ja, u kunt kop- en voetteksten toevoegen aan de nieuwe pagina's na het pagina-einde. Gebruik de`Page.Header` En`Page.Footer` eigenschappen om inhoud toe te voegen aan de kop- en voettekstsecties van de pagina. Bijvoorbeeld:

```csharp
// Voeg koptekst toe aan de nieuwe pagina's
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Voettekst toevoegen aan de nieuwe pagina's
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Vraag: Kan ik pagina-einden invoegen op specifieke locaties, behalve na een bepaald aantal rijen?

 A: Ja, u kunt pagina-einden op specifieke locaties invoegen, behalve na een bepaald aantal rijen. U kunt de`IsInNewPage` eigenschap van een rij naar`true` om de tabel te dwingen na die rij een nieuwe pagina te starten.

#### Vraag: Hoe kan ik het pagina-eindegedrag aanpassen op basis van de inhoudshoogte?

Antwoord: U kunt de`IsBroken` eigenschap van de tabel om het automatisch afbreken van rijen over pagina's heen in of uit te schakelen. Wanneer ingesteld op`true`, staat het toe dat rijen over pagina's worden verdeeld op basis van de hoogte van de inhoud.