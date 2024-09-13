---
title: Stijl Tabel Element
linktitle: Stijl Tabel Element
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelelementen kunt opmaken met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het aanpassen van stijlen en eigenschappen.
type: docs
weight: 170
url: /nl/net/programming-with-tagged-pdf/style-table-element/
---
In deze gedetailleerde tutorial leiden we u stap voor stap door de meegeleverde C#-broncode om het array-element te formatteren met Aspose.PDF voor .NET. Volg de onderstaande instructies om te begrijpen hoe u de stijlen en eigenschappen van het array-element kunt aanpassen.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt geconfigureerd om Aspose.PDF voor .NET te gebruiken. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

## Stap 2: Een document maken

In deze stap maken we een nieuw documentobject Aspose.PDF.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

We hebben een nieuw document gemaakt en de documenttitel en taal ingesteld.

## Stap 3: Het verkrijgen van het wortelstructuurelement

In deze stap verkrijgen we het rootstructuurelement voor ons document.

```csharp
// Verkrijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;
```

We hebben het rootstructuurelement dat als container voor het arrayelement zal dienen.

## Stap 4: Het array-structuurelement maken

Laten we nu een nieuw tabelstructuurelement voor ons document maken.

```csharp
// Maak het array-structuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

We hebben een nieuw array-structuurelement gemaakt en toegevoegd aan het root-structuurelement.

## Stap 5: Array-elementstijlen en -eigenschappen aanpassen

In deze stap passen we de stijlen en eigenschappen van het array-element aan.

```csharp
// Pas de stijlen en eigenschappen van het array-element aan
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Pas de stijl van herhaalde regels aan
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

We hebben verschillende eigenschappen gebruikt om het tabelelement aan te passen, zoals achtergrondkleur, randen, uitlijning, standaardcelstijl, marges, kolombreedte, enzovoort.

## Stap 6: Voeg tabelkopteksten, hoofdtekst en voettekst toe

Nu gaan we de tabelkopteksten, de hoofdtekst en de voettekst aan het tabelelement toevoegen.
```csharp
// Tabelkoppen toevoegen
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Aantal rijen en kolommen in de tabel
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

// Maak de tabelkoprij
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//Voeg de rijen van de tabelbody toe
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Voeg de voetregel van de tabel toe
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

We hebben de kopteksten, hoofdtekstrijen en voettekstrijen aan de tabel toegevoegd met behulp van de bijbehorende elementen.

## Stap 7: Het getagde PDF-document opslaan

Nu we ons document met het gestileerde tabelelement hebben gemaakt, slaan we het op als een getagd PDF-document.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableElement.pdf");
```

We hebben het getagde PDF-document opgeslagen in de opgegeven directory.

## Stap 8: PDF/UA-nalevingsvalidatie

Vervolgens valideren we de PDF/UA-conformiteit van ons document.

```csharp
// PDF/UA-nalevingscontrole
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We hebben het getagde PDF-document geüpload en de PDF/UA-conformiteit ervan gevalideerd door een XML-rapport te genereren.

### Voorbeeldbroncode voor Style Table Element met behulp van Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Krijg wortelstructuur element
StructureElement rootElement = taggedContent.RootElement;

// Maak een tabelstructuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Gelabeld PDF-document opslaan
document.Save(dataDir + "StyleTableElement.pdf");

// Controleren van PDF/UA-compatibiliteit
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze tutorial hebben we geleerd hoe we het array-element kunnen formatteren met Aspose.PDF voor .NET. We hebben de stijlen en eigenschappen van het tabelelement aangepast, headers, body-rijen en een voettekst toegevoegd, het getagde PDF-document opgeslagen en de PDF/UA-compliance gevalideerd.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial over het opmaken van het array-element met Aspose.PDF voor .NET?

A: Het doel van deze tutorial is om u te begeleiden door het proces van het formatteren van het array-element in een PDF-document met behulp van Aspose.PDF voor .NET. Het biedt stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen de stijlen en eigenschappen van het array-element aan te passen.

#### V: Wat zijn de vereisten om deze tutorial te kunnen volgen?

A: Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt ingesteld om Aspose.PDF voor .NET te gebruiken. Dit houdt in dat u de Aspose.PDF-bibliotheek installeert en uw project configureert om ernaar te verwijzen.

#### V: Hoe kan ik een nieuw PDF-document maken en de titel en taal instellen met Aspose.PDF voor .NET?

 A: Om een nieuw PDF-document te maken, moet u een`Document` object uit de Aspose.PDF-bibliotheek. De C#-broncode van de tutorial laat zien hoe u een document maakt en de titel en taaleigenschappen instelt.

#### V: Wat is de betekenis van het rootstructuurelement in een PDF-document?

A: Het root-structuurelement fungeert als een container voor andere structuurelementen en helpt de inhoud van het PDF-document te organiseren en categoriseren. Het speelt een cruciale rol bij het vaststellen van de logische structuur van het document.

#### V: Hoe kan ik een arraystructuurelement maken en aanpassen met Aspose.PDF voor .NET?

 A: U kunt een arraystructuurelement maken met behulp van de`CreateTableElement()` methode. De broncode van de tutorial biedt voorbeelden van het aanpassen van verschillende eigenschappen van het tabelelement, zoals achtergrondkleur, randen, uitlijning, kolombreedte en meer.

#### V: Kan ik de stijlen en eigenschappen van tabelcellen binnen het array-element aanpassen?

A: Ja, de tutorial behandelt hoe u de stijlen en eigenschappen van het gehele tabelelement kunt aanpassen, inclusief headers, body-rijen en footer. Het behandelt echter niet specifiek het aanpassen van individuele tabelcellen.

#### V: Hoe kan ik kopteksten, hoofdtekstrijen en een voettekst toevoegen aan het tabelelement?

A: In de tutorial wordt uitgelegd hoe u headers, body-rijen en een voettekst aan het tabelelement kunt toevoegen met behulp van de juiste methoden die Aspose.PDF voor .NET biedt.

#### V: Wat is PDF/UA-compliance en hoe kan ik dit valideren voor mijn getagde PDF-document?

 A: PDF/UA-compliance zorgt ervoor dat het PDF-document voldoet aan de toegankelijkheidsnormen, waardoor het toegankelijker wordt voor gebruikers met een beperking. De tutorial laat zien hoe u PDF/UA-conformiteit kunt valideren met behulp van de`Validate()` methode en genereer een XML-nalevingsrapport.

#### V: Hoe kan ik deze concepten integreren in mijn eigen .NET-toepassingen?

A: U kunt de meegeleverde C# broncodevoorbeelden gebruiken als leidraad voor het implementeren van array-elementopmaak in uw eigen .NET-toepassingen. Wijzig en pas de code aan om aan uw vereisten te voldoen en integreer deze in uw projecten.

#### V: Zijn er aanbevolen best practices voor het opmaken van array-elementen in PDF-documenten?

A: Houd bij het formatteren van array-elementen (tabellen) rekening met de leesbaarheid en toegankelijkheid van de inhoud. Gebruik duidelijke en leesbare lettertypen, geschikte kleuren en zorg voor een consistente lay-out. Valideer PDF/UA-naleving om te garanderen dat aan de toegankelijkheidsnormen wordt voldaan.

#### V: Welke andere functies van Aspose.PDF voor .NET kan ik gebruiken om PDF-documenten aan te passen?

A: Aspose.PDF voor .NET biedt een scala aan functies voor het aanpassen van PDF-documenten, waaronder tekstmanipulatie, het invoegen van afbeeldingen, beheer van formuliervelden, digitale handtekeningen, annotaties en meer. Raadpleeg de officiële documentatie en bronnen om extra functionaliteiten te verkennen.