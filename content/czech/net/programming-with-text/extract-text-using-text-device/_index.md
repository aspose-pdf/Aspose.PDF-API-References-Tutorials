---
title: Extrahujte text pomocí textového zařízení
linktitle: Extrahujte text pomocí textového zařízení
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat text z dokumentu PDF pomocí Textového zařízení v Aspose.PDF pro .NET.
type: docs
weight: 210
url: /cs/net/programming-with-text/extract-text-using-text-device/
---
## Zavedení

Extrahování textu z PDF může být složité, zejména při práci s dokumenty, které mají různé formáty, vložená písma nebo složitá rozvržení. Ale s Aspose.PDF pro .NET se tento proces stává hračkou! Ať už chcete převést stránky PDF do prostého textu pro další analýzu, nebo jednoduše potřebujete extrahovat konkrétní části, Aspose.PDF vás pokryje. V tomto tutoriálu si krok za krokem rozebereme, jak extrahovat text z PDF pomocí třídy TextDevice v Aspose.PDF. Poskytneme také jasná vysvětlení, takže stejné metody můžete snadno použít na své vlastní projekty.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše, co můžete sledovat. Zde je to, co budete potřebovat:

1.  Aspose.PDF pro .NET: Stáhněte si nejnovější verzi z[Stránka ke stažení Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Visual Studio nebo jakékoli jiné vývojové prostředí C#.
3. .NET Framework: Ujistěte se, že váš projekt cílí na .NET Framework 4.x nebo vyšší.
4. Vstupní soubor PDF: Soubor PDF, který použijete pro extrakci textu. Umístěte to do adresáře na vašem počítači (budeme to označovat jako`YOUR DOCUMENT DIRECTORY`).

## Importujte balíčky

V horní části kódu budete muset importovat potřebné jmenné prostory pro práci s Aspose.PDF:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Krok 1: Načtěte dokument PDF

 Před extrahováním textu musíme načíst dokument PDF do paměti. V tomto kroku otevřete soubor PDF pomocí souboru Aspose.PDF`Document` třída. To vám umožní přístup ke všem stránkám a obsahu v souboru.

```csharp
// Definujte cestu k dokumentu PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte dokument PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Tady, používáme`Document pdfDocument = new Document(dataDir + "input.pdf");` pro načtení PDF. The`dataDir` proměnná obsahuje cestu k adresáři vašeho souboru PDF. To nám umožní přístup k celému dokumentu, což nám umožní procházet stránkami a extrahovat obsah.

## Krok 2: Nastavte Tvůrce řetězců pro ukládání textu

 Nyní, když je dokument načten, potřebujeme způsob, jak extrahovaný text uložit. K tomu použijeme a`StringBuilder` což umožňuje efektivní zřetězení řetězců.

```csharp
// StringBuilder k uložení extrahovaného textu
StringBuilder builder = new StringBuilder();
```

 Inicializujeme a`StringBuilder`instance, která bude shromažďovat text extrahovaný z každé stránky. Je to efektivnější způsob zpracování velkých řetězců ve srovnání s běžným zřetězením řetězců ve smyčce.

## Krok 3: Procházení stránek PDF

 Dále procházíme každou stránku dokumentu PDF, abychom extrahovali text. Každou stránku zpracujeme individuálně pomocí`TextDevice` třídy, která je zodpovědná za převod obsahu PDF do textového formátu.

```csharp
// Projděte všechny stránky v PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Zpracujte každou stránku pro extrakci textu
}
```

Tato smyčka prochází každou stránku PDF (`pdfDocument.Pages` ). Pro každou stránku vyjmeme text a přidáme jej do našeho`StringBuilder`.

## Krok 4: Extrahujte text z každé stránky

 Nyní nastavíme proces extrakce textu pro každou stránku. Zde vytvoříme a`TextDevice` objekt a použít jej ke zpracování stránek PDF. The`TextDevice` extrahuje nezpracovaný nebo formátovaný text na základě námi nastavených možností extrakce.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Vytvořte textové zařízení pro extrakci textu
    TextDevice textDevice = new TextDevice();
    
    // Nastavte možnosti extrakce textu na režim „Čistý“.
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Extrahujte text z aktuální stránky a uložte jej do paměti
    textDevice.Process(pdfPage, textStream);

    // Převod paměti na text
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Přidejte extrahovaný text do StringBuilderu
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : The`TextDevice` třída se používá k extrahování textu z PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Tato možnost extrahuje nezpracovaný text bez zachování jakéhokoli formátování, jako jsou písma nebo pozice. Můžete také použít`TextFormattingMode.Raw` pokud potřebujete větší kontrolu nad formátováním.
- `textDevice.Process(pdfPage, textStream);` : Tím se zpracuje každá stránka PDF a extrahovaný text se uloží do a`MemoryStream`.
-  Nakonec převedeme text z`MemoryStream` k řetězci a připojit jej k`StringBuilder`.

## Krok 5: Uložte extrahovaný text do souboru

 Po zpracování všech stránek se text uloží do`StringBuilder`. Posledním krokem je uložení tohoto extrahovaného textu do souboru.

```csharp
// Definujte výstupní cestu pro textový soubor
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Uložte extrahovaný text do souboru
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Toto píše celý obsah`StringBuilder` do textového souboru.
- Cesta k výstupnímu souboru se nastavuje připojením názvu souboru (`"input_Text_Extracted_out.txt"` ) k`dataDir` cesta.

## Závěr

Extrahování textu z PDF pomocí Aspose.PDF pro .NET je jednoduchý a efektivní proces. Podle kroků uvedených v této příručce můžete snadno otevírat dokumenty PDF, procházet stránkami a extrahovat text do textového souboru. To je užitečné zejména při zpracování velkých objemů dat PDF, provádění analýzy textu nebo převodu dokumentů pro další manipulaci.

S Aspose.PDF nejste omezeni na extrakci textu – můžete pracovat s anotacemi, manipulovat s obrázky nebo dokonce převádět PDF do jiných formátů, jako je HTML nebo Word. Flexibilita a síla této knihovny z ní činí neocenitelný nástroj pro správu PDF v aplikacích .NET.

## FAQ

### Může Aspose.PDF extrahovat text z obrázků PDF?
Ne, Aspose.PDF je navržen tak, aby extrahoval text z obsahu PDF. Pro soubory PDF založené na obrázcích je zapotřebí technologie OCR.

### Zachová Aspose.PDF při extrahování textu formátování?
Ve výchozím nastavení je text extrahován bez formátování, ale pokud chcete zachovat určité formátování, můžete upravit možnosti extrakce.

### Mohu extrahovat text z určitého rozsahu stránek?
Ano, kód můžete upravit tak, aby procházel přes konkrétní rozsah stránek namísto všech stránek.

### Jaké jsou režimy extrakce textu v Aspose.PDF?
Aspose.PDF poskytuje dva režimy: Raw a Pure. Režim Raw se snaží zachovat původní rozvržení, zatímco režim Pure extrahuje pouze text bez formátování.

### Je Aspose.PDF for .NET kompatibilní s .NET Core?
Ano, Aspose.PDF for .NET je plně kompatibilní s .NET Core a .NET Framework.