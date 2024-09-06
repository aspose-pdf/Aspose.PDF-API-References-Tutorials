---
title: Excel-werkbladgegevens exporteren naar tabel
linktitle: Excel-werkbladgegevens exporteren naar tabel
second_title: Aspose.PDF voor .NET API-referentie
description: Exporteer gegevens van een Excel-blad naar een PDF-tabel met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
In deze tutorial leren we hoe u gegevens uit een Excel-werkblad kunt exporteren en een tabel in een PDF-document kunt maken met behulp van de Aspose.PDF voor .NET-bibliotheek. We lopen stap voor stap door de broncode en leggen elke sectie gedetailleerd uit. Aan het einde van deze tutorial kunt u PDF-bestanden genereren met tabellen die gegevens uit Excel-werkbladen bevatten. Laten we beginnen!

## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:

- Basiskennis van de programmeertaal C#
- Visual Studio geïnstalleerd op uw machine
- Aspose.PDF voor .NET-bibliotheek toegevoegd aan uw project

## Stap 1: De omgeving instellen
Om te beginnen, maak een nieuw C#-project in Visual Studio. Voeg de referentie toe aan de Aspose.PDF voor .NET-bibliotheek door met de rechtermuisknop op uw project te klikken in de Solution Explorer, 'Manage NuGet Packages' te selecteren en te zoeken naar 'Aspose.PDF'. Installeer het pakket en u bent klaar om te gaan.

## Stap 2: Het Excel-werkblad laden
In de eerste stap van onze code definiëren we het pad naar de directory die het Excel-document bevat. Vervang "UW DOCUMENTENMAP" door het daadwerkelijke directorypad waar uw Excel-bestand zich bevindt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Hier gebruiken we de Aspose.Cells-bibliotheek om de Excel-werkmap te laden. Zorg ervoor dat u "newBook1.xlsx" vervangt door de naam van uw Excel-bestand.

## Stap 3: Toegang tot het werkblad
 Vervolgens moeten we toegang krijgen tot het eerste werkblad in het Excel-bestand. We doen dit met behulp van de`Worksheets` verzameling van de`Workbook` voorwerp.

```csharp
// Toegang krijgen tot het eerste werkblad in het Excel-bestand
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Als uw Excel-bestand meerdere werkbladen bevat, kunt u de indexwaarde wijzigen`[0]` om toegang te krijgen tot een ander werkblad.

## Stap 4: Gegevens exporteren naar DataTable
 Nu gaan we de inhoud van het Excel-werkblad exporteren naar een`DataTable` object. We specificeren het bereik van cellen dat geëxporteerd moet worden met behulp van de`ExportDataTable` methode.

```csharp
// De inhoud van 7 rijen en 2 kolommen exporteren, beginnend bij de 1e cel, naar DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In dit voorbeeld exporteren we alle rijen en kolommen vanaf de eerste cel (0, 0) tot de laatste cel in het werkblad. Stel het juiste bereik in op basis van uw vereisten.

## Stap 5: Een PDF-document maken
Nu gaan we een nieuw PDF-document maken met behulp van de Aspose.PDF-bibliotheek.

```csharp
// Een Document-instantie instantiëren
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Hiermee wordt een leeg PDF-document gemaakt, waar we inhoud aan kunnen toevoegen.

## Stap 6: Een pagina en tabel toevoegen
Om de gegevens in een tabelformaat weer te geven, moeten we een pagina en een tabel aan het PDF-document toevoegen.

```csharp
// Een pagina maken in het documentexemplaar
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Een tabelobject maken
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg het Table-object toe aan de alineaverzameling van de sectie
sec1.Paragraphs.Add(tab1);
```

Hier maken we een nieuwe pagina en een tabelobject. Vervolgens voegen we de tabel toe aan de paragrafenverzameling van de pagina.

## Stap 7: Tabeleigenschappen instellen
Voordat we de gegevens importeren, moeten we een aantal eigenschappen van de tabel instellen, zoals de kolombreedtes en standaardcelranden.

```csharp
// Kolombreedtes van de tabel instellen
tab1.ColumnWidths = "40 100 100";

// Standaard celrand van de tabel instellen met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In dit voorbeeld stellen we de kolombreedtes in op 40, 100 en 100 eenheden. Pas de waarden aan op basis van uw gegevens. We stellen ook de standaard celrand in om randen aan alle zijden van elke cel weer te geven.

## Stap 8: Gegevens importeren in de tabel
 Nu gaan we de gegevens importeren van de`DataTable` object in de tabel plaatsen met behulp van de`ImportDataTable` methode.

```csharp
// Importeer gegevens in het Table-object vanuit de hierboven gemaakte DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Hier specificeren we het bereik van rijen en kolommen die geïmporteerd moeten worden. In dit voorbeeld importeren we alle rijen en kolommen van de`dataTable` voorwerp.

## Stap 9: De tabel opmaken
Om het uiterlijk van de tabel te verbeteren, kunnen we opmaak toepassen op specifieke cellen of rijen. In deze stap formatteren we de eerste rij en afwisselende rijen van de tabel.

```csharp
// Haal de 1e rij uit de tabel
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formatteer de eerste rij
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Stel de achtergrondkleur van de cellen in de eerste rij in
     curCell.BackgroundColor = Color.Blue;// Stel het gezicht in voor de cellen in de eerste rij
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Stel de letterkleur van de cellen in de eerste rij in
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Stel de tekstuitlijning in voor de cellen in de eerste rij
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatieve rijopmaak
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // De achtergrondkleur van de cellen in afwisselende rijen instellen
         curCell.BackgroundColor = Color.Gray;
        
         // Stel de tekstkleur van de cellen in afwisselende rijen in
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Hier itereren we door de cellen in de eerste rij en stellen hun achtergrondkleur, lettertype, lettertypekleur en tekstuitlijning in. Vervolgens itereren we door alle cellen in de afwisselende rijen en stellen hun achtergrond- en tekstkleur in.

## Stap 10: Het PDF-document opslaan
Ten slotte slaan we het PDF-document op de opgegeven locatie op.

```csharp
// PDF opslaan
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het gewenste mappad en de gewenste bestandsnaam voor het PDF-uitvoerbestand.

### Voorbeeldbroncode voor het exporteren van Excel-werkbladgegevens naar een tabel met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Toegang krijgen tot het eerste werkblad in het Excel-bestand
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// De inhoud van 7 rijen en 2 kolommen exporteren, beginnend bij de 1e cel, naar DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Instantieer een Document-instance
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Een pagina maken in het documentexemplaar
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Een tabelobject maken
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg het Table-object toe aan de alineaverzameling van de sectie
sec1.Paragraphs.Add(tab1);

// Stel kolombreedtes van de tabel in. We moeten de ColumnCount handmatig opgeven.
// Omdat het huidige Excel-werkblad drie kolommen heeft, specificeren we hetzelfde aantal
tab1.ColumnWidths = "40 100 100";

// Standaard celrand van de tabel instellen met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importeer gegevens in het Table-object vanuit de hierboven gemaakte DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Haal de 1e rij uit de tabel
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Loop door alle cellen in de eerste rij en stel hun achtergrondkleur in op blauw
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Stel de achtergrond in van alle cellen in de eerste rij van de tabel.
	curCell.BackgroundColor = Color.Blue;
	// Stel het lettertype in voor de cellen van de eerste rij in de tabel.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Stel de lettertypekleur in van alle cellen in de eerste rij van de tabel.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Stel de tekstuitlijning voor de cellen van de eerste rij in op Centreren.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Loop door alle cellen in de eerste rij en stel hun achtergrondkleur in op blauw
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Stel de achtergrondkleur in voor alle cellen, behalve de eerste rij.
		curCell.BackgroundColor = Color.Gray;
		// Stel de tekstkleur in voor alle cellen, behalve de eerste rij.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// PDF opslaan
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusie
In deze tutorial hebben we geleerd hoe u gegevens van een Excel-werkblad naar een PDF-tabel kunt exporteren met behulp van de Aspose.PDF voor .NET-bibliotheek. We hebben het stapsgewijze proces behandeld van het laden van het Excel-werkblad, het maken van een PDF-document, het toevoegen van een tabel, het importeren van gegevens en het formatteren van de tabel. U kunt nu programmatisch PDF-bestanden genereren met tabellen die Excel-gegevens bevatten.

### Veelgestelde vragen

#### V: Wat is het doel van het exporteren van Excel-werkbladgegevens naar een PDF-tabel?

A: Door Excel-werkbladgegevens te exporteren naar een PDF-tabel kunt u de gegevens in een gestructureerd en georganiseerd formaat presenteren. Hiermee kunt u PDF-bestanden genereren met tabellen die gegevens uit Excel-werkbladen bevatten, waardoor het eenvoudiger wordt om informatie te delen en te bewaren in een draagbaar documentformaat.

#### V: Kan ik het uiterlijk van de PDF-tabel aanpassen?

A: Ja, u kunt het uiterlijk van de PDF-tabel aanpassen met behulp van verschillende eigenschappen die worden geleverd door Aspose.PDF voor .NET. In de meegeleverde C#-broncode kunt u de kolombreedtes, celranden, tekstuitlijning, lettertypestijl en meer aanpassen aan uw specifieke vereisten.

#### V: Hoe kan ik Excel-bestanden met meerdere werkbladen verwerken?

 A: In de meegeleverde C#-code hebben we toegang gekregen tot het eerste werkblad in het Excel-bestand met behulp van de index`[0]` . Als uw Excel-bestand meerdere werkbladen bevat, kunt u deze openen door de indexwaarde dienovereenkomstig te wijzigen, zoals`[1]` voor het tweede werkblad of`[2]` voor het derde werkblad.

#### V: Kan ik een andere opmaak toepassen op specifieke rijen of cellen in de PDF-tabel?

A: Ja, u kunt verschillende opmaak toepassen op specifieke rijen of cellen in de PDF-tabel. In de meegeleverde C#-broncode hebben we gedemonstreerd hoe u de eerste rij en afwisselende rijen anders kunt opmaken door hun achtergrondkleur, lettertypestijl en lettertypekleur te wijzigen. U kunt vergelijkbare opmaaktechnieken toepassen op specifieke rijen of cellen indien nodig.

#### V: Is Aspose.PDF voor .NET de enige bibliotheek waarmee Excel-gegevens naar een PDF-tabel kunnen worden geëxporteerd?

A: Aspose.PDF voor .NET is een krachtige bibliotheek voor het werken met PDF-documenten in .NET-toepassingen. Hoewel er mogelijk andere bibliotheken beschikbaar zijn, biedt Aspose.PDF voor .NET een breed scala aan functies en mogelijkheden voor het genereren, bewerken en exporteren van PDF-bestanden met tabellen uit Excel-gegevens, waardoor het een populaire keuze is voor dergelijke taken.