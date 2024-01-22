---
title: Přidat TOC do souboru PDF
linktitle: Přidat TOC do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat obsah do souboru PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce s ukázkovým zdrojovým kódem. Vylepšete navigaci v dokumentech!
type: docs
weight: 40
url: /cs/net/programming-with-document/addtoc/
---
V tomto tutoriálu prozkoumáme, jak použít funkci Přidat TOC (Table of Contents) do souboru PDF Aspose.PDF for .NET k přidání obsahu do dokumentů PDF. Poskytneme průvodce krok za krokem a vysvětlíme zdrojový kód C# potřebný k dosažení tohoto cíle. Na konci tohoto tutoriálu budete schopni vygenerovat dokument PDF s obsahem pomocí Aspose.PDF pro .NET.


## Krok 1: Načtěte existující soubor PDF

 Abychom mohli začít, musíme načíst existující soubor PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` v následujícím kódu se skutečnou cestou k vašemu souboru PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Krok 2: Vytvořte novou stránku pro obsah

Vytvoříme novou stránku s obsahem. Následující kód vloží novou stránku na index 1:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Krok 3: Definujte informace o obsahu

Dále musíme definovat informace o obsahu. Nastavíme nadpis a další vlastnosti obsahu. Přidejte následující kód:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Krok 4: Vytvořte prvky TOC

Nyní vytvoříme prvky obsahu. V tomto tutoriálu vytvoříme čtyři prvky TOC odpovídající různým stránkám. Upravte následující kód podle svých požadavků:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Krok 5: Uložte aktualizovaný dokument

 Nakonec musíme upravený dokument uložit s obsahem. Nahradit`"YOUR DOCUMENT DIRECTORY"` v níže uvedeném kódu s požadovanou cestou výstupního souboru:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Příklad zdrojového kódu pro přidávání obsahu do dokumentů PDF pomocí Aspose.PDF pro .NET

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubory PDF
Document doc = new Document(dataDir + "AddTOC.pdf");

// Získejte přístup k první stránce souboru PDF
Page tocPage = doc.Pages.Insert(1);

// Vytvořte objekt, který bude reprezentovat informace TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Nastavte název pro TOC
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Vytvořte řetězcové objekty, které budou použity jako prvky TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Vytvořit objekt nadpisu
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Zadejte cílovou stránku pro objekt nadpisu
	heading2.DestinationPage = doc.Pages[i + 2];

	// Cílová stránka
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Souřadnice cíle
	segment2.Text = titles[i];

	// Přidejte nadpis na stránku obsahující TOC
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Uložte aktualizovaný dokument
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak přidat obsah (TOC) do dokumentů PDF pomocí Aspose.PDF pro .NET. Podle podrobného průvodce a pomocí dodaného zdrojového kódu C# můžete snadno vygenerovat dokument PDF s obsahem. Obsah zlepšuje použitelnost dokumentu a umožňuje uživatelům efektivněji procházet konkrétní sekce nebo stránky. Aspose.PDF for .NET poskytuje robustní a uživatelsky přívětivé řešení pro práci se soubory PDF v aplikacích .NET, které vám umožňuje snadno vytvářet dynamické a interaktivní dokumenty PDF.

### Časté dotazy pro přidání obsahu do souboru PDF

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům efektivně pracovat se soubory PDF v aplikacích .NET. Poskytuje širokou škálu funkcí pro vytváření, manipulaci a správu dokumentů PDF programově.

#### Otázka: Jaký je účel přidání obsahu (TOC) do dokumentu PDF?

Odpověď: Obsah (TOC) poskytuje uživatelům navigační pomůcku, která jim umožňuje rychle přejít na určité části nebo stránky v dokumentu PDF. Zlepšuje použitelnost dokumentu a uživatelskou zkušenost.

#### Otázka: Jak přidám obsah do dokumentu PDF pomocí Aspose.PDF pro .NET?

A: Chcete-li přidat obsah do dokumentu PDF pomocí Aspose.PDF pro .NET, musíte vytvořit novou stránku, která bude obsahovat obsah, definovat informace o obsahu a poté vytvořit prvky obsahu, které odpovídají konkrétním stránkám nebo oddíly v dokumentu.

#### Otázka: Mohu přizpůsobit vzhled obsahu?

Odpověď: Ano, vzhled obsahu můžete přizpůsobit nastavením různých vlastností prvků TOC, jako je velikost písma, styl písma a zarovnání. Aspose.PDF for .NET poskytuje flexibilitu při navrhování obsahu tak, aby odpovídal vašemu požadovanému vzhledu a dojmu.

#### Otázka: Je Aspose.PDF for .NET vhodný pro přidávání pokročilých funkcí do dokumentů PDF?

Odpověď: Rozhodně, Aspose.PDF for .NET je knihovna bohatá na funkce, která vám umožňuje přidávat do dokumentů PDF pokročilé funkce, včetně interaktivních prvků, polí formulářů, digitálních podpisů a dalších.