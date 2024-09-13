---
title: Hledat Text A Nakreslit Obdélník
linktitle: Hledat Text A Nakreslit Obdélník
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se hledat text v PDF, kreslit kolem nalezeného textu obdélníky a uložit upravený dokument pomocí Aspose.PDF for .NET.
type: docs
weight: 460
url: /cs/net/programming-with-text/search-text-and-draw-rectangle/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k vyhledání určitého textu v dokumentu PDF, nakreslení obdélníku kolem nalezeného textu a uložení upraveného dokumentu. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

## Předpoklady

Než budete pokračovat ve výukovém programu, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#.
- Nainstalovaná knihovna Aspose.PDF pro .NET. Můžete jej získat z webu Aspose nebo jej pomocí NuGet nainstalovat do svého projektu.

## Krok 1: Nastavte projekt

Začněte vytvořením nového projektu C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte potřebné jmenné prostory

Chcete-li importovat požadované jmenné prostory, přidejte následující pomocí direktiv na začátek souboru C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Krok 3: Nastavte cestu k adresáři dokumentů

 Nastavte cestu k adresáři dokumentů pomocí`dataDir` proměnná:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Načtěte dokument PDF

 Načtěte dokument PDF pomocí`Document` třída:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Nahradit`"SearchAndGetTextFromAll.pdf"` se skutečným názvem vašeho souboru PDF.

## Krok 5: Vytvořte TextFragmentAbsorber

 Vytvořte a`TextFragmentAbsorber` objekt k nalezení všech výskytů vstupní vyhledávací fráze:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Nahradit`@"[\S]+"` s požadovaným vzorem regulárního výrazu.

## Krok 6: Povolte vyhledávání regulárních výrazů

 Povolte vyhledávání regulárních výrazů nastavením`TextSearchOptions` vlastnost absorbéru:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Krok 7: Hledejte na všech stránkách

Přijměte absorbér pro všechny stránky dokumentu:

```csharp
document.Pages.Accept(textAbsorber);
```

## Krok 8: Nakreslete kolem nalezeného textu obdélník

 Vytvořte a`PdfContentEditor` objekt a procházet načtenými fragmenty textu, přičemž kolem každého segmentu textu nakreslíte obdélník:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Krok 9: Uložte upravený dokument

Uložte upravený dokument:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Nezapomeňte vyměnit`"SearchTextAndDrawRectangle_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázka zdrojového kódu pro Search Text And Draw Rectangle pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//Vytvořte objekt TextAbsorber a najděte všechny fráze odpovídající regulárnímu výrazu
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak vyhledat konkrétní text v dokumentu PDF, nakreslit kolem nalezeného textu obdélník a uložit upravený dokument pomocí Aspose.PDF for .NET. Tento výukový program poskytuje průvodce krok za krokem, od nastavení projektu až po provedení požadovaných akcí. Nyní můžete tento kód začlenit do svých vlastních projektů C# a manipulovat s textem a kreslit obdélníky v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Vyhledat text a nakreslit obdélník“?

Odpověď: Výukový program „Vyhledat text a nakreslit obdélník“ má za cíl provést uživatele procesem používání knihovny Aspose.PDF pro .NET k vyhledávání konkrétního textu v dokumentu PDF, kreslení obdélníků kolem nalezených textových segmentů a ukládání upravených dokument. Výukový program poskytuje podrobné pokyny a ukázky kódu C# pro ilustraci každého kroku procesu.

#### Otázka: Jak tento kurz pomáhá při kreslení obdélníků kolem určitého textu v dokumentu PDF?

Odpověď: Tento výukový program poskytuje komplexního průvodce, jak najít a nakreslit obdélníky kolem určitých textových segmentů v dokumentu PDF. Ukazuje proces nastavení projektu, načtení dokumentu PDF, umožnění vyhledávání regulárními výrazy, kreslení obdélníků kolem nalezených segmentů textu a uložení upraveného PDF.

#### Otázka: Jaké předpoklady jsou vyžadovány pro sledování tohoto kurzu?

Odpověď: Než začnete s výukovým programem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej nainstalovat do svého projektu pomocí NuGet.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

Odpověď: Začněte vytvořením nového projektu C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE). Poté do projektu přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní používat funkce knihovny pro manipulaci s dokumenty PDF.

#### Otázka: Mohu pomocí tohoto kurzu kreslit obdélníky kolem určitého textu?

Odpověď: Ano, výukový program se zaměřuje na kreslení obdélníků kolem určitých textových segmentů v dokumentu PDF. Ukazuje, jak najít požadovaný text pomocí regulárních výrazů, vytvořit obdélníky kolem identifikovaných textových segmentů a uložit upravený PDF.

#### Otázka: Jak mohu určit text, který chci hledat, a nakreslit kolem něj obdélníky?

 A: Chcete-li zadat text, který chcete hledat, a kolem něj nakreslit obdélníky, vytvořte a`TextFragmentAbsorber` objekt a nastavte jeho vzor pomocí`Text` parametr. Nahradit výchozí vzor`@"[\S]+"` v kódu výukového programu s požadovaným vzorem regulárního výrazu.

#### Otázka: Jak povolím vyhledávání textu pomocí regulárních výrazů?

 A: Hledání regulárních výrazů je povoleno vytvořením a`TextSearchOptions` objektu a nastavení jeho hodnoty na`true` . Přiřaďte tento objekt k`TextSearchOptions` vlastnictví`TextFragmentAbsorber` instance. Tím je zajištěno, že se při vyhledávání textu použije vzor regulárního výrazu.

#### Otázka: Jak nakreslím kolem nalezeného textu obdélníky?

 A: Po identifikaci textových segmentů pomocí`TextFragmentAbsorber` , výukový program poskytuje smyčku pro iteraci těmito segmenty. Pro každý textový segment výukový program ukazuje, jak vytvořit obdélník kolem něj pomocí`DrawBox` a určete vzhled obdélníku.

#### Otázka: Jaké jsou kroky k uložení upraveného PDF s nakreslenými obdélníky?

Odpověď: Po nakreslení obdélníků kolem požadovaných textových segmentů použijte`Document` třídy`Save` způsob uložení upraveného dokumentu. Ukázkový kód výukového programu ukazuje, jak uložit upravené PDF a zobrazit zprávu o úspěchu.

#### Otázka: Mohu upravit vzhled nakreslených obdélníků?

 Odpověď: Ano, vzhled nakreslených obdélníků si můžete přizpůsobit. V ukázkovém kódu výukového programu je`DrawBox` metoda se používá k vytváření obdélníků. Můžete upravit vlastnosti, jako je barva, styl a tloušťka, a přizpůsobit tak vzhled nakreslených obdélníků.