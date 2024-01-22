---
title: Řádek tabulky stylu
linktitle: Řádek tabulky stylu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přizpůsobit řádky tabulky pomocí Aspose.PDF for .NET krok za krokem průvodce stylováním a formátováním řádků.
type: docs
weight: 180
url: /cs/net/programming-with-tagged-pdf/style-table-row/
---
tomto podrobném tutoriálu vás provedeme dodaným zdrojovým kódem C# krok za krokem k formátování řádku tabulky pomocí Aspose.PDF for .NET. Postupujte podle pokynů níže, abyste pochopili, jak přizpůsobit styly a vlastnosti řádků tabulky.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste své vývojové prostředí nakonfigurovali pro použití Aspose.PDF pro .NET. To zahrnuje instalaci knihovny Aspose.PDF a konfiguraci vašeho projektu tak, aby na něj odkazoval.

## Krok 2: Vytvoření dokumentu

V tomto kroku vytvoříme nový objekt dokumentu Aspose.PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Vytvořili jsme nový dokument a nastavili jsme název dokumentu a jazyk.

## Krok 3: Získání prvku kořenové struktury

V tomto kroku získáme element kořenové struktury pro náš dokument.

```csharp
//Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;
```

Získali jsme prvek kořenové struktury, který bude sloužit jako kontejner pro prvek pole.

## Krok 4: Vytvoření prvku struktury pole

Nyní vytvoříme nový prvek struktury tabulky pro náš dokument.

```csharp
// Vytvořte prvek struktury pole
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Vytvořili jsme nový prvek struktury pole a přidali jej do prvku kořenové struktury.

## Krok 5: Přizpůsobte styly a vlastnosti řádků tabulky

V tomto kroku přizpůsobíme styly a vlastnosti řádků tabulky.

```csharp
// Přizpůsobte styly a vlastnosti řádků tabulky
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

// Vytvořte řádek záhlaví tabulky
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// Přizpůsobte řádky těla tabulky
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

// Vytvořte řádek zápatí tabulky
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Přizpůsobili jsme různé aspekty řádku tabulky, jako je barva pozadí, ohraničení, výška řádku, stránkování, výchozí styl buňky a další.

## Krok 6: Uložení označeného dokumentu PDF

Nyní, když jsme vytvořili náš dokument se stylizovaným řádkem tabulky, uložíme jej jako tagovaný dokument PDF.
```csharp
// Uložte tagovaný dokument PDF
document.Save(dataDir + "StyleTableRow.pdf");
```

Označený dokument PDF jsme uložili do určeného adresáře.

## Krok 7: Ověření souladu s PDF/UA

Dále ověříme shodu našeho dokumentu s PDF/UA.

```csharp
// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Nahráli jsme označený dokument PDF a ověřili jsme jeho shodu s PDF/UA vygenerováním zprávy XML.


### Ukázka zdrojového kódu pro řádek tabulky stylů pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;

// Vytvořte prvek struktury tabulky
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

// Uložit označený dokument PDF
document.Save(dataDir + "StyleTableRow.pdf");

// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

tomto tutoriálu jsme se naučili formátovat řádek tabulky pomocí Aspose.PDF pro .NET. Přizpůsobili jsme styly a vlastnosti řádků tabulky, přidali záhlaví, řádky těla a zápatí, uložili jsme tagovaný dokument PDF a ověřili jeho shodu s PDF/UA.

### FAQ

#### Otázka: Jaký je účel tohoto kurzu o formátování řádků tabulky pomocí Aspose.PDF pro .NET?

Odpověď: Účelem tohoto kurzu je provést vás procesem formátování řádků tabulky v dokumentu PDF pomocí Aspose.PDF pro .NET. Poskytuje podrobné pokyny a příklady zdrojového kódu C#, které vám pomohou přizpůsobit styly a vlastnosti řádků tabulky.

#### Otázka: Jaké jsou předpoklady pro následování tohoto kurzu?

A: Než začnete, ujistěte se, že jste nastavili své vývojové prostředí pro použití Aspose.PDF pro .NET. To zahrnuje instalaci knihovny Aspose.PDF a konfiguraci vašeho projektu tak, aby na ni odkazoval.

#### Otázka: Jak mohu vytvořit nový dokument PDF a nastavit jeho název a jazyk pomocí Aspose.PDF pro .NET?

 A: Chcete-li vytvořit nový dokument PDF, musíte vytvořit a`Document` objekt z knihovny Aspose.PDF. Zdrojový kód jazyka C# poskytnutý tutoriálem ukazuje, jak vytvořit dokument a nastavit jeho název a vlastnosti jazyka.

#### Otázka: Jaký je význam elementu kořenové struktury v dokumentu PDF?

Odpověď: Prvek kořenové struktury funguje jako kontejner pro další prvky struktury a pomáhá organizovat a kategorizovat obsah dokumentu PDF. Hraje klíčovou roli při vytváření logické struktury dokumentu.

#### Otázka: Jak vytvořím a přizpůsobím prvek struktury tabulky pro formátování řádků tabulky pomocí Aspose.PDF for .NET?

Odpověď: Výukový program vysvětluje, jak vytvořit prvek struktury tabulky a přizpůsobit jeho vlastnosti pro formátování řádků tabulky. Pokrývá aspekty, jako je barva pozadí, ohraničení, výška řádku, stránkování, výchozí styl buňky a další.

#### Otázka: Mohu přizpůsobit styly a vlastnosti jednotlivých buněk v řádku tabulky?

Odpověď: Ano, můžete přizpůsobit styly a vlastnosti jednotlivých buněk v řádku tabulky. Kurz ukazuje, jak nastavit vlastnosti, jako je barva pozadí, ohraničení, barva textu, odsazení a další, pro buňky tabulky ve formátovaném řádku tabulky.

#### Otázka: Jak mohu přidat záhlaví, řádky těla a zápatí do řádku formátované tabulky?

Odpověď: Výukový program poskytuje příklady vytváření a přidávání záhlaví, řádků těla a zápatí do prvku struktury tabulky. Tyto prvky lze dále upravovat pomocí vlastností popsaných v tutoriálu.

#### Otázka: Co je soulad s PDF/UA a jak to mohu ověřit pro můj tagovaný dokument PDF?

 Odpověď: Soulad s PDF/UA zajišťuje, že dokument PDF odpovídá standardům přístupnosti, takže je přístupnější pro uživatele se zdravotním postižením. Výukový program ukazuje, jak ověřit shodu PDF/UA pomocí`Validate()` a vygenerovat zprávu o souladu s XML.

#### Otázka: Jak mohu začlenit tyto koncepty do svých vlastních aplikací .NET?

Odpověď: Poskytnuté příklady zdrojového kódu C# můžete použít jako vodítko k implementaci formátování řádků tabulky ve vašich vlastních aplikacích .NET. Upravte a přizpůsobte kód tak, aby odpovídal vašim požadavkům, a integrujte jej do svých projektů.

#### Otázka: Existují nějaké doporučené doporučené postupy pro formátování řádků tabulky v dokumentech PDF?

Odpověď: Při formátování řádků tabulky zvažte čitelnost a přístupnost obsahu. Ujistěte se, že barvy mají dostatečný kontrast, používejte jasná a čitelná písma a udržujte konzistentní rozvržení. Ověřte shodu s PDF/UA, abyste zajistili splnění standardů přístupnosti.

#### Otázka: Jaké další funkce Aspose.PDF pro .NET mohu prozkoumat pro přizpůsobení dokumentu PDF?

Odpověď: Aspose.PDF for .NET nabízí širokou škálu funkcí pro přizpůsobení dokumentu PDF, včetně manipulace s textem, vkládání obrázků, správy polí formuláře, digitálních podpisů, anotací a dalších. Další funkce naleznete v oficiální dokumentaci a zdrojích.