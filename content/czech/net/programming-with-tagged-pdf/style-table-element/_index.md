---
title: Prvek tabulky stylu
linktitle: Prvek tabulky stylu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se formátovat prvek tabulky pomocí Aspose.PDF pro .NET. Podrobný průvodce přizpůsobením stylů a vlastností.
type: docs
weight: 170
url: /cs/net/programming-with-tagged-pdf/style-table-element/
---
tomto podrobném tutoriálu vás provedeme poskytnutým zdrojovým kódem C# krok za krokem k formátování prvku pole pomocí Aspose.PDF for .NET. Postupujte podle pokynů níže, abyste pochopili, jak přizpůsobit styly a vlastnosti prvku pole.

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
taggedContent.SetTitle("Example of table formatting");
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

## Krok 5: Přizpůsobení stylů a vlastností prvků pole

V tomto kroku přizpůsobíme styly a vlastnosti prvku pole.

```csharp
// Přizpůsobte styly a vlastnosti prvku pole
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

// Přizpůsobte styl opakovaných čar
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

K přizpůsobení prvku tabulky jsme použili různé vlastnosti, jako je barva pozadí, okraje, zarovnání, výchozí styl buňky, okraje, šířka sloupce atd.

## Krok 6: Přidejte záhlaví, tělo a zápatí tabulky

Nyní k prvku tabulky přidáme záhlaví, tělo a zápatí tabulky.
```csharp
// Přidejte záhlaví tabulky
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Počet řádků a sloupců v tabulce
int rowCount = 10;
int colCount = 5;
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

//Přidejte řádky těla tabulky
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

// Přidejte spodní čáru stolu
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Do tabulky jsme přidali záhlaví, řádky těla a řádek zápatí pomocí odpovídajících prvků.

## Krok 7: Uložení označeného dokumentu PDF

Nyní, když jsme vytvořili náš dokument s prvkem styled table, uložíme jej jako tagovaný dokument PDF.

```csharp
// Uložte tagovaný dokument PDF
document.Save(dataDir + "StyleTableElement.pdf");
```

Označený dokument PDF jsme uložili do určeného adresáře.

## Krok 8: Ověření souladu s PDF/UA

Dále ověříme shodu našeho dokumentu s PDF/UA.

```csharp
// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Nahráli jsme označený dokument PDF a ověřili jsme jeho shodu s PDF/UA vygenerováním zprávy XML.

### Ukázkový zdrojový kód pro prvek tabulky stylu pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;

// Vytvořte prvek struktury tabulky
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

// Uložit označený dokument PDF
document.Save(dataDir + "StyleTableElement.pdf");

// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

V tomto tutoriálu jsme se naučili formátovat prvek pole pomocí Aspose.PDF pro .NET. Upravili jsme styly a vlastnosti prvku tabulky, přidali záhlaví, řádky těla a zápatí, uložili jsme tagovaný dokument PDF a ověřili jeho shodu s PDF/UA.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu o formátování prvku pole pomocí Aspose.PDF pro .NET?

Odpověď: Cílem tohoto tutoriálu je provést vás procesem formátování prvku pole v dokumentu PDF pomocí Aspose.PDF pro .NET. Poskytuje podrobné pokyny a příklady zdrojového kódu C#, které vám pomohou přizpůsobit styly a vlastnosti prvku pole.

#### Otázka: Jaké jsou předpoklady pro následování tohoto kurzu?

A: Než začnete, ujistěte se, že jste nastavili své vývojové prostředí pro použití Aspose.PDF pro .NET. To zahrnuje instalaci knihovny Aspose.PDF a konfiguraci vašeho projektu tak, aby na ni odkazoval.

#### Otázka: Jak mohu vytvořit nový dokument PDF a nastavit jeho název a jazyk pomocí Aspose.PDF pro .NET?

 A: Chcete-li vytvořit nový dokument PDF, musíte vytvořit a`Document` objekt z knihovny Aspose.PDF. Zdrojový kód jazyka C# poskytnutý tutoriálem ukazuje, jak vytvořit dokument a nastavit jeho název a vlastnosti jazyka.

#### Otázka: Jaký je význam elementu kořenové struktury v dokumentu PDF?

Odpověď: Prvek kořenové struktury funguje jako kontejner pro další prvky struktury a pomáhá organizovat a kategorizovat obsah dokumentu PDF. Hraje klíčovou roli při vytváření logické struktury dokumentu.

#### Otázka: Jak vytvořím a přizpůsobím prvek struktury pole pomocí Aspose.PDF pro .NET?

 Odpověď: Prvek struktury pole můžete vytvořit pomocí`CreateTableElement()` metoda. Zdrojový kód výukového programu poskytuje příklady přizpůsobení různých vlastností prvku tabulky, jako je barva pozadí, ohraničení, zarovnání, šířka sloupce a další.

#### Otázka: Mohu přizpůsobit styly a vlastnosti buněk tabulky v prvku pole?

Odpověď: Ano, výukový program popisuje, jak přizpůsobit styly a vlastnosti celého prvku tabulky, včetně záhlaví, řádků těla a zápatí. Neřeší však konkrétně přizpůsobení jednotlivých buněk tabulky.

#### Otázka: Jak mohu přidat záhlaví, řádky těla a zápatí do prvku tabulky?

Odpověď: Výukový program vysvětluje, jak vytvořit a přidat záhlaví, řádky těla a zápatí do prvku tabulky pomocí vhodných metod poskytovaných Aspose.PDF pro .NET.

#### Otázka: Co je soulad s PDF/UA a jak to mohu ověřit pro můj tagovaný dokument PDF?

 Odpověď: Soulad s PDF/UA zajišťuje, že dokument PDF odpovídá standardům přístupnosti, takže je přístupnější pro uživatele se zdravotním postižením. Výukový program ukazuje, jak ověřit shodu PDF/UA pomocí`Validate()` a vygenerovat zprávu o souladu s XML.

#### Otázka: Jak mohu začlenit tyto koncepty do svých vlastních aplikací .NET?

Odpověď: Poskytnuté příklady zdrojového kódu C# můžete použít jako vodítko k implementaci formátování prvků pole ve vašich vlastních aplikacích .NET. Upravte a přizpůsobte kód tak, aby odpovídal vašim požadavkům, a integrujte jej do svých projektů.

#### Otázka: Existují nějaké doporučené doporučené postupy pro formátování prvků pole v dokumentech PDF?

Odpověď: Při formátování prvků pole (tabulek) zvažte čitelnost a přístupnost obsahu. Používejte jasná a čitelná písma, vhodné barvy a udržujte konzistentní rozvržení. Ověřte shodu s PDF/UA, abyste zajistili splnění standardů přístupnosti.

#### Otázka: Jaké další funkce Aspose.PDF pro .NET mohu prozkoumat pro přizpůsobení dokumentu PDF?

Odpověď: Aspose.PDF for .NET nabízí řadu funkcí pro přizpůsobení dokumentu PDF, včetně manipulace s textem, vkládání obrázků, správy polí formuláře, digitálních podpisů, anotací a dalších. Další funkce naleznete v oficiální dokumentaci a zdrojích.