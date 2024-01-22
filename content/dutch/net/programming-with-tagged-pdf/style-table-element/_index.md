---
title: Stijltabelelement
linktitle: Stijltabelelement
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u een tabelelement opmaakt met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het aanpassen van stijlen en eigenschappen.
type: docs
weight: 170
url: /nl/net/programming-with-tagged-pdf/style-table-element/
---
In deze gedetailleerde zelfstudie leiden we u stap voor stap door de meegeleverde C#-broncode om het array-element te formatteren met Aspose.PDF voor .NET. Volg de onderstaande instructies om te begrijpen hoe u de stijlen en eigenschappen van het array-element kunt aanpassen.

## Stap 1: De omgeving instellen

Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt geconfigureerd voor het gebruik van Aspose.PDF voor .NET. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

## Stap 2: Een document aanmaken

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

## Stap 3: Het wortelstructuurelement verkrijgen

In deze stap krijgen we het hoofdstructuurelement voor ons document.

```csharp
//Verkrijg het hoofdstructuurelement
StructureElement rootElement = taggedContent.RootElement;
```

We hebben het rootstructuurelement dat zal dienen als container voor het array-element.

## Stap 4: Het array-structuurelement maken

Laten we nu een nieuw tabelstructuurelement voor ons document maken.

```csharp
// Maak het arraystructuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

We hebben een nieuw arraystructuurelement gemaakt en dit aan het hoofdstructuurelement toegevoegd.

## Stap 5: De stijlen en eigenschappen van array-elementen aanpassen

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

// Pas de stijl van herhaalde lijnen aan
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

We hebben verschillende eigenschappen gebruikt om het tabelelement aan te passen, zoals achtergrondkleur, randen, uitlijning, standaard celstijl, marges, kolombreedte, enz.

## Stap 6: Voeg tabelkopteksten, hoofdtekst en voettekst toe

Laten we nu de tabelkopteksten, hoofdtekst en voettekst aan het tabelelement toevoegen.
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

//Voeg de rijen van de tabeltekst toe
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

// Voeg de voetlijn van de tabel toe
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

We hebben de kopteksten, hoofdtekstrijen en voettekstrij aan de tabel toegevoegd met behulp van de overeenkomstige elementen.

## Stap 7: Het getagde PDF-document opslaan

Nu we ons document met het opgemaakte tabelelement hebben gemaakt, slaan we het op als een getagd PDF-document.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableElement.pdf");
```

We hebben het getagde PDF-document in de opgegeven map opgeslagen.

## Stap 8: Validatie van PDF/UA-naleving

Vervolgens valideren we de PDF/UA-conformiteit van ons document.

```csharp
// Conformiteitscontrole van PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We hebben het getagde PDF-document geüpload en de PDF/UA-compatibiliteit ervan gevalideerd door een XML-rapport te genereren.

### Voorbeeldbroncode voor Style Table Element met Aspose.PDF voor .NET 

```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Haal het hoofdstructuurelement op
StructureElement rootElement = taggedContent.RootElement;

// Tabelstructuurelement maken
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

// Bewaar het getagde pdf-document
document.Save(dataDir + "StyleTableElement.pdf");

// Conformiteit met PDF/UA controleren
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u het array-element kunt formatteren met Aspose.PDF voor .NET. We hebben de stijlen en eigenschappen van het tabelelement aangepast, kopteksten, hoofdrijen en een voettekst toegevoegd, het getagde PDF-document opgeslagen en de PDF/UA-compatibiliteit ervan gevalideerd.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial over het formatteren van het array-element met Aspose.PDF voor .NET?

A: Het doel van deze tutorial is om u te begeleiden bij het formatteren van het array-element in een PDF-document met Aspose.PDF voor .NET. Het biedt stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen de stijlen en eigenschappen van het array-element aan te passen.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial?

A: Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld voor het gebruik van Aspose.PDF voor .NET. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

#### Vraag: Hoe kan ik een nieuw PDF-document maken en de titel en taal instellen met Aspose.PDF voor .NET?

 A: Om een nieuw PDF-document te maken, moet u een`Document` object uit de Aspose.PDF-bibliotheek. De C#-broncode van de tutorial laat zien hoe u een document maakt en de titel- en taaleigenschappen instelt.

#### Vraag: Wat is de betekenis van het hoofdstructuurelement in een PDF-document?

A: Het hoofdstructuurelement fungeert als container voor andere structuurelementen en helpt bij het ordenen en categoriseren van de inhoud van het PDF-document. Het speelt een cruciale rol bij het vaststellen van de logische structuur van het document.

#### Vraag: Hoe kan ik een arraystructuurelement maken en aanpassen met Aspose.PDF voor .NET?

 A: U kunt een arraystructuurelement maken met behulp van de`CreateTableElement()` methode. De broncode van de tutorial biedt voorbeelden van het aanpassen van verschillende eigenschappen van het tabelelement, zoals achtergrondkleur, randen, uitlijning, kolombreedte en meer.

#### Vraag: Kan ik de stijlen en eigenschappen van tabelcellen binnen het array-element aanpassen?

A: Ja, in de tutorial wordt beschreven hoe u de stijlen en eigenschappen van het gehele tabelelement kunt aanpassen, inclusief kopteksten, hoofdrijen en voettekst. Het gaat echter niet specifiek in op het aanpassen van individuele tabelcellen.

#### Vraag: Hoe kan ik kopteksten, hoofdtekstrijen en een voettekst aan het tabelelement toevoegen?

A: In de tutorial wordt uitgelegd hoe u kopteksten, hoofdrijen en een voettekst kunt maken en toevoegen aan het tabelelement met behulp van de juiste methoden van Aspose.PDF voor .NET.

#### Vraag: Wat is PDF/UA-compliance en hoe kan ik dit valideren voor mijn getagde PDF-document?

 A: PDF/UA-compliance zorgt ervoor dat het PDF-document voldoet aan de toegankelijkheidsnormen, waardoor het toegankelijker wordt voor gebruikers met een beperking. In de tutorial wordt gedemonstreerd hoe u de PDF/UA-conformiteit kunt valideren met behulp van de`Validate()` methode en genereer een XML-compliancerapport.

#### Vraag: Hoe kan ik deze concepten integreren in mijn eigen .NET-applicaties?

A: U kunt de meegeleverde C#-broncodevoorbeelden gebruiken als richtlijn voor het implementeren van de opmaak van array-elementen in uw eigen .NET-toepassingen. Wijzig en pas de code aan uw vereisten aan en integreer deze in uw projecten.

#### Vraag: Zijn er aanbevolen best practices voor het opmaken van array-elementen in PDF-documenten?

A: Houd bij het opmaken van array-elementen (tabellen) rekening met de leesbaarheid en toegankelijkheid van de inhoud. Gebruik duidelijke en leesbare lettertypen, geschikte kleuren en zorg voor een consistente lay-out. Valideer de PDF/UA-compliance om ervoor te zorgen dat aan de toegankelijkheidsnormen wordt voldaan.

#### Vraag: Welke andere functies van Aspose.PDF voor .NET kan ik verkennen voor het aanpassen van PDF-documenten?

A: Aspose.PDF voor .NET biedt een reeks functies voor het aanpassen van PDF-documenten, waaronder tekstmanipulatie, het invoegen van afbeeldingen, beheer van formuliervelden, digitale handtekeningen, annotaties en meer. Raadpleeg de officiële documentatie en bronnen om aanvullende functionaliteiten te verkennen.