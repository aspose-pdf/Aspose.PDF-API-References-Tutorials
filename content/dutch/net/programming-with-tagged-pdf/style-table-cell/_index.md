---
title: Stijl tabelcel
linktitle: Stijl tabelcel
second_title: Aspose.PDF voor .NET API-referentie
description: Leer hoe u tabelcellen kunt stylen met Aspose.PDF voor .NET. Stapsgewijze handleiding voor het maken en aanpassen van tabellen.
type: docs
weight: 160
url: /nl/net/programming-with-tagged-pdf/style-table-cell/
---
Welkom bij deze gedetailleerde tutorial over het formatteren van tabelcellen met Aspose.PDF voor .NET. In deze gids leggen we gedetailleerd elke stap uit van de meegeleverde C#-broncode om u te helpen begrijpen hoe u tabelcellen kunt stylen. Zorg ervoor dat u Aspose.PDF voor .NET hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

We hebben een nieuw document gemaakt en de documenttitel en taal ingesteld.

## Stap 3: Het verkrijgen van het wortelstructuurelement

In deze stap verkrijgen we het rootstructuurelement voor ons document.

```csharp
//Verkrijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;
```

We hebben het rootstructuurelement dat als container voor de array-elementen zal dienen.

## Stap 4: Het array-structuurelement maken

Laten we nu een nieuw tabelstructuurelement voor ons document maken.

```csharp
// Maak het array-structuurelement
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

We hebben een nieuw array-structuurelement gemaakt en toegevoegd aan het root-structuurelement. We hebben ook de tabelheader-, body- en footer-elementen gemaakt.

## Stap 5: Tabelkoppen toevoegen

In deze stap voegen we de tabelkoppen toe aan onze tabel.

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

We hebben een koptekstrij voor onze tabel gemaakt en koptekstcellen toegevoegd met opmaakkenmerken zoals achtergrondkleur, randen, marges en uitlijning.

## Stap 6: De tabelbodyrijen toevoegen

Laten we nu de tabelbodyrijen aan onze tabel toevoegen.
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

We hebben rijen aan de body van de tabel toegevoegd met behulp van lussen om over elke tabelcel te itereren. We hebben opmaakeigenschappen voor elke cel ingesteld, zoals achtergrondkleur, randen, marges, tekstuitlijning, etc.

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

Nu we ons document met de opgemaakte tabel hebben gemaakt, slaan we het op als een PDF-document met tags.

```csharp
// Sla het getagde PDF-document op
document.Save(dataDir + "StyleTableCell.pdf");
```

We hebben het getagde PDF-document opgeslagen in de opgegeven directory.

## Stap 9: PDF/UA-nalevingsvalidatie

Vervolgens valideren we de PDF/UA-conformiteit van ons document.

```csharp
// PDF/UA-nalevingscontrole
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

We hebben het getagde PDF-document geüpload en de PDF/UA-conformiteit ervan gevalideerd door een XML-rapport te genereren.

### Voorbeeldbroncode voor Style Table Cell met behulp van Aspose.PDF voor .NET 
```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Krijg wortelstructuur element
StructureElement rootElement = taggedContent.RootElement;

// Maak een tabelstructuurelement
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

// Gelabeld PDF-document opslaan
document.Save(dataDir + "StyleTableCell.pdf");

// Controleren van PDF/UA-compatibiliteit
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

In deze tutorial hebben we geleerd hoe u tabelcellen kunt stylen met Aspose.PDF voor .NET. We hebben gezien hoe u een document kunt maken, een tabel met headers, body-rijen en een footer kunt toevoegen en celstijlen kunt aanpassen. Tot slot hebben we het getagde PDF-document opgeslagen en de PDF/UA-compliance gevalideerd. U kunt nu Aspose.PDF voor .NET gebruiken om tabellen te maken en te stylen in uw .NET-toepassingen.

### Veelgestelde vragen

#### V: Wat is het doel van deze tutorial over het opmaken van tabelcellen met Aspose.PDF voor .NET?

A: Deze tutorial is bedoeld om een uitgebreide gids te bieden over hoe u tabelcellen in een PDF-document kunt stylen met behulp van de Aspose.PDF-bibliotheek voor .NET. Het bevat stapsgewijze instructies en C#-broncodevoorbeelden om u te helpen tabelcelopmaak te begrijpen en te implementeren.

#### V: Wat zijn de vereisten om deze tutorial te kunnen volgen?

A: Voordat u begint, moet u ervoor zorgen dat u Aspose.PDF voor .NET hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld. Dit omvat het configureren van uw project om te verwijzen naar de Aspose.PDF-bibliotheek.

#### V: Hoe maak ik een nieuw PDF-document met Aspose.PDF voor .NET?

A: Om een nieuw PDF-document te maken, moet u een`Document` object uit de Aspose.PDF-bibliotheek. De meegeleverde C#-broncode laat zien hoe u een document maakt en de titel en taal instelt.

#### V: Wat is de betekenis van het rootstructuurelement in een PDF-document?

A: Het root-structuurelement dient als een container voor andere structuurelementen, en helpt bij het organiseren en categoriseren van de inhoud van het PDF-document. Het speelt een cruciale rol bij het vaststellen van de logische structuur van het document.

#### V: Hoe kan ik een tabelstructuurelement maken en het uiterlijk ervan aanpassen met Aspose.PDF voor .NET?

 A: U kunt een tabelstructuurelement maken met behulp van de`CreateTableElement()` methode. De meegeleverde broncode laat zien hoe u het uiterlijk van de tabel kunt aanpassen, inclusief de koptekst, hoofdtekst en voettekst, door eigenschappen in te stellen zoals achtergrondkleur, randen, marges en uitlijning.

#### V: Kan ik meerdere rijen en kolommen aan de tabel toevoegen en de opmaak ervan aanpassen?

A: Ja, de tutorial laat zien hoe u meerdere rijen en kolommen aan de tabelbody kunt toevoegen met behulp van loops. Het geeft ook voorbeelden van het aanpassen van celopmaak, zoals achtergrondkleur, randen, tekstuitlijning, lettertypestijl en meer.

#### V: Wat is het doel van het valideren van PDF/UA-naleving en hoe kan ik deze validatie uitvoeren?

 A: Validatie van PDF/UA-conformiteit zorgt ervoor dat het PDF-document voldoet aan de toegankelijkheidsnormen, waardoor het toegankelijker wordt voor gebruikers met een beperking. De tutorial laat zien hoe u PDF/UA-conformiteit kunt valideren met behulp van de`Validate()` methode en genereer een XML-rapport.

#### V: Hoe kan ik deze concepten toepassen op mijn eigen .NET-toepassingen?

A: U kunt de meegeleverde C# broncodevoorbeelden gebruiken als leidraad voor het implementeren van tabelcelopmaak in uw eigen .NET-toepassingen. Pas de code naar wens aan om aan uw vereisten te voldoen en integreer deze in uw projecten.

#### V: Zijn er aanbevolen best practices voor het opmaken van tabelcellen in PDF-documenten?

A: Houd bij het stylen van tabelcellen rekening met de behoeften van uw publiek, inclusief toegankelijkheidsvereisten. Gebruik contrasterende kleuren, geschikte lettertypen en duidelijke celuitlijning om de leesbaarheid te verbeteren. Valideer daarnaast PDF/UA-naleving om ervoor te zorgen dat aan de toegankelijkheidsnormen wordt voldaan.

#### V: Welke andere functies van Aspose.PDF voor .NET kan ik gebruiken voor het bewerken van PDF-documenten?

A: Aspose.PDF voor .NET biedt een breed scala aan functies voor PDF-documentmanipulatie, waaronder tekstextractie, afbeeldingsinvoeging, formulierveldbeheer, digitale handtekeningen en meer. Bekijk de officiële documentatie en bronnen om meer te weten te komen over aanvullende functionaliteiten.
