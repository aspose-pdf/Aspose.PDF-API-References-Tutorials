---
title: Bepaal het tabelonderbreking in PDF-bestand
linktitle: Bepaal het tabelonderbreking in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabeleinden in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET.
type: docs
weight: 60
url: /nl/net/programming-with-tables/determine-table-break/
---
In deze zelfstudie leren we hoe u tabeleinden in een PDF-bestand kunt bepalen met behulp van Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet u hoe u kunt bepalen of een tabel de paginamarges overschrijdt. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg er eerst voor dat u uw C#-ontwikkelomgeving hebt ingesteld met Aspose.PDF voor .NET. Voeg de verwijzing naar de bibliotheek toe en importeer de benodigde naamruimten.

## Stap 2: Het PDF-document maken
 In deze stap maken we een nieuw`Document` object dat het PDF-document vertegenwoordigt.

```csharp
pdf-Document = new Document();
```

Dit document wordt gebruikt om secties en tabellen toe te voegen.

## Stap 3: Een sectie en een tabel toevoegen
Nu gaan we een sectie toevoegen aan ons PDF-document en een tabel maken in deze sectie.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Ook voor de tafel specificeren wij een bovenmarge van 300 punten. U kunt deze waarde aanpassen aan uw behoeften.

## Stap 4: Tabelopstelling
In deze stap configureren we tabeleigenschappen, zoals kolombreedtes en randen.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Hier definiëren we de breedte van de tabelkolommen en de celranden. U kunt deze waarden aanpassen aan uw voorkeuren.

## Stap 5: Voeg rijen en cellen toe aan de tabel
Nu gaan we rijen en cellen in de tabel maken met behulp van een lus.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Hier maken we 17 rijen in de tabel en voegen we drie cellen toe aan elke rij. U kunt de gesp aanpassen aan uw behoeften.

## Stap 6: Tabelonderbrekingen bepalen
Nu zullen we bepalen of de tabel de paginamarges overschrijdt door de hoogte van de pagina te vergelijken met de totale hoogte van de objecten in de tabel.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

We berekenen de hoogte van de pagina en de totale hoogte van de objecten, rekening houdend met de marges. Als het verschil 10 of minder is, overschrijdt de tabel de paginamarges.

## Stap 7: Het PDF-document opslaan
Ten slotte slaan we het PDF-document met de resultaten op.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Zorg ervoor dat u de juiste documentmap opgeeft. Het resulterende PDF-bestand wordt opgeslagen met de vastgestelde tabeleinden.

### Voorbeeldbroncode voor Tabelonderbreking bepalen met Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Een object-PDF-klasse instantiëren
Document pdf = new Document();
// Voeg de sectie toe aan de verzameling PDF-documentsecties
Aspose.Pdf.Page page = pdf.Pages.Add();
// Een tabelobject instantiëren
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Voeg de tabel toe aan de alineaverzameling van de gewenste sectie
page.Paragraphs.Add(table1);
// Ingesteld met kolombreedtes van de tabel
table1.ColumnWidths = "100 100 100";
// Stel de standaardcelrand in met het BorderInfo-object
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Stel de tabelrand in met een ander aangepast BorderInfo-object
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Maak een MarginInfo-object en stel de linker-, onder-, rechter- en bovenmarges in
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Stel de standaardcelopvulling in op het MarginInfo-object
table1.DefaultCellPadding = margin;
// Als je de teller verhoogt naar 17, zal de tafel kapot gaan
// Omdat het niet meer op deze pagina kan worden ondergebracht
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Maak rijen in de tabel en vervolgens cellen in de rijen
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Informatie over paginahoogte ophalen
float PageHeight = (float)pdf.PageInfo.Height;
// Krijg de totale hoogte-informatie van de boven- en ondermarge van de pagina,
// Marge tafelblad en tafelhoogte.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Paginahoogte, tafelhoogte, bovenmarge van tafel en bovenkant pagina weergeven
// En informatie over de ondermarge
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Controleer of we de som van Paginabovenmarge + Paginaondermarge aftrekken
// + Tafelbladmarge en tafelhoogte vanaf paginahoogte en minder
// Dan 10 (een gemiddelde rij kan groter zijn dan 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Als de waarde kleiner is dan 10, wordt het bericht weergegeven.
	//Waaruit blijkt dat er geen nieuwe rij kan worden geplaatst en of we een nieuwe toevoegen
	// Rij, tafel zal breken. Het hangt af van de waarde van de rijhoogte.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Sla het pdf-document op
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u tabeleinden in een PDF-document kunt bepalen met behulp van Aspose.PDF voor .NET. Met dit stappenplan kunt u in uw eigen C#-projecten controleren of een tabel de paginamarges overschrijdt.

### Veelgestelde vragen over het bepalen van de tabelonderbreking in een PDF-bestand

#### Vraag: Wat is het doel van het bepalen van tabeleinden in een PDF-document?

A: Het doel van het bepalen van tabeleinden in een PDF-document is om te controleren of de tabel de paginamarges overschrijdt. Dit zorgt ervoor dat de inhoud van de tabel correct wordt weergegeven binnen de beschikbare paginaruimte. Door tabeleinden te detecteren, kunt u de overloop van de inhoud opvangen en de tabelindeling dienovereenkomstig aanpassen.

#### Vraag: Hoe kan ik de bovenmarge van de tabel aanpassen?

 A: In de meegeleverde C#-broncode kunt u de bovenmarge van de tabel aanpassen door de waarde van de`table1.Margin.Top`eigendom. Verhoog of verlaag de waarde indien nodig om de gewenste bovenmarge voor de tabel in te stellen.

#### Vraag: Kan ik het uiterlijk van de tabel aanpassen, zoals celkleuren en lettergrootte?

A: Ja, u kunt het uiterlijk van de tabel en de cellen ervan aanpassen met behulp van verschillende eigenschappen en methoden van Aspose.PDF voor .NET. U kunt bijvoorbeeld de achtergrondkleuren van de cellen, de lettergrootte, de lettertypefamilie, de tekstuitlijning en meer wijzigen. Raadpleeg de officiële documentatie voor meer informatie over het aanpassen van het uiterlijk van de tabel.

#### Vraag: Wat gebeurt er als de tabel de paginamarges overschrijdt?

A: Als de tabel de paginamarges overschrijdt, kan dit resulteren in het afkappen of overlappen van de inhoud, waardoor het PDF-document minder leesbaar en georganiseerd wordt. Door tabeleinden te detecteren en de overloop af te handelen, kunt u ervoor zorgen dat de inhoud correct wordt weergegeven binnen het beschikbare paginagebied.

#### Vraag: Kan ik tabeleinden bepalen voor meerdere tabellen in hetzelfde PDF-document?

A: Ja, u kunt tabeleinden bepalen voor meerdere tabellen in hetzelfde PDF-document. Herhaal eenvoudigweg de stappen voor elke tabel die u wilt analyseren en pas de tabelindeling indien nodig aan om overloop van de inhoud te voorkomen.