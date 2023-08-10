---
title: Skapa tabellelement
linktitle: Skapa tabellelement
second_title: Aspose.PDF för .NET API Referens
description: Steg för steg guide för att skapa ett arrayelement med Aspose.PDF för .NET. Skapa dynamiska PDF-filer med tabeller enkelt.
type: docs
weight: 80
url: /sv/net/programming-with-tagged-pdf/create-table-element/
---
den här steg-för-steg-guiden går vi igenom processen för att skapa ett array-element med Aspose.PDF för .NET. Aspose.PDF är ett kraftfullt bibliotek som låter dig manipulera PDF-dokument programmatiskt. Att skapa ett arrayelement är ett vanligt krav när man skapar dynamiska PDF-filer, och Aspose.PDF erbjuder ett enkelt och effektivt sätt att åstadkomma detta.

Låt oss dyka in i koden och lära oss hur man skapar ett arrayelement med Aspose.PDF för .NET.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.PDF-bibliotek för .NET installerat.
2. Grundläggande kunskaper i programmeringsspråket C#.

## Steg 1: Sätta upp miljön

För att komma igång, öppna din C#-utvecklingsmiljö och skapa ett nytt projekt. Se till att du har lagt till en referens till Aspose.PDF-biblioteket för .NET i ditt projekt.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet

 Det första steget är att skapa ett nytt PDF-dokument med hjälp av`Document` klass.

```csharp
// Skapa dokumentet
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Här ställer vi även in titel och språk för det taggade innehållet.

## Steg 3: Skapa arrayelementet

Därefter måste vi skapa arrayelementet och lägga till det i dokumentet. Vi börjar med att hämta rotstrukturelementet, sedan skapar vi ett nytt tabellelement med hjälp av`CreateTableElement` metod.

```csharp
// Hämta rotstrukturelementet
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

// Spara det taggade PDF-dokumentet
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA-efterlevnadskontroll
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Exempel på källkod för Skapa tabellelement med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Skapa dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Få rotstrukturelement
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

// Spara taggat pdf-dokument
document.Save(dataDir + "CreateTableElement.pdf");

// Kontrollerar PDF/UA-efterlevnad
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Slutsats

Du har lärt dig hur man skapar ett arrayelement med Aspose.PDF för .NET. Du kan nu generera PDF-dokument med dynamiska tabeller med den här metoden. Utforska gärna fler funktioner i Aspose.PDF för att upptäcka dess fulla potential.

### FAQ's

#### F: Vad är ett matriselement i ett PDF-dokument, och varför skulle jag behöva skapa ett med Aspose.PDF för .NET?

S: Ett matriselement i ett PDF-dokument representerar en strukturerad samling av data, som ofta används för att skapa tabeller eller rutnät. Du kan behöva skapa ett array-element med Aspose.PDF för .NET när du genererar dynamiska PDF-filer som kräver strukturerad datapresentation, som tabellinformation eller rutnät.

#### F: Hur förenklar Aspose.PDF för .NET processen att skapa ett arrayelement?

S: Aspose.PDF för .NET tillhandahåller en omfattande uppsättning klasser och metoder som låter dig skapa, anpassa och hantera arrayelement (tabeller) i ett PDF-dokument programmatiskt. Detta eliminerar behovet av manuell PDF-manipulation och effektiviserar skapandet av strukturerade datarepresentationer.

#### F: Vilka är de viktigaste stegen för att skapa ett array-element med Aspose.PDF för .NET?

S: De viktigaste stegen inkluderar att ställa in miljön, skapa dokumentet, hämta rotstrukturelementet, skapa ett tabellelement, definiera rader och celler i tabellen och ange formatering och egenskaper för elementen. Det medföljande kodexemplet visar dessa steg.

####  F: Vilken roll spelar`taggedContent` object play in creating an array element?

 A: Den`taggedContent` föremål, erhållet från dokumentets`TaggedContent`egenskap, låter dig definiera strukturen för det taggade innehållet i PDF-dokumentet. Detta inkluderar att skapa och organisera arrayelement och deras underordnade element på ett hierarkiskt sätt.

#### F: Hur säkerställer koden tillgänglighet och semantik för det skapade arrayelementet?

 S: Koden sätter attribut som t.ex`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , och`ColSpan` för att förbättra tillgängligheten och semantiken för arrayelementet. Dessa attribut bidrar till en välstrukturerad, informativ och visuellt tilltalande representation av data.

#### F: Vilken betydelse har PDF/UA-kompatibilitet i samband med att skapa arrayelement?

 S: PDF/UA-efterlevnad (Universal Accessibility) säkerställer att de genererade PDF-dokumenten är tillgängliga för användare med funktionshinder och uppfyller vissa tillgänglighetsstandarder. Kodexemplet kontrollerar PDF/UA-kompatibilitet med hjälp av`Validate` metod, som hjälper dig att skapa dokument som är inkluderande och tillgängliga.

#### F: Kan jag anpassa formateringen och utseendet på arrayelementen ytterligare?

S: Ja, du kan anpassa formateringen och utseendet på arrayelementen genom att justera attribut som bakgrundsfärg, kantstil, teckenstorlek och justering. Aspose.PDF för .NET tillhandahåller ett brett utbud av egenskaper för att skräddarsy den visuella presentationen efter dina krav.

#### F: Hur kan jag utöka denna kunskap för att skapa mer komplexa tabellstrukturer eller införliva arrayelement i större PDF-dokument?

S: Du kan utöka denna kunskap genom att utforska ytterligare funktioner i Aspose.PDF för .NET, som att slå samman flera arrayelement, skapa kapslade tabeller, lägga till sidhuvuden och sidfötter och integrera arrayelement i större PDF-layouter. Bibliotekets dokumentation och exempel ger vägledning för dessa avancerade scenarier.

#### F: Är det möjligt att importera data från externa källor, såsom databaser eller kalkylblad, för att fylla i arrayelementen?

S: Ja, du kan importera data från externa källor för att fylla i matriselement. Du kan använda datahämtning och transformationsteknik i C# för att hämta data från databaser, kalkylblad eller andra källor och sedan fylla i arrayelementen därefter.

#### F: Hur kan jag använda kunskapen från denna handledning för att förbättra kvaliteten och användbarheten av PDF-dokument som jag skapar programmatiskt?

S: Kunskapen från denna handledning gör att du kan skapa strukturerade och visuellt tilltalande arrayelement (tabeller) i PDF-dokument. Genom att införliva dessa tekniker kan du förbättra läsbarheten, tillgängligheten och användarupplevelsen för dynamiskt genererade PDF-filer, vilket gör dem mer informativa och användarvänliga.