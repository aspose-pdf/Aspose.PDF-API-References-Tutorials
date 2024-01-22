---
title: Povolit opětovné použití obsahu stránky
linktitle: Povolit opětovné použití obsahu stránky
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se optimalizovat soubory PDF povolením funkce „Povolit opětovné použití obsahu stránky“ pomocí Aspose.PDF for .NET. Snižte velikost souboru a zvyšte výkon.
type: docs
weight: 50
url: /cs/net/programming-with-document/allowresusepagecontent/
---
tomto tutoriálu vysvětlíme, jak povolit funkci "Povolit opětovné použití obsahu stránky" pomocí Aspose.PDF pro .NET. Tato funkce optimalizuje dokument PDF opětovným použitím obsahu stránky, zmenšením velikosti souboru a zlepšením výkonu. Postupujte podle níže uvedeného podrobného průvodce:

## Krok 1: Načtěte dokument PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 2: Nastavte možnost AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Krok 3: Optimalizujte dokument PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 4: Uložte aktualizovaný dokument

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Krok 5: Zkontrolujte zmenšení velikosti souboru

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Gratulujeme! Úspěšně jste povolili opětovné použití obsahu stránky v dokumentu PDF.

### Příklad zdrojového kódu pro povolení opětovného použití obsahu stránky pomocí Aspose.PDF pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Nastavte možnost AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Optimalizujte dokument PDF pomocí OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Uložit aktualizovaný dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Nyní můžete efektivně optimalizovat své dokumenty PDF tím, že umožníte opětovné použití obsahu stránky.

## Závěr

tomto tutoriálu jsme vysvětlili, jak povolit funkci "Povolit opětovné použití obsahu stránky" pomocí Aspose.PDF pro .NET. Dodržováním poskytnutého podrobného průvodce a používáním zdrojového kódu C# můžete efektivně optimalizovat své dokumenty PDF tím, že umožníte opětovné použití obsahu stránky. Výsledkem této optimalizace jsou menší soubory PDF, což může vést k rychlejšímu načítání a lepšímu výkonu při práci s velkými dokumenty PDF. Aspose.PDF for .NET poskytuje robustní a uživatelsky přívětivé řešení pro optimalizaci PDF, které vám umožňuje snadno vytvářet efektivní a vysoce kvalitní soubory PDF.

### FAQ

#### Otázka: Jaký je účel povolení funkce „Povolit opětovné použití obsahu stránky“ v dokumentu PDF?

Odpověď: Povolení funkce "Povolit opětovné použití obsahu stránky" v dokumentu PDF optimalizuje soubor opětovným použitím obsahu stránky, což zmenší velikost souboru a zlepší celkový výkon. Výsledkem této optimalizace jsou menší soubory PDF bez kompromisů v kvalitě obsahu.

#### Otázka: Jak funguje funkce „Povolit opětovné použití obsahu stránky“?

Odpověď: Když je povolena funkce "Povolit opětovné použití obsahu stránky", identické objekty stránky v dokumentu PDF jsou sdíleny a znovu použity, místo aby byly duplikovány pro každý výskyt. Toto sdílení obsahu stránky výrazně snižuje celkovou velikost souboru.

#### Otázka: Mohu vrátit optimalizaci a obnovit původní dokument?

Odpověď: Ne, jakmile je provedena optimalizace pomocí „Povolit opětovné použití obsahu stránky“ a dokument PDF je uložen, změny jsou trvalé. Před provedením jakékoli optimalizace je vhodné ponechat si zálohu původního dokumentu.

#### Otázka: Ovlivní povolení této funkce vizuální vzhled nebo obsah dokumentu PDF?

Odpověď: Povolení funkce "Povolit opětovné použití obsahu stránky" neovlivní vizuální vzhled ani obsah dokumentu PDF. Optimalizuje pouze vnitřní strukturu souboru, aby se snížila redundance a zvýšila účinnost.

#### Otázka: Je Aspose.PDF for .NET spolehlivým řešením pro optimalizaci a manipulaci s PDF?

Odpověď: Ano, Aspose.PDF for .NET je spolehlivá knihovna s bohatými funkcemi pro optimalizaci a manipulaci s PDF. Nabízí rozsáhlé možnosti optimalizace souborů PDF, včetně zmenšení velikosti souboru, odstranění nepoužívaných zdrojů a zvýšení celkového výkonu.