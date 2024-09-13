---
title: Vyhledejte text a přidejte hypertextový odkaz
linktitle: Vyhledejte text a přidejte hypertextový odkaz
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se hledat text v PDF, přidávat k nalezenému textu hypertextové odkazy a uložit upravený dokument pomocí Aspose.PDF for .NET.
type: docs
weight: 450
url: /cs/net/programming-with-text/search-text-and-add-hyperlink/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF for .NET k vyhledání určitého textu v dokumentu PDF, přidání hypertextového odkazu k nalezenému textu a uložení upraveného dokumentu. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte cestu k adresáři dokumentů

 Nastavte cestu k adresáři dokumentů pomocí`dataDir` proměnná:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Vytvořte TextFragmentAbsorber

 Vytvořte a`TextFragmentAbsorber` objekt k nalezení všech výskytů vstupní vyhledávací fráze:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Nahradit`"\\d{4}-\\d{4}"` s požadovaným vzorem regulárního výrazu.

## Krok 5: Povolte vyhledávání regulárních výrazů

 Povolte vyhledávání regulárních výrazů nastavením`TextSearchOptions` vlastnost absorbéru:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Krok 6: Otevřete a svažte dokument PDF

 Vytvořte a`PdfContentEditor` objekt a svázat jej se zdrojovým souborem PDF:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Nahradit`"SearchRegularExpressionPage.pdf"` se skutečným názvem vašeho souboru PDF.

## Krok 7: Přijměte absorbér pro stránku

Přijměte absorbér pro požadovanou stránku dokumentu:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Nahradit`1` s požadovaným číslem stránky.

## Krok 8: Přidejte k nalezenému textu hypertextové odkazy

Procházejte načtené části textu a přidejte k nim hypertextové odkazy:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Vytvořte obdélník podle polohy fragmentu textu
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Přidejte do obdélníku webový odkaz
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Nahradit`"http://www.aspose.com"` s požadovanou URL hypertextového odkazu.

## Krok 9: Uložte a zavřete upravený dokument

Uložte upravený dokument a zavřete editor:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Nezapomeňte vyměnit`"SearchTextAndAddHyperlink_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázkový zdrojový kód pro hledání textu a přidání hypertextového odkazu pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořte objekt absorbéru, abyste našli všechny výskyty vstupní hledané fráze
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Povolit vyhledávání regulárních výrazů
absorber.TextSearchOptions = new TextSearchOptions(true);
// Otevřete dokument
PdfContentEditor editor = new PdfContentEditor();
// Svázat zdrojový soubor PDF
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Přijměte absorbér pro stránku
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Projděte fragmenty
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, modrá, název akce);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak vyhledat konkrétní text v dokumentu PDF, přidat k nalezenému textu hypertextové odkazy a uložit upravený dokument pomocí Aspose.PDF for .NET. Tento výukový program poskytuje průvodce krok za krokem, od nastavení projektu až po provedení požadovaných akcí. Nyní můžete tento kód začlenit do svých vlastních projektů C# a manipulovat s textem a přidávat hypertextové odkazy do souborů PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Vyhledat text a přidat hypertextový odkaz“?

Odpověď: Výukový program "Vyhledat text a přidat hypertextový odkaz" si klade za cíl demonstrovat, jak používat knihovnu Aspose.PDF pro .NET k vyhledání konkrétního textu v dokumentu PDF, přidání hypertextových odkazů k nalezenému textu a následnému uložení upraveného dokumentu. Výukový program poskytuje komplexního průvodce a ukázky kódu C#, které ilustrují proces krok za krokem.

#### Otázka: Jak tento kurz pomáhá při přidávání hypertextových odkazů na konkrétní text v dokumentu PDF?

Odpověď: Tento tutoriál vás provede procesem používání knihovny Aspose.PDF k vyhledání určitého textu v dokumentu PDF, použití hypertextového odkazu na identifikovaný text a uložení upraveného PDF. Zahrnuje základní kroky, jako je nastavení projektu, načtení dokumentu, umožnění vyhledávání regulárních výrazů a přidání hypertextových odkazů k nalezenému textu.

#### Otázka: Jaké předpoklady jsou potřeba pro sledování tohoto kurzu?

Odpověď: Než začnete, měli byste mít základní znalosti programovacího jazyka C#. Dále musíte mít nainstalovanou knihovnu Aspose.PDF for .NET, kterou lze získat z webu Aspose nebo nainstalovat pomocí NuGet ve vašem projektu.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

Odpověď: Začněte vytvořením nového projektu C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE). Poté přidejte odkaz na knihovnu Aspose.PDF for .NET, která vám umožní využít možnosti knihovny ve vašem projektu.

#### Otázka: Mohu pomocí tohoto kurzu přidat hypertextové odkazy na konkrétní text?

Odpověď: Ano, tento kurz se konkrétně zaměřuje na přidávání hypertextových odkazů na konkrétní text v dokumentu PDF. Ukazuje, jak najít a extrahovat požadovaný text pomocí regulárních výrazů, vytvořit hypertextové odkazy spojené s fragmenty textu a uložit upravený PDF.

#### Otázka: Jak mohu definovat text, který chci vyhledat, a přidat k němu hypertextový odkaz?

 A: Chcete-li zadat text, který chcete vyhledat a přidat hypertextový odkaz, vytvořte a`TextFragmentAbsorber` objekt a nastavte jeho vzor pomocí`Text` parametr. Nahradit výchozí vzor`"\\d{4}-\\d{4}"` v kódu výukového programu s požadovaným vzorem regulárního výrazu.

#### Otázka: Jak mohu povolit vyhledávání textu pomocí regulárních výrazů?

 A: Hledání regulárních výrazů je povoleno vytvořením a`TextSearchOptions` objektu a nastavení jeho hodnoty na`true` . Přiřaďte tento objekt k`TextSearchOptions` vlastnictví`TextFragmentAbsorber` instance. Tím je zajištěno, že se při vyhledávání textu použije vzor regulárního výrazu.

#### Otázka: Jak přidám hypertextové odkazy k nalezenému textu?

 A: Po identifikaci textových fragmentů pomocí`TextFragmentAbsorber` , výukový program poskytuje smyčku pro iteraci těmito fragmenty. Pro každý textový fragment výukový program ukazuje, jak nastavit barvu textu na modrou a vytvořit hypertextový odkaz pomocí`CreateWebLink` metoda.

#### Otázka: Jaké jsou kroky k uložení upraveného PDF s hypertextovými odkazy?

 Odpověď: Po přidání hypertextových odkazů k požadovaným textovým fragmentům použijte`PdfContentEditor` třídy k uložení upraveného dokumentu. Ukázkový kód výukového programu ukazuje, jak uložit upravené PDF, zavřít editor a zobrazit zprávu o úspěchu.