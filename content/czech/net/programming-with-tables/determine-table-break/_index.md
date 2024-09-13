---
title: Určete zalomení tabulky v souboru PDF
linktitle: Určete zalomení tabulky v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak určit konce tabulek v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 60
url: /cs/net/programming-with-tables/determine-table-break/
---
V tomto tutoriálu se naučíme, jak určit konce tabulek v souboru PDF pomocí Aspose.PDF pro .NET. Vysvětlíme si zdrojový kód v C# krok za krokem. Na konci tohoto tutoriálu budete vědět, jak určit, zda tabulka přesahuje okraje stránky. Začněme!

## Krok 1: Nastavení prostředí
Nejprve se ujistěte, že jste nastavili vývojové prostředí C# pomocí Aspose.PDF pro .NET. Přidejte odkaz do knihovny a importujte potřebné jmenné prostory.

## Krok 2: Vytvoření dokumentu PDF
 V tomto kroku vytvoříme nový`Document` objekt reprezentující dokument PDF.

```csharp
pdf-Document = new Document();
```

Tento dokument bude použit k přidání oddílů a tabulek.

## Krok 3: Přidání sekce a tabulky
Nyní přidáme sekci do našeho dokumentu PDF a vytvoříme tabulku uvnitř této sekce.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Pro tabulku také určujeme horní okraj 300 bodů. Tuto hodnotu můžete upravit podle svých potřeb.

## Krok 4: Nastavení tabulky
V tomto kroku nakonfigurujeme vlastnosti tabulky, jako jsou šířky a okraje sloupců.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Zde definujeme šířku sloupců tabulky a ohraničení buněk. Tyto hodnoty můžete upravit podle svých preferencí.

## Krok 5: Přidejte do tabulky řádky a buňky
Nyní vytvoříme řádky a buňky v tabulce pomocí smyčky.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Zde vytvoříme v tabulce 17 řádků a do každého řádku přidáme tři buňky. Sponu si můžete upravit podle svých potřeb.

## Krok 6: Určení zlomů tabulky
Nyní zjistíme, zda tabulka přesahuje okraje stránky, porovnáním výšky stránky s celkovou výškou objektů v tabulce.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Vypočítáme výšku stránky a celkovou výšku objektů s přihlédnutím k okrajům. Pokud je rozdíl 10 nebo méně, tabulka přesahuje okraje stránky.

## Krok 7: Uložení dokumentu PDF
Nakonec uložíme PDF dokument s výsledky.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Ujistěte se, že jste zadali správný adresář dokumentů. Výsledný soubor PDF bude uložen s určenými zalomeními tabulek.

### Příklad zdrojového kódu pro Determine Table Break pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektové třídy PDF
Document pdf = new Document();
// Přidejte sekci do kolekce oddílů dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Přidejte tabulku do kolekce odstavců požadované sekce
page.Paragraphs.Add(table1);
// Nastavte šířku sloupců tabulky
table1.ColumnWidths = "100 100 100";
// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Nastavte ohraničení tabulky pomocí jiného přizpůsobeného objektu BorderInfo
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Vytvořte objekt MarginInfo a nastavte jeho levý, spodní, pravý a horní okraj
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Nastavte výchozí odsazení buněk na objekt MarginInfo
table1.DefaultCellPadding = margin;
// Pokud zvýšíte počítadlo na 17, stůl se rozbije
// Protože už to přes tuto stránku nelze umístit
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//Vytvořte řádky v tabulce a poté buňky v řádcích
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Získejte informace o výšce stránky
float PageHeight = (float)pdf.PageInfo.Height;
// Získejte informace o celkové výšce horního a dolního okraje stránky,
// Okraj desky stolu a výška stolu.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Zobrazte výšku stránky, výšku tabulky, horní okraj tabulky a horní okraj stránky
// A informace o spodním okraji
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Zkontrolujte, zda odečteme součet Horní okraj stránky + Spodní okraj stránky
// + Okraj desky a výška tabulky z výšky stránky a její menší
// Než 10 (průměrný řádek může být větší než 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Pokud je hodnota menší než 10, zobrazte zprávu.
	//Což ukazuje, že další řádek nelze umístit a pokud přidáme nový
	// Řádek, stůl se rozbije. Záleží na hodnotě výšky řádku.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Uložte dokument pdf
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak určit konce tabulek v dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí tohoto podrobného průvodce můžete zkontrolovat, zda tabulka nepřesahuje okraje stránky ve vašich vlastních projektech C#.

### Časté dotazy pro určení zlomu tabulky v souboru PDF

#### Otázka: Jaký je účel určování zalomení tabulek v dokumentu PDF?

Odpověď: Účelem určení zalomení tabulek v dokumentu PDF je zkontrolovat, zda tabulka nepřesahuje okraje stránky. Tím je zajištěno, že obsah tabulky je správně zobrazen v dostupném prostoru stránky. Detekcí zlomů tabulek můžete zvládnout přetečení obsahu a podle toho upravit rozvržení tabulky.

#### Otázka: Jak mohu upravit horní okraj tabulky?

 Odpověď: V poskytnutém zdrojovém kódu C# můžete upravit horní okraj tabulky úpravou hodnoty`table1.Margin.Top`vlastnictví. Zvyšte nebo snižte hodnotu podle potřeby pro nastavení požadovaného horního okraje pro tabulku.

#### Otázka: Mohu upravit vzhled tabulky, jako jsou barvy buněk a velikost písma?

Odpověď: Ano, vzhled tabulky a jejích buněk můžete přizpůsobit pomocí různých vlastností a metod poskytovaných Aspose.PDF pro .NET. Můžete například změnit barvy pozadí buňky, velikost písma, rodinu písem, zarovnání textu a další. Další informace o přizpůsobení vzhledu stolu naleznete v oficiální dokumentaci.

#### Otázka: Co se stane, pokud tabulka přesahuje okraje stránky?

Odpověď: Pokud tabulka přesahuje okraje stránky, může to mít za následek zkrácení obsahu nebo překrývání, takže dokument PDF bude méně čitelný a organizovaný. Detekcí zalomení tabulky a zpracováním přetečení můžete zajistit, že obsah zůstane správně zobrazen v dostupné oblasti stránky.

#### Otázka: Mohu určit konce tabulek pro více tabulek ve stejném dokumentu PDF?

Odpověď: Ano, můžete určit konce tabulek pro více tabulek ve stejném dokumentu PDF. Jednoduše opakujte kroky pro každou tabulku, kterou chcete analyzovat, a upravte rozložení tabulky podle potřeby, abyste zabránili přetečení obsahu.