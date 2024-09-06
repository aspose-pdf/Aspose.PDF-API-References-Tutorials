---
title: Hledat regulární výraz v souboru PDF
linktitle: Hledat regulární výraz v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vyhledávat a načítat text pomocí regulárních výrazů v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 440
url: /cs/net/programming-with-text/search-regular-expression/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k vyhledávání a načítání textu, který odpovídá regulárnímu výrazu v souboru PDF. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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
```

## Krok 3: Načtěte dokument PDF

 Nastavte cestu k adresáři vašeho dokumentu PDF a načtěte dokument pomocí`Document` třída:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Hledejte pomocí regulárního výrazu

 Vytvořte a`TextFragmentAbsorber` objekt a nastavte vzor regulárního výrazu, abyste našli všechny fráze, které odpovídají vzoru:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Jako 1999-2000
```

 Nahradit`"\\d{4}-\\d{4}"` s požadovaným vzorem regulárního výrazu.

## Krok 5: Nastavte možnosti textového vyhledávání

 Vytvořte a`TextSearchOptions` objekt a nastavte jej na`TextSearchOptions` majetek z`TextFragmentAbsorber` objekt umožňující použití regulárního výrazu:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## Krok 6: Hledejte na všech stránkách

Přijměte absorbér pro všechny stránky dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 7: Načtěte extrahované fragmenty textu

Získejte extrahované fragmenty textu pomocí`TextFragments` majetek z`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 8: Procházejte fragmenty textu

Procházejte načtené fragmenty textu a získejte přístup k jejich vlastnostem:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Kód ve smyčce můžete upravit a provést další akce s každým textovým fragmentem.

### Ukázka zdrojového kódu pro hledání regulárních výrazů pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// Vytvořte objekt TextAbsorber a najděte všechny fráze odpovídající regulárnímu výrazu
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Jako 1999-2000
// Nastavte možnost textového vyhledávání pro určení použití regulárního výrazu
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Přijměte absorbér pro všechny stránky
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Projděte fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak vyhledávat a získávat text, který odpovídá regulárnímu výrazu v dokumentu PDF pomocí Aspose.PDF for .NET. Tento výukový program poskytl průvodce krok za krokem, od načtení dokumentu až po přístup k extrahovaným fragmentům textu. Nyní můžete tento kód začlenit do svých vlastních projektů C# a provádět pokročilé vyhledávání textu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Hledat regulární výraz v souboru PDF“?

Odpověď: Výukový program „Vyhledat regulární výraz v souboru PDF“ si klade za cíl předvést, jak používat knihovnu Aspose.PDF pro .NET k vyhledávání a extrahování textu, který odpovídá zadanému vzoru regulárního výrazu v souboru PDF. Výukový program poskytuje komplexní návod a ukázkový kód C# pro demonstraci procesu.

#### Otázka: Jak tento kurz pomáhá při hledání textu pomocí regulárních výrazů v dokumentu PDF?

Odpověď: Tento tutoriál poskytuje podrobný přístup k použití knihovny Aspose.PDF k provádění textového vyhledávání v dokumentu PDF na základě vzoru regulárních výrazů. Podrobně popisuje, jak nastavit projekt, načíst dokument PDF, definovat vzor regulárního výrazu a načíst odpovídající textové fragmenty.

#### Otázka: Jaké jsou předpoklady pro následování tohoto kurzu?

Odpověď: Než začnete s tímto tutoriálem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej pomocí NuGet integrovat do svého projektu.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

Odpověď: Pro začátek vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využít možnosti knihovny v rámci vašeho projektu.

#### Otázka: Mohu použít regulární výrazy k vyhledávání textu v dokumentu PDF?

 Odpověď: Ano, tento tutoriál ukazuje, jak používat regulární výrazy k vyhledávání a extrahování textu z dokumentu PDF. Zahrnuje využití`TextFragmentAbsorber` třídy a zadáním vzoru regulárního výrazu k nalezení frází, které odpovídají poskytnutému vzoru.

#### Otázka: Jak mohu definovat vzor regulárního výrazu pro textové vyhledávání?

 A: Chcete-li definovat vzor regulárního výrazu pro textové vyhledávání, vytvořte a`TextFragmentAbsorber` objekt a nastavte jeho vzor pomocí`Text` parametr. Nahradit výchozí vzor`"\\d{4}-\\d{4}"` v kódu výukového programu s požadovaným vzorem regulárního výrazu.

#### Otázka: Jak mohu povolit použití regulárních výrazů pro textové vyhledávání?

 A: Použití regulárního výrazu je umožněno vytvořením a`TextSearchOptions` objektu a nastavení jeho hodnoty na`true` . Přiřaďte tento objekt k`TextSearchOptions` majetek z`TextFragmentAbsorber` instance. Tím je zajištěno, že se při vyhledávání textu použije vzor regulárního výrazu.

#### Otázka: Mohu načíst fragmenty textu, které odpovídají vzoru regulárního výrazu?

 A: Rozhodně. Po použití hledání regulárních výrazů na dokument PDF můžete získat extrahované textové fragmenty pomocí`TextFragments` majetek z`TextFragmentAbsorber` objekt. Tyto textové fragmenty obsahují textové segmenty, které odpovídají zadanému vzoru regulárního výrazu.

#### Otázka: K čemu mám přístup z načtených fragmentů textu?

Odpověď: Z načtených textových fragmentů můžete přistupovat k různým vlastnostem, jako je obsah shodného textu, poloha (souřadnice X a Y), informace o písmu (název, velikost, barva) a další. Ukázkový kód ve smyčce kurzu ukazuje, jak získat přístup k těmto vlastnostem a jak je zobrazit.

#### Otázka: Jak mohu přizpůsobit akce s extrahovanými fragmenty textu?

Odpověď: Jakmile budete mít extrahované fragmenty textu, můžete upravit kód ve smyčce tak, aby s každým fragmentem textu provedl další akce. To může zahrnovat ukládání extrahovaného textu, analýzu vzorů nebo implementaci změn formátování na základě vašich požadavků.