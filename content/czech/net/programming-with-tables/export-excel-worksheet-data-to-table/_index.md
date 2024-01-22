---
title: Export dat listu aplikace Excel do tabulky
linktitle: Export dat listu aplikace Excel do tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Exportujte data z listu aplikace Excel do tabulky PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 70
url: /cs/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
V tomto návodu se naučíme exportovat data z excelového listu a vytvořit tabulku v PDF dokumentu pomocí knihovny Aspose.PDF for .NET. Projdeme si zdrojový kód krok za krokem a podrobně vysvětlíme každou sekci. Na konci tohoto tutoriálu budete schopni generovat soubory PDF s tabulkami obsahujícími data z listů aplikace Excel. Začněme!

## Požadavky
Než začneme, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#
- Visual Studio nainstalované na vašem počítači
- Do vašeho projektu byla přidána knihovna Aspose.PDF for .NET

## Krok 1: Nastavení prostředí
Chcete-li začít, vytvořte nový projekt C# v sadě Visual Studio. Přidejte odkaz na knihovnu Aspose.PDF for .NET kliknutím pravým tlačítkem na váš projekt v Průzkumníku řešení, výběrem „Spravovat balíčky NuGet“ a vyhledáním „Aspose.PDF“. Nainstalujte balíček a můžete vyrazit.

## Krok 2: Načtení listu aplikace Excel
V prvním kroku našeho kódu definujeme cestu k adresáři obsahujícímu dokument Excel. Nahraďte "VÁŠ ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš soubor Excel.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Zde používáme knihovnu Aspose.Cells k načtení sešitu aplikace Excel. Nezapomeňte nahradit "newBook1.xlsx" názvem souboru aplikace Excel.

## Krok 3: Přístup k listu
 Dále musíme získat přístup k prvnímu listu v souboru aplikace Excel. Děláme to pomocí`Worksheets` sbírka`Workbook` objekt.

```csharp
// Přístup k prvnímu listu v souboru aplikace Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Pokud váš soubor Excel obsahuje více listů, můžete změnit hodnotu indexu`[0]` pro přístup k jinému listu.

## Krok 4: Export dat do DataTable
 Nyní exportujeme obsah excelového listu do a`DataTable` objekt. Rozsah buněk k exportu určíme pomocí`ExportDataTable` metoda.

```csharp
// Export obsahu 7 řádků a 2 sloupců počínaje 1. buňkou do DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

V tomto příkladu exportujeme všechny řádky a sloupce počínaje první buňkou (0, 0) do poslední buňky v listu. Nastavte vhodný rozsah na základě vašich požadavků.

## Krok 5: Vytvoření dokumentu PDF
Nyní vytvoříme nový dokument PDF pomocí knihovny Aspose.PDF.

```csharp
// Vytvořte instanci instance dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Vznikne tak prázdný PDF dokument, kam můžeme přidat obsah.

## Krok 6: Přidání stránky a tabulky
Pro zobrazení dat ve formátu tabulky musíme do dokumentu PDF přidat stránku a tabulku.

```csharp
// Vytvořte stránku v instanci dokumentu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Vytvořte objekt Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Přidejte objekt Tabulka do kolekce odstavců sekce
sec1.Paragraphs.Add(tab1);
```

Zde vytvoříme novou stránku a objekt tabulky. Tabulku pak přidáme do kolekce odstavců na stránce.

## Krok 7: Nastavení vlastností tabulky
Před importem dat musíme nastavit některé vlastnosti tabulky, jako jsou šířky sloupců a výchozí ohraničení buněk.

```csharp
// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "40 100 100";

// Nastavte výchozí ohraničení buňky tabulky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

V tomto příkladu nastavíme šířky sloupců na 40, 100 a 100 jednotek. Upravte hodnoty na základě vašich dat. Nastavili jsme také výchozí ohraničení buňky, abychom zobrazili ohraničení na všech stranách každé buňky.

## Krok 8: Import dat do tabulky
 Nyní naimportujeme data z`DataTable` objekt do tabulky pomocí`ImportDataTable` metoda.

```csharp
// Importujte data do objektu Table z výše vytvořené DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Zde určíme rozsah řádků a sloupců, které se mají importovat. V tomto příkladu importujeme všechny řádky a sloupce z`dataTable` objekt.

## Krok 9: Formátování tabulky
Pro vylepšení vzhledu tabulky můžeme použít formátování na konkrétní buňky nebo řádky. V tomto kroku naformátujeme první řádek a střídáme řádky tabulky.

```csharp
// Získejte 1. řádek z tabulky
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Naformátujte první řádek
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Nastavte barvu pozadí buněk v prvním řádku
     curCell.BackgroundColor = Color.Blue;// Nastavte plochu pro buňky v prvním řádku
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Nastavte barvu písma buněk v prvním řádku
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Nastavte zarovnání textu pro buňky v prvním řádku
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternativní formát řádku
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Nastavte barvu pozadí buněk v alternativních řádcích
         curCell.BackgroundColor = Color.Gray;
        
         // Nastavte barvu textu buněk v alternativních řádcích
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Zde iterujeme přes buňky v prvním řádku a nastavíme jim barvu pozadí, řez písma, barvu písma a zarovnání textu. Poté projdeme všechny buňky v alternativních řádcích a nastavíme jejich pozadí a barvu textu.

## Krok 10: Uložení dokumentu PDF
Nakonec dokument PDF uložíme na určené místo.

```csharp
// Uložte soubor PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Nezapomeňte nahradit "VÁŠ ADRESÁŘ DOKUMENTŮ" požadovanou cestou k adresáři a názvem souboru pro výstupní soubor PDF.

### Příklad zdrojového kódu pro Export dat listu aplikace Excel do tabulky pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Přístup k prvnímu listu v souboru aplikace Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// Export obsahu 7 řádků a 2 sloupců počínaje 1. buňkou do DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Vytvořte instanci dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Vytvořte stránku v instanci dokumentu
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Vytvořte objekt Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Přidejte objekt Tabulka do kolekce odstavců sekce
sec1.Paragraphs.Add(tab1);

// Nastavte šířku sloupců tabulky. Musíme zadat ColumnCount ručně.
// Protože aktuální excelový list má tři sloupce, zadáváme stejný počet
tab1.ColumnWidths = "40 100 100";

// Nastavte výchozí ohraničení buňky tabulky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importujte data do objektu Table z výše vytvořené DataTable
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Získejte 1. řádek z tabulky
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Iterujte všechny buňky v 1. řádku a nastavte jim barvu pozadí na modrou
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Nastavte pozadí všech buněk v 1. řádku tabulky.
	curCell.BackgroundColor = Color.Blue;
	// Nastavte vzhled písma pro buňky 1. řádku v tabulce.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Nastavte barvu písma pro všechny buňky v 1. řádku tabulky.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Nastavte zarovnání textu pro buňky 1. řádku jako Střed.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Iterujte všechny buňky v 1. řádku a nastavte jim barvu pozadí na modrou
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Nastavte barvu pozadí všech buněk kromě 1. řádku.
		curCell.BackgroundColor = Color.Gray;
		// Nastavte barvu textu všech buněk kromě 1. řádku.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Uložte Pdf
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Závěr
tomto tutoriálu jsme se naučili exportovat data z excelového listu do tabulky PDF pomocí knihovny Aspose.PDF for .NET. Popsali jsme krok za krokem proces načítání listu aplikace Excel, vytvoření dokumentu PDF, přidání tabulky, import dat a formátování tabulky. Nyní můžete generovat soubory PDF s tabulkami obsahujícími data aplikace Excel programově.

### FAQ

#### Otázka: Jaký je účel exportu dat listu aplikace Excel do tabulky PDF?

Odpověď: Export dat listu aplikace Excel do tabulky PDF umožňuje prezentovat data ve strukturovaném a organizovaném formátu. Umožňuje generovat soubory PDF s tabulkami, které obsahují data z listů aplikace Excel, což usnadňuje sdílení a uchovávání informací ve formátu přenosných dokumentů.

#### Otázka: Mohu přizpůsobit vzhled tabulky PDF?

Odpověď: Ano, vzhled tabulky PDF můžete přizpůsobit pomocí různých vlastností poskytovaných Aspose.PDF pro .NET. V poskytnutém zdrojovém kódu C# můžete upravit šířky sloupců, ohraničení buněk, zarovnání textu, styl písma a další, aby vyhovovaly vašim specifickým požadavkům.

#### Otázka: Jak mohu pracovat se soubory aplikace Excel s více listy?

 Odpověď: V poskytnutém kódu C# jsme přistoupili k prvnímu listu v souboru aplikace Excel pomocí indexu`[0]` . Pokud váš soubor Excel obsahuje více listů, můžete k nim přistupovat odpovídající změnou hodnoty indexu, jako je např`[1]` pro druhý pracovní list popř`[2]` pro třetí pracovní list.

#### Otázka: Mohu použít jiné formátování na konkrétní řádky nebo buňky v tabulce PDF?

Odpověď: Ano, na konkrétní řádky nebo buňky v tabulce PDF můžete použít různé formátování. V poskytnutém zdrojovém kódu C# jsme ukázali, jak formátovat první řádek a střídat řádky odlišně změnou jejich barvy pozadí, stylu písma a barvy písma. Podobné techniky formátování můžete podle potřeby použít na libovolné konkrétní řádky nebo buňky.

#### Otázka: Je Aspose.PDF for .NET jedinou knihovnou, která umožňuje export dat aplikace Excel do tabulky PDF?

A: Aspose.PDF for .NET je výkonná knihovna pro práci s dokumenty PDF v aplikacích .NET. I když mohou být k dispozici další knihovny, Aspose.PDF for .NET nabízí širokou škálu funkcí a možností pro generování, manipulaci a export souborů PDF s tabulkami z dat aplikace Excel, což z něj činí oblíbenou volbu pro takové úkoly.