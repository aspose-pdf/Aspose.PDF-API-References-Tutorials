---
title: Extrahujte text pomocí textového zařízení
linktitle: Extrahujte text pomocí textového zařízení
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat text z dokumentu PDF pomocí Textového zařízení v Aspose.PDF pro .NET.
type: docs
weight: 210
url: /cs/net/programming-with-text/extract-text-using-text-device/
---
Tento tutoriál vás provede procesem extrahování textu z dokumentu PDF pomocí textového zařízení v Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Otevřete dokument PDF
 Otevřete existující dokument PDF pomocí`Document`konstruktoru a předání cesty ke vstupnímu souboru PDF.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## Krok 5: Extrahujte text pomocí textového zařízení
 Vytvořte a`StringBuilder` objekt, do kterého se bude ukládat extrahovaný text. Iterujte každou stránku dokumentu a použijte a`TextDevice` extrahovat text z každé stránky.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## Krok 6: Uložte extrahovaný text
 Zadejte cestu k výstupnímu souboru a uložte extrahovaný text do textového souboru pomocí`File.WriteAllText` metoda.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### Ukázkový zdrojový kód pro extrahování textu pomocí textového zařízení pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//Řetězec pro uložení extrahovaného textu
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// Vytvořte textové zařízení
		TextDevice textDevice = new TextDevice();
		// Nastavení možností extrakce textu - nastavení režimu extrakce textu (Raw nebo Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// Převeďte konkrétní stránku a uložte text do streamu
		textDevice.Process(pdfPage, textStream);
		// Převeďte konkrétní stránku a uložte text do streamu
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// Zavřete datový proud paměti
		textStream.Close();
		// Získejte text z paměti
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// Uložte extrahovaný text do textového souboru
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## Závěr
Úspěšně jste extrahovali text z dokumentu PDF pomocí Textového zařízení v Aspose.PDF pro .NET. Extrahovaný text byl uložen do zadaného výstupního souboru.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento výukový program poskytuje návod na extrahování textu z dokumentu PDF pomocí funkce Textové zařízení v Aspose.PDF pro .NET. Doprovodný zdrojový kód C# demonstruje nezbytné kroky k dosažení tohoto úkolu.

#### Otázka: Jaké jmenné prostory mám importovat?

Odpověď: Do souboru kódu, do kterého plánujete extrahovat text, zahrňte na začátek souboru následující pomocí direktiv:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak otevřu existující dokument PDF?

 Odpověď: V kroku 4 otevřete existující dokument PDF pomocí`Document` konstruktoru a poskytnutí cesty ke vstupnímu souboru PDF.

#### Otázka: Jak extrahuji text pomocí textového zařízení?

 Odpověď: Krok 5 zahrnuje vytvoření a`StringBuilder` objekt, do kterého se bude ukládat extrahovaný text. Poté budete iterovat každou stránku dokumentu a použít a`TextDevice` spolu s`TextExtractionOptions` extrahovat text z každé stránky.

#### Otázka: Jak uložím extrahovaný text do souboru?

 Odpověď: V kroku 6 zadáte cestu k výstupnímu souboru a použijete`File.WriteAllText`metoda pro uložení extrahovaného textu do textového souboru.

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se naučili, jak využít funkci Textové zařízení v Aspose.PDF for .NET k extrahování textu z dokumentu PDF. Extrahovaný text byl uložen do určeného výstupního souboru, což vám umožňuje manipulovat a využívat extrahovaný obsah podle potřeby.