---
title: SVG do PDF
linktitle: SVG do PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném návodu se dozvíte, jak převést SVG do PDF pomocí Aspose.PDF for .NET. Ideální pro vývojáře a designéry.
type: docs
weight: 280
url: /cs/net/document-conversion/svg-to-pdf/
---
## Zavedení

dnešním digitálním světě je potřeba převádět soubory z jednoho formátu do druhého běžnější než kdy jindy. Ať už jste vývojář, designér nebo prostě někdo, kdo často pracuje s dokumenty, vědět, jak převést soubory SVG (Scalable Vector Graphics) do PDF (Portable Document Format), může být neuvěřitelně užitečné. Soubory SVG jsou skvělé pro svou škálovatelnost a kvalitu, ale někdy potřebujete PDF pro sdílení, tisk nebo archivaci. V tomto tutoriálu vás provedeme procesem převodu SVG do PDF pomocí Aspose.PDF pro .NET. Takže si vezměte svůj oblíbený nápoj a pojďme se ponořit!

## Předpoklady

Než začneme, je potřeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Zde budete psát a spouštět svůj kód .NET.
2.  Aspose.PDF pro .NET: Musíte mít knihovnu Aspose.PDF. Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Základní znalost programování v C# vám pomůže postupovat podle příkladů.
4. Soubor SVG: Připravte si soubor SVG ke konverzi. Můžete si jej vytvořit nebo si stáhnout ukázkový soubor SVG z internetu.

## Importujte balíčky

Chcete-li začít s Aspose.PDF, budete muset do svého projektu importovat potřebné balíčky. Můžete to udělat takto:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```
Nyní, když máte vše nastaveno, pojďme si proces převodu rozebrat krok za krokem.

## Krok 1: Nastavte adresář dokumentů

Než budete moci převést soubor SVG, musíte určit, kde jsou vaše dokumenty uloženy. To je zásadní, protože kód bude hledat soubor SVG v tomto adresáři.

Ve svém kódu definujete řetězcovou proměnnou, která ukazuje na adresář, kde se nachází váš soubor SVG. To usnadňuje správu souborů a zajišťuje, že program ví, kde má najít soubor SVG.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou ke složce dokumentů.

## Krok 2: Vytvořte instanci objektu LoadOption

 Dále musíte vytvořit instanci souboru`LoadOptions` třídy speciálně pro soubory SVG. To říká Aspose.PDF, jak zacházet se souborem SVG během procesu převodu.

 The`SvgLoadOptions` třída je navržena pro načítání souborů SVG. Vytvořením instance této třídy zajistíte, že knihovna ví, že pracujete se souborem SVG.

```csharp
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();
```

## Krok 3: Vytvořte objekt dokumentu

 Nyní je čas vytvořit a`Document`objekt. Tento objekt bude v kódu představovat váš soubor SVG.

 The`Document` třída je jádrem knihovny Aspose.PDF. Předáním cesty k vašemu souboru SVG a možností načtení, které jste právě vytvořili, říkáte knihovně, aby načetla váš soubor SVG do paměti.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Nezapomeňte vyměnit`"SVGToPDF.svg"` s názvem vašeho skutečného souboru SVG.

## Krok 4: Uložte výsledný dokument PDF

Nakonec uložíte převedený dokument PDF. Toto je poslední krok v procesu konverze.

 The`Save` metoda`Document` třída umožňuje zadat název výstupního souboru a formát. V tomto případě jej uložíte jako PDF.

```csharp
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

 Opět vyměňte`"SVGToPDF_out.pdf"` s požadovaným názvem výstupního souboru.

## Závěr

A tady to máte! Úspěšně jste převedli soubor SVG do PDF pomocí Aspose.PDF for .NET. Tento proces je nejen přímočarý, ale také neuvěřitelně efektivní a umožňuje vám snadno pracovat se soubory SVG. Ať už pracujete na projektu, který vyžaduje časté konverze, nebo jen potřebujete převést jeden soubor, Aspose.PDF vám pomůže.

## FAQ

### Co je SVG?
SVG je zkratka pro Scalable Vector Graphics, formát pro vektorové obrázky, které lze škálovat bez ztráty kvality.

### Proč převádět SVG do PDF?
PDF je široce používaný formát pro sdílení a tisk dokumentů, díky čemuž je přístupnější pro uživatele, kteří nemusí mít software kompatibilní s SVG.

### Mohu převést více souborů SVG najednou?
Ano, můžete procházet adresář souborů SVG a každý z nich převést do PDF pomocí podobného kódu.

### Je Aspose.PDF zdarma?
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro plné funkce si budete muset zakoupit licenci. Více informací naleznete[zde](https://purchase.aspose.com/buy).

### Kde najdu podporu pro Aspose.PDF?
 Na jejich stránkách můžete získat podporu od komunity Aspose[fórum podpory](https://forum.aspose.com/c/pdf/10).