---
title: Bepaal tabelonderbreking in PDF-bestand
linktitle: Bepaal tabelonderbreking in PDF-bestand
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabeleinden in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET.
type: docs
weight: 60
url: /nl/net/programming-with-tables/determine-table-break/
---
In deze tutorial gaan we leren hoe je tabelonderbrekingen in een PDF-bestand kunt bepalen met Aspose.PDF voor .NET. We leggen de broncode in C# stap voor stap uit. Aan het einde van deze tutorial weet je hoe je kunt bepalen of een tabel de paginamarges overschrijdt. Laten we beginnen!

## Stap 1: De omgeving instellen
Zorg er eerst voor dat u uw C#-ontwikkelomgeving hebt ingesteld met Aspose.PDF voor .NET. Voeg de referentie toe aan de bibliotheek en importeer de benodigde naamruimten.

## Stap 2: Het PDF-document maken
 In deze stap maken we een nieuwe`Document` object om het PDF-document weer te geven.

```csharp
pdf-Document = new Document();
```

Dit document wordt gebruikt om secties en tabellen toe te voegen.

## Stap 3: Een sectie en een tabel toevoegen
Nu gaan we een sectie toevoegen aan ons PDF-document en een tabel in deze sectie maken.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

We specificeren ook een topmarge van 300 punten voor de tabel. U kunt deze waarde aanpassen naar uw behoeften.

## Stap 4: Tafelopstelling
In deze stap configureren we tabeleigenschappen, zoals kolombreedtes en randen.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Hier definiëren we de breedte van de tabelkolommen en de celranden. U kunt deze waarden aanpassen naar uw voorkeuren.

## Stap 5: Rijen en cellen toevoegen aan de tabel
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

Hier maken we 17 rijen in de tabel en voegen drie cellen toe aan elke rij. U kunt de gesp aanpassen aan uw behoeften.

## Stap 6: Tabelonderbrekingen bepalen
Nu gaan we bepalen of de tabel de paginamarges overschrijdt door de hoogte van de pagina te vergelijken met de totale hoogte van de objecten in de tabel.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

We berekenen de hoogte van de pagina en de totale hoogte van de objecten, rekening houdend met de marges. Als het verschil 10 of minder is, overschrijdt de tabel de paginamarges.

## Stap 7: Het PDF-document opslaan
Tot slot slaan we het PDF-document met de resultaten op.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Zorg ervoor dat u de juiste documentdirectory opgeeft. Het resulterende PDF-bestand wordt opgeslagen met de vastgestelde tabelonderbrekingen.

### Voorbeeldbroncode voor het bepalen van een tabelonderbreking met behulp van Aspose.PDF voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instantieer een object PDF-klasse
Document pdf = new Document();
// Voeg de sectie toe aan de PDF-documentsectiesverzameling
Aspose.Pdf.Page page = pdf.Pages.Add();
// Een tabelobject instantiëren
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Voeg de tabel toe in de alineaverzameling van de gewenste sectie
page.Paragraphs.Add(table1);
// Instellen met kolombreedtes van de tabel
table1.ColumnWidths = "100 100 100";
// Standaard celrand instellen met behulp van het BorderInfo-object
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Stel de tabelrand in met behulp van een ander aangepast BorderInfo-object
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Maak een MarginInfo-object en stel de linker-, onder-, rechter- en bovenmarges in
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Stel de standaard celopvulling in op het MarginInfo-object
table1.DefaultCellPadding = margin;
// Als je de teller op 17 zet, zal de tafel kapot gaan
// Omdat het niet meer op deze pagina kan worden ondergebracht
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//Maak rijen in de tabel en vervolgens cellen in de rijen
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Ontvang de informatie over de paginahoogte
float PageHeight = (float)pdf.PageInfo.Height;
// Ontvang de totale hoogte-informatie van de boven- en ondermarge van de pagina,
// Tafelbladmarge en tafelhoogte.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Weergavepaginahoogte, tabelhoogte, tabelbovenmarge en paginabovenkant
// En informatie over de ondermarge
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Controleer of we de som van de bovenste paginamarge + de onderste paginamarge aftrekken
// + Tafelbladmarge en tabelhoogte van paginahoogte en zijn minder
// Dan 10 (een gemiddelde rij kan groter zijn dan 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Als de waarde kleiner is dan 10, wordt het bericht weergegeven.
	//Wat aantoont dat er geen andere rij geplaatst kan worden en als we een nieuwe toevoegen
	// Rij, tabel zal breken. Het hangt af van de rijhoogtewaarde.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Sla het pdf-document op
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusie
In deze tutorial hebben we geleerd hoe u tabelonderbrekingen in een PDF-document kunt bepalen met Aspose.PDF voor .NET. U kunt deze stapsgewijze handleiding gebruiken om te controleren of een tabel de paginamarges in uw eigen C#-projecten overschrijdt.

### FAQ's voor het bepalen van een tabelonderbreking in een PDF-bestand

#### V: Wat is het doel van het bepalen van tabeleinden in een PDF-document?

A: Het doel van het bepalen van tabelonderbrekingen in een PDF-document is om te controleren of de tabel de paginamarges overschrijdt. Dit zorgt ervoor dat de inhoud van de tabel correct wordt weergegeven binnen de beschikbare paginaruimte. Door tabelonderbrekingen te detecteren, kunt u de overloop van de inhoud verwerken en de tabelindeling dienovereenkomstig aanpassen.

#### V: Hoe kan ik de bovenmarge van de tabel aanpassen?

 A: In de meegeleverde C#-broncode kunt u de bovenmarge van de tabel aanpassen door de waarde van de`table1.Margin.Top`eigenschap. Verhoog of verlaag de waarde indien nodig om de gewenste bovenmarge voor de tabel in te stellen.

#### V: Kan ik het uiterlijk van de tabel aanpassen, zoals de celkleuren en de lettergrootte?

A: Ja, u kunt het uiterlijk van de tabel en de cellen aanpassen met behulp van verschillende eigenschappen en methoden die worden geboden door Aspose.PDF voor .NET. U kunt bijvoorbeeld de achtergrondkleuren van cellen, de lettergrootte, het lettertype, de tekstuitlijning en meer wijzigen. Raadpleeg de officiële documentatie voor meer informatie over het aanpassen van het uiterlijk van de tabel.

#### V: Wat gebeurt er als de tabel de paginamarges overschrijdt?

A: Als de tabel de paginamarges overschrijdt, kan dit resulteren in afkapping of overlapping van de inhoud, waardoor het PDF-document minder leesbaar en georganiseerd wordt. Door tabelonderbrekingen te detecteren en de overloop te verwerken, kunt u ervoor zorgen dat de inhoud correct wordt weergegeven binnen het beschikbare paginagebied.

#### V: Kan ik tabeleinden bepalen voor meerdere tabellen in hetzelfde PDF-document?

A: Ja, u kunt tabelonderbrekingen bepalen voor meerdere tabellen in hetzelfde PDF-document. Herhaal de stappen eenvoudigweg voor elke tabel die u wilt analyseren en pas de tabelindeling indien nodig aan om overloop van inhoud te voorkomen.