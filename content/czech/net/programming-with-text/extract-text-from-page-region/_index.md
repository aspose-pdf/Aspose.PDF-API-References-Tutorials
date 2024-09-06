---
title: Extrahujte text z oblasti stránky v souboru PDF
linktitle: Extrahujte text z oblasti stránky v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat text z konkrétní oblasti na stránce v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 190
url: /cs/net/programming-with-text/extract-text-from-page-region/
---
Tento tutoriál vás provede procesem extrahování textu z konkrétní oblasti na stránce v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete extrahovat text, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Otevřete dokument PDF
 Otevřete existující dokument PDF pomocí`Document` konstruktoru a předání cesty ke vstupnímu souboru PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Krok 5: Extrahujte text z oblasti stránky
 Vytvořte a`TextAbsorber` objekt pro extrahování textu z dokumentu. Nakonfigurujte`TextSearchOptions` pro omezení hledání na konkrétní oblast stránky definovanou obdélníkem.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## Krok 6: Získejte extrahovaný text
 Přístup k extrahovanému textu z`TextAbsorber` objekt.

```csharp
string extractedText = absorb.Text;
```

## Krok 7: Uložte extrahovaný text
 Vytvořte a`TextWriter` a otevřete soubor, kam chcete extrahovaný text uložit. Zapište extrahovaný text do souboru a zavřete stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Ukázka zdrojového kódu pro extrahování textu z oblasti stránky pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Vytvořte objekt TextAbsorber pro extrahování textu
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// Přijměte absorbér pro první stránku
pdfDocument.Pages[1].Accept(absorber);
// Získejte extrahovaný text
string extractedText = absorber.Text;
// Vytvořte zapisovač a otevřete soubor
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Napište do souboru řádek textu
tw.WriteLine(extractedText);
// Zavřete stream
tw.Close();
```

## Závěr
Úspěšně jste extrahovali text z určité oblasti na stránce dokumentu PDF pomocí Aspose.PDF pro .NET. Extrahovaný text byl uložen do zadaného výstupního souboru.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem extrahování textu z konkrétní oblasti na stránce do souboru PDF pomocí Aspose.PDF for .NET. Doprovodný zdrojový kód C# poskytuje podrobné pokyny pro provedení tohoto úkolu.

#### Otázka: Jaké jmenné prostory mám importovat?

Odpověď: Do souboru s kódem, ze kterého chcete extrahovat text, zahrňte na začátek souboru následující pomocí direktiv:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Otázka: Jak určím adresář dokumentů?

 A: Najděte linku`string dataDir = "YOUR DOCUMENT DIRECTORY";` v kódu a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak otevřu existující dokument PDF?

 Odpověď: V kroku 4 otevřete existující dokument PDF pomocí`Document` konstruktoru a poskytnutí cesty ke vstupnímu souboru PDF.

#### Otázka: Jak extrahuji text z určité oblasti stránky?

 Odpověď: Krok 5 zahrnuje vytvoření a`TextAbsorber`objekt pro extrahování textu z dokumentu PDF. Poté nakonfigurujete`TextSearchOptions` k definování konkrétní obdélníkové oblasti na stránce pomocí souřadnic.

#### Otázka: Jak se dostanu k extrahovanému textu?

 Odpověď: Krok 6 vás provede přístupem k extrahovanému textu z`TextAbsorber` objekt.

#### Otázka: Jak uložím extrahovaný text do souboru?

 Odpověď: V kroku 7 vytvoříte a`TextWriter`, otevřete soubor, do kterého chcete uložit extrahovaný text, zapište extrahovaný text do souboru a poté stream zavřete.

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se naučili, jak extrahovat text z určité oblasti na stránce dokumentu PDF pomocí Aspose.PDF for .NET. Extrahovaný text byl uložen do určeného výstupního souboru, což vám umožňuje přesně zacílit a analyzovat požadovaný textový obsah.