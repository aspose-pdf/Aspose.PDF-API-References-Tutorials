---
title: Přidat textový rámeček do souboru PDF
linktitle: Přidat textový rámeček do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat textové ohraničení do souboru PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce. Vylepšete své PDF dokumenty.
type: docs
weight: 70
url: /cs/net/programming-with-text/add-text-border/
---
## Zavedení

Vytváření a manipulace s dokumenty PDF se v dnešním digitálním světě staly nezbytnou dovedností. Ať už generujete sestavy, faktury nebo jakýkoli jiný typ dokumentace, mít kontrolu nad tím, jak bude váš text vypadat, může znamenat významný rozdíl. Jedním z takových vylepšení, které možná budete chtít implementovat, je přidání ohraničení kolem textu v souboru PDF. V této příručce vás provedeme kroky k přidání textového ohraničení do souboru PDF pomocí knihovny Aspose.PDF pro .NET. Takže, pojďme se rovnou ponořit!

## Předpoklady

Než začneme, je pár věcí, které musíte mít na svém místě. Nebojte se, je to docela jednoduché!

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Toto bude vaše vývojové prostředí, kde budete psát a spouštět svůj kód.
2.  Aspose.PDF for .NET: Budete si muset stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete to získat z[Aspose PDF for .NET download page](https://releases.aspose.com/pdf/net/) . Pokud si to chcete nejprve vyzkoušet, můžete také získat a[zkušební verze zdarma zde](https://releases.aspose.com/).
3. Základní znalost C#: Základní znalost programovacího jazyka C# vám pomůže snadno následovat příklady.
4. .NET Framework: Ujistěte se, že máte ve svém projektu nainstalované a nastavené rozhraní .NET Framework.

Jakmile máte tyto předpoklady na místě, jste připraveni začít kódovat!

## Importujte balíčky

Nyní, když máme vše nastaveno, pojďme importovat potřebné balíčky pro použití Aspose.PDF v našem projektu. Můžete to udělat přidáním následujícího pomocí direktiv v horní části souboru C#:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

Tyto jmenné prostory vám umožní efektivně pracovat s dokumenty PDF a textovými fragmenty. 

Nyní si rozeberme proces přidávání ohraničení textu do podrobných kroků. Projdeme si každý krok, abyste přesně pochopili, co se děje pod kapotou.

## Krok 1: Nastavte dokument

Nejprve musíme vytvořit nový dokument PDF. Tady se stane všechna naše kouzla.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořte nový objekt dokumentu
Document pdfDocument = new Document();
```

 V tomto kroku určíme adresář, kam chceme uložit náš PDF soubor. Poté vytvoříme novou instanci`Document` třídy, která představuje náš dokument PDF.

## Krok 2: Přidejte novou stránku

Dále musíme do našeho dokumentu přidat stránku. Berte to jako přidání prázdného plátna, kam umístíme náš text.

```csharp
// Získejte konkrétní stránku
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

 Zde nazýváme`Add()` metoda na`Pages` sbírka našeho`pdfDocument` objekt. Tím se do dokumentu přidá nová stránka a odkaz na ni uložíme do souboru`pdfPage` variabilní.

## Krok 3: Vytvořte textový fragment

Nyní vytvoříme text, který chceme zobrazit v našem PDF. Zde definujeme obsah našeho textového fragmentu.

```csharp
// Vytvořte fragment textu
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

 V tomto kódu vytvoříme nový`TextFragment` objekt s textem "hlavní text". Jeho pozici na stránce nastavíme také pomocí`Position` třída. Souřadnice (100, 600) určují, kde bude text na stránce umístěn.

## Krok 4: Nastavte vlastnosti textu

Dále upravíme náš fragment textu, aby byl vizuálně přitažlivý. To zahrnuje nastavení velikosti písma, typu písma, barvy pozadí a barvy popředí.

```csharp
// Nastavte vlastnosti textu
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

Zde nastavíme velikost písma na 12, jako písmo použijeme „Times New Roman“ a použijeme světle šedou barvu pozadí s červeným textem. Tyto vlastnosti pomáhají zlepšit viditelnost textu.

## Krok 5: Nastavte barvu tahu pro okraj

Nyní se dostáváme k vzrušující části – přidávání ohraničení kolem našeho textu!

```csharp
// Nastavte vlastnost StrokingColor pro kreslení ohraničení (tahu) kolem textového obdélníku
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

V tomto kroku určíme barvu ohraničení, které chceme kolem našeho textu nakreslit. Zde jsme zvolili tmavě červenou barvu.

## Krok 6: Povolte ohraničení obdélníku textu

 Abychom skutečně nakreslili ohraničení kolem našeho textu, musíme povolit`DrawTextRectangleBorder` vlastnictví.

```csharp
// Nastavte hodnotu vlastnosti DrawTextRectangleBorder na true
textFragment.TextState.DrawTextRectangleBorder = true;
```

 Nastavením této vlastnosti na`true`, řekneme Aspose.PDF, aby nakreslil ohraničení kolem textového obdélníku na základě zadané barvy tahu.

## Krok 7: Připojte textový fragment na stránku

Nyní, když máme náš textový fragment připraven se všemi nastavenými vlastnostmi, je čas jej přidat na stránku.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

 Zde vytvoříme a`TextBuilder` objekt, který je spojen s naším`pdfPage` . Poté použijeme`AppendText` způsob přidání našeho`textFragment` na stránku. 

## Krok 8: Uložte dokument

Nakonec musíme uložit náš dokument PDF do zadaného adresáře. Toto je okamžik pravdy!

```csharp
// Uložte dokument
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

 tomto kroku zavoláme`Save` metoda na našem`pdfDocument` objekt, poskytující cestu, kam chceme soubor uložit. Jakmile kód spustíte, měli byste najít svůj nově vytvořený PDF s ohraničením textu v určeném adresáři!

## Závěr

A tady to máte! Úspěšně jste přidali textové ohraničení do souboru PDF pomocí Aspose.PDF for .NET. Tato jednoduchá, ale výkonná funkce může výrazně zlepšit čitelnost a estetiku vašich dokumentů PDF. Ať už vytváříte zprávy, brožury nebo jakýkoli jiný typ dokumentace, vědět, jak manipulovat s formátováním textu, se může hodit.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, manipulovat a zpracovávat dokumenty PDF programově pomocí rozhraní .NET.

### Mohu vyzkoušet Aspose.PDF zdarma?
 Ano! Aspose nabízí a[zkušební verze zdarma](https://releases.aspose.com/) jejich knihovny PDF, což vám umožní otestovat její funkce před nákupem.

### Jak koupím Aspose.PDF pro .NET?
 Aspose.PDF pro .NET si můžete koupit přímo od nich[nákupní stránku](https://purchase.aspose.com/buy).

### Je k dispozici podpora pro Aspose.PDF?
 Absolutně! Podporu můžete získat návštěvou stránky[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10).

### Co když potřebuji dočasnou licenci?
 Aspose poskytuje a[dočasná licence](https://purchase.aspose.com/temporary-license/) možnost pro vývojáře, kteří potřebují hodnotit knihovnu po omezenou dobu.