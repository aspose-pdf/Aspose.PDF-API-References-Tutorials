---
title: Vyhledejte a získejte textovou stránku v souboru PDF
linktitle: Vyhledejte a získejte textovou stránku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vyhledávat a získávat text z konkrétní stránky v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 430
url: /cs/net/programming-with-text/search-and-get-text-page/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k vyhledávání a získávání textu z konkrétní stránky v souboru PDF. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Vyhledejte a extrahujte text ze stránky

 Vytvořte a`TextFragmentAbsorber`objekt k nalezení všech výskytů vstupní vyhledávací fráze na konkrétní stránce:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Nahradit`"Figure"` se skutečným textem, který chcete vyhledat.

## Krok 5: Hledejte na konkrétní stránce

Přijměte absorbér pro konkrétní stránku dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 6: Získejte extrahované fragmenty textu

Získejte extrahované fragmenty textu pomocí`TextFragments` majetek z`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 7: Procházejte fragmenty textu a segmenty

Procházejte získané textové fragmenty a jejich segmenty a získejte přístup k jejich vlastnostem:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Kód ve smyčce můžete upravit a provést další akce s každým textovým segmentem.

### Ukázka zdrojového kódu pro stránku Hledat a získat text pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Vytvořte objekt TextAbsorber, abyste našli všechny výskyty vstupní hledané fráze
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Přijměte absorbér pro všechny stránky
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Projděte fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak vyhledávat a získávat text z konkrétní stránky dokumentu PDF pomocí Aspose.PDF for .NET. Tento výukový program poskytl průvodce krok za krokem, od načtení dokumentu až po přístup k extrahovaným textovým segmentům. Nyní můžete začlenit

### FAQ

#### Otázka: Jaký je účel výukového programu „Vyhledat a získat textovou stránku“?

Odpověď: Výukový program "Vyhledat a získat textovou stránku" je navržen tak, aby ilustroval, jak používat knihovnu Aspose.PDF pro .NET k vyhledávání a načítání textu z konkrétní stránky v souboru PDF. Výukový program poskytuje podrobné pokyny a ukázkový kód C# k demonstraci procesu.

#### Otázka: Jak tento kurz pomáhá při extrahování textu z konkrétní stránky v dokumentu PDF?

Odpověď: Tento tutoriál vás provede procesem extrahování textu z konkrétní stránky dokumentu PDF pomocí knihovny Aspose.PDF. Nastiňuje nezbytné kroky a poskytuje kód C# pro vyhledání zadané textové fráze na vybrané stránce a načtení souvisejících textových segmentů.

#### Otázka: Jaké jsou předpoklady pro následování tohoto kurzu?

Odpověď: Než začnete s tímto tutoriálem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej pomocí NuGet integrovat do svého projektu.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

A: Chcete-li začít, vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využít možnosti knihovny ve vašem projektu.

#### Otázka: Mohu hledat text na konkrétní stránce dokumentu PDF?

Odpověď: Ano, tento tutoriál ukazuje, jak hledat text na konkrétní stránce dokumentu PDF. Zahrnuje použití`TextFragmentAbsorber` třídy k vyhledání instancí konkrétní textové fráze na zvolené stránce.

#### Otázka: Jak získám přístup k extrahovaným textovým segmentům z konkrétní stránky?

 Odpověď: Po vyhledání textu na určené stránce můžete získat přístup k extrahovaným textovým segmentům pomocí`TextSegments` majetek z`TextFragment` objekt. Tato vlastnost poskytuje přístup ke sbírce`TextSegment` objekty, které obsahují extrahovaný text a související informace.

#### Otázka: Jaké informace mohu získat z extrahovaných textových segmentů?

Odpověď: Z extrahovaných textových segmentů můžete získat různé podrobnosti, včetně obsahu textu, polohy (souřadnice X a Y), informací o písmu (název, velikost, barva atd.) a další. Ukázkový kód kurzu ukazuje, jak získat a vytisknout tyto podrobnosti pro každý textový segment.

#### Otázka: Mohu provádět vlastní akce s extrahovanými textovými segmenty?

A: Určitě. Jakmile budete mít segmenty extrahovaného textu, můžete upravit kód ve smyčce a provádět další akce na každém segmentu. To může zahrnovat uložení extrahovaného textu, analýzu vzorů textu nebo použití změn formátování.