---
title: Číslo Stránky V Zápatí Záhlaví Pomocí Plovoucí Krabice
linktitle: Číslo Stránky V Zápatí Záhlaví Pomocí Plovoucí Krabice
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném tutoriálu můžete snadno přidat čísla stránek do záhlaví a zápatí PDF pomocí plovoucího rámečku s Aspose.PDF pro .NET.
type: docs
weight: 150
url: /cs/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Zavedení

Pokud jde o programovou správu dokumentů PDF, Aspose.PDF for .NET vyniká jako výjimečný nástroj. Zjednodušuje způsob, jakým vytváříme, upravujeme a manipulujeme se soubory PDF v aplikacích .NET. Ať už generujete faktury, sestavy nebo jakýkoli typ dokumentu, elegantní přidání čísel stránek může zlepšit profesionalitu a organizaci vašich PDF. V tomto tutoriálu se ponoříme do toho, jak přidat čísla stránek do záhlaví a zápatí vašeho PDF pomocí plovoucího rámečku. Jste připraveni začít? Jdeme!

## Předpoklady

Než se pustíme do této vzrušující cesty do oblasti manipulace s PDF, musíte mít několik věcí:

### Nastavení prostředí .NET
Ujistěte se, že máte vývojové prostředí .NET. Můžete použít Visual Studio, které je mezi vývojáři oblíbenou volbou pro aplikace .NET.

### Knihovna Aspose.PDF
Nainstalujte knihovnu Aspose.PDF. Můžete si jej snadno stáhnout z webu:

- [Stáhněte si Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/)

### Základní znalost programování v C#
Základní porozumění C# vám pomůže pochopit koncepty a úryvky kódování uvedené v tomto tutoriálu.

### Přístup k dokumentaci
 Vždy je výhodné mít[Dokumentace Aspose.PDF](https://reference.aspose.com/pdf/net/) užitečné pro referenci a hlubší prozkoumání jakýchkoli dalších funkcí.

## Importujte balíčky

Chcete-li začít, budete muset do projektu importovat potřebné balíčky. To zajistí, že sestavení Aspose.PDF bude přístupné pro použití ve vašem kódu. Jak na to:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní si rozeberme proces přidávání čísel stránek pomocí plovoucího rámečku do zvládnutelných kroků. Následujte nás, když procházíme.

## Krok 1: Nastavte prostředí dokumentu

Začněme zadáním adresáře, kde bude uložen váš dokument PDF. To je zásadní, protože určuje, kam se uloží váš výstupní soubor.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`YOUR DOCUMENT DIRECTORY` s cestou dle vašeho výběru, kam chcete uložit výstupní soubor PDF.

## Krok 2: Vytvořte instanci dokumentu

 Vytvoření nového dokumentu PDF je dalším krokem. To zahrnuje použití`Document` třídy z knihovny Aspose.PDF.

```csharp
// Instancia dokumentu instance
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Zde vytvoříme novou instanci`Document` třídy, která nám slouží jako plátno pro manipulaci.

## Krok 3: Přidejte novou stránku

Nyní přidejte stránku do našeho dokumentu PDF. Každý PDF potřebuje alespoň jednu stránku, že?

```csharp
// Přidejte stránku do dokumentu PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Tento fragment kódu přidá do našeho dokumentu novou stránku a připraví jej na příjem obsahu, včetně našeho plovoucího pole s čísly stránek.

## Krok 4: Vytvořte plovoucí krabici

 Dále je čas vytvořit náš plovoucí box, který bude obsahovat číslo stránky. The`FloatingBox`třída nám umožňuje volně umístit obsah na stránku.

```csharp
// Inicializuje novou instanci třídy FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Tady parametry`(140, 80)` zadejte šířku a výšku plovoucího boxu. Tyto hodnoty můžete upravit podle vašich preferencí rozvržení.

## Krok 5: Umístění plovoucího boxu

 Umístění je klíčové! Chcete určit, kde se na stránce zobrazí číslo stránky. Budete pracovat s`Left` a`Top` vlastnosti k určení polohy.

```csharp
// Plovoucí hodnota, která označuje levou pozici odstavce
box1.Left = 2;
// Plovoucí hodnota, která označuje horní pozici odstavce
box1.Top = 10;
```
Tyto hodnoty určují umístění plovoucího rámečku na stránce. Nebojte se s nimi experimentovat, abyste zjistili, co vypadá pro váš dokument nejlépe.

## Krok 6: Přidejte text pomocí makra čísla stránky

Nyní přidáme řetězec, který dynamicky zobrazuje číslo stránky. Tady se děje kouzlo!

```csharp
// Přidejte makra do kolekce odstavců FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 v tomto případě`($p/ $P)`je makro, které zobrazí aktuální číslo stránky (`$p`) a celkový počet stran (`$P`). Výsledkem je, že formátuje text tak, aby četl něco jako „Stránka: 1/5“.

## Krok 7: Přidejte plovoucí pole na stránku

Je čas přidat plovoucí rámeček spolu s textem čísla stránky na naši nově vytvořenou stránku.

```csharp
// Přidejte na stránku plovoucí rámeček
page.Paragraphs.Add(box1);
```
Tento řádek v podstatě vloží váš plovoucí rámeček do stránky, čímž se stane součástí rozvržení dokumentu. 

## Krok 8: Uložte dokument

Nakonec si svou práci nezapomeňte uložit! Posledním krokem je uložení dokumentu PDF se správným názvem souboru.

```csharp
// Uložte dokument
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Ujistěte se, že zadaná cesta obsahuje požadovaný název souboru. Nyní je vytvořen váš úžasný PDF s čísly stránek! 

## Závěr

tady to máte, lidi! Přidání čísel stránek do záhlaví a zápatí vašeho PDF pomocí Aspose.PDF for .NET je tak jednoduché. S pouhými několika řádky kódu jste se vydali na cestu ke zpracování hlavních dokumentů ve vašich aplikacích. Neváhejte experimentovat s různými rozvrženími a formátováním – kreativitě se přece meze nekladou! Jste připraveni vytvořit tento profesionální dokument? Popadněte svůj kódovací klobouk a začněte experimentovat.

## FAQ

### Mohu upravit vzhled textu čísla stránky?  
 Ano, můžete upravit vlastnosti textu, jako je velikost písma, barva a styl úpravou`TextFragment` vlastnosti.

### Je Aspose.PDF zdarma k použití?  
 Zatímco Aspose.PDF nabízí bezplatnou zkušební verzi, je to placený produkt pro produkční použití. Můžete[kupte si to zde](https://purchase.aspose.com/buy).

### Kde najdu podrobnější dokumentaci?  
 Komplexní dokumentaci naleznete na[Dokumentační stránka Aspose.PDF](https://reference.aspose.com/pdf/net/).

### Jak mohu použít záhlaví a zápatí na více stránek?  
Můžete procházet všechny stránky v dokumentu a použít plovoucí rámeček na každou z nich podobně.

### Co když potřebuji podporu pro další funkce?  
Máte-li jakékoli další dotazy nebo podporu, můžete navštívit stránku[Fórum Aspose](https://forum.aspose.com/c/pdf/10).