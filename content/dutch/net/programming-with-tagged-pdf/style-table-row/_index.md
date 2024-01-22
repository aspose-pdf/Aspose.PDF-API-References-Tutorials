---
title: Stijltabelrij
linktitle: Stijltabelrij
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelrijen kunt aanpassen met Aspose.PDF voor .NET, stapsgewijze handleiding voor het opmaken en opmaken van rijen.
type: docs
weight: 180
url: /nl/net/programming-with-tagged-pdf/style-table-row/
---
In deze gedetailleerde zelfstudie leiden we u stap voor stap door de meegeleverde C#-broncode om de tabelrij te formatteren met Aspose.PDF voor .NET. Volg de onderstaande instructies om te begrijpen hoe u de stijlen en eigenschappen van tabelrijen kunt aanpassen.

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
taggedContent.SetTitle("Example of Table Row Formatting");
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

## Stap 5: Pas de stijlen en eigenschappen van tabelrijen aan

In deze stap passen we de stijlen en eigenschappen van de tabelrijen aan.

```csharp
// Pas de stijlen en eigenschappen van tabelrijen aan
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

We hebben verschillende aspecten van de tabelrij aangepast, zoals achtergrondkleur, randen, rijhoogte, paginering, standaardcelstijl en meer.

## Stap 6: Het getagde PDF-document opslaan

Nu we ons document met de opgemaakte tabelrij hebben gemaakt, slaan we het op als een getagd PDF-document.
```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableRow.pdf");
```

We hebben het getagde PDF-document in de opgegeven map opgeslagen.

## Stap 7: Validatie van PDF/UA-naleving

Vervolgens valideren we de PDF/UA-conformiteit van ons document.

```csharp
// Conformiteitscontrole van PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We hebben het getagde PDF-document geüpload en de PDF/UA-compatibiliteit ervan gevalideerd door een XML-rapport te genereren.


### Voorbeeldbroncode voor Style Table Row met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Haal het hoofdstructuurelement op
StructureElement rootElement = taggedContent.RootElement;

// Tabelstructuurelement maken
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

// Bewaar het getagde pdf-document
document.Save(dataDir + "StyleTableRow.pdf");

// Conformiteit met PDF/UA controleren
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een tabelrij kunt opmaken met Aspose.PDF voor .NET. We hebben de rijstijlen en -eigenschappen van de tabel aangepast, de kopteksten, hoofdrijen en voettekst toegevoegd, het getagde PDF-document opgeslagen en de PDF/UA-compatibiliteit ervan gevalideerd.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial over het opmaken van tabelrijen met Aspose.PDF voor .NET?

A: Het doel van deze tutorial is om u te begeleiden bij het opmaken van tabelrijen in een PDF-document met Aspose.PDF voor .NET. Het biedt stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen de stijlen en eigenschappen van tabelrijen aan te passen.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial?

A: Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld voor het gebruik van Aspose.PDF voor .NET. Dit omvat het installeren van de Aspose.PDF-bibliotheek en het configureren van uw project om ernaar te verwijzen.

#### Vraag: Hoe kan ik een nieuw PDF-document maken en de titel en taal instellen met Aspose.PDF voor .NET?

 A: Om een nieuw PDF-document te maken, moet u een`Document` object uit de Aspose.PDF-bibliotheek. De C#-broncode van de tutorial laat zien hoe u een document maakt en de titel- en taaleigenschappen instelt.

#### Vraag: Wat is de betekenis van het hoofdstructuurelement in een PDF-document?

A: Het hoofdstructuurelement fungeert als container voor andere structuurelementen en helpt bij het ordenen en categoriseren van de inhoud van het PDF-document. Het speelt een cruciale rol bij het vaststellen van de logische structuur van het document.

#### Vraag: Hoe kan ik een tabelstructuurelement maken en aanpassen om tabelrijen op te maken met Aspose.PDF voor .NET?

A: In de tutorial wordt uitgelegd hoe u een tabelstructuurelement maakt en de eigenschappen ervan aanpast om tabelrijen op te maken. Het behandelt aspecten zoals achtergrondkleur, randen, rijhoogte, paginering, standaard celstijl en meer.

#### Vraag: Kan ik de stijlen en eigenschappen van individuele cellen binnen een tabelrij aanpassen?

A: Ja, u kunt de stijlen en eigenschappen van individuele cellen binnen een tabelrij aanpassen. In de zelfstudie wordt gedemonstreerd hoe u eigenschappen zoals achtergrondkleur, randen, tekstkleur, opvulling en meer instelt voor tabelcellen binnen de opgemaakte tabelrij.

#### Vraag: Hoe kan ik kopteksten, hoofdrijen en een voettekst toevoegen aan de opgemaakte tabelrij?

A: De tutorial biedt voorbeelden van het maken en toevoegen van kopteksten, hoofdrijen en een voettekst aan het tabelstructuurelement. Deze elementen kunnen verder worden aangepast met behulp van de eigenschappen die in de tutorial worden beschreven.

#### Vraag: Wat is PDF/UA-compliance en hoe kan ik dit valideren voor mijn getagde PDF-document?

 A: PDF/UA-compliance zorgt ervoor dat het PDF-document voldoet aan de toegankelijkheidsnormen, waardoor het toegankelijker wordt voor gebruikers met een beperking. In de tutorial wordt gedemonstreerd hoe u de PDF/UA-conformiteit kunt valideren met behulp van de`Validate()` methode en genereer een XML-compliancerapport.

#### Vraag: Hoe kan ik deze concepten integreren in mijn eigen .NET-applicaties?

A: U kunt de meegeleverde C#-broncodevoorbeelden gebruiken als richtlijn voor het implementeren van de opmaak van tabelrijen in uw eigen .NET-toepassingen. Wijzig en pas de code aan uw vereisten aan en integreer deze in uw projecten.

#### Vraag: Zijn er aanbevolen best practices voor het opmaken van tabelrijen in PDF-documenten?

A: Houd bij het opmaken van tabelrijen rekening met de leesbaarheid en toegankelijkheid van de inhoud. Zorg ervoor dat kleuren voldoende contrast hebben, gebruik duidelijke en leesbare lettertypen en zorg voor een consistente lay-out. Valideer de PDF/UA-compliance om ervoor te zorgen dat aan de toegankelijkheidsnormen wordt voldaan.

#### Vraag: Welke andere functies van Aspose.PDF voor .NET kan ik verkennen voor het aanpassen van PDF-documenten?

A: Aspose.PDF voor .NET biedt een breed scala aan functies voor het aanpassen van PDF-documenten, waaronder tekstmanipulatie, het invoegen van afbeeldingen, beheer van formuliervelden, digitale handtekeningen, annotaties en meer. Raadpleeg de officiële documentatie en bronnen om aanvullende functionaliteiten te verkennen.