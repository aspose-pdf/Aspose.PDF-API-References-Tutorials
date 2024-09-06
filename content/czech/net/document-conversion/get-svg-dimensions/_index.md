---
title: Získejte rozměry SVG
linktitle: Získejte rozměry SVG
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak používat Aspose.PDF pro .NET k převodu souborů SVG do PDF pomocí tohoto podrobného průvodce. Ideální pro vývojáře, kteří chtějí manipulovat s PDF.
type: docs
weight: 40
url: /cs/net/document-conversion/get-svg-dimensions/
---
## Zavedení

Vítejte ve světě Aspose.PDF pro .NET! Pokud chcete programově manipulovat se soubory PDF, jste na správném místě. Aspose.PDF je výkonná knihovna, která umožňuje vývojářům snadno vytvářet, upravovat a převádět dokumenty PDF. Ať už jste zkušený vývojář nebo teprve začínáte, tato příručka vás provede základy používání Aspose.PDF pro .NET a zaměří se na to, jak získat rozměry SVG a převést je do formátu PDF.

## Předpoklady

Než se pustíme do kódu, je třeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Je to IDE, které budeme používat pro tento tutoriál.
2.  .NET Framework: Ujistěte se, že máte nainstalované rozhraní .NET Framework. Aspose.PDF podporuje různé verze, takže zkontrolujte[dokumentace](https://reference.aspose.com/pdf/net/) kvůli kompatibilitě.
3.  Knihovna Aspose.PDF: Nejnovější verzi Aspose.PDF pro .NET si můžete stáhnout z[odkaz ke stažení](https://releases.aspose.com/pdf/net/) . Pokud si to chcete nejprve vyzkoušet, můžete také získat a[zkušební verze zdarma](https://releases.aspose.com/).
4. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět příkladům.

## Importujte balíčky

Chcete-li začít, musíte importovat potřebné balíčky. Můžete to udělat takto:

1. Otevřete projekt sady Visual Studio.
2. Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3. Vyhledejte "Aspose.PDF" a nainstalujte balíček.

Jakmile budete mít balíček nainstalován, můžete začít kódovat!

## Krok 1: Nastavte svůj projekt

### Vytvořit nový projekt

Nejprve vytvořte nový projekt C# ve Visual Studiu.

- Otevřete Visual Studio a vyberte „Vytvořit nový projekt“.
- Vyberte „Console App (.NET Framework)“ a klikněte na „Další“.
- Pojmenujte svůj projekt (např. „AsposePDFEexample“) a klikněte na „Vytvořit“.

### Přidat pomocí direktiv

 Nyní, když je váš projekt nastaven, musíte přidat potřebné direktivy pomocí v horní části vašeho`Program.cs` soubor:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

To vám umožní přístup ke třídám a metodám poskytovaným knihovnou Aspose.PDF.

## Krok 2: Načtěte dokument SVG

### Definujte adresář dokumentů

Před načtením dokumentu SVG musíte zadat cestu k adresáři vašich dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš soubor SVG.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Načtěte dokument SVG

 Nyní načteme dokument SVG pomocí`SvgLoadOptions` třída. Tato třída vám umožňuje upravit velikost stránky na základě obsahu SVG.

```csharp
var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

## Krok 3: Upravte okraje stránky

Chcete-li zajistit, aby se obsah SVG dokonale vešel do PDF, musíte nastavit okraje stránky na nulu. Tento krok je zásadní pro zachování integrity dimenzí SVG.

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

## Krok 4: Uložte dokument jako PDF

Konečně je čas uložit dokument SVG jako PDF. Název výstupního souboru a cestu můžete zadat následovně:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

A je to! Úspěšně jste převedli soubor SVG do PDF pomocí Aspose.PDF for .NET.

## Závěr

Gratuluji! Právě jste dokončili jednoduchý, ale výkonný úkol pomocí Aspose.PDF pro .NET. Podle tohoto průvodce jste se naučili, jak načíst dokument SVG, upravit jeho okraje a uložit jej jako PDF. Možnosti s Aspose.PDF jsou nekonečné a toto je jen špička ledovce. Ať už chcete vytvářet složité soubory PDF, manipulovat s těmi stávajícími nebo převádět mezi formáty, Aspose.PDF vám pomůže. Tak na co čekáš? Ponořte se hlouběji do[dokumentace](https://reference.aspose.com/pdf/net/) a prozkoumejte všechny funkce, které tato knihovna nabízí!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, upravovat a převádět dokumenty PDF programově.

### Jak nainstaluji Aspose.PDF?
 Aspose.PDF můžete nainstalovat přes NuGet Package Manager ve Visual Studiu nebo si jej stáhnout z[místo](https://releases.aspose.com/pdf/net/).

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí a[zkušební verze zdarma](https://releases.aspose.com/) abyste si knihovnu před zakoupením otestovali.

### Kde najdu podporu pro Aspose.PDF?
 Můžete získat podporu od[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Jak získám dočasnou licenci pro Aspose.PDF?
 Můžete požádat a[dočasná licence](https://purchase.aspose.com/temporary-license/) z webu Aspose.