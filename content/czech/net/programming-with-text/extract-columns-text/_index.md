---
title: Extrahujte text sloupců v souboru PDF
linktitle: Extrahujte text sloupců v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat text sloupců v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 150
url: /cs/net/programming-with-text/extract-columns-text/
---
Tento tutoriál vás provede procesem extrahování textu sloupců v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete extrahovat text sloupců, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Otevřete dokument PDF
 Otevřete existující dokument PDF pomocí`Document` konstruktoru a předání cesty ke vstupnímu souboru PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## Krok 5: Upravte velikost písma
Zmenšete velikost písma fragmentů textu faktorem 0,7, abyste zlepšili čitelnost a lépe reprezentovali sloupcový text.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## Krok 6: Extrahujte text ze sloupců
 Uložte upravený dokument PDF do paměťového proudu a znovu jej načtěte jako nový dokument. Poté použijte`TextAbsorber` třídy extrahovat text ze sloupců.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## Krok 7: Uložte extrahovaný text
Uložte extrahovaný text do textového souboru v zadané cestě k výstupnímu souboru.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### Ukázkový zdrojový kód pro extrahování textu sloupců pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// Potřebujete zmenšit velikost písma alespoň o 70 %
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Závěr
Úspěšně jste extrahovali text sloupců z dokumentu PDF pomocí Aspose.PDF pro .NET. Extrahovaný text byl uložen do zadaného výstupního souboru.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál nabízí podrobného průvodce extrahováním sloupců textu ze souboru PDF pomocí Aspose.PDF pro .NET. Doprovodný zdrojový kód C# poskytuje praktickou ukázku požadovaných postupů.

#### Otázka: Jaké jmenné prostory mám importovat?

Odpověď: Do souboru s kódem, do kterého hodláte extrahovat sloupce textu, zahrňte následující pomocí direktiv na začátek souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Otázka: Jak určím adresář dokumentů?

 A: Najděte linku`string dataDir = "YOUR DOCUMENT DIRECTORY";` v kódu a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak otevřu existující dokument PDF?

 Odpověď: V kroku 4 otevřete existující dokument PDF pomocí`Document` konstruktoru a poskytnutí cesty ke vstupnímu souboru PDF.

#### Otázka: Proč se upravuje velikost písma?

Odpověď: Krok 5 zahrnuje zmenšení velikosti písma fragmentů textu faktorem 0,7. Tato úprava zlepšuje čitelnost a přesněji zobrazuje sloupcový text.

#### Otázka: Jak extrahuji text ze sloupců?

 Odpověď: Krok 6 se skládá z uložení upraveného dokumentu PDF do paměťového toku, jeho opětovného načtení jako nového dokumentu a následného použití`TextAbsorber` třídy extrahovat text ze sloupců.

#### Otázka: Jaký je účel uložení extrahovaného textu?

Odpověď: V kroku 7 uložíte extrahovaný text do textového souboru v zadané cestě k výstupnímu souboru.

#### Otázka: Proč zmenšit velikost písma před extrakcí?

Odpověď: Zmenšení velikosti písma pomáhá zajistit, aby byl extrahovaný text správně zarovnán ve sloupcích, což poskytuje přesnější reprezentaci původního rozvržení.

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Sledováním tohoto kurzu jste získali znalosti a dovednosti potřebné k extrahování sloupců textu z dokumentu PDF pomocí Aspose.PDF pro .NET. Výsledný text byl uložen do zadaného výstupního souboru.