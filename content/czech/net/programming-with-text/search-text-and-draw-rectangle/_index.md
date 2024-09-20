---
title: Hledat Text A Nakreslit Obdélník
linktitle: Hledat Text A Nakreslit Obdélník
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vyhledávat text v PDF a zvýrazňovat jej pomocí obdélníků pomocí Aspose.PDF for .NET! Jednoduchý návod krok za krokem pro vylepšené dovednosti manipulace s PDF.
type: docs
weight: 460
url: /cs/net/programming-with-text/search-text-and-draw-rectangle/
---
## Zavedení

Chcete zlepšit své dovednosti v manipulaci s PDF? Chcete se naučit vyhledávat konkrétní text v souborech PDF a zvýraznit jej obdélníkem? Dostali jste se na perfektního průvodce! Dnes vás provedu tím, jak pomocí Aspose.PDF for .NET vyhledávat text v dokumentu PDF a kreslit kolem něj obdélníky. Tento článek poskytne návod krok za krokem navržený s ohledem na srozumitelnost a užitečnost a zajistí, že budete moci tyto techniky sledovat a aplikovat na své projekty. 

## Předpoklady

Než se pustíme do výukového programu, připravme si, co potřebujete k zajištění hladkého pracovního postupu:

1. Základní porozumění .NET: Abyste mohli efektivně sledovat tento výukový program, měli byste být obeznámeni s programováním v C# a frameworkem .NET.
   
2. Visual Studio nainstalované: K psaní a testování kódu budete potřebovat integrované vývojové prostředí (IDE). Visual Studio Community je skvělá volba a je zdarma.
   
3. Aspose.PDF for .NET: Ve svém projektu musíte mít nainstalovanou knihovnu Aspose.PDF. Můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/) nebo zvážit a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro rozšířené funkce.
   
4.  Ukázkový dokument PDF: Pro tento výukový program budete potřebovat ukázkový soubor PDF s názvem`SearchAndGetTextFromAll.pdf` uloženy v adresáři vašeho projektu. 

## Importujte balíčky

Chcete-li začít, musíte nejprve importovat potřebné balíčky do svého projektu .NET. Postupujte takto:

### Otevřete Visual Studio

Spusťte Visual Studio a vytvořte novou konzolovou aplikaci nebo použijte existující, kde chcete implementovat funkce PDF.

### Přidejte Aspose.PDF do svého projektu

1. Klepněte pravým tlačítkem myši na svůj projekt v Průzkumníku řešení.
2. Vyberte „Spravovat balíčky NuGet“.
3.  Hledat`Aspose.PDF` a nainstalujte nejnovější verzi.

Tím vytvoříte základ pro všechny úžasné manipulace s PDF, které se chystáte provést.

## Importovat jmenné prostory

V horní části souboru programu budete chtít importovat příslušné jmenné prostory z knihovny Aspose:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

To usnadňuje přístup ke třídám a metodám v rámci knihovny Aspose.PDF pro vaše úkoly.


Nyní, když máte vše nastaveno, pojďme si rozdělit proces hledání textu v PDF a nakreslení obdélníku kolem něj do zvládnutelných kroků.

## Krok 1: Nastavte cestu pro váš dokument

 Nejprve nastavte cestu k souboru PDF. Nezapomeňte vyměnit`YOUR DOCUMENT DIRECTORY` se skutečnou cestou, kde jste`SearchAndGetTextFromAll.pdf` je uložen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument PDF

 Dále vytvořte instanci souboru`Document` třída pro načtení vašeho PDF:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Tento řádek kódu otevře zadaný soubor PDF a umožní vám s ním dále manipulovat.

## Krok 3: Vytvořte absorbér textu

 Nyní budete potřebovat způsob, jak hledat text v tomto dokumentu. K tomu používáme`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Regulární výraz`@"[\S]+"` je navržen tak, aby odpovídal jakémukoli řetězci bez mezer v PDF. 

## Krok 4: Nakonfigurujte možnosti vyhledávání textu

Dále byste měli nastavit možnosti textového vyhledávání:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Tady,`true` parametr znamená, že vyhledávání bude rozlišovat malá a velká písmena. Můžete to nastavit na`false` pokud chcete vyhledávání bez rozlišení velkých a malých písmen.

## Krok 5: Přijměte v dokumentu absorbér textu

 S tvým`TextFragmentAbsorber` a možnosti vyhledávání jsou připraveny, je čas absorbovat text z dokumentu:

```csharp
document.Pages.Accept(textAbsorber);
```

Tato metoda prozkoumá každou stránku ve vašem PDF a najde fragmenty textu, které odpovídají zadanému vzoru.

## Krok 6: Vytvořte PdfContentEditor

 Chcete-li na dokument kreslit tvary, budete potřebovat`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Tento editor vám umožňuje snadno manipulovat a upravovat obsah PDF.

## Krok 7: Procházení nalezených textových fragmentů

Nyní budete chtít procházet nalezené fragmenty textu a nakreslit kolem nich obdélníky:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Tato smyčka iteruje každý textový fragment a jeho segmenty a volá a`DrawBox` metoda kreslení obdélníku.

## Krok 8: Definujte metodu DrawBox

 Musíte definovat`DrawBox` metoda, která bude zpracovávat logiku kreslení obdélníku. Zde je jednoduchá implementace:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Vypočítejte rozměry obdélníku na základě segmentu textu
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Nakreslete obdélník pomocí vypočtených hodnot
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Tato metoda určuje polohu a velikost obdélníku na základě ohraničujícího obdélníku segmentu a pomocí editoru jej nakreslí.

## Krok 9: Uložte upravený dokument

Po nakreslení obdélníků kolem nalezeného textu můžete upravený dokument uložit:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Ujistěte se, že je nový soubor uložen pod odlišným názvem, aby nedošlo k přepsání původního dokumentu.

## Krok 10: Potvrzující zpráva

Nakonec vytiskněte potvrzovací zprávu do konzoly, abyste věděli, že operace byla úspěšná:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

A tady to máte! Úspěšně jste vytvořili skript pro vyhledávání textu v PDF a jeho zvýraznění pomocí obdélníků.

## Závěr

Gratuluji! Právě jste odemkli výkonnou dovednost, která může výrazně zlepšit vaše schopnosti manipulace s PDF pomocí Aspose.PDF pro .NET. Pomocí několika jednoduchých kroků můžete vyhledat jakýkoli text v dokumentu a vizuálně jej zvýraznit, díky čemuž budou vaše dokumenty PDF interaktivnější a lépe spravovatelné. Neváhejte experimentovat s různými vzory regulárních výrazů a barevnými možnostmi, abyste si tento nástroj skutečně přizpůsobili!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která poskytuje komplexní způsob, jak programově vytvářet, manipulovat a převádět dokumenty PDF.

### Mohu používat Aspose.PDF zdarma?
Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k otestování funkcí knihovny. Podívejte se na to[zde](https://releases.aspose.com/).

### Jaký programovací jazyk musím používat s Aspose.PDF pro .NET?
Aspose.PDF for .NET je navržen pro použití s C# a dalšími jazyky .NET.

### Jak získám pomoc s Aspose.PDF?
 Můžete navštívit fórum podpory Aspose, kde získáte pomoc ohledně jakéhokoli problému nebo dotazu, který můžete mít. Najděte podporu[zde](https://forum.aspose.com/c/pdf/10).

### Kde si stáhnu Aspose.PDF pro .NET?
 Knihovnu si můžete stáhnout z webu Aspose,[zde](https://releases.aspose.com/pdf/net/).