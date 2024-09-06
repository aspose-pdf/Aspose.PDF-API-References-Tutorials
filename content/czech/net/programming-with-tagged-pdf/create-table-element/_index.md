---
title: Vytvořit prvek tabulky
linktitle: Vytvořit prvek tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce vytvořením prvku pole pomocí Aspose.PDF pro .NET. Snadno generujte dynamické soubory PDF s tabulkami.
type: docs
weight: 80
url: /cs/net/programming-with-tagged-pdf/create-table-element/
---
tomto podrobném průvodci vás provedeme procesem vytváření prvku pole pomocí Aspose.PDF for .NET. Aspose.PDF je výkonná knihovna, která vám umožní programově manipulovat s dokumenty PDF. Vytvoření prvku pole je běžným požadavkem při generování dynamických PDF a Aspose.PDF nabízí snadný a efektivní způsob, jak toho dosáhnout.

Pojďme se ponořit do kódu a naučit se vytvořit prvek pole pomocí Aspose.PDF pro .NET.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Nainstalovaná knihovna Aspose.PDF pro .NET.
2. Základní znalost programovacího jazyka C#.

## Krok 1: Nastavení prostředí

Chcete-li začít, otevřete vývojové prostředí C# a vytvořte nový projekt. Ujistěte se, že jste do svého projektu přidali odkaz na knihovnu Aspose.PDF pro .NET.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu

 Prvním krokem je vytvoření nového dokumentu PDF pomocí`Document` třída.

```csharp
// Vytvořte dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Zde také nastavujeme název a jazyk pro označený obsah.

## Krok 3: Vytvoření prvku pole

Dále musíme vytvořit prvek pole a přidat jej do dokumentu. Začneme získáním elementu kořenové struktury, poté vytvoříme nový element tabulky pomocí`CreateTableElement` metoda.

```csharp
// Získejte prvek kořenové struktury
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

// Uložte označený dokument PDF
document.Save(dataDir + "CreateTableElement.pdf");

// Kontrola shody s PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Ukázkový zdrojový kód pro Create Table Element pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Získejte prvek kořenové struktury
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

// Uložit označený dokument PDF
document.Save(dataDir + "CreateTableElement.pdf");

// Kontrola shody s PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

Naučili jste se, jak vytvořit prvek pole pomocí Aspose.PDF pro .NET. Pomocí této metody nyní můžete generovat dokumenty PDF s dynamickými tabulkami. Neváhejte a prozkoumejte další funkce Aspose.PDF, abyste objevili jeho plný potenciál.

### FAQ

#### Otázka: Co je prvek pole v dokumentu PDF a proč bych jej měl vytvářet pomocí Aspose.PDF for .NET?

Odpověď: Prvek pole v dokumentu PDF představuje strukturovanou kolekci dat, která se často používá k vytváření tabulek nebo mřížek. Možná budete muset vytvořit prvek pole pomocí Aspose.PDF for .NET při generování dynamických PDF, které vyžadují prezentaci strukturovaných dat, jako jsou tabulkové informace nebo mřížky.

#### Otázka: Jak Aspose.PDF for .NET zjednodušuje proces vytváření prvku pole?

Odpověď: Aspose.PDF for .NET poskytuje komplexní sadu tříd a metod, které umožňují vytvářet, přizpůsobovat a spravovat prvky pole (tabulky) v dokumentu PDF programově. To eliminuje potřebu ruční manipulace s PDF a zjednodušuje vytváření reprezentací strukturovaných dat.

#### Otázka: Jaké jsou klíčové kroky při vytváření prvku pole pomocí Aspose.PDF pro .NET?

Odpověď: Mezi klíčové kroky patří nastavení prostředí, vytvoření dokumentu, získání prvku kořenové struktury, vytvoření prvku tabulky, definování řádků a buněk v tabulce a určení formátování a vlastností prvků. Poskytnutý příklad kódu ukazuje tyto kroky.

####  Otázka: Jakou roli hraje`taggedContent` object play in creating an array element?

 A:`taggedContent` objekt, získaný z dokumentu`TaggedContent`vlastnost, umožňuje definovat strukturu tagovaného obsahu v dokumentu PDF. To zahrnuje vytváření a organizování prvků pole a jejich podřízených prvků hierarchickým způsobem.

#### Otázka: Jak kód zajišťuje dostupnost a sémantiku vytvořeného prvku pole?

 A: Kód nastavuje atributy jako např`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` a`ColSpan` zlepšit dostupnost a sémantiku prvku pole. Tyto atributy přispívají k dobře strukturované, informativní a vizuálně přitažlivé reprezentaci dat.

#### Otázka: Jaký význam má soulad s PDF/UA v kontextu vytváření prvků pole?

 Odpověď: Soulad s PDF/UA (Universal Accessibility) zajišťuje, že vygenerované dokumenty PDF jsou přístupné uživatelům se zdravotním postižením a splňují určité standardy přístupnosti. Příklad kódu kontroluje shodu s PDF/UA pomocí`Validate` metoda, která vám pomůže vytvořit dokumenty, které jsou inkluzivní a přístupné.

#### Otázka: Mohu dále přizpůsobit formátování a vzhled prvků pole?

Odpověď: Ano, můžete přizpůsobit formátování a vzhled prvků pole úpravou atributů, jako je barva pozadí, styl ohraničení, velikost písma a zarovnání. Aspose.PDF for .NET poskytuje širokou škálu vlastností pro přizpůsobení vizuální prezentace vašim požadavkům.

#### Otázka: Jak mohu rozšířit tyto znalosti, abych vytvořil složitější struktury tabulek nebo začlenil prvky pole do větších dokumentů PDF?

Odpověď: Tyto znalosti můžete rozšířit prozkoumáním dalších funkcí Aspose.PDF pro .NET, jako je slučování více prvků pole, vytváření vnořených tabulek, přidávání záhlaví a zápatí a integrace prvků pole do větších rozvržení PDF. Pokyny pro tyto pokročilé scénáře poskytují dokumentace a příklady knihovny.

#### Otázka: Je možné importovat data z externích zdrojů, jako jsou databáze nebo tabulky, k naplnění prvků pole?

Odpověď: Ano, můžete importovat data z externích zdrojů pro naplnění prvků pole. Techniky načítání a transformace dat v C# můžete použít k načtení dat z databází, tabulek nebo jiných zdrojů a poté odpovídajícím způsobem naplnit prvky pole.

#### Otázka: Jak mohu využít znalosti získané v tomto kurzu ke zvýšení kvality a použitelnosti dokumentů PDF, které vytvářím programově?

Odpověď: Znalosti získané v tomto tutoriálu vám umožňují vytvářet strukturované a vizuálně přitažlivé prvky pole (tabulky) v dokumentech PDF. Začleněním těchto technik můžete zlepšit čitelnost, přístupnost a uživatelskou zkušenost s dynamicky generovanými soubory PDF, díky čemuž jsou informativnější a uživatelsky přívětivější.