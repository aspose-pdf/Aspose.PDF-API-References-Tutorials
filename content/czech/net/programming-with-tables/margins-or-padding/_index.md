---
title: Okraje nebo výplně
linktitle: Okraje nebo výplně
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit okraje nebo odsazení v tabulce pomocí Aspose.PDF pro .NET.
type: docs
weight: 140
url: /cs/net/programming-with-tables/margins-or-padding/
---
V tomto tutoriálu vás provedeme krok za krokem procesem použití Aspose.PDF for .NET k nastavení okrajů nebo odsazení v tabulce. Poskytneme vysvětlení a úryvky kódu, které vám pomohou pochopit a implementovat tuto funkci ve zdrojovém kódu C#.

## Krok 1: Nastavení dokumentu a stránky
Chcete-li začít, musíte nastavit dokument a stránku pomocí následujícího kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektu Document voláním jeho prázdného konstruktoru
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 2: Vytvoření tabulky
Dále vytvoříme objekt tabulky pomocí třídy Aspose.Pdf.Table:

```csharp
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Přidejte tabulku do kolekce odstavců požadované sekce
page.Paragraphs.Add(tab1);
```

## Krok 3: Nastavení šířky sloupců a výchozího ohraničení buňky
Chcete-li nastavit šířky sloupců a výchozí ohraničení buňky tabulky, použijte následující kód:

```csharp
// Nastavte šířku sloupců tabulky
tab1. ColumnWidths = "50 50 50";
// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 4: Nastavení ohraničení tabulky a odsazení buněk
Chcete-li nastavit ohraničení tabulky a odsazení buněk, vytvořte objekt MarginInfo a nastavte jeho vlastnosti:

```csharp
// Vytvořte objekt MarginInfo a nastavte jeho levý, spodní, pravý a horní okraj
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Nastavte výchozí odsazení buněk na objekt MarginInfo
tab1. DefaultCellPadding = margin;

// Nastavte ohraničení tabulky pomocí jiného přizpůsobeného objektu BorderInfo
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## Krok 5: Přidání řádků a buněk
Nyní do tabulky přidáme řádky a buňky. Vytvoříme nový řádek a přidáme do něj buňky:

```csharp
// Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## Krok 6: Přidání textu do buněk
Chcete-li do buňky přidat text, vytvořte objekt TextFragment a přidejte jej do požadované buňky:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## Krok 7: Uložení PDF
Chcete-li uložit dokument PDF, použijte následující kód:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Uložte soubor PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Příklad zdrojového kódu pro Margins Or Padding pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Iniciujte objekt Document voláním jeho prázdného konstruktoru
Document doc = new Document();
Page page = doc.Pages.Add();
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Přidejte tabulku do kolekce odstavců požadované sekce
page.Paragraphs.Add(tab1);
// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "50 50 50";
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
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("sloupec3 s velkým textovým řetězcem pro umístění do buňky");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Řádek1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Uložte Pdf
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Závěr
Gratuluji! Úspěšně jste se naučili, jak nastavit okraje nebo odsazení v tabulce pomocí Aspose.PDF pro .NET. Tyto znalosti vám pomohou zlepšit možnosti formátování dokumentů a učinit vaše tabulky vizuálně přitažlivými.

### FAQ

#### Otázka: Mohu nastavit různé okraje nebo odsazení pro jednotlivé buňky v tabulce?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete nastavit různé okraje nebo odsazení pro jednotlivé buňky v tabulce. V uvedeném příkladu nastavíme výchozí odsazení buněk pro celou tabulku pomocí`DefaultCellPadding` vlastnictví. Chcete-li nastavit různé odsazení pro konkrétní buňky, můžete získat přístup k`MarginInfo` každé buňky jednotlivě a upravit jejich okraje.

#### Otázka: Jak mohu změnit barvu nebo styl ohraničení tabulky?

 A: Chcete-li změnit barvu nebo styl ohraničení tabulky, můžete upravit`Color` a`Width` vlastnosti`BorderInfo` objekt. V uvedeném příkladu nastavíme barvu okraje na černou a šířku 1F (jeden bod) pomocí`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. Barvu a šířku si můžete upravit podle svých požadavků.

#### Otázka: Je možné do tabulky přidat záhlaví nebo zápatí?

Odpověď: Ano, můžete do tabulky přidat záhlaví nebo zápatí pomocí Aspose.PDF pro .NET. Záhlaví a zápatí jsou obvykle samostatné řádky, které obsahují další informace, jako jsou popisky sloupců, názvy tabulek nebo souhrnná data. Můžete vytvořit další řádky, upravit je jinak a přidat je nad nebo pod obsah tabulky.

#### Otázka: Jak upravím zarovnání textu v buňce tabulky?

 Odpověď: Chcete-li upravit zarovnání textu v buňce tabulky, můžete použít`HorizontalAlignment` a`VerticalAlignment` vlastnosti`TextFragment` objekt. Chcete-li například text zarovnat na střed vodorovně, můžete nastavit`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Podobně můžete nastavit`mytext.VerticalAlignment` pro ovládání vertikálního zarovnání.

#### Otázka: Mohu do buněk tabulky místo textu přidat obrázky?

 Odpověď: Ano, můžete přidat obrázky do buněk tabulky pomocí Aspose.PDF pro .NET. Místo vytvoření a`TextFragment` objekt, můžete vytvořit`Image` objekt, načtěte soubor obrázku a přidejte jej do požadované buňky pomocí`cell.Paragraphs.Add(image);` metoda. To vám umožní vkládat obrázky do tabulky vedle textového obsahu.