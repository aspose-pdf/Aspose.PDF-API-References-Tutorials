---
title: Prohledejte stránku textových segmentů v souboru PDF
linktitle: Prohledejte stránku textových segmentů v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vyhledávat textové segmenty na stránce v souboru PDF a získávat jejich vlastnosti pomocí Aspose.PDF for .NET.
type: docs
weight: 470
url: /cs/net/programming-with-text/search-text-segments-page/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF for .NET k vyhledávání specifických textových segmentů na stránce souboru PDF a získávání jejich vlastností. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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

## Krok 3: Nastavte cestu k adresáři dokumentů

 Nastavte cestu k adresáři dokumentů pomocí`dataDir` proměnná:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Načtěte dokument PDF

 Načtěte dokument PDF pomocí`Document` třída:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Nahradit`"SearchTextSegmentsPage.pdf"` se skutečným názvem vašeho souboru PDF.

## Krok 5: Vytvořte TextFragmentAbsorber

 Vytvořte a`TextFragmentAbsorber` objekt k nalezení všech výskytů vstupní vyhledávací fráze:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Nahradit`"text"` s požadovanou hledanou frází.

## Krok 6: Přijměte absorbér pro konkrétní stránku

Přijměte absorbér pro požadovanou stránku dokumentu:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Nahradit`2` s požadovaným číslem stránky (index založený na 1).

## Krok 7: Načtěte extrahované textové segmenty

 Získejte extrahované textové segmenty pomocí`TextFragments` vlastnictví`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 8: Procházejte segmenty textu

Procházejte načtené textové segmenty a získejte přístup k jejich vlastnostem:

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

Upravte kód ve smyčce, abyste v případě potřeby provedli další akce s každým textovým segmentem.

### Ukázkový zdrojový kód pro stránku Segmenty textu vyhledávání pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Vytvořte objekt TextAbsorber, abyste našli všechny výskyty vstupní hledané fráze
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Přijměte absorbér pro všechny stránky
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Projděte fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak vyhledávat konkrétní textové segmenty na stránce dokumentu PDF pomocí Aspose.PDF for .NET. Tento výukový program poskytl průvodce krok za krokem, od načtení dokumentu až po přístup k extrahovaným textovým segmentům. Nyní můžete tento kód začlenit do svých vlastních projektů C# a provádět pokročilé vyhledávání textových segmentů v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Vyhledat stránku textových segmentů v souboru PDF“?

Odpověď: Výukový program "Vyhledat stránku textových segmentů v souboru PDF" poskytuje komplexního průvodce, jak využít knihovnu Aspose.PDF pro .NET k vyhledávání konkrétních textových segmentů na konkrétní stránce dokumentu PDF. Pokrývá proces nastavení projektu, načítání dokumentu PDF, vyhledávání textových segmentů a získávání jejich vlastností pomocí kódu C#.

#### Otázka: Jak tento kurz pomáhá při hledání konkrétních textových segmentů v dokumentu PDF?

Odpověď: Tento výukový program demonstruje proces vyhledání a extrahování určitých textových segmentů na konkrétní stránce dokumentu PDF. Podle uvedených kroků a ukázek kódu mohou uživatelé efektivně vyhledávat požadované textové segmenty a získávat informace o jejich vlastnostech.

#### Otázka: Jaké předpoklady jsou vyžadovány pro sledování tohoto kurzu?

Odpověď: Než začnete s výukovým programem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej nainstalovat do svého projektu pomocí NuGet.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

A: Chcete-li začít, vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využívat funkce knihovny pro vyhledávání a práci s dokumenty PDF.

#### Otázka: Mohu tento výukový program použít k vyhledávání konkrétních textových segmentů na libovolné stránce PDF?

Odpověď: Ano, tento výukový program poskytuje pokyny, jak vyhledávat konkrétní textové segmenty na vybrané stránce dokumentu PDF. Vede uživatele k nastavení projektu, načtení PDF a použití knihovny Aspose.PDF k vyhledání a načtení vlastností požadovaných textových segmentů.

#### Otázka: Jak určím text, který chci v tomto tutoriálu hledat?

 A: Chcete-li zadat text, který chcete hledat, vytvořte a`TextFragmentAbsorber` objekt a nastavte jeho vyhledávací parametr pomocí`Text` vlastnictví. Nahradit výchozí`"text"` v kódu výukového programu s požadovanou vyhledávací frází.

#### Otázka: Jak získám vlastnosti extrahovaných textových segmentů?

Po přijetí`TextFragmentAbsorber` pro konkrétní stránku PDF můžete získat extrahované textové segmenty pomocí`TextFragments` vlastnost objektu absorbéru. To poskytuje přístup ke kolekci textových fragmentů, z nichž každý obsahuje více textových segmentů.

#### Otázka: Mohu upravit kód tak, aby prováděl další akce s každým textovým segmentem?

A: Rozhodně. Ukázkový kód výukového programu poskytuje smyčku pro iteraci načtených textových segmentů. Kód v této smyčce můžete přizpůsobit tak, aby prováděl další akce s každým textovým segmentem na základě požadavků vašeho projektu.

#### Otázka: Jak uložím upravený dokument PDF po extrahování segmentů textu?

Odpověď: Tento tutoriál se primárně zaměřuje na vyhledávání textových segmentů a získávání jejich vlastností. Pokud máte v úmyslu provést úpravy v PDF, můžete se podívat na další dokumentaci Aspose.PDF, kde se dozvíte, jak s dokumentem manipulovat a jak jej uložit na základě vašich specifických potřeb.