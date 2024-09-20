---
title: Prvek tabulky stylu
linktitle: Prvek tabulky stylu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet a upravovat prvky tabulky v Aspose.PDF pro .NET pomocí podrobných pokynů, vlastního stylu a souladu s PDF/UA.
type: docs
weight: 170
url: /cs/net/programming-with-tagged-pdf/style-table-element/
---
## Zavedení

V tomto článku se ponoříme do toho, jak vytvořit a nastylovat prvek tabulky pomocí Aspose.PDF pro .NET. Dozvíte se, jak strukturovat tabulku, používat vlastní styly a ověřovat shodu vašeho dokumentu s PDF/UA. Na konci tohoto tutoriálu budete schopni snadno vytvářet profesionálně vypadající tabulky ve vašich PDF!

## Předpoklady

Než se pustíte do výukového programu, musíte se ujistit, že máte následující:

1. Visual Studio nebo podobné IDE nainstalované na vašem počítači.
2. .NET Framework nebo .NET Core SDK pro spuštění aplikace.
3.  Knihovna Aspose.PDF for .NET stažená a odkazovaná ve vašem projektu. Nejnovější verzi si můžete stáhnout z[zde](https://releases.aspose.com/pdf/net/).
4.  Platná licence Aspose nebo a[dočasná licence](https://purchase.aspose.com/temporary-license/) k odemknutí plné funkčnosti knihovny.

## Importujte balíčky

Chcete-li začít, importujte potřebné jmenné prostory do svého projektu:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Tyto jmenné prostory pokrývají základní operace PDF, tagovaný obsah, tabulky a formátování textu.

Nyní si rozeberme proces vytváření a stylování tabulky v Aspose.PDF. Projdeme si každou část podrobně, abyste ji mohli sledovat.

## Krok 1: Vytvořte nový dokument PDF a nastavte označený obsah

V tomto prvním kroku vytvoříme prázdný dokument PDF a nastavíme jeho tagovaný obsah.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte nový dokument PDF
Document document = new Document();

// Nastavení označeného obsahu
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Začneme vytvořením nového`Document` objekt představující naše PDF. The`TaggedContent`objekt slouží ke správě struktury dokumentu a zajišťuje soulad se standardy přístupnosti. Nastavíme název a jazyk dokumentu pro správné tagování.

## Krok 2: Definujte kořenový prvek

Dále vytvoříme element kořenové struktury, který funguje jako kontejner pro veškerý obsah v našem PDF.

```csharp
// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;
```

 The`RootElement` slouží jako základní kontejner pro všechny strukturované prvky včetně našeho stolu. Pomáhá udržovat strukturní hierarchii dokumentu, což je důležité pro organizaci i dostupnost.

## Krok 3: Vytvořte a upravte styl prvku tabulky

 Nyní, když je kořenový prvek nastaven, vytvoříme a`TableElement` a použít styly, jako je barva pozadí, okraje a zarovnání.

```csharp
// Vytvořte prvek struktury tabulky
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Upravte styl stolu
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Vytváříme a`TableElement` , který definuje strukturu naší tabulky. The`BackgroundColor`, `Border` a`Alignment` vlastnosti nám umožňují přizpůsobit vzhled tabulky. The`Broken` Vlastnost zajišťuje, že pokud se tabulka přeruší přes stránky, přeruší se vertikálně.

## Krok 4: Nastavte rozměry tabulky a styly buněk

V tomto kroku definujeme počet sloupců, odsazení buněk a další důležité vlastnosti tabulky.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Specifikujeme šířky sloupců, abychom zajistili, že každý sloupec v tabulce bude rovnoměrně rozmístěn. The`DefaultCellBorder`, `DefaultCellPadding` a`DefaultCellTextState` definovat výchozí styly pro buňky, včetně ohraničení, odsazení, barvy textu a velikosti písma.

## Krok 5: Přidejte opakující se řádky a vlastní styly

Můžeme také definovat styly pro opakování řádků a dalších specifických prvků tabulky, jako jsou záhlaví a zápatí.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 The`RepeatingRowsCount` zajišťuje, že se první tři řádky opakují, pokud tabulka zahrnuje více stránek. Nastavili jsme`RepeatingRowsStyle` chcete-li na tyto řádky použít vlastní barvu pozadí.

## Krok 6: Přidejte prvky hlavy, těla a nohy stolu

Nyní vytvoříme sekce záhlaví, těla a zápatí tabulky a naplníme je obsahem.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Vytvořte řádek záhlaví
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Naplňte tělo tabulky
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Stůl je rozdělen na tři části: hlavu, tělo a nohu. Nejprve vytvoříme řádek záhlaví pomocí`TableTHElement` přidejte záhlaví sloupců. Poté naplníme tělo tabulky`TableTDElement`, vyplní každou buňku štítkem, který obsahuje její polohu.

## Krok 7: Uložte dokument

Nakonec PDF dokument uložíme do určeného adresáře.

```csharp
// Uložte tagovaný dokument PDF
document.Save(dataDir + "StyleTableElement.pdf");
```

Tento krok dokončuje proces vytváření dokumentu uložením souboru PDF se stylizovanou tabulkou.

## Krok 8: Ověřte soulad s PDF/UA

Po uložení dokumentu je nezbytné zajistit, aby vyhovoval standardům PDF/UA (Universal Accessibility).

```csharp
// Zkontrolujte shodu s PDF/UA
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Zde znovu načteme dokument a ověříme jej podle standardů PDF/UA. Soulad zajišťuje, že vaše PDF splňuje požadavky na přístupnost, takže je vhodné pro širokou škálu uživatelů.

## Závěr

Aspose.PDF pro .NET je vytváření a stylování tabulek v dokumentech PDF jednoduché a intuitivní. Podle kroků uvedených v tomto kurzu můžete vytvářet tabulky s přizpůsobenými styly a zajistit, aby vaše soubory PDF splňovaly standardy usnadnění. Ať už generujete sestavy nebo vytváříte strukturované dokumenty, tabulky jsou mocným nástrojem pro přehlednou prezentaci dat.

## FAQ

### Mohu přidat obrázky do buněk tabulky?
 Ano, obrázky můžete vkládat do buněk tabulky pomocí`Image` živel.

### Jak dynamicky upravím šířku sloupců?
 Můžete nastavit`ColumnAdjustment` majetek do`AutoFitToWindow` pro automatickou úpravu šířky sloupců podle obsahu.

### Je soulad s PDF/UA povinný pro všechny dokumenty?
I když to není povinné, doporučuje se pro dokumenty, které vyžadují vysoké standardy přístupnosti.

### Mohu na konkrétní řádky použít různé styly?
 Ano, můžete přizpůsobit jednotlivé řádky nebo buňky jejich úpravou`TextState` nebo`BackgroundColor`.

### Jaká je výhoda používání označeného obsahu?
Tagovaný obsah zlepšuje dostupnost dokumentů a pomáhá zajistit shodu se standardy jako PDF/UA.