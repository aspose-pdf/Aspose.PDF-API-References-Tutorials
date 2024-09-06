---
title: Extrahovat text vše v souboru PDF
linktitle: Extrahovat text AllIn PDF souboru
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat veškerý text v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 180
url: /cs/net/programming-with-text/extract-text-all/
---
Tento tutoriál vás provede procesem extrahování veškerého textu v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

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

## Krok 5: Extrahujte veškerý text
 Vytvořte a`TextAbsorber`objekt pro extrahování textu z dokumentu. Poté přijměte absorbér pro všechny stránky.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Krok 6: Získejte extrahovaný text
 Přístup k extrahovanému textu z`TextAbsorber` objekt.

```csharp
string extractedText = textAbsorber.Text;
```

## Krok 7: Uložte extrahovaný text
 Vytvořte a`TextWriter` a otevřete soubor, kam chcete extrahovaný text uložit. Zapište extrahovaný text do souboru a zavřete stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Ukázkový zdrojový kód pro Extrahovat text vše pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Vytvořte objekt TextAbsorber pro extrahování textu
TextAbsorber textAbsorber = new TextAbsorber();
// Přijměte absorbér pro všechny stránky
pdfDocument.Pages.Accept(textAbsorber);
// Získejte extrahovaný text
string extractedText = textAbsorber.Text;
// Vytvořte zapisovač a otevřete soubor
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Napište do souboru řádek textu
tw.WriteLine(extractedText);
// Zavřete stream
tw.Close();
```

## Závěr
Úspěšně jste extrahovali veškerý text z dokumentu PDF pomocí Aspose.PDF pro .NET. Extrahovaný text byl uložen do zadaného výstupního souboru.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál slouží jako průvodce, který vám pomůže extrahovat veškerý text ze souboru PDF pomocí Aspose.PDF pro .NET. Doprovodný zdrojový kód C# poskytuje podrobné pokyny pro dosažení tohoto úkolu.

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

#### Otázka: Jak extrahuji veškerý text z dokumentu?

 Odpověď: Krok 5 zahrnuje vytvoření a`TextAbsorber` objekt pro extrahování textu z dokumentu PDF. Poté přijmete absorbér pro všechny stránky.

#### Otázka: Jak se dostanu k extrahovanému textu?

 Odpověď: Krok 6 vás provede přístupem k extrahovanému textu z`TextAbsorber` objekt.

#### Otázka: Jak uložím extrahovaný text do souboru?

 Odpověď: V kroku 7 vytvoříte a`TextWriter`, otevřete soubor, do kterého chcete uložit extrahovaný text, zapište extrahovaný text do souboru a poté stream zavřete.

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Podle tohoto návodu jste se naučili, jak extrahovat veškerý text z dokumentu PDF pomocí Aspose.PDF for .NET. Extrahovaný text byl uložen do určeného výstupního souboru, což vám umožňuje analyzovat a manipulovat s textovým obsahem dokumentu.