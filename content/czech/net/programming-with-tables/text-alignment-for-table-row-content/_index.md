---
title: Zarovnání textu pro obsah řádku tabulky
linktitle: Zarovnání textu pro obsah řádku tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak zarovnat obsah řádků v tabulce PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 210
url: /cs/net/programming-with-tables/text-alignment-for-table-row-content/
---
V tomto tutoriálu vás krok za krokem provedeme zarovnáním obsahu řádku v tabulce dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat.

## Krok 1: Vytvoření dokumentu PDF
Nejprve vytvoříme dokument PDF:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Krok 2: Inicializace tabulky
Dále inicializujeme tabulku:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Krok 3: Nastavení barvy ohraničení tabulky
Nastavíme barvu okraje tabulky:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 4: Konfigurace ohraničení buňky tabulky
Chystáme se nakonfigurovat ohraničení buňky tabulky:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 5: Smyčkou přidejte do tabulky 10 řádků
Nyní použijeme smyčku k přidání 10 řádků do tabulky:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## Krok 6: Konfigurace zarovnání svislé čáry
Nakonfigurujeme vertikální zarovnání řádků tabulky:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## Krok 7: Přidání obsahu do buněk řádku
Do buněk řádku přidáme obsah:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## Krok 8: Přidání tabulky na stránku dokumentu
Nyní přidáme tabulku na stránku dokumentu:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## Krok 9: Uložení dokumentu PDF
Nakonec dokument PDF uložíme:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Příklad zdrojového kódu pro zarovnání textu pro obsah řádků tabulky pomocí Aspose.PDF pro .NET

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Inicializuje novou instanci tabulky
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Nastavte barvu okraje tabulky jako LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// nastavit ohraničení buněk tabulky
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// vytvořte smyčku pro přidání 10 řádků
for (int row_count = 0; row_count < 10; row_count++)
{
	// přidat řádek do tabulky
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Přidejte objekt tabulky na první stránku vstupního dokumentu
tocPage.Paragraphs.Add(table);
// Uložte aktualizovaný dokument obsahující objekt tabulky
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Závěr
gratuluji! Nyní jste se naučili, jak zarovnat obsah řádku v tabulce v dokumentu PDF pomocí Aspose.PDF for .NET. Tento podrobný průvodce vám ukázal, jak vytvořit dokument, inicializovat tabulku, nakonfigurovat ohraničení a zarovnání, přidat obsah a uložit dokument PDF. Nyní můžete tyto znalosti aplikovat na své vlastní projekty.

### FAQ

#### Otázka: Jak mohu zarovnat obsah buněk tabulky vodorovně?

 Odpověď: Obsah buněk tabulky můžete zarovnat vodorovně nastavením`HorizontalAlign` vlastnost buňky`TextState` objekt. Chcete-li například text zarovnat na střed, použijte`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Můžete to také nastavit na`HorizontalAlignment.Left` nebo`HorizontalAlignment.Right` pro zarovnání vlevo a vpravo.

#### Otázka: Mohu na jednotlivé buňky v tabulce použít různé styly a barvy ohraničení?

 Odpověď: Ano, na jednotlivé buňky v tabulce můžete použít různé styly a barvy ohraničení. Chcete-li upravit ohraničení pro konkrétní buňku, nastavte`cell.Border` nemovitost na novou`BorderInfo`objekt s požadovaným nastavením, jako jsou strany okraje, šířka a barva.

#### Otázka: Jak mohu upravit vertikální zarovnání obsahu tabulky v buňkách?

 Odpověď: Vertikální zarovnání obsahu tabulky v buňkách můžete upravit nastavením`VerticalAlignment` vlastnost řádku k`VerticalAlignment.Center`, `VerticalAlignment.Top` nebo`VerticalAlignment.Bottom`. Tato vlastnost řídí svislé zarovnání všech buněk v daném řádku.

#### Otázka: Je možné do tabulky dynamicky přidávat další sloupce nebo řádky?

 Odpověď: Ano, do tabulky můžete dynamicky přidávat další sloupce a řádky pomocí`table.Rows.Add()` metoda pro přidání nových řádků a`row.Cells.Add()` metoda pro přidání nových buněk do řádků. Můžete to udělat uvnitř smyček nebo na základě vašich specifických požadavků.

#### Otázka: Jak mohu nastavit barvu pozadí pro konkrétní buňky nebo celou tabulku?

 A: Chcete-li nastavit barvu pozadí pro konkrétní buňky nebo celou tabulku, použijte`BackgroundColor` vlastnictvím`Cell` nebo`Table` objekt. Chcete-li například nastavit barvu pozadí buňky, použijte`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.