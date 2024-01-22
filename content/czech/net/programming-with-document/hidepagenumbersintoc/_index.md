---
title: Skrýt čísla stránek v obsahu
linktitle: Skrýt čísla stránek v obsahu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se skrýt čísla stránek v obsahu pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce.
type: docs
weight: 220
url: /cs/net/programming-with-document/hidepagenumbersintoc/
---
V tomto článku budeme diskutovat o implementaci funkce Skrýt čísla stránek v obsahu Aspose.PDF pro .NET pomocí C#. Začneme krátkým úvodem do Aspose.PDF pro .NET a poté se ponoříme do podrobného průvodce implementací této funkce. 

## Úvod do Aspose.PDF pro .NET

Aspose.PDF for .NET je výkonná komponenta pro manipulaci s PDF, která umožňuje vývojářům vytvářet, upravovat a manipulovat soubory PDF programově. Poskytuje širokou škálu funkcí a funkcí, které usnadňují práci s dokumenty PDF. Aspose.PDF for .NET podporuje 32bitové i 64bitové operační systémy a lze jej použít s platformami .NET Framework, .NET Core a Xamarin. 

## Co je funkce Skrýt čísla stránek v obsahu?

Obsah (TOC) je nezbytnou součástí dokumentu PDF, který uživatelům poskytuje rychlý přehled o obsahu. Někdy mohou uživatelé chtít skrýt čísla stránek v obsahu, aby byl uživatelsky přívětivější. Aspose.PDF for .NET poskytuje vestavěnou funkci pro skrytí čísel stránek v obsahu. Tuto funkci lze použít k vytvoření uživatelsky přívětivějších dokumentů PDF. 

## Předpoklady

Abyste mohli postupovat podle tohoto návodu, budete potřebovat následující:

- Visual Studio 2010 nebo novější
- Aspose.PDF for .NET nainstalovaný ve vašem systému
- Základní znalost programovacího jazyka C#

## Podrobný průvodce implementací funkce Skrýt čísla stránek v obsahu

Při implementaci funkce Hide Page Numbers In TOC pomocí Aspose.PDF for .NET postupujte podle následujících kroků:

## Krok 1: Vytvořte novou konzolovou aplikaci C# v sadě Visual Studio

Otevřete Visual Studio a vytvořte novou konzolovou aplikaci C#.

## Krok 2: Přidejte odkaz na Aspose.PDF pro .NET

Klepněte pravým tlačítkem myši na složku Reference ve vašem projektu a vyberte Přidat odkaz. Přejděte do umístění, kde je na vašem systému nainstalován Aspose.PDF for .NET, a přidejte na něj odkaz.

## Krok 1: Vytvořte nový dokument PDF

Vytvořte nový dokument PDF pomocí následujícího kódu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Krok 2: Vytvořte stránku TOC

Vytvořte novou stránku obsahu a přidejte ji do dokumentu PDF pomocí následujícího kódu:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Krok 3: Přidejte sekci seznamu do kolekce sekcí dokumentu PDF

Přidejte sekci seznamu do kolekce sekcí dokumentu PDF pomocí následujícího kódu:

```csharp
tocPage.TocInfo = tocInfo;
```

## Krok 4: Definujte formát seznamu čtyř úrovní

Definujte formát seznamu čtyř úrovní nastavením levých okrajů a nastavení formátu textu každé úrovně pomocí následujícího kódu:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Krok 5: Přidejte do sekce čtyři nadpisy

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Příklad zdrojového kódu pro Hide Page Numbers in TOC pomocí Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Přidejte sekci seznamu do kolekce sekcí dokumentu Pdf
tocPage.TocInfo = tocInfo;
//Definujte formát seznamu čtyř úrovní nastavením levých okrajů a
//nastavení formátu textu každé úrovně

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Přidejte do oddílu čtyři nadpisy
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak pracovat s metadaty XMP v dokumentu PDF pomocí Aspose.PDF pro .NET. Metadata XMP poskytují cenné informace o dokumentu PDF, včetně jeho názvu, autora, data vytvoření a dalších. Aspose.PDF for .NET umožňuje vývojářům přistupovat a manipulovat s těmito metadaty a poskytuje flexibilní a výkonné API pro práci s dokumenty PDF.

### FAQ

#### Otázka: Co jsou metadata XMP v dokumentu PDF?

Odpověď: Metadata XMP (Extensible Metadata Platform) v dokumentu PDF jsou standardním formátem pro ukládání informací metadat o dokumentu. Obsahuje podrobnosti, jako je název dokumentu, autor, datum vytvoření, klíčová slova a další. Metadata XMP poskytují strukturovaný a standardizovaný způsob ukládání a sdílení informací o dokumentu PDF.

#### Otázka: Mohu upravit metadata XMP dokumentu PDF pomocí Aspose.PDF pro .NET?

 Odpověď: Ano, metadata XMP dokumentu PDF můžete upravit programově pomocí Aspose.PDF for .NET. Můžete přistupovat k`Info` vlastnictvím`Document` objekt, který vám umožňuje přístup k vlastnostem metadat XMP. Poté můžete aktualizovat hodnoty těchto vlastností a upravit metadata XMP dokumentu PDF.

#### Otázka: Mohu extrahovat vlastní vlastnosti metadat XMP z dokumentu PDF pomocí Aspose.PDF pro .NET?

 Odpověď: Ano, můžete extrahovat vlastní vlastnosti metadat XMP z dokumentu PDF pomocí Aspose.PDF pro .NET. Můžete použít`Metadata` vlastnictvím`Document`objekt, který poskytuje přístup ke všem vlastnostem metadat XMP dokumentu PDF. Poté můžete extrahovat uživatelské vlastnosti a použít jejich hodnoty podle potřeby.