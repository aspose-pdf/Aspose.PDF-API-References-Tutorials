---
title: Export dat listu aplikace Excel do tabulky
linktitle: Export dat listu aplikace Excel do tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se exportovat data listu aplikace Excel do tabulky PDF pomocí Aspose.PDF for .NET. Výukový program krok za krokem s příklady kódu, předpoklady a užitečnými tipy.
type: docs
weight: 70
url: /cs/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Zavedení

Potřebovali jste někdy exportovat data z excelového listu do souboru PDF, úhledně uspořádaného do formátu tabulky? Představte si, že máte spoustu dat v Excelu, ale potřebujete je sdílet jako profesionálně vypadající PDF. Může to znít složitě, že? Ale s Aspose.PDF pro .NET můžete tento úkol proměnit v hračku. V tomto tutoriálu vás provedeme procesem exportu dat listu aplikace Excel do tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Provedeme vás krok za krokem, vše rozebereme tak, že i když jste v tom nováčci, nakonec se budete cítit jako profíci.

## Předpoklady

Než se ponoříme do kódování, pojďme si nastavit několik věcí:

1.  Aspose.PDF for .NET Library – Ujistěte se, že máte nainstalovanou nejnovější verzi. Můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells for .NET Library – budete ji potřebovat ke zpracování operací aplikace Excel. Stáhněte si jej z[zde](https://releases.aspose.com/cells/net/).
3. .NET Development Environment – Nástroj jako Visual Studio bude perfektně fungovat pro kódování.
4. Soubor Excel – Připravte si soubor Excel s daty, která chcete exportovat.

 Pokud nemáte knihovny Aspose.PDF a Aspose.Cells, můžete začít s[zkušební verze zdarma](https://releases.aspose.com/).

## Importujte balíčky

Nejprve se ujistěte, že jste do svého projektu nainstalovali knihovny Aspose.PDF i Aspose.Cells. Můžete je nainstalovat pomocí NuGet Package Manager v sadě Visual Studio.

Zde je návod, jak importovat potřebné balíčky do kódu C#:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Nyní, když jsou předpoklady nastaveny, pojďme si projít proces exportu dat z listu aplikace Excel do tabulky v dokumentu PDF.

## Krok 1: Načtěte sešit aplikace Excel

Chcete-li začít, musíte do programu načíst sešit aplikace Excel. V tomto kroku použijeme Aspose.Cells k otevření souboru Excel.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte sešit aplikace Excel
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Vysvětlení: Zde zadáme cestu k adresáři, kde se nachází náš soubor Excel, a načteme sešit pomocí`Aspose.Cells.Workbook` . Nezapomeňte upravit`"YOUR DOCUMENT DIRECTORY"` ukázat na umístění vašeho souboru.

## Krok 2: Otevřete první pracovní list

Po načtení sešitu potřebujeme přistupovat k prvnímu listu, kde jsou uložena naše data.

```csharp
// Přístup k prvnímu listu v souboru aplikace Excel
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Vysvětlení: Tento krok je přímočarý – vezmeme si první list ze sešitu, který obsahuje data k exportu.

## Krok 3: Exportujte data do DataTable

Nyní vyexportujme data z listu Excelu do objektu DataTable, který bude fungovat jako prostředník pro přenos dat do PDF.

```csharp
// Export obsahu 7 řádků a 2 sloupců počínaje 1. buňkou do DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Vysvětlení: The`ExportDataTable` metoda extrahuje data počínaje první buňkou listu a zahrnuje všechny řádky a sloupce. Tato data jsou pak uložena v a`DataTable` pro další použití.

## Krok 4: Vytvořte nový dokument PDF

Dále musíme vytvořit nový dokument PDF pomocí Aspose.PDF.

```csharp
// Vytvořte instanci instance dokumentu
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Vytvořte stránku v instanci dokumentu
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Vysvětlení: Zde inicializujeme nový`Aspose.Pdf.Document` přidejte k němu stránku. Tato stránka bude později obsahovat tabulku, kterou vytváříme z dat aplikace Excel.

## Krok 5: Vytvořte objekt tabulky v PDF

Pojďme k vytvoření tabulky uvnitř dokumentu PDF.

```csharp
// Vytvořte objekt Table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Přidejte objekt Tabulka do kolekce odstavců na stránce
page.Paragraphs.Add(table);
```

 Vysvětlení: Vytváříme an`Aspose.Pdf.Table` objekt a přidejte jej do kolekce odstavců stránky, což zajistí zobrazení tabulky na stránce.

## Krok 6: Nastavte šířky a okraje sloupců

Tabulky v PDF potřebují definované šířky sloupců. Přidáme také ohraničení, aby byla tabulka čitelnější.

```csharp
// Nastavte šířku sloupců tabulky
table.ColumnWidths = "40 100 100";

// Nastavit výchozí ohraničení buňky
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Vysvětlení: Nastavíme šířky tří sloupců a všem buňkám dáme výchozí ohraničení o tloušťce`0.1F`.

## Krok 7: Importujte data z DataTable do tabulky PDF

Nyní je čas importovat data z DataTable do naší tabulky PDF.

```csharp
// Importujte data do objektu Table z DataTable
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Vysvětlení: The`ImportDataTable`metoda přenáší všechna data z`DataTable` do tabulky PDF. Tím se tabulka naplní daty z vašeho listu Excel.

## Krok 8: Upravte styl řádku záhlaví

Upravme styl záhlaví tabulky změnou barvy pozadí, písma a zarovnání.

```csharp
// Získejte první řádek z tabulky
Aspose.Pdf.Row headerRow = table.Rows[0];

// Nastavte styl pro řádek záhlaví
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Vysvětlení: Projdeme všechny buňky v prvním řádku (záhlaví) a nastavíme jim barvu pozadí na modrou, barvu textu na žlutou a zarovnáme text na střed.

## Krok 9: Upravte styl zbývajících řádků

Abychom odlišili záhlaví a zbytek řádků, přidáme pro zbývající řádky jiný styl.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Vysvětlení: Pro všechny řádky kromě záhlaví nastavíme šedé pozadí a bílou barvu textu.

## Krok 10: Uložte dokument PDF

Nakonec uložte dokument PDF s tabulkou.

```csharp
// Uložte Pdf
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Vysvětlení: Uložíme PDF do zadaného adresáře. Voilà! Vaše data Excelu jsou nyní uvnitř krásně formátované tabulky PDF.

## Závěr

tady to máte! V několika krocích jste exportovali data z excelového listu do tabulky uvnitř PDF pomocí Aspose.PDF for .NET. Rozdělením procesu a jeho stylingem můžete svůj výstup přizpůsobit a zajistit, aby vaše data vypadala čistě a profesionálně. Takže až vám příště někdo předá soubor Excel a požádá o zprávu ve formátu PDF, budete přesně vědět, co máte dělat.

## FAQ

### Mohu si stůl více přizpůsobit?
Absolutně! Můžete upravit barvy, písma, zarovnání a dokonce přidat ohraničení ke konkrétním buňkám.

### Je Aspose.PDF pro .NET zdarma?
 Nabízí bezplatnou zkušební verzi, ale pro delší používání budete potřebovat licenci. Můžete[kupte si to zde](https://purchase.aspose.com/buy).

### Mohu exportovat pouze určité řádky a sloupce?
 Ano, můžete upravit parametry v`ExportDataTable` způsob exportu konkrétních rozsahů.

### Funguje to s velkými soubory Excel?
Ano, Aspose.Cells je navržen tak, aby efektivně zpracovával velké soubory aplikace Excel.

### Jak mohu do PDF přidat další stránky?
 Můžete použít`pdfDocument.Pages.Add()` přidat tolik stránek, kolik potřebujete.