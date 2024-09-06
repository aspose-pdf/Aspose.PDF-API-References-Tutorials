---
title: Hledat a získat text vše
linktitle: Hledat a získat text vše
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vyhledávat a získávat text ze všech stránek dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 420
url: /cs/net/programming-with-text/search-and-get-text-all/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k vyhledávání a získávání textu ze všech stránek dokumentu PDF. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Vyhledejte a extrahujte text

 Vytvořte a`TextFragmentAbsorber` objekt k nalezení všech výskytů vstupní vyhledávací fráze:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Nahradit`"text"` se skutečným textem, který chcete vyhledat.

## Krok 5: Hledejte na všech stránkách

Přijměte absorbér pro všechny stránky dokumentu:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Krok 6: Získejte extrahované fragmenty textu

Získejte extrahované fragmenty textu pomocí`TextFragments` majetek z`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 7: Procházejte fragmenty textu

Procházejte získané fragmenty textu a získejte přístup k jejich vlastnostem:

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

### Ukázkový zdrojový kód pro Search And Get Text All pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Vytvořte objekt TextAbsorber, abyste našli všechny výskyty vstupní hledané fráze
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
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

Gratuluji! Úspěšně jste se naučili, jak vyhledávat a získávat text ze všech stránek dokumentu PDF pomocí Aspose.PDF pro .NET. Tento výukový program poskytl průvodce krok za krokem, od načtení dokumentu až po přístup k extrahovaným fragmentům textu. Nyní můžete tento kód začlenit do svých vlastních projektů C# pro analýzu a zpracování textového obsahu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Vyhledat a získat text vše“?

Odpověď: Výukový program "Vyhledat a získat text vše" ukazuje, jak používat knihovnu Aspose.PDF pro .NET k vyhledávání a extrahování textu ze všech stránek dokumentu PDF. Výukový program poskytuje podrobné pokyny spolu s ukázkovým kódem C# pro provádění textového vyhledávání a načítání.

#### Otázka: Jak tento kurz pomáhá při extrahování textu z dokumentů PDF?

Odpověď: Tento výukový program vás provede procesem extrahování textu ze všech stránek dokumentu PDF. Používá knihovnu Aspose.PDF k vyhledání konkrétních textových frází a načtení souvisejících informací, jako je poloha, vlastnosti písma a barvy.

#### Otázka: Jaké jsou předpoklady pro následování tohoto kurzu?

Odpověď: Než začnete s tímto tutoriálem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej pomocí NuGet integrovat do svého projektu.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

A: Chcete-li začít, vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní přístup k funkcím knihovny ve vašem projektu.

#### Otázka: Jak vyhledám konkrétní text v dokumentu PDF?

 A: Můžete použít`TextFragmentAbsorber`třídy k vyhledání instancí konkrétní vyhledávací fráze v dokumentu PDF. Vytvořením instance této třídy a určením cílového textu můžete zachytit všechny výskyty tohoto textu.

#### Otázka: Mohu hledat text na všech stránkách dokumentu PDF?

 Odpověď: Ano, výukový program ukazuje, jak hledat text na všech stránkách dokumentu PDF. The`pdfDocument.Pages.Accept(textFragmentAbsorber)` metoda se používá k přijetí absorbéru pro všechny stránky, což vám umožňuje hledat požadovaný text na každé stránce.

#### Otázka: Jak získám přístup k fragmentům extrahovaného textu?

 Odpověď: Po vyhledání textu můžete získat přístup k extrahovaným textovým fragmentům pomocí`TextFragments` majetek z`TextFragmentAbsorber` objekt. Tato vlastnost poskytuje přístup ke sbírce`TextFragment` objekty, které obsahují extrahovaný text a související informace.

#### Otázka: Jaké informace mohu získat z extrahovaných textových fragmentů?

Odpověď: Z extrahovaných fragmentů textu můžete získat různé podrobnosti, jako je skutečný obsah textu, poloha (souřadnice X a Y), informace o písmu (název, velikost, barva atd.) a další. Ukázkový kód kurzu ukazuje, jak získat přístup k těmto podrobnostem a jak je vytisknout.

#### Otázka: Mohu s extrahovanými fragmenty textu provádět další akce?

A: Rozhodně. Jakmile budete mít extrahované fragmenty textu, můžete upravit kód ve smyčce a provádět vlastní akce s každým fragmentem. To může zahrnovat uložení extrahovaného textu, analýzu vzorů textu nebo použití změn formátování.