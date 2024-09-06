---
title: Tabelelement maken
linktitle: Tabelelement maken
second_title: Aspose.PDF voor .NET API-referentie
description: Stapsgewijze handleiding voor het maken van een array-element met Aspose.PDF voor .NET. Genereer eenvoudig dynamische PDF's met tabellen.
type: docs
weight: 80
url: /nl/net/programming-with-tagged-pdf/create-table-element/
---
In deze stapsgewijze handleiding leiden we u door het proces van het maken van een array-element met Aspose.PDF voor .NET. Aspose.PDF is een krachtige bibliotheek waarmee u PDF-documenten programmatisch kunt manipuleren. Het maken van een array-element is een veelvoorkomende vereiste bij het genereren van dynamische PDF's, en Aspose.PDF biedt een eenvoudige en efficiënte manier om dit te bereiken.

Laten we de code eens bekijken en leren hoe u een array-element kunt maken met Aspose.PDF voor .NET.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u het volgende bij de hand hebt:

1. Aspose.PDF-bibliotheek voor .NET geïnstalleerd.
2. Basiskennis van de programmeertaal C#.

## Stap 1: De omgeving instellen

Om te beginnen opent u uw C#-ontwikkelomgeving en maakt u een nieuw project. Zorg ervoor dat u een verwijzing naar de Aspose.PDF-bibliotheek voor .NET in uw project hebt toegevoegd.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document maken

 De eerste stap is het maken van een nieuw PDF-document met behulp van de`Document` klas.

```csharp
// Maak het document
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Hier stellen we ook de titel en taal in voor de getagde inhoud.

## Stap 3: Het array-element maken

Vervolgens moeten we het array-element maken en toevoegen aan het document. We beginnen met het ophalen van het root-structuurelement, daarna maken we een nieuw tabelelement met behulp van de`CreateTableElement` methode.

```csharp
// Krijg het wortelstructuurelement
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Sla het getagde PDF-document op
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA-nalevingscontrole
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Voorbeeldbroncode voor Create Table Element met behulp van Aspose.PDF voor .NET 
```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Document maken
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Krijg wortelstructuur element
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Gelabeld PDF-document opslaan
document.Save(dataDir + "CreateTableElement.pdf");

// Controleren van PDF/UA-compatibiliteit
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusie

U hebt geleerd hoe u een array-element kunt maken met Aspose.PDF voor .NET. U kunt nu PDF-documenten met dynamische tabellen genereren met behulp van deze methode. Voel u vrij om meer functies van Aspose.PDF te verkennen om het volledige potentieel ervan te ontdekken.

### Veelgestelde vragen

#### V: Wat is een array-element in een PDF-document en waarom zou ik er een moeten maken met Aspose.PDF voor .NET?

A: Een array-element in een PDF-document vertegenwoordigt een gestructureerde verzameling gegevens, vaak gebruikt voor het maken van tabellen of rasters. U moet mogelijk een array-element maken met Aspose.PDF voor .NET bij het genereren van dynamische PDF's die een gestructureerde gegevenspresentatie vereisen, zoals tabelinformatie of rasters.

#### V: Hoe vereenvoudigt Aspose.PDF voor .NET het proces van het maken van een array-element?

A: Aspose.PDF voor .NET biedt een uitgebreide set klassen en methoden waarmee u array-elementen (tabellen) in een PDF-document programmatisch kunt maken, aanpassen en beheren. Dit elimineert de noodzaak voor handmatige PDF-manipulatie en stroomlijnt de creatie van gestructureerde datarepresentaties.

#### V: Wat zijn de belangrijkste stappen bij het maken van een array-element met Aspose.PDF voor .NET?

A: De belangrijkste stappen zijn het instellen van de omgeving, het maken van het document, het verkrijgen van het root structure element, het maken van een tabelelement, het definiëren van rijen en cellen binnen de tabel en het specificeren van opmaak en eigenschappen voor de elementen. Het meegeleverde codevoorbeeld demonstreert deze stappen.

####  V: Welke rol speelt de`taggedContent` object play in creating an array element?

 A: De`taggedContent` object, verkregen uit het document`TaggedContent`property, waarmee u de structuur van de getagde inhoud in het PDF-document kunt definiëren. Dit omvat het maken en organiseren van array-elementen en hun onderliggende elementen op een hiërarchische manier.

#### V: Hoe zorgt de code voor de toegankelijkheid en semantiek van het gemaakte array-element?

 A: De code stelt attributen in zoals`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , En`ColSpan` om de toegankelijkheid en semantiek van het array-element te verbeteren. Deze kenmerken dragen bij aan een goed gestructureerde, informatieve en visueel aantrekkelijke weergave van gegevens.

#### V: Wat is de betekenis van PDF/UA-compatibiliteit in de context van het maken van array-elementen?

 A: PDF/UA (Universal Accessibility)-compliance zorgt ervoor dat de gegenereerde PDF-documenten toegankelijk zijn voor gebruikers met een beperking en voldoen aan bepaalde toegankelijkheidsnormen. Het codevoorbeeld controleert PDF/UA-compliance met behulp van de`Validate` methode, waarmee u documenten kunt maken die inclusief en toegankelijk zijn.

#### V: Kan ik de opmaak en het uiterlijk van de elementen in de matrix verder aanpassen?

A: Ja, u kunt de opmaak en het uiterlijk van de array-elementen aanpassen door kenmerken aan te passen, zoals achtergrondkleur, randstijl, lettergrootte en uitlijning. Aspose.PDF voor .NET biedt een breed scala aan eigenschappen om de visuele presentatie aan te passen aan uw vereisten.

#### V: Hoe kan ik deze kennis uitbreiden om complexere tabelstructuren te maken of matrixelementen op te nemen in grotere PDF-documenten?

A: U kunt deze kennis uitbreiden door aanvullende functies van Aspose.PDF voor .NET te verkennen, zoals het samenvoegen van meerdere array-elementen, het maken van geneste tabellen, het toevoegen van headers en footers en het integreren van array-elementen in grotere PDF-lay-outs. De documentatie en voorbeelden van de bibliotheek bieden begeleiding voor deze geavanceerde scenario's.

#### V: Is het mogelijk om gegevens uit externe bronnen, zoals databases of spreadsheets, te importeren om de elementen in de matrix te vullen?

A: Ja, u kunt gegevens importeren uit externe bronnen om array-elementen te vullen. U kunt data retrieval- en transformatietechnieken in C# gebruiken om gegevens op te halen uit databases, spreadsheets of andere bronnen en vervolgens de array-elementen dienovereenkomstig te vullen.

#### V: Hoe kan ik de kennis die ik in deze tutorial heb opgedaan, gebruiken om de kwaliteit en bruikbaarheid van de PDF-documenten die ik programmatisch maak, te verbeteren?

A: De kennis die u uit deze tutorial hebt opgedaan, stelt u in staat om gestructureerde en visueel aantrekkelijke array-elementen (tabellen) in PDF-documenten te maken. Door deze technieken te integreren, kunt u de leesbaarheid, toegankelijkheid en gebruikerservaring van dynamisch gegenereerde PDF's verbeteren, waardoor ze informatiever en gebruiksvriendelijker worden.