---
title: Tabulka V části Záhlaví Zápatí
linktitle: Tabulka V části Záhlaví Zápatí
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat tabulku do sekce záhlaví/zápatí dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 170
url: /cs/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
V tomto tutoriálu vás krok za krokem provedeme přidáním tabulky do části záhlaví nebo zápatí dokumentu PDF pomocí Aspose.PDF for .NET. Poskytnutý zdrojový kód C# vám ukáže, jak vytvořit prázdný dokument PDF, přidat stránku, nakonfigurovat sekci záhlaví, vytvořit tabulku, přidat do tabulky řádky a buňky a nakonec dokument PDF uložit.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Vytvoření dokumentu a stránky PDF

 Prvním krokem je vytvoření instance souboru`Document` třídy a přidejte stránku do dokumentu. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte instanci objektu dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Vytvořte stránku v dokumentu PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kam chcete uložit dokument PDF.

## Krok 3: Konfigurace sekce záhlaví

 Nyní nakonfigurujeme sekci záhlaví dokumentu PDF vytvořením instance souboru`HeaderFooter` třída. Zde je postup:

```csharp
// Vytvořte sekci záhlaví pro soubor PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Definujte sekci záhlaví stránky
page. Header = header;

// Nastavte horní okraj sekce záhlaví
header. Margin. Top = 20;
```

## Krok 4: Vytvoření tabulky

 Nyní vytvoříme tabulku pomocí`Table` třídy a přidejte ji do kolekce odstavců sekce nadpisu. Zde je postup:

```csharp
// Vytvořte instanci objektu Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Přidejte tabulku do kolekce odstavců sekce záhlaví
header.Paragraphs.Add(tab1);

// Definujte šířky sloupců tabulky
tab1.ColumnWidths = "60,300";
```

Výše uvedený kód vytvoří tabulku se dvěma sloupci zadaných šířek.

## Krok 5: Přidejte do tabulky řádky a buňky

 Nyní přidáme do tabulky řádky a buňky pomocí`Row` třída a`Cell` třída. Zde je postup:

```csharp
// Vytvořte řádek v tabulce a přidejte buňky
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Sloučit první buňku prvního řádku
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Vytvořte další řádek v tabulce a přidejte buňku s obrázkem
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Krok 6: Uložení dokumentu PDF

Jakmile je tabulka přidána do sekce záhlaví, můžeme uložit dokument PDF. Zde je postup:

```csharp
// Uložte soubor PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kam chcete uložit dokument PDF.

### Ukázkový zdrojový kód pro sekci Tabulka v záhlaví zápatí pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci dokumentu voláním prázdného konstruktoru
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Vytvořte stránku v dokumentu pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Vytvořte sekci záhlaví souboru PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Nastavte liché záhlaví pro soubor PDF
page.Header = header;

// Nastavte horní okraj pro sekci záhlaví
header.Margin.Top = 20;

// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Přidejte tabulku do kolekce odstavců požadované sekce
header.Paragraphs.Add(tab1);

// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Nastavte hodnotu rozsahu řádku pro první řádek jako 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Nastavte barvu pozadí pro řádek 2
row2.BackgroundColor = Color.White;

// Přidejte buňku, která obsahuje obrázek
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Nastavte šířku obrázku na 60
img.FixWidth = 60;

// Přidejte obrázek do buňky tabulky
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Nastavte svislé zarovnání textu na střed
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Uložte soubor Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Závěr

gratuluji! Naučili jste se, jak přidat tabulku do sekce záhlaví nebo zápatí dokumentu PDF pomocí Aspose.PDF for .NET. Nyní si můžete upravit záhlaví a zápatí přidáním tabulek pro zobrazení dalších informací v dokumentech PDF.

### Nejčastější dotazy k tabulce v sekci záhlaví zápatí

#### Otázka: Jaký je účel přidání tabulky do části záhlaví nebo zápatí dokumentu PDF?

Odpověď: Přidání tabulky do části záhlaví nebo zápatí dokumentu PDF vám umožní zobrazit strukturované a uspořádané informace, jako jsou názvy, titulky, loga nebo jakýkoli jiný obsah, který chcete, aby se na každé stránce dokumentu konzistentně zobrazoval.

#### Otázka: Jak dodaný zdrojový kód C# dosáhne přidání tabulky do části záhlaví nebo zápatí dokumentu PDF?

Odpověď: Kód demonstruje proces vytvoření prázdného dokumentu PDF, přidání stránky, konfiguraci sekce záhlaví, vytvoření tabulky s řádky a buňkami a nakonec uložení dokumentu PDF. Výsledkem je tabulka zobrazená v záhlaví dokumentu PDF.

#### Otázka: Mohu upravit vzhled buněk tabulky, jako jsou okraje, barva pozadí a styl textu?

Odpověď: Ano, vzhled buněk tabulky můžete přizpůsobit nastavením vlastností, jako jsou okraje buněk, barva pozadí, styl textu, písmo, velikost písma a další.

#### Otázka: Jak se tabulka přidá do sekce záhlaví dokumentu PDF?

Odpověď: Kód přidá tabulku do kolekce odstavců sekce záhlaví, což zajistí, že se tabulka zobrazí v záhlaví každé stránky.

#### Otázka: Mohu do tabulky přidat další řádky a buňky podle potřeby?

 Odpověď: Rozhodně můžete do tabulky přidat další řádky a buňky pomocí`Rows.Add()` a`Cells.Add()` metody. To vám umožní strukturovat obsah tabulky podle potřeby.

#### Q: Je možné upravit šířku sloupců tabulky?
 Odpověď: Ano, můžete upravit šířku sloupců tabulky pomocí`ColumnWidths` vlastnictví. To vám umožní ovládat rozložení tabulky.

#### Otázka: Jak mohu rozložit buňky přes více sloupců nebo řádků v tabulce?
 Odpověď: Chcete-li rozložit buňky přes více sloupců, můžete použít`ColSpan`vlastnost odpovídající buňky. Podobně můžete použít`RowSpan` vlastnost rozprostírat buňky přes více řádků.

#### Otázka: Co se stane, když chci přidat tabulku do části záhlaví i zápatí dokumentu PDF?

 Odpověď: Podobný přístup můžete použít pro sekce záhlaví i zápatí. Jednoduše vytvořte a`HeaderFooter` instanci zápatí, nakonfigurujte ji a přidejte tabulku do její kolekce odstavců.

#### Otázka: Mohu použít obrázky v buňkách tabulky a jak toho lze dosáhnout?

 Odpověď: Ano, do buněk tabulky můžete přidávat obrázky. Příklad kódu ukazuje přidání obrázku do buňky vytvořením souboru`Image` objekt, nastavení jeho cesty k souboru a rozměrů a poté jeho přidání do odstavců buňky.

#### Otázka: Jak zajistím, že se tabulka zobrazí konzistentně na všech stránkách v dokumentu PDF?

 A: Když přidáte tabulku do sekce záhlaví nebo zápatí pomocí`HeaderFooter` Aspose.PDF zajišťuje, že se tabulka zobrazuje konzistentně na každé stránce a poskytuje jednotné rozvržení.