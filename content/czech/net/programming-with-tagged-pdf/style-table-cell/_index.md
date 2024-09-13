---
title: Buňka tabulky stylu
linktitle: Buňka tabulky stylu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se stylovat buňky tabulky pomocí Aspose.PDF pro .NET. Podrobný průvodce vytvářením a přizpůsobením tabulek.
type: docs
weight: 160
url: /cs/net/programming-with-tagged-pdf/style-table-cell/
---
Vítejte v tomto podrobném tutoriálu o formátování buněk tabulky pomocí Aspose.PDF pro .NET. V této příručce podrobně vysvětlíme každý krok poskytnutého zdrojového kódu C#, abychom vám pomohli pochopit, jak stylovat buňky tabulky. Než začnete, ujistěte se, že jste nainstalovali Aspose.PDF for .NET a nastavili své vývojové prostředí.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Vytvořili jsme nový dokument a nastavili jsme název dokumentu a jazyk.

## Krok 3: Získání prvku kořenové struktury

V tomto kroku získáme element kořenové struktury pro náš dokument.

```csharp
// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;
```

Získali jsme element kořenové struktury, který bude sloužit jako kontejner pro prvky pole.

## Krok 4: Vytvoření prvku struktury pole

Nyní vytvoříme nový prvek struktury tabulky pro náš dokument.

```csharp
// Vytvořte prvek struktury pole
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Vytvořili jsme nový prvek struktury pole a přidali jej do prvku kořenové struktury. Vytvořili jsme také prvky záhlaví, těla a zápatí tabulky.

## Krok 5: Přidání záhlaví tabulky

V tomto kroku přidáme záhlaví tabulky do naší tabulky.

```csharp
// Počet řádků a sloupců v tabulce
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Vytvořte řádek záhlaví tabulky
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

Vytvořili jsme řádek záhlaví pro naši tabulku a přidali buňky záhlaví s vlastnostmi formátování, jako je barva pozadí, okraje, okraje a zarovnání.

## Krok 6: Přidání řádků těla tabulky

Nyní přidáme řádky těla tabulky do naší tabulky.
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

Do těla tabulky jsme přidali řádky pomocí smyček k iteraci přes každou buňku tabulky. Pro každou buňku nastavujeme vlastnosti formátování, jako je barva pozadí, okraje, okraje, zarovnání textu atd.

## Krok 7: Přidání zápatí

Nakonec na náš stůl přidáme zápatí stolu.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Vytvořili jsme zápatí pro naši tabulku a přidali buňky zápatí s textem.



## Krok 8: Uložení označeného dokumentu PDF

Nyní, když jsme vytvořili náš dokument se stylizovanou tabulkou, uložíme jej jako tagovaný dokument PDF.

```csharp
// Uložte označený dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");
```

Označený dokument PDF jsme uložili do určeného adresáře.

## Krok 9: Ověření souladu s PDF/UA

Dále ověříme shodu našeho dokumentu s PDF/UA.

```csharp
// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Nahráli jsme označený dokument PDF a ověřili jsme jeho shodu s PDF/UA vygenerováním zprávy XML.

### Ukázka zdrojového kódu pro buňku tabulky stylu pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte dokument
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;

// Vytvořte prvek struktury tabulky
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

// Uložit označený dokument PDF
document.Save(dataDir + "StyleTableCell.pdf");

// Kontrola shody s PDF/UA
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

V tomto tutoriálu jsme se naučili stylovat buňky tabulky pomocí Aspose.PDF pro .NET. Viděli jsme, jak vytvořit dokument, přidat tabulku se záhlavími, řádky těla a zápatím a přizpůsobit styly buněk. Nakonec jsme uložili označený dokument PDF a ověřili jeho shodu s PDF/UA. Nyní můžete použít Aspose.PDF pro .NET k vytváření a stylování tabulek v aplikacích .NET.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu o formátování buněk tabulky pomocí Aspose.PDF pro .NET?

Odpověď: Tento tutoriál si klade za cíl poskytnout komplexní návod, jak stylovat buňky tabulky v dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Obsahuje podrobné pokyny a příklady zdrojového kódu C#, které vám pomohou pochopit a implementovat formátování buněk tabulky.

#### Otázka: Jaké jsou předpoklady pro následování tohoto kurzu?

Odpověď: Než začnete, ujistěte se, že jste nainstalovali Aspose.PDF pro .NET a nastavili své vývojové prostředí. To zahrnuje konfiguraci vašeho projektu tak, aby odkazoval na knihovnu Aspose.PDF.

#### Otázka: Jak vytvořím nový dokument PDF pomocí Aspose.PDF for .NET?

 A: Chcete-li vytvořit nový dokument PDF, musíte vytvořit instanci a`Document` objekt z knihovny Aspose.PDF. Poskytnutý zdrojový kód C# ukazuje, jak vytvořit dokument a nastavit jeho název a jazyk.

#### Otázka: Jaký je význam elementu kořenové struktury v dokumentu PDF?

Odpověď: Prvek kořenové struktury slouží jako kontejner pro další prvky struktury, což pomáhá organizovat a kategorizovat obsah dokumentu PDF. Hraje klíčovou roli při vytváření logické struktury dokumentu.

#### Otázka: Jak mohu vytvořit prvek struktury tabulky a upravit jeho vzhled pomocí Aspose.PDF pro .NET?

 Odpověď: Prvek struktury tabulky můžete vytvořit pomocí`CreateTableElement()` metoda. Poskytnutý zdrojový kód ukazuje, jak upravit vzhled tabulky, včetně jejího záhlaví, těla a zápatí, nastavením vlastností, jako je barva pozadí, okraje, okraje a zarovnání.

#### Otázka: Mohu do těla tabulky přidat více řádků a sloupců a upravit jejich formátování?

Odpověď: Ano, tutoriál ukazuje, jak přidat více řádků a sloupců do těla tabulky pomocí smyček. Poskytuje také příklady přizpůsobení formátování buněk, jako je barva pozadí, okraje, zarovnání textu, styl písma a další.

#### Otázka: Jaký je účel ověření souladu s PDF/UA a jak mohu toto ověření provést?

 Odpověď: Ověření shody s PDF/UA zajišťuje, že dokument PDF splňuje standardy přístupnosti, takže je přístupnější pro uživatele se zdravotním postižením. Výukový program ukazuje, jak ověřit shodu PDF/UA pomocí`Validate()` a vygenerovat zprávu XML.

#### Otázka: Jak mohu tyto koncepty aplikovat na své vlastní aplikace .NET?

Odpověď: Poskytnuté příklady zdrojového kódu C# můžete použít jako vodítko k implementaci formátování buněk tabulky ve vašich vlastních aplikacích .NET. Přizpůsobte kód podle potřeby, aby vyhovoval vašim požadavkům, a integrujte jej do svých projektů.

#### Otázka: Existují nějaké doporučené doporučené postupy pro stylování buněk tabulky v dokumentech PDF?

Odpověď: Při vytváření stylů buněk tabulky zvažte potřeby svého publika, včetně požadavků na přístupnost. Pro zlepšení čitelnosti použijte kontrastní barvy, vhodná písma a jasné zarovnání buněk. Kromě toho ověřte shodu s PDF/UA, abyste zajistili splnění standardů přístupnosti.

#### Otázka: Jaké další funkce Aspose.PDF pro .NET mohu prozkoumat pro manipulaci s dokumenty PDF?

Odpověď: Aspose.PDF for .NET nabízí širokou škálu funkcí pro manipulaci s dokumenty PDF, včetně extrakce textu, vkládání obrázků, správy polí formuláře, digitálních podpisů a dalších. Prozkoumejte oficiální dokumentaci a zdroje, kde se dozvíte o dalších funkcích.
