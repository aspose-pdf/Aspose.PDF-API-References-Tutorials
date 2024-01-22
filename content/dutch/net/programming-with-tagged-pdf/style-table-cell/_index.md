---
title: Stijltabelcel
linktitle: Stijltabelcel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelcellen kunt opmaken met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het maken en aanpassen van tabellen.
type: docs
weight: 160
url: /nl/net/programming-with-tagged-pdf/style-table-cell/
---
Welkom bij deze gedetailleerde tutorial over het opmaken van tabelcellen met Aspose.PDF voor .NET. In deze handleiding leggen we elke stap van de meegeleverde C#-broncode gedetailleerd uit, zodat u begrijpt hoe u tabelcellen kunt opmaken. Zorg ervoor dat u Aspose.PDF voor .NET hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

We hebben een nieuw document gemaakt en de documenttitel en taal ingesteld.

## Stap 3: Het wortelstructuurelement verkrijgen

In deze stap krijgen we het hoofdstructuurelement voor ons document.

```csharp
//Verkrijg het hoofdstructuurelement
StructureElement rootElement = taggedContent.RootElement;
```

We hebben het rootstructuurelement dat zal dienen als container voor de array-elementen.

## Stap 4: Het array-structuurelement maken

Laten we nu een nieuw tabelstructuurelement voor ons document maken.

```csharp
// Maak het arraystructuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

We hebben een nieuw arraystructuurelement gemaakt en dit aan het hoofdstructuurelement toegevoegd. We hebben ook de tabelkoptekst-, hoofdtekst- en voettekstelementen gemaakt.

## Stap 5: Tabelkoppen toevoegen

In deze stap voegen we de tabelkoppen aan onze tabel toe.

```csharp
// Aantal rijen en kolommen in de tabel
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Maak de tabelkoprij
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

We hebben een koptekstrij voor onze tabel gemaakt en koptekstcellen toegevoegd met opmaakeigenschappen zoals achtergrondkleur, randen, marges en uitlijning.

## Stap 6: De rijen van de tabeltekst toevoegen

Laten we nu de rijen van de tabeltekst aan onze tabel toevoegen.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

We hebben rijen aan de hoofdtekst van de tabel toegevoegd met behulp van lussen om elke tabelcel te doorlopen. We stellen opmaakeigenschappen voor elke cel in, zoals achtergrondkleur, randen, marges, tekstuitlijning, enz.

## Stap 7: De voettekst toevoegen

Ten slotte voegen we de tabelvoettekst toe aan onze tabel.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

We hebben een voettekst voor onze tabel gemaakt en voettekstcellen met tekst toegevoegd.



## Stap 8: Het getagde PDF-document opslaan

Nu we ons document met de opgemaakte tabel hebben gemaakt, slaan we het op als een getagd PDF-document.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableCell.pdf");
```

We hebben het getagde PDF-document in de opgegeven map opgeslagen.

## Stap 9: Validatie van PDF/UA-naleving

Vervolgens valideren we de PDF/UA-conformiteit van ons document.

```csharp
// Conformiteitscontrole van PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We hebben het getagde PDF-document geüpload en de PDF/UA-compatibiliteit ervan gevalideerd door een XML-rapport te genereren.

### Voorbeeldbroncode voor Style Table Cell met Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Haal het hoofdstructuurelement op
StructureElement rootElement = taggedContent.RootElement;

// Tabelstructuurelement maken
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// Conformiteit met PDF/UA controleren
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze zelfstudie hebben we geleerd hoe u tabelcellen kunt opmaken met Aspose.PDF voor .NET. We hebben gezien hoe u een document kunt maken, een tabel met kopteksten, hoofdrijen en een voettekst kunt toevoegen en de celstijlen kunt aanpassen. Ten slotte hebben we het getagde PDF-document opgeslagen en de PDF/UA-compatibiliteit ervan gevalideerd. U kunt nu Aspose.PDF voor .NET gebruiken om tabellen in uw .NET-toepassingen te maken en op te maken.

### Veelgestelde vragen

#### Vraag: Wat is het doel van deze tutorial over het opmaken van tabelcellen met Aspose.PDF voor .NET?

A: Deze tutorial is bedoeld om een uitgebreide handleiding te bieden over hoe u tabelcellen in een PDF-document kunt opmaken met behulp van de Aspose.PDF-bibliotheek voor .NET. Het bevat stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen de opmaak van tabelcellen te begrijpen en te implementeren.

#### Vraag: Wat zijn de vereisten voor het volgen van deze tutorial?

A: Voordat u begint, moet u ervoor zorgen dat u Aspose.PDF voor .NET hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Dit omvat het configureren van uw project om te verwijzen naar de Aspose.PDF-bibliotheek.

#### Vraag: Hoe maak ik een nieuw PDF-document met Aspose.PDF voor .NET?

A: Om een nieuw PDF-document te maken, moet u een`Document` object uit de Aspose.PDF-bibliotheek. De meegeleverde C#-broncode laat zien hoe u een document maakt en de titel en taal ervan instelt.

#### Vraag: Wat is de betekenis van het hoofdstructuurelement in een PDF-document?

A: Het hoofdstructuurelement dient als container voor andere structuurelementen, waardoor de inhoud van het PDF-document wordt georganiseerd en gecategoriseerd. Het speelt een cruciale rol bij het vaststellen van de logische structuur van het document.

#### Vraag: Hoe kan ik een tabelstructuurelement maken en het uiterlijk ervan aanpassen met Aspose.PDF voor .NET?

 A: U kunt een tabelstructuurelement maken met behulp van de`CreateTableElement()` methode. De meegeleverde broncode laat zien hoe u het uiterlijk van de tabel kunt aanpassen, inclusief de koptekst, hoofdtekst en voettekst, door eigenschappen in te stellen zoals achtergrondkleur, randen, marges en uitlijning.

#### Vraag: Kan ik meerdere rijen en kolommen aan de tabeltekst toevoegen en de opmaak ervan aanpassen?

A: Ja, de tutorial laat zien hoe u meerdere rijen en kolommen aan de tabel kunt toevoegen met behulp van lussen. Het biedt ook voorbeelden van het aanpassen van celopmaak, zoals achtergrondkleur, randen, tekstuitlijning, lettertypestijl en meer.

#### Vraag: Wat is het doel van het valideren van PDF/UA-compliance en hoe kan ik deze validatie uitvoeren?

 A: Het valideren van PDF/UA-compliance zorgt ervoor dat het PDF-document voldoet aan de toegankelijkheidsnormen, waardoor het toegankelijker wordt voor gebruikers met een beperking. De tutorial laat zien hoe u de PDF/UA-conformiteit kunt valideren met behulp van de`Validate()` methode en genereer een XML-rapport.

#### Vraag: Hoe kan ik deze concepten toepassen op mijn eigen .NET-applicaties?

A: U kunt de meegeleverde C#-broncodevoorbeelden gebruiken als richtlijn voor het implementeren van tabelcelopmaak in uw eigen .NET-toepassingen. Pas de code indien nodig aan uw vereisten aan en integreer deze in uw projecten.

#### Vraag: Zijn er aanbevolen best practices voor het opmaken van tabelcellen in PDF-documenten?

A: Houd bij het opmaken van tabelcellen rekening met de behoeften van uw publiek, inclusief toegankelijkheidsvereisten. Gebruik contrasterende kleuren, geschikte lettertypen en duidelijke celuitlijning om de leesbaarheid te verbeteren. Valideer bovendien de PDF/UA-compliance om ervoor te zorgen dat aan de toegankelijkheidsnormen wordt voldaan.

#### Vraag: Welke andere functies van Aspose.PDF voor .NET kan ik verkennen voor manipulatie van PDF-documenten?

A: Aspose.PDF voor .NET biedt een breed scala aan functies voor het manipuleren van PDF-documenten, waaronder tekstextractie, het invoegen van afbeeldingen, beheer van formuliervelden, digitale handtekeningen en meer. Verken de officiële documentatie en bronnen voor meer informatie over aanvullende functionaliteiten.
