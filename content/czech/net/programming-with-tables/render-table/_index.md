---
title: Vykreslit tabulku v dokumentu PDF
linktitle: Vykreslit tabulku v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak zobrazit tabulku v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 170
url: /cs/net/programming-with-tables/render-table/
---
V tomto tutoriálu vás krok za krokem provedeme zobrazením tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat.

## Krok 1: Vytvoření dokumentu
Nejprve vytvoříme nový dokument PDF:

```csharp
// Cesta k adresáři dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte nový dokument
Document doc = new Document();
```

## Krok 2: Konfigurace okrajů a orientace stránky
Dále nakonfigurujeme okraje stránky a nastavíme orientaci na režim na šířku:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## Krok 3: Vytvoření tabulky a sloupců
Nyní vytvoříme tabulku a nastavíme šířky sloupců:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## Krok 4: Přidejte do tabulky řádky a buňky
Dále do tabulky přidáme řádky a buňky pomocí smyčky:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## Krok 5: Přidání tabulky na stránku
Nyní přidáme tabulku na stránku dokumentu:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## Krok 6: Zobrazení tabulky na nové stránce
Dále vytvoříme novou tabulku a nastavíme vlastnost „IsInNewPage“ na „true“, aby se tabulka zobrazila na nové stránce:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## Krok 7: Uložte PDF
Nakonec dokument PDF uložíme:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Příklad zdrojového kódu pro tabulku vykreslení pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Přidána stránka.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Chci si ponechat tabulku 1 na další stránku, prosím...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Závěr
gratuluji! Nyní jste se naučili, jak zobrazit tabulku v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce vám ukázal, jak vytvořit dokument, nakonfigurovat okraje a orientaci stránky, přidat tabulku a zobrazit tabulku na nové stránce. Nyní můžete tyto znalosti aplikovat na své vlastní projekty.

### Nejčastější dotazy k vykreslování tabulky v dokumentu PDF

#### Otázka: Jak mohu upravit vzhled tabulky, například změnit barvy buněk nebo přidat ohraničení?

A: Chcete-li upravit vzhled tabulky, můžete nastavit různé vlastnosti tabulky`Aspose.Pdf.Table` a její buňky. Můžete například nastavit`BackgroundColor` vlastnost buněk změnit barvu pozadí. Můžete také nastavit`Border` vlastnost tabulky nebo jednotlivých buněk pro přidání ohraničení. Navíc můžete upravit písmo, barvu textu a zarovnání obsahu tabulky úpravou`TextState` z`TextFragment` objekty přidané do buněk.

#### Otázka: Mohu do tabulky přidat záhlaví nebo zápatí?

Odpověď: Ano, do tabulky můžete přidat záhlaví nebo zápatí vytvořením dalších řádků na začátku nebo na konci tabulky a nastavením příslušného obsahu v buňkách. Záhlaví nebo zápatí můžete přizpůsobit nezávisle na zbytku obsahu tabulky přidáním různých stylů nebo obsahu do těchto konkrétních řádků.

#### Otázka: Jak mohu ovládat pozici tabulky na stránce?

 A: Chcete-li ovládat pozici tabulky na stránce, můžete upravit`MarginInfo` z`PageInfo` objekt. The`MarginInfo`umožňuje nastavit levý, pravý, horní a dolní okraj stránky, což ovlivňuje dostupné místo pro tabulku. Můžete také použít`PositioningType` vlastnictvím`Aspose.Pdf.Table` k ovládání jejího vodorovného a svislého zarovnání v oblasti obsahu stránky.

#### Otázka: Mohu exportovat tabulku do různých formátů souborů, jako je Excel nebo CSV?

A: Aspose.PDF for .NET je primárně určen pro práci s dokumenty PDF. I když může exportovat dokument PDF jako obrázek nebo XPS, nepodporuje přímo export tabulek do formátů jako Excel nebo CSV. Chcete-li exportovat data tabulky do různých formátů souborů, možná budete muset použít další knihovny nebo metody pro převod obsahu PDF do požadovaného formátu.

#### Otázka: Jak mohu přidat hypertextové odkazy do buněk tabulky?

 A: Chcete-li přidat hypertextové odkazy do buněk tabulky, můžete použít`Aspose.Pdf.WebHyperlink` třídy vytvořit hypertextový odkaz a poté jej přidat jako kotvu do`TextFragment`uvnitř buňky. To vám umožní přiřadit adresu URL nebo cíl odkazu ke konkrétnímu textu nebo obsahu v buňce a vytvořit tak hypertextové odkazy, na které lze kliknout.