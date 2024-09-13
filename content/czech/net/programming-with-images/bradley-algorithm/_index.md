---
title: Bradleyho algoritmus
linktitle: Bradleyho algoritmus
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak převést PDF na TIFF pomocí Bradleyho algoritmu v Aspose.PDF pro .NET. Podrobný průvodce, předpoklady a často kladené otázky pro bezproblémový převod.
type: docs
weight: 30
url: /cs/net/programming-with-images/bradley-algorithm/
---
## Zavedení

Práce se soubory PDF může někdy vyžadovat více než jen jejich čtení nebo úpravy – možná je budete muset převést na obrázky. Jedním z účinných způsobů, jak převést soubory PDF na obrázky TIFF, je použití Bradleyho algoritmu prostřednictvím knihovny Aspose.PDF for .NET. Tato metoda zajišťuje vysoce kvalitní binární obrazy, ideální pro archivaci dokumentů a další specializované případy použití.

Tento tutoriál vás provede podrobným a snadno pochopitelným procesem převodu stránky PDF na obrázek TIFF pomocí algoritmu Bradley Binarization Algorithm. Aspose.PDF for .NET tento úkol zjednodušuje a poskytuje vám možnost automatizovat a zefektivnit vaše pracovní postupy s dokumenty.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte vše, co potřebujete k dodržení:

-  Aspose.PDF pro .NET: Budete potřebovat knihovnu. Stáhněte si jej z[zde](https://releases.aspose.com/pdf/net/).
- Visual Studio (nebo jakékoli C# IDE).
- Základní znalost C#.
-  Platná licence nebo a[dočasná licence](https://purchase.aspose.com/temporary-license/) od Aspose.

## Importujte balíčky

Nejprve se ujistěte, že jste do projektu importovali potřebné jmenné prostory. Tyto knihovny vám poskytnou nástroje pro manipulaci s dokumenty PDF, jejich převod do formátu TIFF a aplikaci Bradleyho binarizačního algoritmu.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Pojďme si tento proces rozdělit do jednoduchých kroků, abyste zajistili, že budete moci plynule pokračovat. Na konci této příručky úspěšně převedete stránku PDF na binární obrázek TIFF pomocí Bradleyho algoritmu.

## Krok 1: Nastavte adresář dokumentů

Prvním krokem je zadat cestu k adresáři, kde se nachází váš dokument PDF. Také definujete výstupní cesty pro obrázky TIFF, které budou generovány.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Cesta k vašemu souboru PDF
```

Zde ukládáte zdrojové soubory PDF i převedené soubory TIFF. Ujistěte se, že je adresář správně nastaven, aby kód mohl číst a zapisovat soubory bez chyb.

## Krok 2: Otevřete dokument PDF

Nyní, když je cesta nastavena, je čas otevřít dokument PDF, který chcete převést. Aspose.PDF pro .NET usnadňuje načtení dokumentu pro další zpracování.

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

 Zde,`PageToTIFF.pdf` je ukázkový soubor. Můžete jej nahradit libovolným souborem PDF podle vašeho výběru. Objekt dokumentu nyní uchovává PDF pro další manipulaci.

## Krok 3: Definujte výstupní cesty pro obrázky

Dále určíte výstupní cesty pro vygenerované soubory TIFF, včetně standardního TIFF i binarizované verze.

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

Oddělením těchto cest získáte po použití Bradleyho algoritmu jeden soubor pro standardní převod TIFF a další pro binarizovaný obrázek.

## Krok 4: Vytvořte objekt rozlišení

Při převodu PDF na TIFF hraje rozlišení významnou roli při určování kvality obrazu. Pro naše účely jej nastavíme na 300 DPI, abychom zajistili vysoce kvalitní výstup.

```csharp
Resolution resolution = new Resolution(300);
```

Vyšší DPI znamená lepší čistotu obrazu, zejména při práci s dokumenty, které se budou tisknout nebo archivovat.

## Krok 5: Nakonfigurujte nastavení TIFF

Dále budete muset nakonfigurovat nastavení pro obrázek TIFF. Zde použijeme kompresi LZW a nastavíme barevnou hloubku na 1bpp (1bit na pixel), abychom dosáhli binárního obrazu.

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

Nastavením hloubky na 1bpp připravíme obraz pro binární výstup. Komprese LZW je zvolena pro svou účinnost při snižování velikosti souboru bez ztráty kvality.

## Krok 6: Vytvořte zařízení TIFF

Nyní budete muset vytvořit zařízení TIFF, které převod zvládne. Toto zařízení používá rozlišení a nastavení TIFF definované dříve.

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

Jádrem této operace je zařízení TIFF. Vezme dokument PDF a převede každou stránku na obrázek TIFF na základě vašeho předdefinovaného nastavení.

## Krok 7: Převeďte stránku PDF na TIFF

 Je čas zpracovat PDF a převést první stránku na obrázek TIFF. The`Process` umožňuje převést konkrétní stránky nebo celý dokument. V tomto příkladu převádíme první stránku.

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

Jakmile bude metoda dokončena, budete mít obrázek TIFF uložený na místě definovaném dříve.

## Krok 8: Použijte Bradleyův binarizační algoritmus

Nyní přichází kouzlo – Bradleyho algoritmus! Tento algoritmus převádí obrázek TIFF ve stupních šedi na binární obrázek a optimalizuje jej pro systémy rozpoznávání dokumentů.

```csharp
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
    using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
    {
        tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
    }
}
```

 Metoda BinarizeBradley bere dva proudy souborů (vstup a výstup) a také prahovou hodnotu (zde,`0.1`), který určuje úroveň binarizace. Po spuštění budete mít dokonale binarizovaný obrázek připravený k použití.

## Krok 9: Potvrďte úspěšnou konverzi

Nakonec je dobrým zvykem informovat uživatele, že proces byl úspěšný. Můžete to udělat pomocí jednoduchého výstupu konzoly.

```csharp
System.Console.WriteLine("Conversion using Bradley algorithm performed successfully!");
```

Jakmile se to vytiskne, víte, že vaše stránka PDF byla úspěšně převedena na binární obrázek TIFF!

## Závěr

Tady to máš! Právě jste se naučili, jak převést stránku PDF na obrázek TIFF a použít Bradleyův binarizační algoritmus pomocí Aspose.PDF for .NET. Tento proces je nezbytný pro archivaci dokumentů, optické rozpoznávání znaků (OCR) a další profesionální aplikace. S vysoce kvalitním rozlišením a efektivní kompresí můžete zajistit, že obrázky dokumentů budou jasné a jejich velikost se dá spravovat.

## FAQ

### Co je to Bradleyho algoritmus?
Bradleyho algoritmus je binarizační technika, která převádí obrázky ve stupních šedi na binární (černé a bílé) obrázky určením adaptivního prahu pro každý pixel na základě jeho okolí.

### Mohu pomocí této metody převést více stránek PDF na TIFF?
 Ano, můžete upravit`Process` metoda pro převod všech stránek procházením stránek v dokumentu.

### Jaké je optimální rozlišení pro převod PDF na TIFF?
Pro vysoce kvalitní obrázky se obecně doporučuje 300 DPI. Tuto hodnotu však můžete upravit podle svých potřeb.

### Co znamená 1bpp v barevné hloubce?
1bpp (1 bit na pixel) znamená, že obrázek bude černobílý, přičemž každý pixel bude buď zcela černý, nebo zcela bílý.

### Je Bradleyův algoritmus vhodný pro OCR?
Ano, Bradleyův algoritmus se často používá při předběžném zpracování OCR, protože zvyšuje kontrast textu v naskenovaných dokumentech.