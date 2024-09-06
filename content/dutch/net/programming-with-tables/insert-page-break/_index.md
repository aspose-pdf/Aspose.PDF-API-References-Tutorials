---
title: Pagina-einde invoegen in PDF-bestand
linktitle: Pagina-einde invoegen in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een pagina-einde in een PDF-bestand invoegt met Aspose.PDF voor .NET.
type: docs
weight: 110
url: /nl/net/programming-with-tables/insert-page-break/
---
In deze tutorial leren we hoe je een pagina-einde invoegt in een PDF-bestand met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet je hoe je een pagina-einde toevoegt na een bepaald aantal regels in een tabel van een PDF-document. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg ervoor dat u uw C#-ontwikkelomgeving hebt geconfigureerd met Aspose.PDF voor .NET. Voeg de referentie toe aan de bibliotheek en importeer de benodigde naamruimten.

## Stap 2: Het document en de tabel maken
We maken een nieuw Document-exemplaar en voegen een pagina toe aan dit document. Vervolgens maken we een Tabel-exemplaar om onze tabel in het PDF-document te vertegenwoordigen. We definiëren ook de randstijlen voor de tabel.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Stap 3: Rijen toevoegen aan tabel
We gebruiken een lus om 200 rijen toe te voegen aan de array. Voor elke rij maken we een exemplaar van Row en voegen we twee cellen met tekstinhoud toe.

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
    
     // Wanneer er 10 regels worden toegevoegd, voegen we een nieuwe pagina-einde in
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
We slaan het PDF-document op met de pagina-einde ingevoegd.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Voorbeeldbroncode voor het invoegen van een pagina-einde met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer Document-instantie
Document doc = new Document();
// Pagina toevoegen aan paginaverzameling van PDF-bestand
doc.Pages.Add();
// Tabelinstantie maken
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Randstijl voor tabel instellen
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Stel de standaardrandstijl voor de tabel in met de randkleur Rood
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Specificeer de breedte van de tabelkolommen
tab.ColumnWidths = "100 100";
// Maak een lus om 200 rijen toe te voegen aan de tabel
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Wanneer er 10 rijen zijn toegevoegd, wordt er een nieuwe rij op een nieuwe pagina weergegeven
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
In deze tutorial hebben we geleerd hoe u een pagina-einde in een PDF-document kunt invoegen met Aspose.PDF voor .NET. U kunt deze stapsgewijze handleiding gebruiken om een pagina-einde toe te voegen na een bepaald aantal regels in een tabel in een PDF-document met C#.

### FAQ's voor het invoegen van een pagina-einde in een PDF-bestand

#### V: Hoe kan ik het paginaformaat wijzigen voor de nieuwe pagina's die na de pagina-einde worden aangemaakt?

 A: Om de paginagrootte te wijzigen voor de nieuwe pagina's die na de pagina-einde zijn gemaakt, kunt u de`PageSize` eigendom van de`Page` object. U kunt bijvoorbeeld de volgende code gebruiken om de paginagrootte in te stellen op A4:

```csharp
// Stel het paginaformaat in op A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### V: Kan ik de paginamarges voor de nieuwe pagina's na de pagina-einde bepalen?

 A: Ja, u kunt de paginamarges voor de nieuwe pagina's na de pagina-einde bepalen. Gebruik de`Margin` eigendom van de`Page` object om de paginamarges in te stellen. Om bijvoorbeeld alle marges op 10 punten in te stellen, kunt u de volgende code gebruiken:

```csharp
// Stel alle marges in op 10 punten
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### V: Is het mogelijk om kop- en voetteksten toe te voegen aan de nieuwe pagina's na de pagina-einde?

 A: Ja, u kunt kop- en voetteksten toevoegen aan de nieuwe pagina's na de pagina-einde. Gebruik de`Page.Header` En`Page.Footer` eigenschappen om inhoud toe te voegen aan de header- en footersecties van de pagina. Bijvoorbeeld:

```csharp
// Koptekst toevoegen aan de nieuwe pagina's
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Voeg een voettekst toe aan de nieuwe pagina's
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### V: Kan ik pagina-einden op specifieke locaties invoegen, maar niet na een bepaald aantal rijen?

 A: Ja, u kunt pagina-einden invoegen op specifieke locaties, behalve na een bepaald aantal rijen. U kunt de`IsInNewPage` eigenschap van een rij naar`true` om de tabel te dwingen een nieuwe pagina te starten na die rij.

#### V: Hoe kan ik het gedrag van pagina-einden aanpassen op basis van de hoogte van de inhoud?

 A: U kunt de`IsBroken` eigenschap van de tabel om automatische rij-onderbreking over pagina's in of uit te schakelen. Wanneer ingesteld op`true`Hiermee kunnen rijen over pagina's worden verdeeld op basis van de hoogte van de inhoud.