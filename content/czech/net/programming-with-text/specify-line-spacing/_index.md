---
title: Určete řádkování v souboru PDF
linktitle: Určete řádkování v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak určit řádkování v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 510
url: /cs/net/programming-with-text/specify-line-spacing/
---
Tento tutoriál vysvětluje, jak určit řádkování v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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
using System.IO;
```

## Krok 3: Nastavte cestu k adresáři dokumentů

 Nastavte cestu k adresáři dokumentů pomocí`dataDir` proměnná:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Načtěte vstupní soubor PDF

 Načtěte vstupní soubor PDF pomocí`Document` třída:

```csharp
Document doc = new Document();
```

## Krok 5: Vytvořte možnosti TextFormattingOptions

 Vytvořte a`TextFormattingOptions` objekt a nastavte režim řádkování na`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## Krok 6: Vytvořte TextFragment

 Vytvořte a`TextFragment` objekt a určete obsah textu:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## Krok 7: Načtěte soubor písma (volitelné)

 Pokud chcete pro text použít konkrétní písmo, načtěte soubor písma TrueType do souboru a`FileStream` objekt:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Nahradit`"HPSimplified.TTF"` se skutečným názvem souboru písma.

## Krok 8: Určete polohu textu a řádkování

 Nastavte polohu fragmentu textu a přiřaďte jej`TextFormattingOptions` k`TextState.FormattingOptions` vlastnictví:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## Krok 9: Přidejte text do dokumentu

 Přidejte textový fragment do dokumentu buď jeho připojením k a`TextBuilder` nebo přímo na stránku`Paragraphs` sbírka:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## Krok 10: Uložte výsledný dokument PDF

Uložte upravený dokument PDF:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Nezapomeňte vyměnit`"SpecifyLineSpacing_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázkový zdrojový kód pro specifikaci řádkování pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Načíst vstupní soubor PDF
Document doc = new Document();
//Vytvořte TextFormattingOptions s LineSpacingMode.FullSize
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Vytvořte objekt pro tvorbu textu pro první stránku dokumentu
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Vytvořte textový fragment s ukázkovým řetězcem
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	//Načtěte písmo TrueType do objektu streamu
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		// Nastavte název písma pro textový řetězec
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Určete pozici pro textový fragment
		textFragment.Position = new Position(100, 600);
		//Nastavit TextFormattingOptions aktuálního fragmentu na předdefinovaný (který ukazuje na LineSpacingMode.FullSize)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Přidejte text do TextBuilderu, aby jej bylo možné umístit přes soubor PDF
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Uložte výsledný dokument PDF
	doc.Save(dataDir);
}
```

## Závěr

Gratuluji! Úspěšně jste se naučili, jak určit řádkování v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento výukový program poskytuje podrobného průvodce, od nastavení projektu až po uložení upraveného dokumentu. Nyní můžete tento kód začlenit do svých vlastních projektů C# a přizpůsobit tak řádkování textu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Určit řádkování v souboru PDF"?

Odpověď: Výukový program "Určit řádkování v souboru PDF" má za cíl vést uživatele, jak používat knihovnu Aspose.PDF pro .NET k přizpůsobení řádkování textu v dokumentu PDF. Výukový program poskytuje podrobné pokyny a ukázky kódu C#, které demonstrují proces.

#### Otázka: Jak tento kurz pomáhá při určování řádkování v dokumentu PDF?

Odpověď: Tento výukový program pomáhá uživatelům pochopit, jak využít možnosti Aspose.PDF pro .NET k určení řádkování pro text v dokumentu PDF. Podle poskytnutých kroků a příkladů kódu mohou uživatelé upravit řádkování podle svých preferencí.

#### Otázka: Jaké předpoklady jsou vyžadovány pro sledování tohoto kurzu?

Odpověď: Než začnete s výukovým programem, měli byste mít základní znalosti programovacího jazyka C#. Navíc musíte mít nainstalovanou knihovnu Aspose.PDF for .NET. Můžete jej získat z webu Aspose nebo jej nainstalovat do svého projektu pomocí NuGet.

#### Otázka: Jak nastavím svůj projekt, aby následoval tento tutoriál?

A: Chcete-li začít, vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET. To vám umožní využít funkce knihovny pro práci s dokumenty PDF a přizpůsobení řádkování.

#### Otázka: Mohu použít tento tutoriál k určení řádkování pro jakýkoli typ textu?

Odpověď: Ano, tento tutoriál poskytuje pokyny, jak určit řádkování pro jakýkoli textový obsah v dokumentu PDF pomocí Aspose.PDF for .NET. Pomocí poskytnutých ukázek kódu můžete upravit řádkování textu podle svých potřeb.

#### Otázka: Jak ve výukovém programu určím režim řádkování?

 Odpověď: Tutoriál ukazuje, jak vytvořit a`TextFormattingOptions` objekt a nastavte jej`LineSpacing` majetek do`TextFormattingOptions.LineSpacingMode.FullSize`. Tento režim určuje plné řádkování pro obsah textu.

#### Otázka: Jak mohu načíst konkrétní písmo pro text?

 Odpověď: Pokud chcete pro textový obsah použít konkrétní písmo, výukový program poskytuje návod, jak načíst soubor písma TrueType do`FileStream` objekt a nastavte jej jako písmo pro`TextFragment`. To vám umožní přizpůsobit písmo textu spolu s jeho řádkováním.

#### Otázka: Jak přizpůsobím pozici textu v dokumentu PDF?

 A: Chcete-li upravit polohu textu, vytvořte a`TextFragment` objekt a nastavte jej`Position`vlastnost na požadované souřadnice (X a Y). To vám umožňuje řídit, kde je text v dokumentu PDF umístěn.

#### Otázka: Mohu použít tyto úpravy řádkování na existující dokumenty PDF?

 Odpověď: Ano, můžete upravit řádkování textu ve stávajících dokumentech PDF. Tutoriál ukazuje, jak vytvořit a`TextFragment` se zadaným řádkováním a pozicí a poté jej přidejte na stránku`Paragraphs` sbírka.