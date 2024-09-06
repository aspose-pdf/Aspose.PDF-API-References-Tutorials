---
title: PDF do XPS
linktitle: PDF do XPS
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak převést PDF na XPS pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce. Ideální pro vývojáře a nadšence pro zpracování dokumentů.
type: docs
weight: 220
url: /cs/net/document-conversion/pdf-to-xps/
---
## Zavedení

V dnešním digitálním světě je potřeba převádět dokumenty z jednoho formátu do druhého běžnější než kdy jindy. Ať už jste vývojář, který chce integrovat zpracování dokumentů do své aplikace, nebo obchodní profesionál, který potřebuje sdílet soubory v univerzálně přijímaném formátu, pochopení toho, jak převést soubory PDF do XPS (XML Paper Specification), může být neuvěřitelně užitečné. V tomto tutoriálu se ponoříme do procesu převodu PDF do XPS pomocí výkonné knihovny Aspose.PDF pro .NET.

## Předpoklady

Než začneme, je třeba splnit několik předpokladů:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Zde budete psát a spouštět svůj kód .NET.
2. .NET Framework: Znalost .NET frameworku je nezbytná, protože pro naše příklady budeme používat C#.
3.  Knihovna Aspose.PDF: Musíte mít nainstalovanou knihovnu Aspose.PDF. Můžete si jej stáhnout z[Aspose PDF for .NET releases page](https://releases.aspose.com/pdf/net/).
4. Základní znalosti C#: Základní znalost programování v C# vám pomůže postupovat podle příkladů.

## Importujte balíčky

Chcete-li začít s Aspose.PDF, musíte do projektu importovat potřebné balíčky. Můžete to udělat takto:

1. Otevřete Visual Studio: Spusťte Visual Studio a vytvořte nový projekt.
2. Přidat odkaz: Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení, vyberte "Spravovat balíčky NuGet" a vyhledejte "Aspose.PDF." Nainstalujte balíček do svého projektu.
3. Použití direktiv: V horní části souboru C# zahrňte následující direktivu using:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
```

Nyní, když máme vše nastaveno, rozdělíme proces převodu do zvládnutelných kroků.

## Krok 1: Nastavte adresář dokumentů

Než budete moci převést PDF na XPS, musíte určit adresář, kde je umístěn váš soubor PDF. To je zásadní, protože program potřebuje vědět, kde najde vstupní soubor.

V tomto kroku definujete řetězcovou proměnnou, která obsahuje cestu k adresáři dokumentů. Tato cesta by měla ukazovat na umístění vašeho souboru PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou na vašem počítači, kde je soubor PDF uložen.

## Krok 2: Načtěte dokument PDF

Nyní, když máte nastavený adresář dokumentů, je dalším krokem načtení dokumentu PDF, který chcete převést.

 Vytvoříte instanci souboru`Document` třídy z knihovny Aspose.PDF a předejte cestu k vašemu PDF souboru jeho konstruktoru. Tím se načte dokument PDF do paměti.

```csharp
// Načíst dokument PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Nezapomeňte vyměnit`"input.pdf"` s názvem vašeho skutečného souboru PDF.

## Krok 3: Vytvořte možnosti uložení XPS

 Před uložením dokumentu ve formátu XPS musíte vytvořit instanci souboru`XpsSaveOptions` třída. Tato třída umožňuje zadat různé možnosti pro uložení dokumentu.

 Vytvořením instance`XpsSaveOptions`můžete přizpůsobit, jak se PDF převádí na XPS. Pro tento základní převod můžete použít výchozí nastavení.

```csharp
// Okamžité možnosti ukládání XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Krok 4: Uložte dokument jako XPS

Konečně je čas uložit načtený dokument PDF jako soubor XPS. Tady se děje kouzlo!

 Zavoláte na`Save` metoda na`pdfDocument` objekt, předáním požadovaného názvu výstupního souboru a`saveOptions` jste vytvořili dříve.

```csharp
// Uložte dokument XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Tento řádek kódu vytvoří soubor XPS s názvem`PDFToXPS_out.xps` ve vašem projektovém adresáři.

## Závěr

Gratuluji! Úspěšně jste převedli dokument PDF do formátu XPS pomocí Aspose.PDF for .NET. Tato jednoduchá, ale výkonná knihovna vám umožňuje snadno zvládnout různé úlohy zpracování dokumentů. Ať už převádíte soubory pro lepší kompatibilitu nebo jednoduše archivujete dokumenty v jiném formátu, Aspose.PDF vám pomůže.

## FAQ

### Co je formát XPS?
XPS (XML Paper Specification) je formát dokumentu vyvinutý společností Microsoft, který zachovává rozložení a vzhled dokumentů.

### Mohu převést více souborů PDF do XPS najednou?
Ano, můžete procházet více soubory PDF v adresáři a každý z nich převést na XPS pomocí stejné metody.

### Je Aspose.PDF zdarma k použití?
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro plnou funkčnost si budete muset zakoupit licenci. Více podrobností najdete na[koupit stránku](https://purchase.aspose.com/buy).

### Co když během převodu narazím na problémy?
 Na jejich stránkách můžete vyhledat pomoc od komunity Aspose[fórum podpory](https://forum.aspose.com/c/pdf/10).

### Mohu získat dočasnou licenci pro Aspose.PDF?
 Ano, můžete požádat o dočasnou licenci pro účely vyzkoušení od[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).