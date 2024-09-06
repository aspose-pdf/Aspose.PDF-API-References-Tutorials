---
title: Extrahujte textovou stránku v souboru PDF
linktitle: Extrahujte textovou stránku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat text z konkrétní stránky v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 200
url: /cs/net/programming-with-text/extract-text-page/
---
Tento tutoriál vás provede procesem extrahování textu z konkrétní stránky v souboru PDF pomocí Aspose.PDF for .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

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
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 5: Extrahujte text z konkrétní stránky
 Vytvořte a`TextAbsorber` objekt pro extrahování textu z dokumentu. Přijměte absorbér pro požadovanou stránku tím, že k ní přistoupíte přes`Pages` sbírka`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## Krok 6: Získejte extrahovaný text
 Přístup k extrahovanému textu z`TextAbsorber` objekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Krok 7: Uložte extrahovaný text
 Vytvořte a`TextWriter` a otevřete soubor, kam chcete extrahovaný text uložit. Zapište extrahovaný text do souboru a zavřete stream.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Ukázkový zdrojový kód pro extrahovat textovou stránku pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Vytvořte objekt TextAbsorber pro extrahování textu
TextAbsorber textAbsorber = new TextAbsorber();
//Přijměte absorbér pro konkrétní stránku
pdfDocument.Pages[1].Accept(textAbsorber);
// Získejte extrahovaný text
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Vytvořte zapisovač a otevřete soubor
TextWriter tw = new StreamWriter(dataDir);
// Napište do souboru řádek textu
tw.WriteLine(extractedText);
// Zavřete stream
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Závěr
Úspěšně jste extrahovali text z konkrétní stránky dokumentu PDF pomocí Aspose.PDF for .NET. Extrahovaný text byl uložen do zadaného výstupního souboru.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem extrahování textu z konkrétní stránky v souboru PDF pomocí Aspose.PDF pro .NET. Doprovodný zdrojový kód C# demonstruje požadované kroky k dosažení tohoto úkolu.

#### Otázka: Jaké jmenné prostory mám importovat?

Odpověď: Do souboru kódu, do kterého plánujete extrahovat text, zahrňte na začátek souboru následující pomocí direktiv:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak otevřu existující dokument PDF?

 Odpověď: V kroku 4 otevřete existující dokument PDF pomocí`Document` konstruktoru a poskytnutí cesty ke vstupnímu souboru PDF.

#### Otázka: Jak extrahuji text z konkrétní stránky?

 Odpověď: Krok 5 zahrnuje vytvoření a`TextAbsorber` objekt pro extrahování textu z dokumentu PDF. Poté přijmete absorbér pro požadovanou stránku tím, že k ní přistoupíte prostřednictvím`Pages` sbírka`pdfDocument`.

#### Otázka: Jak se dostanu k extrahovanému textu?

 Odpověď: Krok 6 vás provede přístupem k extrahovanému textu z`TextAbsorber` objekt.

#### Otázka: Jak uložím extrahovaný text do souboru?

 Odpověď: V kroku 7 vytvoříte a`TextWriter`, otevřete soubor, do kterého chcete uložit extrahovaný text, zapište extrahovaný text do souboru a poté stream zavřete.

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Podle tohoto návodu jste se naučili, jak extrahovat text z konkrétní stránky dokumentu PDF pomocí Aspose.PDF for .NET. Extrahovaný text byl uložen do určeného výstupního souboru, což vám umožňuje cílit a analyzovat textový obsah z konkrétních stránek.