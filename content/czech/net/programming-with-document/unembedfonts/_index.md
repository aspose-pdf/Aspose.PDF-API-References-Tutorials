---
title: Zrušte vložení písem a optimalizujte soubory PDF
linktitle: Zrušte vložení písem a optimalizujte soubory PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat Aspose.PDF pro .NET k získání Unembed Fonts a optimalizaci souborů PDF. Průvodce krok za krokem.
type: docs
weight: 370
url: /cs/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET je výkonná knihovna, která poskytuje širokou škálu funkcí pro práci s dokumenty PDF. Jednou z jeho funkcí je získání nevložených písem z dokumentu PDF. To může být užitečné, pokud potřebujete extrahovat písma z dokumentu PDF a použít je v jiných aplikacích.

poskytneme průvodce krok za krokem, který vysvětlí následující zdrojový kód C# funkce get unembed fonts Aspose.PDF for .NET.

## Krok 1: Nastavte cestu k adresáři dokumentů

Než začneme, musíme nastavit cestu k adresáři, kde se nachází náš PDF dokument. Tuto cestu uložíme do proměnné s názvem „dataDir“.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Nahraďte "VÁŠ ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

## Krok 2: Otevřete dokument PDF

 Prvním krokem je načíst dokument PDF, který chcete provést, použijte`Document` třídy Aspose.PDF pro .NET. Následující fragment kódu ukazuje, jak načíst dokument PDF:

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Krok 3: Nastavte možnost UnembedFonts

 Chcete-li získat nevložená písma z dokumentu PDF, musíte nastavit`UnembedFonts` možnost`true` . Tato možnost je dostupná v`OptimizationOptions` třída. Následující fragment kódu ukazuje, jak nastavit`UnembedFonts` volba:

```csharp
// Nastavte možnost UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## Krok 4: Optimalizujte dokument PDF

 Po nastavení`UnembedFonts` můžete optimalizovat dokument PDF pomocí`OptimizeResources` metoda`Document` třída. Následující fragment kódu ukazuje, jak optimalizovat dokument PDF:

```csharp
// Optimalizujte dokument PDF pomocí OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

## Krok 5: Uložte aktualizovaný dokument

 Jakmile je dokument PDF optimalizován, můžete aktualizovaný dokument uložit pomocí`Save` metoda`Document`třída. Následující fragment kódu ukazuje, jak uložit aktualizovaný dokument:

```csharp
// Uložit aktualizovaný dokument
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Krok 6: Získejte původní a zmenšenou velikost souboru

 Nakonec můžete získat původní a zmenšenou velikost souboru PDF dokumentu pomocí`FileInfo` třídy System.IO. Následující fragment kódu ukazuje, jak získat původní a zmenšenou velikost souboru:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Příklad zdrojového kódu pro Get Unembed Fonts pomocí Aspose.PDF for .NET

Zde je úplný ukázkový zdrojový kód pro získání nevložených písem z dokumentu PDF pomocí Aspose.PDF pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Nastavte možnost UnembedFonts
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
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
```

## Závěr

V tomto tutoriálu jsme si ukázali, jak používat Aspose.PDF pro .NET k získání nevložených písem z dokumentu PDF. Podle podrobného průvodce můžete tuto funkci snadno implementovat do svých aplikací C#. Zrušení vkládání písem může být výhodné, když potřebujete pracovat s extrahovanými písmy samostatně nebo zajistit konzistentní používání písem na různých platformách.

## FAQ

#### Otázka: Jaký je účel zrušení vkládání písem z dokumentu PDF?

Odpověď: Zrušení vložení písem z dokumentu PDF umožňuje extrahovat vložená písma a použít je v jiných aplikacích. To může být užitečné pro zajištění konzistentního vykreslování písem a zachování vizuálního vzhledu dokumentu.

#### Otázka: Jak mohu zadat cestu k adresáři dokumentů v kódu C#?

 A: Chcete-li zadat cestu k adresáři dokumentů, nahraďte`"YOUR DOCUMENT DIRECTORY"` v kódu se skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

####  Q: Co dělá`UnembedFonts` option do, and where is it set?

 A:`UnembedFonts` možnost, dostupná v`OptimizationOptions` třídy, povolí nebo zakáže zrušení vkládání písem z dokumentu PDF. Chcete-li tuto možnost nastavit na`true`, použijte následující kód:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Otázka: Mohu vrátit změny provedené během procesu optimalizace?

Odpověď: Aspose.PDF for .NET neprovádí trvalé změny původního dokumentu PDF během optimalizace. Proces optimalizace se provádí na kopii dokumentu, přičemž originál zůstává nedotčen.

#### Otázka: Jak mohu po optimalizaci zkontrolovat původní a zmenšenou velikost souboru?

A: Můžete použít`FileInfo` třída`System.IO` získat původní a zmenšenou velikost souboru. Zde je příklad fragmentu kódu, jak toho dosáhnout:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```