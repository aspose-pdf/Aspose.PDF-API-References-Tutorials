---
title: Excel-werkbladgegevens exporteren naar tabel
linktitle: Excel-werkbladgegevens exporteren naar tabel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u Excel-werkbladgegevens exporteert naar een PDF-tabel met Aspose.PDF voor .NET. Stapsgewijze zelfstudie met codevoorbeelden, vereisten en nuttige tips.
type: docs
weight: 70
url: /nl/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Invoering

Heb je ooit gegevens uit een Excel-werkblad moeten exporteren naar een PDF-bestand, netjes gerangschikt in een tabelformaat? Stel je voor dat je een heleboel gegevens in Excel hebt, maar ze moet delen als een professioneel ogende PDF. Dat klinkt ingewikkeld, toch? Maar met Aspose.PDF voor .NET kun je deze taak in een handomdraai uitvoeren. In deze tutorial leiden we je door het proces van het exporteren van Excel-werkbladgegevens naar een tabel in een PDF-document met behulp van Aspose.PDF voor .NET. We nemen je stap voor stap mee en breken alles af, zodat je je aan het einde een professional voelt, zelfs als je hier nieuw in bent.

## Vereisten

Voordat we beginnen met coderen, moeten we eerst een paar dingen regelen:

1.  Aspose.PDF voor .NET Library – Zorg ervoor dat u de nieuwste versie hebt geïnstalleerd. U kunt[download het hier](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells voor .NET Library – U hebt dit nodig om Excel-bewerkingen uit te voeren. Download het van[hier](https://releases.aspose.com/cells/net/).
3. .NET-ontwikkelomgeving – Een hulpmiddel als Visual Studio is perfect voor codering.
4. Excel-bestand – Zorg dat u een Excel-bestand met de gegevens die u wilt exporteren bij de hand hebt.

 Als u de bibliotheken Aspose.PDF en Aspose.Cells niet hebt, kunt u beginnen met een[gratis proefperiode](https://releases.aspose.com/).

## Pakketten importeren

Zorg er allereerst voor dat u zowel de Aspose.PDF- als de Aspose.Cells-bibliotheken in uw project hebt geïnstalleerd. U kunt ze installeren met NuGet Package Manager in Visual Studio.

Hier leest u hoe u de benodigde pakketten in uw C#-code importeert:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Nu de vereisten zijn ingesteld, gaan we het proces van het exporteren van gegevens van een Excel-blad naar een tabel in een PDF-document doorlopen.

## Stap 1: Laad de Excel-werkmap

Om te beginnen moet u uw Excel-werkmap in het programma laden. In deze stap gebruiken we Aspose.Cells om het Excel-bestand te openen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad de Excel-werkmap
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Uitleg: Hier geven we het pad op naar de map waar ons Excel-bestand zich bevindt en laden we de werkmap met behulp van`Aspose.Cells.Workbook` Zorg ervoor dat je het aanpast`"YOUR DOCUMENT DIRECTORY"` om naar de locatie van uw bestand te verwijzen.

## Stap 2: Toegang tot het eerste werkblad

Nadat we de werkmap hebben geladen, moeten we toegang krijgen tot het eerste werkblad waarin onze gegevens zijn opgeslagen.

```csharp
// Toegang krijgen tot het eerste werkblad in het Excel-bestand
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Uitleg: Deze stap is eenvoudig: we pakken het eerste werkblad uit de werkmap, dat de te exporteren gegevens bevat.

## Stap 3: Gegevens exporteren naar DataTable

Nu gaan we de gegevens uit het Excel-bestand exporteren naar een DataTable-object. Dit object fungeert als tussenpersoon voor het overbrengen van de gegevens naar de PDF.

```csharp
// De inhoud van 7 rijen en 2 kolommen exporteren vanaf de 1e cel naar DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Uitleg: De`ExportDataTable` methode extraheert de gegevens vanaf de eerste cel van het werkblad en bestrijkt alle rijen en kolommen. Deze gegevens worden vervolgens opgeslagen in een`DataTable` voor verder gebruik.

## Stap 4: Maak een nieuw PDF-document

Vervolgens moeten we een nieuw PDF-document maken met behulp van Aspose.PDF.

```csharp
// Een Document-instantie instantiëren
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Een pagina maken in het documentexemplaar
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Uitleg: Hier initialiseren we een nieuwe`Aspose.Pdf.Document`en voeg er een pagina aan toe. Deze pagina zal later de tabel bevatten die we maken van de Excel-gegevens.

## Stap 5: Een tabelobject in PDF maken

Laten we verder gaan met het maken van een tabel in het PDF-document.

```csharp
// Een tabelobject maken
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Voeg het Tabel-object toe aan de alineaverzameling van de pagina
page.Paragraphs.Add(table);
```

 Uitleg: Wij creëren een`Aspose.Pdf.Table` object en voeg het toe aan de alineaverzameling van de pagina. Dit zorgt ervoor dat de tabel op de pagina wordt weergegeven.

## Stap 6: Kolombreedtes en randen instellen

Tabellen in PDF hebben gedefinieerde kolombreedtes nodig. We voegen ook randen toe om de tabel leesbaarder te maken.

```csharp
// Kolombreedtes van de tabel instellen
table.ColumnWidths = "40 100 100";

// Standaard celrand instellen
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Uitleg: We stellen de breedtes van de drie kolommen in en geven alle cellen een standaardrand met een dikte van`0.1F`.

## Stap 7: Gegevens importeren uit DataTable naar PDF-tabel

Nu is het tijd om de gegevens uit de DataTable te importeren in onze PDF-tabel.

```csharp
// Gegevens importeren in het tabelobject vanuit de DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Uitleg: De`ImportDataTable`methode brengt alle gegevens over van de`DataTable` naar de PDF-tabel. Hiermee wordt de tabel gevuld met de gegevens uit uw Excel-sheet.

## Stap 8: Stijl de koptekstrij

Laten we de koptekstrij van de tabel opmaken door de achtergrondkleur, het lettertype en de uitlijning te wijzigen.

```csharp
// Haal de eerste rij uit de tabel
Aspose.Pdf.Row headerRow = table.Rows[0];

// Stijl instellen voor de koptekstrij
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Uitleg: We doorlopen alle cellen in de eerste rij (kop) en stellen de achtergrondkleur in op blauw, de tekstkleur op geel en lijnen de tekst uit op het midden.

## Stap 9: Stijl de resterende rijen

Om onderscheid te maken tussen de koptekst en de rest van de rijen, voegen we een andere stijl toe voor de overige rijen.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Uitleg: Voor alle rijen behalve de koptekst stellen we een grijze achtergrond en een witte tekstkleur in.

## Stap 10: Sla het PDF-document op

Sla ten slotte het PDF-document met de tabel op.

```csharp
// PDF opslaan
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Uitleg: We slaan de PDF op in de opgegeven directory. Voilà! Uw Excel-gegevens staan nu in een prachtig opgemaakte PDF-tabel.

## Conclusie

En daar heb je het! In slechts een paar stappen heb je gegevens uit een Excel-werkblad geëxporteerd naar een tabel in een PDF met Aspose.PDF voor .NET. Door het proces op te splitsen en het gaandeweg te stylen, kun je je uitvoer aanpassen en ervoor zorgen dat je gegevens er schoon en professioneel uitzien. Dus de volgende keer dat iemand je een Excel-bestand geeft en vraagt om een PDF-rapport, weet je precies wat je moet doen.

## Veelgestelde vragen

### Kan ik de tabel verder aanpassen?
Absoluut! Je kunt kleuren, lettertypen, uitlijning en zelfs randen aan specifieke cellen toevoegen.

### Is Aspose.PDF voor .NET gratis?
 Het biedt een gratis proefperiode, maar voor langdurig gebruik heb je een licentie nodig. Je kunt[koop het hier](https://purchase.aspose.com/buy).

### Kan ik alleen specifieke rijen en kolommen exporteren?
 Ja, u kunt de parameters in de`ExportDataTable` Methode om specifieke bereiken te exporteren.

### Werkt dit met grote Excel-bestanden?
Ja, Aspose.Cells is ontworpen om grote Excel-bestanden efficiënt te verwerken.

### Hoe kan ik meer pagina's aan de PDF toevoegen?
 Je kunt gebruiken`pdfDocument.Pages.Add()` om zoveel pagina's toe te voegen als u nodig hebt.