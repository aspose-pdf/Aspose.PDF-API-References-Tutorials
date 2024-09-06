---
title: Hledat Text S Dot Net Regex
linktitle: Hledat Text S Dot Net Regex
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vyhledávat text pomocí regulárních výrazů .NET v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 480
url: /cs/net/programming-with-text/search-text-with-dot-net-regex/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k vyhledávání textu pomocí regulárních výrazů .NET v dokumentu PDF. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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

## Krok 4: Vytvořte objekt .NET Regex

 Vytvořte a`.NET Regex` objekt pro definování vyhledávacího vzoru:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 Nahradit`@"[\S]+"` s požadovaným vzorem regulárního výrazu.

## Krok 5: Načtěte dokument PDF

 Načtěte dokument PDF pomocí`Document` třída:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 Nahradit`"SearchTextRegex.pdf"` se skutečným názvem vašeho souboru PDF.

## Krok 6: Získejte konkrétní stránku

Získejte požadovanou stránku dokumentu:

```csharp
Page page = document.Pages[1];
```

 Nahradit`1` s požadovaným číslem stránky (index založený na 1).

## Krok 7: Vytvořte TextFragmentAbsorber

 Vytvořte a`TextFragmentAbsorber` objekt k nalezení všech instancí vstupního regulárního výrazu:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## Krok 8: Přijměte absorbér pro stránku

Přijměte absorbér pro stránku:

```csharp
page.Accept(textFragmentAbsorber);
```

## Krok 9: Načtěte extrahované fragmenty textu

Získejte extrahované fragmenty textu pomocí`TextFragments` majetek z`TextFragmentAbsorber` objekt:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## Krok 10: Procházejte fragmenty textu

Projděte načtené části textu a proveďte požadované akce:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

Upravte kód ve smyčce, abyste v případě potřeby provedli další akce s každým textovým fragmentem.

### Ukázka zdrojového kódu pro Search Text With Dot Net Regex pomocí Aspose.PDF pro .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořte objekt Regex, abyste našli všechna slova
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// Otevřete dokument
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// Získejte konkrétní stránku
Page page = document.Pages[1];
// Vytvořte objekt TextAbsorber a najděte všechny instance vstupního regulárního výrazu
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// Přijměte absorbér pro stránku
page.Accept(textFragmentAbsorber);
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Projděte fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## Závěr

Gratuluji! Úspěšně jste se naučili vyhledávat text pomocí regulárních výrazů .NET v dokumentu PDF pomocí Aspose.PDF for .NET. Tento tutoriál poskytl průvodce krok za krokem, od nastavení projektu až po přístup k extrahovaným fragmentům textu. Nyní můžete tento kód začlenit do svých vlastních projektů C# a provádět pokročilé vyhledávání textu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Vyhledat text pomocí Dot Net Regex“?

Odpověď: Výukový program "Search Text With Dot Net Regex" si klade za cíl vést uživatele k používání knihovny Aspose.PDF pro .NET k vyhledávání textu v dokumentu PDF pomocí regulárních výrazů .NET. Výukový program poskytuje podrobné pokyny a ukázky kódu C#, které demonstrují proces.

#### Otázka: Jak tento kurz pomáhá při hledání textu pomocí regulárních výrazů .NET v PDF?

Odpověď: Tento výukový program pomáhá uživatelům pochopit, jak využít možnosti Aspose.PDF pro .NET k vyhledávání textu pomocí regulárních výrazů .NET v dokumentu PDF. Podle poskytnutých kroků a příkladů kódu mohou uživatelé efektivně vyhledávat vzory textu, které odpovídají jejich zadaným regulárním výrazům.

#### Otázka: Jaké předpoklady jsou vyžadovány pro sledování tohoto kurzu?

Odpověď: Než začnete s výukovým programem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej nainstalovat do svého projektu pomocí NuGet.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

Odpověď: Pro začátek vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využívat funkce knihovny pro vyhledávání a práci s dokumenty PDF.

#### Otázka: Mohu použít tento tutoriál k vyhledání jakéhokoli konkrétního typu textu pomocí regulárních výrazů .NET?

 Odpověď: Ano, tento tutoriál poskytuje pokyny, jak vyhledávat text pomocí regulárních výrazů .NET v dokumentu PDF. Můžete si přizpůsobit`.NET Regex` objekt k definování konkrétního vyhledávacího vzoru, který chcete použít.

#### Otázka: Jak určím vzor regulárního výrazu .NET, který se má hledat v tomto kurzu?

 A: Chcete-li zadat vzor regulárního výrazu .NET, který chcete hledat, vytvořte a`.NET Regex` objekt a nastavte jeho vzor pomocí příslušné syntaxe regulárního výrazu. Nahradit výchozí`@"[\S]+"` v kódu výukového programu s požadovaným regulárním výrazem.

#### Otázka: Jak získám vlastnosti extrahovaných textových fragmentů?

 A: Po přijetí`TextFragmentAbsorber` pro konkrétní stránku PDF můžete získat fragmenty extrahovaného textu pomocí`TextFragments` vlastnost objektu absorbéru. To poskytuje přístup ke kolekci textových fragmentů, které odpovídají zadanému regulárnímu výrazu .NET.

#### Otázka: Mohu upravit kód tak, aby prováděl další akce s každým extrahovaným textovým fragmentem?

A: Určitě. Ukázkový kód výukového programu obsahuje smyčku pro iteraci načtených textových fragmentů. Kód v této smyčce můžete přizpůsobit tak, aby prováděl další akce s každým extrahovaným textovým fragmentem na základě požadavků vašeho projektu.

#### Otázka: Jak uložím upravený dokument PDF po extrahování fragmentů textu?

Odpověď: Tento tutoriál se primárně zaměřuje na vyhledávání textu pomocí regulárních výrazů .NET a načítání textových fragmentů. Pokud máte v úmyslu provést úpravy v PDF, můžete se podívat na další dokumentaci Aspose.PDF, kde se dozvíte, jak s dokumentem manipulovat a jak jej uložit na základě vašich specifických potřeb.