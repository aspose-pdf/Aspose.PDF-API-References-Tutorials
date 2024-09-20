---
title: Použít styl čísel v souboru PDF
linktitle: Použít styl čísel v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak používat různé styly čísel (římské číslice, abecední) na nadpisy v PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce.
type: docs
weight: 10
url: /cs/net/programming-with-headings/apply-number-style/
---
## Zavedení

Přistihli jste se někdy, že potřebujete do dokumentů PDF přidat krásně očíslované seznamy? Ať už formátujete právní dokumenty, zprávy nebo prezentace, správné styly číslování jsou pro uspořádání informací zásadní. S Aspose.PDF for .NET můžete na nadpisy souboru PDF použít různé styly číslování a vytvářet dobře strukturované a profesionální dokumenty. 

## Předpoklady

Než se pustíme do kódování, pojďme si projít, co budete potřebovat:

1. Aspose.PDF pro .NET: Stáhněte si nejnovější verzi Aspose.PDF z[zde](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Ujistěte se, že máte Visual Studio nebo jakékoli jiné IDE kompatibilní s .NET.
3. .NET Framework: Ujistěte se, že máte nainstalované rozhraní .NET Framework 4.0 nebo vyšší.
4.  Licence: Můžete použít dočasnou licenci z[zde](https://purchase.aspose.com/temporary-license/) nebo prozkoumat[zkušební verze zdarma](https://releases.aspose.com/) možnosti.

## Importujte balíčky

Chcete-li začít, ujistěte se, že máte do projektu importovány následující jmenné prostory:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 1: Nastavení dokumentu

Začněme vytvořením nového dokumentu PDF a nakonfigurováním nastavení jeho stránky. Nastavíme velikost stránky a okraje, abychom řídili rozložení našeho obsahu.

Vysvětlení: V tomto kroku nastavujeme základní strukturu PDF, která zahrnuje definování velikosti stránky, výšky a okrajů pro konzistentní formátování.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Nastavte rozměry a okraje stránky
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Tímto způsobem bude mít váš dokument standardní velikost stránky, ekvivalentní stránce 8,5 x 11 palců, a okraj 72 bodů (nebo 1 palec) na všech stranách.

## Krok 2: Přidání stránky do PDF

Dále do dokumentu PDF přidáme novou stránku, kde později použijeme styly číslování.

Vysvětlení: Každý PDF vyžaduje stránky! Tento krok přidá do PDF prázdnou stránku a nastaví její okraje tak, aby odpovídaly nastavení na úrovni dokumentu.

```csharp
// Přidejte do dokumentu PDF novou stránku
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Krok 3: Vytvořte plovoucí krabici

FloatingBox vám umožňuje umístit obsah (jako text nebo nadpisy) do rámečku, který se chová nezávisle na toku stránky. To je užitečné, když chcete mít úplnou kontrolu nad rozložením vašeho obsahu.

Vysvětlení: Zde nastavujeme FloatingBox, který bude obsahovat nadpisy, pro které budou použity styly čísel.

```csharp
// Vytvořte FloatingBox pro strukturovaný obsah
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Krok 4: Přidejte první nadpis s římskými číslicemi

Nyní přichází ta vzrušující část! Doplňme první nadpis s číslováním malými římskými číslicemi.

Vysvětlení: Na nadpis aplikujeme styl NumberingStyle.NumeralsRomanLowercase, který zobrazí číslování římskými číslicemi (i, ii, iii atd.).

```csharp
// Vytvořte první nadpis římskými číslicemi
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Krok 5: Přidejte nadpis druhé římské číslice

Pro demonstrační účely přidáme nadpis druhé římské číslice, ale tentokrát začneme od 13.

Vysvětlení: Vlastnost StartNumber umožňuje začít číslovat od vlastního čísla – v tomto případě začínáme od 13.

```csharp
// Vytvořte druhý nadpis začínající římskou číslicí 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Krok 6: Přidejte nadpis s abecedním číslováním

Pro zpestření přidáme třetí nadpis, tentokrát však použijeme abecední číslování malými písmeny (a, b, c atd.).

Vysvětlení: Změna NumberingStyle na LettersLowercase nám umožňuje použít pro naše nadpisy abecední číslování.

```csharp
// Vytvořte nadpis s abecedním číslováním
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Krok 7: Uložení PDF

Nakonec, po použití všech nadpisů a stylů čísel, uložme soubor PDF do požadovaného adresáře.

Vysvětlení: Tento krok uloží soubor PDF obsahující všechna formátovaná záhlaví s použitými styly číslování.

```csharp
// Uložte dokument PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Závěr

A tady to máte! Úspěšně jste použili styly číslování – římské číslice a abecedu – na nadpisy v souboru PDF pomocí Aspose.PDF for .NET. Flexibilita poskytovaná Aspose.PDF pro ovládání rozvržení stránky, stylů číslování a umístění obsahu vám poskytuje výkonnou sadu nástrojů pro vytváření dobře organizovaných profesionálních dokumentů PDF.

## FAQ

### Mohu na stejný dokument PDF použít různé styly čísel?  
Ano, Aspose.PDF for .NET vám umožňuje kombinovat různé styly číslování, jako jsou římské číslice, arabské číslice a abecední číslování v rámci jednoho dokumentu.

### Jak mohu upravit počáteční číslo pro nadpisy?  
 Počáteční číslo pro jakýkoli nadpis můžete nastavit pomocí`StartNumber` vlastnictví.

### Existuje způsob, jak resetovat posloupnost číslování?  
Ano, číslování můžete resetovat úpravou`StartNumber` vlastnost pro každý nadpis.

### Mohu na nadpisy kromě číslování použít i tučný styl nebo kurzívu?  
 Absolutně! Styly nadpisů můžete upravit úpravou vlastností, jako je písmo, velikost, tučné písmo a kurzíva pomocí`TextState` objekt.

### Jak získám dočasnou licenci pro Aspose.PDF?  
 Dočasnou licenci můžete získat od[zde](https://purchase.aspose.com/temporary-license/) k testování Aspose.PDF bez omezení.