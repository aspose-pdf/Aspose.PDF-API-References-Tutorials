---
title: Automaticky Přizpůsobit Oknu
linktitle: Automaticky Přizpůsobit Oknu
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném podrobném průvodci se dozvíte, jak automaticky přizpůsobit tabulku oknu pomocí Aspose.PDF for .NET. Perfektní pro vytváření leštěných a dobře vybavených tabulek v PDF.
type: docs
weight: 50
url: /cs/net/programming-with-tables/auto-fit-to-window/
---
## Zavedení

Při práci s PDF je běžné pracovat s tabulkami a jsou chvíle, kdy potřebujete, aby tyto tabulky dokonale zapadaly do šířky stránky. V tomto tutoriálu prozkoumáme, jak automaticky přizpůsobit tabulku oknu pomocí Aspose.PDF pro .NET. Díky tomu budou vaše tabulky vypadat uhlazeně a uspořádaně a zabráníte problémům, jako je přetékání nebo nerovnoměrné sloupce. Jste připraveni se učit? Pojďme se ponořit!

## Předpoklady

Než se pustíme do podrobného průvodce, budete potřebovat několik věcí:

1. Aspose.PDF for .NET nainstalovaný ve vašem projektu. Pokud ho ještě nemáte, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/) nebo prozkoumat jejich[zkušební verze zdarma](https://releases.aspose.com/).
2. Základní znalost programování .NET.
3. Visual Studio nebo jakékoli IDE s podporou .NET nainstalované ve vašem systému.

>  PS Nezapomeňte, že k používání Aspose.PDF bez omezení budete potřebovat licenci. Buď si můžete jeden koupit[zde](https://purchase.aspose.com/buy) nebo získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) vyzkoušet všechny funkce.

## Importujte balíčky

Než se ponoříte do kódu, budete muset importovat potřebné jmenné prostory:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nyní, když jsme připraveni, pojďme si to rozdělit do jednoduchých, stravitelných kroků, abychom pochopili, jak můžete automaticky přizpůsobit tabulku oknu pomocí Aspose.PDF pro .NET.

## Krok 1: Inicializujte objekt dokumentu

Nejprve musíte vytvořit dokument PDF. Představte si tento dokument jako prázdný list, kam budete přidávat stránky a tabulky.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektu Pdf voláním jeho prázdného konstruktoru
Document doc = new Document();
```
  
 Zde vytvoříme nový dokument pomocí`Document` třídy z Aspose.PDF. The`dataDir` je místo, kam bude váš PDF uložen poté, co budete hotovi.

## Krok 2: Přidejte stránku do dokumentu

PDF dokument potřebuje stránky, že? Přidejme jeden.

```csharp
// Vytvořte sekci (stránku) v objektu Pdf
Page sec1 = doc.Pages.Add();
```
  
 Do dokumentu jsme přidali novou stránku pomocí`Pages.Add()` metoda. Můžete si to představit jako přidání nového listu do dokumentu, kam umístíte tabulku.

## Krok 3: Vytvořte a nakonfigurujte tabulku

Nyní je čas vytvořit tabulku a upravit ji tak, aby se vešla do okna.

```csharp
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Přidejte tabulku do kolekce odstavců požadované sekce
sec1.Paragraphs.Add(tab1);
```
  
 Inicializovali jsme nový`Table` objekt a přidali jej do kolekce odstavců stránky. Každá stránka PDF může mít různé odstavce a zde s tabulkou zacházíme jako s odstavcem.

## Krok 4: Definujte šířky sloupců a Automatické přizpůsobení oknu

Dále nastavíme šířky sloupců a zajistíme, aby se tabulka sama přizpůsobila oknu.

```csharp
// Nastavte šířku sloupců pro tabulku
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```
  
 Nastavili jsme pevné šířky sloupců pro tabulku, ale také přidali`ColumnAdjustment.AutoFitToWindow`, což zajišťuje, že tabulka přizpůsobí svou velikost tak, aby odpovídala dostupnému oknu.

## Krok 5: Nastavte okraje a okraje pro tabulku a buňky

Tabulky bez ohraničení jsou často nečitelné. Pojďme definovat hranice a okraje, aby to vypadalo uklizeně.

```csharp
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
```
  
 Ohraničení se přidávají k tabulce i buňkám pomocí`BorderInfo` třídy, kde definujete tloušťku. Okraje jsou nastaveny tak, aby buňkám poskytly určitý prostor pro výplň.

## Krok 6: Přidejte do tabulky řádky a buňky

Stůl bez obsahu? To není dobré! Přidejme nějaké řádky a buňky.

```csharp
//Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```
  
Vytváříme dva řádky a do každého řádku přidáváme tři buňky. Zde zadáte svá skutečná data (což může být cokoli od řetězců po složitější prvky).

## Krok 7: Uložte dokument

Jakmile je vše nastaveno, budete chtít uložit nově vytvořený dokument PDF.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Uložte aktualizovaný dokument obsahující objekt tabulky
doc.Save(dataDir);
```
  
 The`doc.Save()` metoda uloží PDF do zadaného adresáře. V tomto případě bude dokument uložen jako`AutoFitToWindow_out.pdf` ve vámi definovaném adresáři.

## Závěr

tady to máte! Právě jste vytvořili tabulku, která se automaticky přizpůsobí oknu pomocí Aspose.PDF pro .NET. To nejen zajišťuje, že váš stůl vypadá profesionálně a dobře namontovaný, ale také vám poskytuje flexibilitu při práci s různými velikostmi dat. Ať už vytváříte sestavy, faktury nebo jakýkoli dokument vyžadující tabulky, tato metoda je skvělým způsobem, jak udržovat čisté a čitelné rozvržení.

## FAQ

### Mohu dynamicky přidávat další řádky?  
 Ano, můžete pokračovat v přidávání řádků pomocí`tab1.Rows.Add()` metoda, dynamicky založená na obsahu.

### Jak upravím stůl, když nechci, aby se automaticky přizpůsobil?  
 Můžete ručně nastavit`ColumnWidths` bez použití`ColumnAdjustment.AutoFitToWindow` aby byla zachována pevná šířka stolu.

### Mohu do buněk přidat obrázky nebo jiný obsah?  
Ano, Aspose.PDF vám umožňuje přidávat obrázky, text a dokonce i další tabulky do buněk!

### Co když potřebuji složitější styly tabulek?  
Styly tabulky a buněk můžete dále přizpůsobit pomocí vlastností, jako je barva pozadí, zarovnání textu a nastavení písma.

### Je možné exportovat tuto tabulku do jiných formátů než PDF?  
Absolutně! Aspose.PDF podporuje export do různých formátů, jako je HTML, DOCX a další.