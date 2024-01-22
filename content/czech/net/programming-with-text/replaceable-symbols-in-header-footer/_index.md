---
title: Vyměnitelné Symboly V Zápatí Záhlaví
linktitle: Vyměnitelné Symboly V Zápatí Záhlaví
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat vyměnitelné symboly v záhlaví a zápatí dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 320
url: /cs/net/programming-with-text/replaceable-symbols-in-header-footer/
---
V tomto tutoriálu si vysvětlíme, jak používat vyměnitelné symboly v záhlaví a zápatí dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces vytvoření PDF, nastavení okrajů, přidání záhlaví a zápatí s vyměnitelnými symboly a uložení PDF pomocí dodaného zdrojového kódu C#.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve je potřeba nastavit cestu k adresáři, kam chcete vygenerovaný PDF soubor uložit. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir`proměnnou s cestou k požadovanému adresáři.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a stránku PDF

 Dále vytvoříme nový dokument PDF a přidáme do něj stránku pomocí`Document` třída a`Page` třídy z knihovny Aspose.PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Nastavte okraje

 Okraje stránky nastavíme pomocí`MarginInfo`třída. Upravte hodnoty okrajů podle svých požadavků.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## Krok 4: Přidejte záhlaví s vyměnitelnými symboly

 Vytváříme a`HeaderFooter` objekt pro stránku a přidejte a`TextFragment` s vyměnitelnými symboly.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// V případě potřeby nastavte vlastnosti textu
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Přidejte další TextFragmenty nebo upravte podle potřeby
```

## Krok 5: Přidejte zápatí s vyměnitelnými symboly

 Podobně vytvoříme a`HeaderFooter` objekt pro zápatí stránky a přidejte`TextFragment` objekty s vyměnitelnými symboly.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Přidejte další TextFragmenty nebo upravte podle potřeby

hfFoot.Paragraphs.Add(tab2);
```

## Krok 6: Uložte dokument PDF

Nakonec dokument PDF uložíme do zadaného výstupního souboru.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Ukázka zdrojového kódu pro vyměnitelné symboly v záhlaví zápatí pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
// Přiřaďte instanci marginInfo vlastnosti Margin sec1.PageInfo
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Vytvořte instanci textového odstavce, který uloží obsah, který se zobrazí jako záhlaví
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Vytvořte objekt HeaderFooter pro sekci
HeaderFooter hfFoot = new HeaderFooter();
// Nastavte objekt HeaderFooter na liché a sudé zápatí
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Přidejte textový odstavec obsahující aktuální číslo stránky z celkového počtu stránek
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Vytvořte instanci objektu tabulky
Table tab2 = new Table();
// Přidejte tabulku do kolekce odstavců požadované sekce
hfFoot.Paragraphs.Add(tab2);
// Nastavte šířku sloupců tabulky
tab2.ColumnWidths = "165 172 165";
// Vytvořte řádky v tabulce a poté buňky v řádcích
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Nastavte svislé zarovnání textu na střed
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java je kompilací všech komponent Java nabízených společností Aspose. Je kompilován na #$NL" + "denně, aby bylo zajištěno, že obsahuje nejaktuálnější verze každého našich komponent Java. #$NL " + "Pomocí Aspose.Total for Java mohou vývojáři vytvořit širokou škálu aplikací. #$NL #$NL #$NP" + "Aspose.Total for Java je kompilací všech komponent Java nabízené společností Aspose. Je kompilován na #$NL" + "denně, aby bylo zajištěno, že obsahuje nejaktuálnější verze každé z našich komponent Java. #$NL " + "Pomocí Aspose.Total pro vývojáře Java mohou vytvořit široké rozsah aplikací. #$NL #$NL #$NP" + "Aspose.Total for Java je kompilací všech komponent Java nabízených společností Aspose. Kompiluje se na #$NL" + "denně, aby bylo zajištěno, že obsahuje co nejvíce aktuální verze každé z našich komponent Java. #$NL " + "Pomocí Aspose.Total pro vývojáře Java mohou vytvářet širokou škálu aplikací. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Přidejte tabulku do kolekce odstavců požadované sekce
page.Paragraphs.Add(table);
// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Nastavte ohraničení tabulky pomocí jiného přizpůsobeného objektu BorderInfo
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
// Vytvořte řádky v tabulce a poté buňky v řádcích
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Závěr

tomto tutoriálu jste se naučili používat vyměnitelné symboly v záhlaví a zápatí dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a provedením poskytnutého kódu C# můžete vytvořit PDF, nastavit okraje, přidat záhlaví a zápatí s vyměnitelnými symboly a uložit PDF.

### FAQ

#### Otázka: Jaký je účel kurzu "Vyměnitelné symboly v záhlaví a zápatí"?

Odpověď: Výukový program "Vyměnitelné symboly v záhlaví zápatí" si klade za cíl vás provést procesem používání knihovny Aspose.PDF pro .NET k přidávání vyměnitelných symbolů do záhlaví a zápatí dokumentu PDF. Nahraditelné symboly vám umožňují při generování PDF dynamicky nahrazovat konkrétní zástupné symboly skutečnými hodnotami.

#### Otázka: Co jsou nahraditelné symboly v kontextu záhlaví a zápatí PDF?

Odpověď: Nahraditelné symboly jsou zástupné symboly, které můžete vložit do záhlaví a zápatí dokumentu PDF. Tyto symboly fungují jako dynamické zástupné symboly pro hodnoty, které lze vyplnit za běhu, jako jsou čísla stránek, data a vlastní informace.

#### Otázka: Proč bych měl chtít v záhlaví a zápatí PDF používat vyměnitelné symboly?

Odpověď: Nahraditelné symboly v záhlaví a zápatí jsou užitečné, když chcete do dokumentů PDF zahrnout dynamické informace, jako jsou čísla stránek, data nebo jiná proměnná data, která se mohou při generování dokumentu změnit.

#### Otázka: Jak mohu nastavit okraje pro stránku PDF?

 Odpověď: Okraje stránky PDF můžete nastavit pomocí`MarginInfo` třídy a přiřadit ji k`Margin` vlastnictvím`PageInfo` stránky. Podle potřeby upravte hodnoty okrajů.

#### Otázka: Jak přidám vyměnitelné symboly do záhlaví a zápatí?

 A: Můžete přidat vyměnitelné symboly vytvořením a`HeaderFooter` objekt pro záhlaví a zápatí stránky. Pak můžete přidat`TextFragment`objektů s požadovaným textem, včetně vyměnitelných symbolů, do`Paragraphs` sbírka`HeaderFooter` objekt.

#### Otázka: Mohu upravit vzhled vyměnitelných symbolů?

 Odpověď: Ano, vzhled vyměnitelných symbolů můžete upravit úpravou vlastností`TextFragment` objekty, které obsahují symboly. Můžete nastavit vlastnosti, jako je písmo, velikost písma, barva, zarovnání a řádkování.

#### Otázka: Jaký druh vyměnitelných symbolů mohu použít?

Odpověď: Můžete použít různé vyměnitelné symboly, například:

- `$p`: Číslo aktuální stránky.
- `$P`: Celkový počet stránek.
- `$d`: Dnešní datum.
- `$t`: Aktuální čas.
- Vlastní zástupné symboly, které definujete.

#### Otázka: Mohu kolem vyměnitelných symbolů zahrnout jiný text a formátování?

 Odpověď: Ano, kolem vyměnitelných symbolů můžete vložit další text a formátování`TextFragment` objektů. To vám umožní vytvářet složitější záhlaví a zápatí, které zahrnují dynamický a statický obsah.

#### Otázka: Jak mohu uložit vygenerovaný dokument PDF?

 A: Chcete-li uložit vygenerovaný dokument PDF, můžete použít`Save` metoda`Document`třída. Jako argument zadejte požadovanou cestu a název výstupního souboru.

#### Otázka: Je pro tento výukový program vyžadována platná licence Aspose?

Odpověď: Ano, pro úspěšné spuštění kódu v tomto kurzu je vyžadována platná licence Aspose. Na webu Aspose můžete získat plnou licenci nebo 30denní dočasnou licenci.