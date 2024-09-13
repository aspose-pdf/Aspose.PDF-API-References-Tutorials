---
title: Zrušte vložení písem a optimalizujte soubory PDF
linktitle: Zrušte vložení písem a optimalizujte soubory PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném návodu se dozvíte, jak zrušit vložení písem a optimalizovat soubory PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 370
url: /cs/net/programming-with-document/unembedfonts/
---
## Zavedení

digitálním věku jsou soubory PDF všudypřítomné. Ať už sdílíte zprávy, prezentace nebo elektronické knihy, formát Portable Document Format (PDF) je tou správnou volbou pro zachování integrity vašich dokumentů. Jak však vytváříme a sdílíme více souborů PDF, velikost souborů se může zvětšovat, takže odesílání nebo ukládání je těžkopádné. Zde vstupuje do hry Aspose.PDF for .NET, který nabízí výkonné nástroje pro optimalizaci vašich souborů PDF. V tomto tutoriálu se ponoříme do toho, jak zrušit vložení písem a optimalizovat soubory PDF pomocí Aspose.PDF pro .NET.

## Předpoklady

Než se vrhneme na to, abychom mohli začít, ujistěte se, že máte vše, co potřebujete:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Je to IDE, které budeme používat k psaní a spouštění našeho .NET kódu.
2.  Aspose.PDF for .NET: Budete si muset stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete to vzít z[odkaz ke stažení](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže porozumět úryvkům kódu, které budeme používat.
4.  Soubor PDF: Připravte si soubor PDF, který chcete optimalizovat. Můžete použít jakýkoli soubor PDF, ale pro demonstraci jej budeme označovat jako`OptimizeDocument.pdf`.

## Importujte balíčky

Chcete-li začít, musíte do svého projektu C# importovat potřebné balíčky. Můžete to udělat takto:

1. Otevřete projekt v sadě Visual Studio.
2. Přidejte odkaz na Aspose.PDF: Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení, vyberte „Spravovat balíčky NuGet“ a vyhledejte`Aspose.PDF`. Nainstalujte balíček.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní, když máme vše nastaveno, rozdělíme proces optimalizace do zvládnutelných kroků.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte definovat cestu k adresáři dokumentů. Zde budou uloženy vaše soubory PDF. Jak na to:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš soubor PDF. To je zásadní, protože program potřebuje vědět, kde najde PDF, které chcete optimalizovat.

## Krok 2: Otevřete dokument PDF

Nyní, když máme nastavený adresář, je čas otevřít dokument PDF, který chceme optimalizovat. Zde je kód, jak to udělat:

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

 Tento řádek kódu vytvoří nový`Document` objekt, který představuje váš soubor PDF. Ujistěte se, že název souboru odpovídá názvu, který máte v adresáři.

## Krok 3: Nastavte možnosti optimalizace

Dále musíme specifikovat možnosti optimalizace. V tomto případě chceme zrušit vložení písem. Zde je návod, jak to nastavit:

```csharp
// Nastavte možnost UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

 Nastavením`UnembedFonts` na`true`, dáváme Aspose.PDF pokyn k optimalizaci PDF zrušením vkládání písem. To může výrazně snížit velikost souboru, zejména pokud PDF obsahuje mnoho vložených písem.

## Krok 4: Optimalizujte dokument PDF

S našimi nastavenými možnostmi je čas na optimalizaci dokumentu PDF. Zde je kód, jak to udělat:

```csharp
Console.WriteLine("Start");
// Optimalizujte dokument PDF pomocí OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Tento fragment kódu volá`OptimizeResources` metoda na`pdfDocument` objekt s použitím možností optimalizace, které jsme definovali dříve. V konzole se zobrazí zpráva oznamující, že proces optimalizace byl zahájen.

## Krok 5: Uložte aktualizovaný dokument

Po optimalizaci PDF musíme aktualizovaný dokument uložit. Jak na to:

```csharp
// Uložit aktualizovaný dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

 Tento kód uloží optimalizované PDF jako`OptimizeDocument_out.pdf` ve stejném adresáři. Pokud chcete, můžete zvolit jiný název, ale jeho zachování pomáhá při identifikaci původní a optimalizované verze.

## Krok 6: Porovnejte velikosti souborů

Nakonec je vždy dobré zkontrolovat, kolik místa jste ušetřili. Zde je návod, jak porovnat původní a optimalizované velikosti souborů:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Tento kód načte velikosti souborů původních i optimalizovaných PDF a vytiskne je do konzoly. Je to uspokojující okamžik vidět, jak moc jste zmenšili velikost souboru!

## Závěr

tady to máte! Úspěšně jste odstranili vložená písma a optimalizovali soubor PDF pomocí Aspose.PDF pro .NET. Tento proces nejen pomáhá zmenšit velikost souborů, ale také zvyšuje výkon vašich dokumentů PDF. Ať už sdílíte soubory e-mailem nebo je ukládáte do cloudu, menší velikost souboru může znamenat velký rozdíl.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, manipulovat a optimalizovat dokumenty PDF programově.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi. Můžete si jej stáhnout z[zde](https://releases.aspose.com/).

### Jak získám podporu pro Aspose.PDF?
 Podporu můžete získat prostřednictvím[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Jaké typy optimalizací mohu provádět na souborech PDF?
Můžete zrušit vložení písem, komprimovat obrázky, odstranit nepoužívané objekty a další pro optimalizaci souborů PDF.

### Kde si mohu koupit Aspose.PDF pro .NET?
 Licenci si můžete zakoupit od[Aspose nákupní stránku](https://purchase.aspose.com/buy).