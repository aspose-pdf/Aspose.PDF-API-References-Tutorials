---
title: Stijl tabelrij
linktitle: Stijl tabelrij
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelrijen kunt aanpassen met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het opmaken en stylen van rijen.
type: docs
weight: 180
url: /nl/net/programming-with-tagged-pdf/style-table-row/
---
In deze gedetailleerde tutorial leiden we u stap voor stap door de meegeleverde C#-broncode om de tabelrij te formatteren met Aspose.PDF voor .NET. Volg de onderstaande instructies om te begrijpen hoe u tabelrijstijlen en -eigenschappen kunt aanpassen.

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
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

We hebben een nieuw document gemaakt en de documenttitel en taal ingesteld.

## Stap 3: Het verkrijgen van het wortelstructuurelement

In deze stap verkrijgen we het rootstructuurelement voor ons document.

```csharp
//Verkrijg het wortelstructuurelement
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

## Stap 5: Pas de rijstijlen en eigenschappen van de tabel aan

In deze stap passen we de rijstijlen en eigenschappen van de tabel aan.

```csharp
// Stijlen en eigenschappen van tabelrijen aanpassen
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
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

// Pas de rijen van de hoofdtekst van de tabel aan
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Maak de voettekstregel van de tabel
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

We hebben verschillende aspecten van de tabelrij aangepast, zoals de achtergrondkleur, randen, rijhoogte, paginering, standaardcelstijl en meer.

## Stap 6: Het getagde PDF-document opslaan

Nu we ons document met de opgemaakte tabelrij hebben gemaakt, slaan we het op als een PDF-document met tags.
```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableRow.pdf");
```

We hebben het getagde PDF-document opgeslagen in de opgegeven directory.

## Stap 7: PDF/UA-nalevingsvalidatie

Vervolgens valideren we de PDF/UA-conformiteit van ons document.

```csharp
// PDF/UA-nalevingscontrole
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We hebben het getagde PDF-document geüpload en de PDF/UA-conformiteit ervan gevalideerd door een XML-rapport te genereren.


### Voorbeeldbroncode voor Style Table Row met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Krijg wortelstructuur element
StructureElement rootElement = taggedContent.RootElement;

// Maak een tabelstructuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
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
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
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
document.Save(dataDir + "StyleTableRow.pdf");

// Controleren van PDF/UA-compatibiliteit
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze tutorial hebben we geleerd hoe we een tabelrij kunnen formatteren met Aspose.PDF voor .NET. We hebben de stijlen en eigenschappen van de tabelrij aangepast, de headers, bodyrijen en footer toegevoegd, het getagde PDF-document opgeslagen en de PDF/UA-compliance gevalideerd.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial over het opmaken van tabelrijen met Aspose.PDF voor .NET?

A: Het doel van deze tutorial is om u te begeleiden door het proces van het formatteren van tabelrijen in een PDF-document met behulp van Aspose.PDF voor .NET. Het biedt stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen bij het aanpassen van tabelrijstijlen en -eigenschappen.

#### V: Wat zijn de vereisten om deze tutorial te kunnen volgen?

A: Voordat u begint, moet u ervoor zorgen dat u uw ontwikkelomgeving hebt ingesteld om Aspose.PDF voor .NET te gebruiken. Dit houdt in dat u de Aspose.PDF-bibliotheek installeert en uw project configureert om ernaar te verwijzen.

#### V: Hoe kan ik een nieuw PDF-document maken en de titel en taal instellen met Aspose.PDF voor .NET?

 A: Om een nieuw PDF-document te maken, moet u een`Document` object uit de Aspose.PDF-bibliotheek. De C#-broncode van de tutorial laat zien hoe u een document maakt en de titel en taaleigenschappen instelt.

#### V: Wat is de betekenis van het rootstructuurelement in een PDF-document?

A: Het root-structuurelement fungeert als een container voor andere structuurelementen en helpt de inhoud van het PDF-document te organiseren en categoriseren. Het speelt een cruciale rol bij het vaststellen van de logische structuur van het document.

#### V: Hoe kan ik een tabelstructuurelement maken en aanpassen om tabelrijen op te maken met behulp van Aspose.PDF voor .NET?

A: De tutorial legt uit hoe u een tabelstructuurelement maakt en de eigenschappen ervan aanpast om tabelrijen op te maken. Het behandelt aspecten zoals achtergrondkleur, randen, rijhoogte, paginering, standaard celstijl en meer.

#### V: Kan ik de stijlen en eigenschappen van afzonderlijke cellen in een tabelrij aanpassen?

A: Ja, u kunt de stijlen en eigenschappen van afzonderlijke cellen binnen een tabelrij aanpassen. De tutorial laat zien hoe u eigenschappen zoals achtergrondkleur, randen, tekstkleur, opvulling en meer instelt voor tabelcellen binnen de opgemaakte tabelrij.

#### V: Hoe kan ik kopteksten, hoofdtekstrijen en een voettekst toevoegen aan de opgemaakte tabelrij?

A: De tutorial geeft voorbeelden van het maken en toevoegen van headers, body-rijen en een footer aan het tabelstructuurelement. Deze elementen kunnen verder worden aangepast met behulp van de eigenschappen die in de tutorial worden beschreven.

#### V: Wat is PDF/UA-compliance en hoe kan ik dit valideren voor mijn getagde PDF-document?

 A: PDF/UA-compliance zorgt ervoor dat het PDF-document voldoet aan de toegankelijkheidsnormen, waardoor het toegankelijker wordt voor gebruikers met een beperking. De tutorial laat zien hoe u PDF/UA-conformiteit kunt valideren met behulp van de`Validate()` methode en genereer een XML-nalevingsrapport.

#### V: Hoe kan ik deze concepten integreren in mijn eigen .NET-toepassingen?

A: U kunt de meegeleverde C# broncodevoorbeelden gebruiken als leidraad voor het implementeren van tabelrijopmaak in uw eigen .NET-toepassingen. Wijzig en pas de code aan om aan uw vereisten te voldoen en integreer deze in uw projecten.

#### V: Zijn er aanbevolen best practices voor het opmaken van tabelrijen in PDF-documenten?

A: Houd bij het formatteren van tabelrijen rekening met de leesbaarheid en toegankelijkheid van de inhoud. Zorg ervoor dat kleuren voldoende contrast hebben, gebruik duidelijke en leesbare lettertypen en zorg voor een consistente lay-out. Valideer PDF/UA-naleving om te zorgen dat aan de toegankelijkheidsnormen wordt voldaan.

#### V: Welke andere functies van Aspose.PDF voor .NET kan ik gebruiken om PDF-documenten aan te passen?

A: Aspose.PDF voor .NET biedt een breed scala aan functies voor het aanpassen van PDF-documenten, waaronder tekstmanipulatie, het invoegen van afbeeldingen, beheer van formuliervelden, digitale handtekeningen, annotaties en meer. Raadpleeg de officiële documentatie en bronnen om extra functionaliteiten te verkennen.