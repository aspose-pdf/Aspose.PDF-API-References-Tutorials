---
title: Automatické přizpůsobení oknu
linktitle: Automatické přizpůsobení oknu
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce používáním Aspose.PDF pro .NET a dosažením automatického přizpůsobení oknu při generování PDF.
type: docs
weight: 50
url: /cs/net/programming-with-tables/auto-fit-to-window/
---
Následující článek je podrobným průvodcem, jak použít dodaný zdrojový kód C# k dosažení funkce Auto Fit To Window pomocí knihovny Aspose.PDF pro .NET. Funkce Auto Fit To Window umožňuje generovat soubory PDF s rozložením přizpůsobeným prohlížecímu oknu. Tato funkce je zvláště užitečná, když chcete, aby se váš dokument PDF automaticky přizpůsobil velikosti okna pro čtení PDF používaného uživatelem.

## Krok 1: Nastavení prostředí

Než začnete, musíte do počítače nainstalovat knihovnu Aspose.PDF pro .NET. Také se ujistěte, že jste do projektu importovali potřebné jmenné prostory.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvoření dokumentu PDF

 Chcete-li začít, musíte vytvořit a`Document` objekt voláním jeho výchozího konstruktoru.

```csharp
Document doc = new Document();
```

 Dále vytvořte sekci v`Pdf` objekt.

```csharp
Page sec1 = doc.Pages.Add();
```

## Krok 3: Přidání tabulky do dokumentu

 V tomto kroku přidáme tabulku do našeho dokumentu PDF. Nejprve vytvořte a`Table` objekt.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Dále přidejte tabulku do kolekce odstavců sekce.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Krok 4: Přizpůsobení vzhledu tabulky

Vzhled tabulky můžete přizpůsobit nastavením vlastností, jako je ohraničení buněk a okraj.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Krok 4: Přidání řádků a buněk do tabulky

Nyní do naší tabulky přidáme řádky a buňky. Začněte vytvořením řádku a přidáním buněk do tohoto řádku.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Krok 5: Uložení dokumentu

Nakonec zadejte cestu k výstupnímu souboru a uložte dokument.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Příklad zdrojového kódu pro Auto Fit To Window pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Iniciujte objekt Pdf voláním jeho prázdného konstruktoru
Document doc = new Document();
// Vytvořte sekci v objektu Pdf
Page sec1 = doc.Pages.Add();

// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Přidejte tabulku do kolekce odstavců požadované sekce
sec1.Paragraphs.Add(tab1);

// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Nastavte ohraničení tabulky pomocí jiného přizpůsobeného objektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Vytvořte objekt MarginInfo a nastavte jeho levý, spodní, pravý a horní okraj
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Nastavte výchozí odsazení buněk na objekt MarginInfo
tab1.DefaultCellPadding = margin;

// Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Uložte aktualizovaný dokument obsahující objekt tabulky
doc.Save(dataDir);
```

## Závěr

tomto tutoriálu jsme se naučili používat Aspose.PDF pro .NET ke generování souboru PDF s funkcí Auto Fit To Window. Tato funkce je mimořádně užitečná, když chcete, aby se váš dokument PDF automaticky přizpůsobil velikosti zobrazovacího okna. Aspose.PDF for .NET nabízí mnoho dalších výkonných funkcí pro generování a manipulaci se soubory PDF. Doporučuji vám tuto knihovnu dále prozkoumat, abyste objevili všechny její možnosti.

### FAQ

#### Otázka: Jaký je účel funkce Automaticky přizpůsobit oknu při generování PDF?

Odpověď: Funkce Automaticky přizpůsobit oknu při generování PDF zajišťuje, že se rozvržení dokumentu PDF automaticky přizpůsobí velikosti okna pro čtení PDF používaného uživatelem. To umožňuje lepší sledování a zajišťuje, že obsah dokonale zapadne do dostupné oblasti zobrazení.

#### Otázka: Mohu přizpůsobit vzhled tabulky, jako je velikost písma a barvy?

Odpověď: Ano, vzhled tabulky v dokumentu PDF můžete upravit pomocí Aspose.PDF pro .NET. Poskytnutý fragment kódu ukazuje, jak nastavit vlastnosti, jako jsou okraje buněk, okraje a šířky sloupců. Dále můžete přizpůsobit velikost písma, barvy a další stylingové aspekty tabulky a jejího obsahu.

#### Otázka: Jak integruji Aspose.PDF for .NET do svého projektu v jazyce C#?

A: Chcete-li použít Aspose.PDF pro .NET ve svém projektu C#, musíte nejprve nainstalovat knihovnu Aspose.PDF pro .NET na váš počítač. Poté můžete přidat odkaz na knihovnu ve svém projektu C#. Nakonec importujte potřebné jmenné prostory pro přístup ke třídám a metodám poskytovaným Aspose.PDF pro .NET.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s aplikacemi .NET Core?

Odpověď: Ano, Aspose.PDF pro .NET je kompatibilní s aplikacemi .NET Core. Podporuje různé platformy .NET, včetně .NET Framework, .NET Core a .NET 5.0+.

#### Otázka: Mohu do dokumentu PDF přidat další tabulky?

Odpověď: Ano, do dokumentu PDF můžete přidat více tabulek podle podobných kroků, jak je ukázáno ve fragmentu kódu. Jednoduše vytvořte nové instance`Aspose.Pdf.Table` třídy a přidejte je do různých částí nebo stránek dokumentu PDF.