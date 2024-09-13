---
title: Vyplnit text tahu v souboru PDF
linktitle: Vyplnit text tahu v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak bez námahy vyplnit text tahu v souborech PDF pomocí Aspose.PDF for .NET, pomocí tohoto podrobného průvodce plného praktických příkladů.
type: docs
weight: 90
url: /cs/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Zavedení

Chtěli jste někdy upravit soubor PDF, aby vynikl? Možná budete muset přidat výrazný vodoznak nebo výrazné razítko, díky kterému bude důležitý dokument nezaměnitelně váš. S Aspose.PDF for .NET můžete snadno vyplnit text tahu v souboru PDF a přidat umělecký vkus, který upoutá pozornost. V dnešním tutoriálu si projdeme proces, jak toho dosáhnout – vyplňování textu tahu do PDF pomocí C#. Na konci budete mít solidní přehled o tom, jak manipulovat se soubory PDF jako profesionál.

## Předpoklady

Než se ponoříme do kódování, je potřeba mít připraveno několik věcí, aby byl tento tutoriál hračkou:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio, protože budeme psát kód C#.
2.  Knihovna Aspose.PDF: Ujistěte se, že jste si stáhli knihovnu Aspose.PDF pro .NET. Můžeš to chytit[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže snáze pochopit tutoriál.
4. Ukázkový soubor PDF: Budete potřebovat ukázkový soubor PDF (`input.pdf`pro testovací účely. Můžete vytvořit jednoduchý soubor nebo použít jakýkoli existující soubor PDF, který máte.

Nyní, když máme vše na svém místě, pojďme se pustit do hrubšího vyplňování textu tahu ve vašem souboru PDF.

## Importujte balíčky

Chcete-li začít, budeme muset importovat potřebné balíčky. Zde je stručný přehled základních importů pro náš projekt:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Tyto balíčky nám umožní využívat robustní funkce knihovny Aspose.PDF.

Rozdělme si hlavní úkol do jasných kroků. Pomocí těchto kroků můžete snadno vyplnit text tahu do souborů PDF. 

## Krok 1: Nastavte své prostředí

Nejprve se ujistěte, že máte vše správně nastaveno v projektu sady Visual Studio. Vytvořte nový projekt nebo vyberte existující. Pokud potřebujete pomoc, postupujte takto:

1. Otevřete Visual Studio.
2. Vytvořte nový projekt C# (např. Console Application).
3. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
4.  Hledat`Aspose.PDF` a nainstalujte jej.

## Krok 2: Definujte svůj adresář dokumentů

Každá cesta potřebuje výchozí bod a v našem případě je to adresář dokumentů, kde budou umístěny vstupní a výstupní soubory. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš vstupní soubor PDF. 

## Krok 3: Vytvořte objekt TextState

V tomto kroku začnete definovat vlastnosti textu, který chcete přidat. 

```csharp
TextState ts = new TextState();
```

 The`TextState` objekt bude obsahovat možnosti stylů pro váš text tahu.

## Krok 4: Nastavte barvu pro tah

Dále budete chtít definovat barvu tahu pro váš text. 

```csharp
ts.StrokingColor = Color.Gray;
```

V tomto kódu používáme pro tah šedou barvu. Neváhejte změnit barvu podle svých potřeb!

## Krok 5: Nakonfigurujte režim vykreslování

Chcete-li zajistit, aby se text zobrazoval podle očekávání, nastavte režim vykreslování:

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

To dává knihovně Aspose pokyn, že pracujeme s textem tahu.

## Krok 6: Načtěte svůj vstupní dokument PDF

Nyní je čas načíst soubor PDF, který se chystáte upravit. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Ujistěte se, že jste zadali PDF (`input.pdf`se nachází v adresáři dokumentů definovaném v předchozích krocích.

## Krok 7: Vytvořte objekt razítka

Dále vytvořte razítko, které bude držet text vašeho tahu. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Toto razítko bude použito k překrytí vašeho textu na PDF.

## Krok 8: Definujte text k razítku

Budete muset určit, jaký text chcete do PDF přidat:

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Zde je text „ZAPLACENO V PLNÉM ROZSAHU“ doplněný spolu s jeho atributy stylu. Přizpůsobte si jej podle svých požadavků!

## Krok 9: Svažte stav textu

 Nyní svažte`TextState` jste definovali dříve k razítku. 

```csharp
stamp.BindTextState(ts);
```

Tento krok aplikuje na váš text všechny styly, jako je barva a režim vykreslování.

## Krok 10: Nastavte pozici razítka

Určete, kde se vaše razítko v PDF objeví:

```csharp
stamp.SetOrigin(100, 100);
```

 Argumenty`(100, 100)` označte souřadnice X a Y (v bodech) pro počátek textu. Upravte tyto hodnoty tak, aby byl váš text dokonale umístěn!

## Krok 11: Nakonfigurujte neprůhlednost a rotaci

Zde si můžete pohrát se vzhledem svého textu:

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

V tomto případě hodnota krytí a úhel otočení 45 stupňů dodají vašemu textu jedinečný šmrnc. Neváhejte a upravte tato nastavení pro různé efekty.

## Krok 12: Přidejte razítko do PDF

Toto je zásadní krok, kdy konečně přidáme naše razítko, které obsahuje text tahu do PDF:

```csharp
fileStamp.AddStamp(stamp);
```

A stejně tak je váš text připraven k vyjádření!

## Krok 13: Uložte a zavřete dokument

Nakonec uložte změny a ujistěte se, že je vše správně vyčištěno. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 Váš nově upravený soubor PDF obsahující text tahu bude uložen jako`output_out.pdf` ve vašem adresáři dokumentů. 

## Závěr

A tady to máte! Pomocí těchto jednoduchých kroků můžete snadno vyplnit text tahu v souboru PDF pomocí Aspose.PDF pro .NET. Ať už se jedná o obchodní dokumenty nebo osobní projekty, tato technika vám umožní dodat vašim PDF jedinečný nádech, díky čemuž vyniknou na jakémkoli stohu papírů.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět soubory PDF programově.

### Mohu používat Aspose.PDF zdarma?
Ano, Aspose nabízí bezplatnou zkušební verzi. Můžete to získat[zde](https://releases.aspose.com/).

### Musím za licenci platit?
 Zatímco knihovna má bezplatnou zkušební verzi, dočasnou licenci lze také zakoupit na[tento odkaz](https://purchase.aspose.com/temporary-license/).

### Kde najdu dokumentaci?
 Máte přístup ke kompletní dokumentaci[zde](https://reference.aspose.com/pdf/net/).

### Je k dispozici podpora, pokud narazím na problémy?
 Absolutně! Podporu můžete získat na fóru Aspose[zde](https://forum.aspose.com/c/pdf/10).