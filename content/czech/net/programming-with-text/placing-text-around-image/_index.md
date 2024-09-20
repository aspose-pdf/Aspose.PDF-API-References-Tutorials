---
title: Umístění textu kolem obrázku v souboru PDF
linktitle: Umístění textu kolem obrázku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak umístit text kolem obrázků v PDF pomocí Aspose.PDF pro .NET. Postupujte podle našeho podrobného průvodce a vytvořte profesionální soubory PDF s obrázky a textem vedle sebe.
type: docs
weight: 260
url: /cs/net/programming-with-text/placing-text-around-image/
---
## Zavedení

Zkoušeli jste někdy umístit text kolem obrázku v souboru PDF, ale zdálo se vám to náročné? Pokud ano, jste na správném místě! Aspose.PDF for .NET tento proces zjednodušuje a umožňuje vám umístit text vedle obrázků pomocí pouhých několika řádků kódu. Ať už vytváříte zprávy, dokumenty nebo prezentace, tato funkce je fantastickým způsobem, jak vylepšit rozvržení obsahu a učinit jej vizuálně přitažlivějším. Dnes si projdeme, jak používat Aspose.PDF pro .NET k umístění textu kolem obrázků v dokumentu PDF.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máme vše nastaveno. Zde je to, co budete potřebovat:

-  Aspose.PDF pro .NET: Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
- Visual Studio: Ujistěte se, že máte nainstalovanou nejnovější verzi, abyste mohli hladce pokračovat.
- .NET Framework: Tento příklad používá .NET, takže se ujistěte, že je vaše prostředí nastaveno pro vývoj .NET.
-  Dočasná licence: Můžete požádat o dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/) pokud hodnotíte produkt.

Pokud jste ještě nenastavili Aspose.PDF pro .NET, postupujte podle pokynů k instalaci v souboru[dokumentace](https://reference.aspose.com/pdf/net/).

## Importovat jmenné prostory

Než začneme kódovat, musíme naimportovat potřebné jmenné prostory. Zde je fragment kódu, jak to udělat:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Tyto jmenné prostory jsou nezbytné, protože poskytují přístup k třídám jako`Document`, `Page`, `Image` a`HtmlFragment`, který použijeme k vytvoření a manipulaci s PDF.

Nyní, když jsme připravili scénu, pojďme si rozebrat, jak umístit text kolem obrázku v souboru PDF pomocí Aspose.PDF for .NET. Tímto vás krok za krokem provedeme.

## Krok 1: Vytvořte instanci objektu dokumentu

 Nejprve musíte vytvořit dokument PDF. V Aspose.PDF se to provede vytvořením instance a`Document` objekt. Tento objekt bude sloužit jako základ pro veškerý obsah, který přidáme.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Zde jsme vytvořili prázdný dokument PDF. Zatím nemá žádné stránky, ale nebojte se, v dalším kroku jednu přidáme.

## Krok 2: Přidejte stránku do dokumentu

Nyní, když máme dokument, je čas přidat stránku. Berte to jako vytvoření prázdného listu papíru, kam přidáte svůj obsah.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Tento kód přidá do dokumentu novou stránku. Ve výchozím nastavení je stránka prázdná, ale to se chystáme změnit.

## Krok 3: Vytvořte tabulku pro uspořádání obsahu

Aby náš obrázek a text byly správně zarovnány, použijeme tabulku. Tabulky v PDF mohou pomoci strukturovat vaše rozvržení, podobně jako v dokumentech Word nebo HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Tento úryvek vytvoří tabulku a přidá ji na stránku. Představte si tabulku jako rámec pro zarovnání obrázku a textu.

## Krok 4: Nastavte šířku sloupců pro tabulku

Nyní, když jsme přidali tabulku, musíme definovat, jak široké mají být sloupce. To zajistí, že obrázek a text budou mít na stránce vhodnou velikost.

```csharp
table1.ColumnWidths = "120 270";
```

Tento řádek nastavuje šířku dvou sloupců – jednoho pro obrázek a druhého pro text. Upravte tyto hodnoty, pokud váš obrázek nebo text potřebuje více nebo méně místa.

## Krok 5: Definujte okraje a odsazení

Aby vše vypadalo úhledně, přidejte na stůl nějaké okraje a vycpávky.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Tato nastavení zajistí, že vaše tabulka bude mít konzistentní mezery, díky čemuž bude obsah vizuálně přitažlivý.

## Krok 6: Vložte obrázek do tabulky

Nyní pojďme k zábavnější části – přidání obrázku. V tomto případě přidáme logo Aspose, ale můžete použít libovolný obrázek, který se vám líbí.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Zde je to, co se děje:
- Načteme obrázek z vámi zadaného adresáře.
- Nastavíme výšku a šířku obrázku.
- Nakonec přidáme obrázek do první buňky v tabulce.

## Krok 7: Přidejte text vedle obrázku

Nyní, když je obrázek na místě, přidáme k němu nějaký text. V tomto příkladu použijeme ke stylování obsahu text ve formátu HTML.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Tento blok přidá stylizovaný název a popis do buňky vedle obrázku. Pro větší přizpůsobení můžete text formátovat pomocí značek HTML.

## Krok 8: Upravte vertikální zarovnání

Ve výchozím nastavení se obsah v buňkách tabulky nemusí zarovnat tak, jak chcete. V tomto případě se chceme ujistit, že je text zarovnán k horní části buňky.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Tím je zajištěno, že text bude umístěn v horní části buňky a rozvržení zůstane čisté a profesionální.

## Krok 9: Přidejte další text pod obrázek a popis

Možná budete chtít zahrnout více obsahu pod obrázek a text. Za tímto účelem přidáme do tabulky další řádek.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Zde jsme přidali další řádek s dalším textem, který zahrnuje oba sloupce, abychom zachovali rovnováhu v rozložení.

## Krok 10: Uložte dokument PDF

Nakonec musíme dokument uložit, abyste si mohli prohlédnout změny.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Tím se uloží PDF s obrázkem a textem ve formátu, jak chceme.

## Závěr

Umístění textu kolem obrázků v PDF se může zdát jako skličující úkol, ale Aspose.PDF for .NET tento proces zjednodušuje. Využitím tabulek, obrázků a stylizovaného textu můžete s minimálním úsilím vytvářet profesionálně vypadající soubory PDF. Pomocí pouhých několika řádků kódu můžete umístit obsah přesně tam, kde ho chcete, a dodat vašim dokumentům uhlazený a dobře organizovaný vzhled.

## FAQ

### Mohu použít tuto metodu k umístění více obrázků s textem?
Ano, jednoduše přidejte do tabulky další řádky a buňky a zahrňte tak další obrázky a text.

### Mohu změnit zarovnání obrázku?
Absolutně! Zarovnání obrázku můžete upravit úpravou vlastností zarovnání buňky.

### Jak mohu text dále stylizovat?
 Můžete použít HTML tagy v`HtmlFragment` objekt pro použití různých stylů, jako je tučné písmo, kurzíva nebo různá písma.

### Mohu ovládat mezery mezi textem a obrázkem?
 Ano, pomocí`MarginInfo` objekt umožňuje ovládat odsazení a okraje mezi prvky.

### Je možné do textu přidat odkazy?
 Rozhodně! Hypertextové odkazy můžete vložit do textu ve formátu HTML pomocí`<a>` štítek.