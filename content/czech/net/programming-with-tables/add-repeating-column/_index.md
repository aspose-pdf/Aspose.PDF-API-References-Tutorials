---
title: Přidat opakující se sloupec do dokumentu PDF
linktitle: Přidat opakující se sloupec do dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat opakující se sloupec do dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 20
url: /cs/net/programming-with-tables/add-repeating-column/
---
V tomto tutoriálu se naučíme, jak přidat opakující se sloupec do dokumentu PDF pomocí Aspose.PDF pro .NET. Vysvětlíme si zdrojový kód v C# krok za krokem. Na konci tohoto tutoriálu budete vědět, jak vytvořit tabulku s opakujícím se sloupcem v dokumentu PDF. Začněme!

## Krok 1: Nastavení prostředí
Nejprve se ujistěte, že jste nastavili vývojové prostředí C# pomocí Aspose.PDF pro .NET. Přidejte odkaz do knihovny a importujte potřebné jmenné prostory.

## Krok 2: Vytvoření dokumentu PDF
V tomto kroku vytvoříme nový dokument PDF.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Vytvořili jsme prázdný dokument PDF, kam můžeme přidat obsah.

## Krok 3: Vytvoření tabulek
V tomto kroku vytvoříme hlavní tabulku (`outerTable`) a vnořená tabulka (`mytable`), který se bude ve sloupci opakovat.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Zadali jsme vlastnosti tabulky, jako je šířka sloupce a režim zalomení vnořené tabulky.

## Krok 4: Přidání tabulek do dokumentu
Nyní přidáme vytvořené tabulky do PDF dokumentu.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Nejprve přidáme hlavní tabulku (`outerTable`) do dokumentu PDF. Dále přidáme vnořenou tabulku (`mytable` ) jako odstavec v buňce v hlavní tabulce. Uvádíme také počet opakujících se sloupců pro`mytable` (v tomto příkladu 5 sloupců).

## Krok 5: Přidání záhlaví a řádků
Nyní přidáme záhlaví a řádky do tabulky.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//Zde přidejte další záhlaví

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Zde přidejte další sloupce
}
```

Nejprve přidáme záhlaví do prvního řádku tabulky (`headerRow`). Poté přidáme řádky dat ze smyčky. V tomto příkladu přidáme 6 řádků dat.

## Krok 6: Uložení dokumentu PDF
Nakonec dokument PDF uložíme do zadaného souboru.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Ujistěte se, že zadáváte správný adresář a název souboru pro uložení výstupního souboru PDF.

### Příklad zdrojového kódu pro přidání opakujícího se sloupce pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Vytvořte nový dokument
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Vytvořte instanci vnější tabulky, která zabírá celou stránku
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

// Vytvořte instanci objektu tabulky, který bude vnořen do externalTable, který se rozpadne na stejné stránce
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Přidejte vnější tabulku do odstavců stránky
// Přidejte mytable do externalTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Přidat řádek záhlaví
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Vytvořte řádky v tabulce a poté buňky v řádcích
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## Závěr
tomto tutoriálu jsme se naučili, jak přidat opakující se sloupec do dokumentu PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce můžete použít k vytvoření tabulek s opakujícími se sloupci ve vašich vlastních projektech C#.

### Časté dotazy pro přidání opakujícího se sloupce do dokumentu PDF

#### Otázka: Mohu přizpůsobit počet opakujících se sloupců ve vnořené tabulce?

 Odpověď: Ano, počet opakujících se sloupců ve vnořené tabulce můžete přizpůsobit. V uvedeném příkladu jsme nastavili`mytable.RepeatingColumnsCount = 5;`, což znamená, že se bude opakovat 5 sloupců. Tuto hodnotu můžete změnit na libovolné požadované číslo.

#### Otázka: Je možné dynamicky přidávat další řádky do vnořené tabulky?

Odpověď: Ano, do vnořené tabulky můžete dynamicky přidávat další řádky stejným způsobem, jak je znázorněno ve výukovém programu. K přidání řádků na základě vašich dat můžete použít smyčky nebo jakoukoli jinou logiku.

#### Otázka: Mohu použít styly a formátování na tabulku a její buňky?

Odpověď: Ano, na tabulku a její buňky můžete použít styly a formátování pomocí Aspose.PDF for .NET. Knihovna poskytuje různé vlastnosti a metody pro přizpůsobení vzhledu tabulky a jejího obsahu.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s .NET Core?

Odpověď: Ano, Aspose.PDF pro .NET je kompatibilní s .NET Core. Můžete jej použít v aplikacích .NET Framework i .NET Core.

#### Otázka: Mohu tento přístup použít k přidání opakujících se sloupců do existujícího dokumentu PDF?

Odpověď: Ano, tento přístup můžete použít k přidání opakujících se sloupců do existujícího dokumentu PDF. Jednoduše načtěte existující dokument pomocí Aspose.PDF pro .NET a postupujte podle stejných kroků pro vytvoření a přidání opakujícího se sloupce.