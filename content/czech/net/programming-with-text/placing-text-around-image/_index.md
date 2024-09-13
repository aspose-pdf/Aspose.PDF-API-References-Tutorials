---
title: Umístění textu kolem obrázku v souboru PDF
linktitle: Umístění textu kolem obrázku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak umístit text kolem obrázku v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 260
url: /cs/net/programming-with-text/placing-text-around-image/
---
tomto tutoriálu vysvětlíme, jak umístit text kolem obrázku v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces vytvoření tabulky, přidání obrázku a umístění textu kolem obrázku pomocí poskytnutého zdrojového kódu C#.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve je potřeba nastavit cestu k adresáři, kam chcete vygenerovaný PDF soubor uložit. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k požadovanému adresáři.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a stránku

 Dále vytvoříme a`Document` objekt a přidejte k němu stránku pomocí`Pages.Add()` metoda.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 3: Vytvořte tabulku

 Vytvoříme tabulku pomocí`Table` třídy a přidejte jej do kolekce odstavců na stránce.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## Krok 4: Nastavte šířky a okraje sloupců tabulky

 Nastavíme šířky sloupců tabulky a vytvoříme a`MarginInfo` objekt pro nastavení okrajů.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## Krok 5: Přidejte obrázek do tabulky

 Vytváříme`Image` objekt, zadejte cestu k souboru obrázku a nastavte pevnou výšku a šířku obrázku. Poté obrázek přidáme do kolekce odstavců buňky tabulky.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## Krok 6: Přidejte text kolem obrázku

 Vytvoříme řetězcové proměnné obsahující text ve formátu HTML a vytvoříme`HtmlFragment`objekt. Poté přidáme text HTML do buňky tabulky obsahující obrázek.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## Krok 7: Přidejte další text

 Tvoříme další`HtmlFragment` objekt obsahující další text ve formátu HTML a přidejte jej do samostatné buňky tabulky.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## Krok 8: Uložte dokument PDF

Nakonec dokument PDF uložíme do zadaného výstupního souboru.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Ukázkový zdrojový kód pro umístění textu kolem obrázku pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Okamžitý objekt dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Vytvořte stránku v Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Přidejte tabulku do kolekce odstavců požadované sekce
page.Paragraphs.Add(table1);
// Nastavte šířku sloupců tabulky
table1.ColumnWidths = "120 270";
// Vytvořte objekt MarginInfo a nastavte jeho levý, spodní, pravý a horní okraj
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Nastavte výchozí odsazení buněk na objekt MarginInfo
table1.DefaultCellPadding = margin;
// Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Vytvořte objekt obrázku
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Zadejte cestu k souboru obrázku
logo.File = dataDir + "aspose-logo.jpg";
// Zadejte obrázek Fixed Height
logo.FixHeight = 120;
// Zadejte obrázek s pevnou šířkou
logo.FixWidth = 110;
row1.Cells.Add();
// Přidejte obrázek do kolekce odstavců buňky tabulky
row1.Cells[0].Paragraphs.Add(logo);
// Vytvořte řetězcové proměnné s textem obsahujícím html značky
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Vytvořte textový objekt, který se přidá napravo od obrázku
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Přidejte do buňky tabulky textové odstavce obsahující text HTML
row1.Cells[1].Paragraphs.Add(TitleText);
// Nastavte svislé zarovnání obsahu řádku jako Horní
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
//Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Nastavte hodnotu rozsahu řádku pro druhý řádek jako 2
SecondRow.Cells[0].ColSpan = 2;
// Nastavte svislé zarovnání druhé řady jako Horní
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Přidejte do buňky tabulky textové odstavce obsahující text HTML
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Uložte soubor Pdf
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Závěr

V tomto tutoriálu jste se naučili, jak umístit text kolem obrázku v dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a spuštěním poskytnutého kódu C# můžete vytvořit tabulku, přidat obrázek a umístit text kolem obrázku v dokumentu PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Umístění textu kolem obrázku v souboru PDF"?

Odpověď: Výukový program "Umístění textu kolem obrázku v souboru PDF" ukazuje, jak použít knihovnu Aspose.PDF pro .NET k umístění textu kolem obrázku v dokumentu PDF. Výukový program poskytuje podrobného průvodce a zdrojový kód C#, který vám pomůže vytvořit tabulku, přidat obrázek a umístit text kolem obrázku.

#### Otázka: Proč bych měl chtít umístit text kolem obrázku v dokumentu PDF?

Odpověď: Umístěním textu kolem obrázku vylepšíte vizuální prezentaci vašich dokumentů PDF, čímž se stanou poutavějšími a informativnějšími. Tato technika se často používá v dokumentech, brožurách, zprávách a dalších materiálech, kde chcete kombinovat obrázky a text esteticky příjemným způsobem.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kam chcete vygenerovaný PDF soubor uložit.

#### Otázka: Jak vytvořím tabulku a přidám do ní obrázek?

 Odpověď: Výukový program vás provede procesem vytváření tabulky pomocí`Table` třídy a přidání obrázku do tabulky pomocí`Image` třída. Před přidáním do buňky tabulky určíte cestu k souboru obrázku, výšku a šířku.

#### Otázka: Jak umístím text kolem obrázku?

 A: Chcete-li umístit text kolem obrázku, vytvoříte text ve formátu HTML pomocí`HtmlFragment` třída. Tento text bude obsahovat nadpis i hlavní text. Tento HTML text pak přidáte do buňky tabulky, která sousedí s buňkou obrázku.

#### Otázka: Mohu přizpůsobit vzhled textu a obrázku?

Odpověď: Ano, vzhled textu a obrázku můžete upravit pomocí značek a vlastností HTML. Můžete například nastavit velikosti písma, barvy, styly a zarovnání textu. Navíc můžete upravit velikost a rozměry obrázku.

#### Otázka: Jak uložím dokument PDF?

 Odpověď: Po přidání obrázku a textu do tabulky můžete uložit dokument PDF pomocí`Save` metoda`Document` třída. Zadejte požadovanou cestu výstupního souboru jako argument pro`Save` metoda.

#### Otázka: Jaký je očekávaný výstup tohoto tutoriálu?

Odpověď: Podle návodu a provedení poskytnutého kódu C# vygenerujete dokument PDF, který ukazuje, jak umístit text kolem obrázku. Výstupní dokument bude obsahovat tabulku s obrázkem a textem umístěným kolem ní.

#### Otázka: Mohu použít jiné formáty obrázků než JPG?

 Odpověď: Ano, můžete použít různé formáty obrázků podporované knihovnou Aspose.PDF, jako jsou PNG, BMP, GIF a další. Při vytváření`Image` objekt, zadejte cestu k souboru požadovaného formátu obrázku.

#### Otázka: Je pro tento výukový program vyžadována platná licence Aspose?

Odpověď: Ano, pro správné fungování tohoto kurzu je vyžadována platná licence Aspose. Na webu Aspose si můžete zakoupit plnou licenci nebo získat 30denní dočasnou licenci.