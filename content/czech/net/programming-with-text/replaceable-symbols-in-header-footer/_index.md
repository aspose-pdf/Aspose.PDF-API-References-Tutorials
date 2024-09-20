---
title: Vyměnitelné Symboly V Zápatí Záhlaví
linktitle: Vyměnitelné Symboly V Zápatí Záhlaví
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat vyměnitelné symboly v záhlaví a zápatí dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 320
url: /cs/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## Zavedení

Při práci se soubory PDF někdy potřebujete upravit záhlaví a zápatí pomocí dynamického obsahu, jako jsou čísla stránek, názvy sestav nebo vygenerovaná data. Naštěstí Aspose.PDF for .NET tento proces zjednodušuje a umožňuje vám vytvářet soubory PDF s automaticky aktualizovanými symboly v záhlaví a zápatí, jako jsou čísla stránek nebo podrobnosti o generování sestav. Tento článek vás provede krok za krokem procesem nahrazování symbolů v záhlaví a zápatí pomocí Aspose.PDF pro .NET způsobem, který je nejen jednoduchý, ale také neuvěřitelně účinný.

## Předpoklady

Než se ponoříte do podrobného průvodce, ujistěte se, že máte následující:

-  Aspose.PDF pro knihovnu .NET –[Stáhnout](https://releases.aspose.com/pdf/net/) nebo získat a[zkušební verze zdarma](https://releases.aspose.com/).
- Visual Studio nebo jakékoli C# IDE nainstalované ve vašem systému.
- Základní znalost vývoje v C# a .NET.
-  A platné[licence](https://purchase.aspose.com/temporary-license/) pro Aspose.PDF, nebo můžete použít zkušební verzi.

## Importujte balíčky

Chcete-li začít, musíte importovat potřebné jmenné prostory, které umožní funkčnost Aspose.PDF pro .NET. Níže je nutný import:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Ty jsou nezbytné pro zpracování vytváření PDF, manipulaci s textem a správu záhlaví/zápatí.

Pojďme si ukázkový kód rozdělit do snadno srozumitelných kroků.

## Krok 1: Nastavte dokument a stránku

Nejprve musíme dokument inicializovat a přidat do něj stránku. Tím se nastaví základ pro přidávání záhlaví a zápatí.

```csharp
// Nastavte adresář dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializujte objekt dokumentu
Document doc = new Document();

// Přidejte do dokumentu stránku
Page page = doc.Pages.Add();
```

 Zde nastavujeme dokument PDF pomocí`Document` třídy a přidání stránky s`doc.Pages.Add()`Tato stránka bude obsahovat záhlaví, zápatí a další obsah.

## Krok 2: Nakonfigurujte okraje stránky

Dále definujeme okraje stránky, abychom zajistili, že náš obsah nebude sahat až k okraji.

```csharp
// Nakonfigurujte okraje
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 Zde jsme definovali horní, dolní, levý a pravý okraj pomocí`MarginInfo` třídy a aplikoval ji na stránku pomocí`page.PageInfo.Margin`.

## Krok 3: Vytvořte a nakonfigurujte záhlaví

Nyní vytvoříme záhlaví a přidáme ho na stránku. Záhlaví bude obsahovat název a název sestavy.

```csharp
// Vytvořit záhlaví
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// Nastavte okraje záhlaví
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// Přidejte nadpis do záhlaví
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// Přidejte název sestavy do záhlaví
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 Přidali jsme dva`TextFragment` objekty do záhlaví: jeden pro název sestavy a druhý pro název sestavy. Text je stylizován pomocí`TextState` vlastnosti jako písmo, velikost a zarovnání.

## Krok 4: Vytvořte a nakonfigurujte zápatí

Nyní je čas nastavit zápatí, které bude obsahovat dynamický obsah, jako jsou čísla stránek a datum generování.

```csharp
// Vytvořit zápatí
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// Nastavte okraje zápatí
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// Přidejte obsah zápatí
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

zápatí zahrneme fragmenty pro datum generování, název sestavy a dynamická čísla stránek (`$p` a`$P` představují aktuální číslo stránky a celkový počet stránek).

## Krok 5: Vytvořte tabulku v zápatí

Můžete také přidat složitější prvky, jako jsou tabulky, do zápatí, abyste lépe uspořádali svá data.

```csharp
// Vytvořte tabulku pro zápatí
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// Vytvořte řádky a buňky pro tabulku
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// Nastavte zarovnání pro každou buňku
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// Přidejte obsah do buněk tabulky
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

Tento blok kódu vytvoří v zápatí tabulku se 3 sloupci, přičemž každý sloupec obsahuje různé informace, jako je datum vytvoření, název sestavy a čísla stránek.

## Krok 6: Přidejte obsah na stránku

Kromě záhlaví a zápatí můžete do těla stránky PDF přidat obsah. Zde přidáme tabulku s nějakým zástupným textem.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// Přidejte obsah tabulky
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

Tento kód přidá na stránku jednoduchou tabulku se třemi sloupci. Můžete jej upravit tak, aby vyhovoval vašim konkrétním potřebám.

## Krok 7: Uložte soubor PDF

Jakmile je vše nastaveno, posledním krokem je uložení dokumentu PDF na požadované místo.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 Zadáte cestu k souboru a uložíte dokument pomocí`doc.Save()`. To je vše! Úspěšně jste vytvořili PDF s přizpůsobeným záhlavím a zápatím.

## Závěr

Nahrazení symbolů v záhlaví a zápatí pomocí Aspose.PDF for .NET je nejen jednoduché, ale také výkonné. Podle výše uvedeného podrobného průvodce můžete snadno přizpůsobit své PDF pomocí dynamického obsahu, jako jsou čísla stránek, názvy sestav a data. Tato metoda je vysoce flexibilní a umožňuje vkládat tabulky, upravovat formátování a řídit rozvržení tak, aby vyhovovalo vašim specifickým požadavkům.

## FAQ

### Mohu přizpůsobit písma pro záhlaví a zápatí?  
Ano, můžete si plně přizpůsobit písma, velikosti, barvy a styly textu v záhlaví a zápatí.

### Jak přidám obrázky do záhlaví a zápatí?  
 Můžete použít`ImageStamp` pro vkládání obrázků do záhlaví a zápatí.

### Je možné přidat hypertextové odkazy do záhlaví nebo zápatí?  
 Ano, můžete použít`TextFragment` s hypertextovým odkazem nastavením`Hyperlink` vlastnictví.

### Mohu použít různá záhlaví pro liché a sudé stránky?  
Ano, Aspose.PDF vám umožňuje určit různá záhlaví a zápatí pro liché a sudé stránky.

### Jak upravím pozice záhlaví a zápatí?  
Můžete upravit vlastnosti okrajů a zarovnání a řídit tak polohu záhlaví a zápatí.