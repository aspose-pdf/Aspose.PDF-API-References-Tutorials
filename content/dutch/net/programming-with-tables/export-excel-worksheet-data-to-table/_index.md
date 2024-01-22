---
title: Excel-werkbladgegevens exporteren naar tabel
linktitle: Excel-werkbladgegevens exporteren naar tabel
second_title: Aspose.PDF voor .NET API-referentie
description: Exporteer gegevens van een Excel-werkblad naar een PDF-tabel met Aspose.PDF voor .NET.
type: docs
weight: 70
url: /nl/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
In deze zelfstudie leren we hoe u gegevens uit een Excel-werkblad kunt exporteren en een tabel in een PDF-document kunt maken met behulp van de Aspose.PDF voor .NET-bibliotheek. We lopen stap voor stap door de broncode en leggen elke sectie gedetailleerd uit. Aan het einde van deze zelfstudie kunt u PDF-bestanden genereren met tabellen die gegevens uit Excel-werkbladen bevatten. Laten we beginnen!

## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

- Basiskennis van de programmeertaal C#
- Visual Studio is op uw computer geïnstalleerd
- Aspose.PDF voor .NET-bibliotheek toegevoegd aan uw project

## Stap 1: De omgeving instellen
Maak om te beginnen een nieuw C#-project in Visual Studio. Voeg de verwijzing naar de Aspose.PDF voor .NET-bibliotheek toe door met de rechtermuisknop op uw project in de Solution Explorer te klikken, 'NuGet-pakketten beheren' te selecteren en naar 'Aspose.PDF' te zoeken. Installeer het pakket en u bent klaar om te gaan.

## Stap 2: Het Excel-werkblad laden
In de eerste stap van onze code definiëren we het pad naar de map met het Excel-document. Vervang "UW DOCUMENTENMAP" door het daadwerkelijke mappad waar uw Excel-bestand zich bevindt.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Hier gebruiken we de Aspose.Cells-bibliotheek om de Excel-werkmap te laden. Zorg ervoor dat u "newBook1.xlsx" vervangt door de naam van uw Excel-bestand.

## Stap 3: Toegang tot het werkblad
 Vervolgens moeten we toegang krijgen tot het eerste werkblad in het Excel-bestand. Dit doen wij met behulp van de`Worksheets` verzameling van de`Workbook` voorwerp.

```csharp
// Toegang tot het eerste werkblad in het Excel-bestand
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Als uw Excel-bestand meerdere werkbladen bevat, kunt u de indexwaarde wijzigen`[0]` om een ander werkblad te openen.

## Stap 4: Gegevens exporteren naar DataTable
 Nu exporteren we de inhoud van het Excel-werkblad naar een`DataTable` voorwerp. We specificeren het cellenbereik dat moet worden geëxporteerd met behulp van de`ExportDataTable` methode.

```csharp
// Exporteren van de inhoud van 7 rijen en 2 kolommen, beginnend bij de eerste cel, naar DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

In dit voorbeeld exporteren we alle rijen en kolommen, beginnend bij de eerste cel (0, 0) tot de laatste cel in het werkblad. Stel het juiste bereik in op basis van uw vereisten.

## Stap 5: Een PDF-document maken
Nu gaan we een nieuw PDF-document maken met behulp van de Aspose.PDF-bibliotheek.

```csharp
// Een documentinstantie instantiëren
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Hierdoor ontstaat een leeg PDF-document waarin we inhoud kunnen toevoegen.

## Stap 6: Een pagina en tabel toevoegen
Om de gegevens in tabelformaat weer te geven, moeten we een pagina en een tabel aan het PDF-document toevoegen.

```csharp
// Maak een pagina in de documentinstantie
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Maak een Table-object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg het Table-object toe aan de alineacollectie van de sectie
sec1.Paragraphs.Add(tab1);
```

Hier maken we een nieuwe pagina en een tabelobject. Vervolgens voegen we de tabel toe aan de alineaverzameling van de pagina.

## Stap 7: Tabeleigenschappen instellen
Voordat we de gegevens importeren, moeten we enkele eigenschappen van de tabel instellen, zoals kolombreedtes en standaard celranden.

```csharp
// Stel de kolombreedte van de tabel in
tab1.ColumnWidths = "40 100 100";

// Stel de standaardcelrand van de tabel in met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

In dit voorbeeld stellen we de kolombreedtes in op 40, 100 en 100 eenheden. Pas de waarden aan op basis van uw gegevens. We hebben ook de standaardcelrand ingesteld om randen aan alle zijden van elke cel weer te geven.

## Stap 8: Gegevens naar de tabel importeren
 Nu zullen we de gegevens importeren uit de`DataTable` object in de tabel met behulp van de`ImportDataTable` methode.

```csharp
// Importeer gegevens in het Table-object uit de hierboven gemaakte DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Hier specificeren we het bereik van rijen en kolommen die moeten worden geïmporteerd. In dit voorbeeld importeren we alle rijen en kolommen uit de`dataTable` voorwerp.

## Stap 9: De tabel opmaken
Om het uiterlijk van de tabel te verbeteren, kunnen we opmaak toepassen op specifieke cellen of rijen. In deze stap formatteren we de eerste rij en de alternatieve rijen van de tabel.

```csharp
// Neem de 1e rij uit de tabel
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

// Alternatief rijformaat
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Stel de achtergrondkleur van de cellen in afwisselende rijen in
         curCell.BackgroundColor = Color.Gray;
        
         // Stel de tekstkleur van de cellen in afwisselende rijen in
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Hier doorlopen we de cellen in de eerste rij en stellen we de achtergrondkleur, het lettertype, de letterkleur en de tekstuitlijning in. Vervolgens doorlopen we alle cellen in de afwisselende rijen en stellen we hun achtergrond- en tekstkleur in.

## Stap 10: Het PDF-document opslaan
Ten slotte slaan we het PDF-document op de opgegeven locatie op.

```csharp
// Sla de pdf op
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het gewenste mappad en de gewenste bestandsnaam voor het uitgevoerde PDF-bestand.

### Voorbeeldbroncode voor het exporteren van Excel-werkbladgegevens naar tabel met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Toegang tot het eerste werkblad in het Excel-bestand
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Exporteren van de inhoud van 7 rijen en 2 kolommen, beginnend bij de eerste cel, naar DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Een documentinstantie instantiëren
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Maak een pagina in de documentinstantie
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Maak een Table-object
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Voeg het Table-object toe aan de alineacollectie van de sectie
sec1.Paragraphs.Add(tab1);

// Stel de kolombreedte van de tabel in. We moeten de ColumnCount handmatig opgeven.
// Omdat het huidige Excel-werkblad drie kolommen heeft, specificeren we hetzelfde aantal
tab1.ColumnWidths = "40 100 100";

// Stel de standaardcelrand van de tabel in met behulp van het BorderInfo-object
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importeer gegevens in het Table-object uit de hierboven gemaakte DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Neem de 1e rij uit de tabel
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Doorloop alle cellen in de eerste rij en stel hun achtergrondkleur in op blauw
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Stel de achtergrond in van alle cellen in de eerste rij van de tabel.
	curCell.BackgroundColor = Color.Blue;
	// Stel het lettertype in voor de cellen van de eerste rij in de tabel.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Stel de lettertypekleur in van alle cellen in de eerste rij van de tabel.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Stel de tekstuitlijning voor de cellen van de eerste rij in als Midden.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Doorloop alle cellen in de eerste rij en stel hun achtergrondkleur in op blauw
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Stel de achtergrondkleur van alle cellen in, behalve die van de eerste rij.
		curCell.BackgroundColor = Color.Gray;
		// Stel de tekstkleur in van alle cellen behalve de eerste rij.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Bewaar de pdf
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u gegevens van een Excel-werkblad naar een PDF-tabel kunt exporteren met behulp van de Aspose.PDF voor .NET-bibliotheek. We hebben het stapsgewijze proces besproken van het laden van het Excel-werkblad, het maken van een PDF-document, het toevoegen van een tabel, het importeren van gegevens en het opmaken van de tabel. U kunt nu programmatisch PDF-bestanden genereren met tabellen die Excel-gegevens bevatten.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het exporteren van Excel-werkbladgegevens naar een PDF-tabel?

A: Door Excel-werkbladgegevens naar een PDF-tabel te exporteren, kunt u de gegevens in een gestructureerd en georganiseerd formaat presenteren. Hiermee kunt u PDF-bestanden genereren met tabellen die gegevens uit Excel-werkbladen bevatten, waardoor het gemakkelijker wordt om informatie in een draagbaar documentformaat te delen en te bewaren.

#### Vraag: Kan ik het uiterlijk van de PDF-tabel aanpassen?

A: Ja, u kunt het uiterlijk van de PDF-tabel aanpassen met behulp van verschillende eigenschappen van Aspose.PDF voor .NET. In de meegeleverde C#-broncode kunt u de kolombreedte, celranden, tekstuitlijning, lettertypestijl en meer aanpassen aan uw specifieke vereisten.

#### Vraag: Hoe ga ik om met Excel-bestanden met meerdere werkbladen?

 A: In de meegeleverde C#-code hebben we toegang gekregen tot het eerste werkblad in het Excel-bestand met behulp van de index`[0]` . Als uw Excel-bestand meerdere werkbladen bevat, kunt u deze openen door de indexwaarde dienovereenkomstig te wijzigen, bijvoorbeeld`[1]` voor het tweede werkblad of`[2]` voor het derde werkblad.

#### Vraag: Kan ik verschillende opmaak toepassen op specifieke rijen of cellen in de PDF-tabel?

A: Ja, u kunt verschillende opmaak toepassen op specifieke rijen of cellen in de PDF-tabel. In de meegeleverde C#-broncode hebben we gedemonstreerd hoe u de eerste rij en de alternatieve rijen anders kunt opmaken door de achtergrondkleur, de tekenstijl en de tekenkleur te wijzigen. U kunt indien nodig vergelijkbare opmaaktechnieken toepassen op specifieke rijen of cellen.

#### Vraag: Is Aspose.PDF voor .NET de enige bibliotheek waarmee Excel-gegevens naar een PDF-tabel kunnen worden geëxporteerd?

A: Aspose.PDF voor .NET is een krachtige bibliotheek voor het werken met PDF-documenten in .NET-toepassingen. Hoewel er mogelijk andere bibliotheken beschikbaar zijn, biedt Aspose.PDF voor .NET een breed scala aan functies en mogelijkheden voor het genereren, manipuleren en exporteren van PDF-bestanden met tabellen uit Excel-gegevens, waardoor het een populaire keuze is voor dergelijke taken.