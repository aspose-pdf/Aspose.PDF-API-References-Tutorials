---
title: Přizpůsobte si čísla stránek při přidávání obsahu
linktitle: Přizpůsobte si čísla stránek při přidávání obsahu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přizpůsobit čísla stránek při přidávání obsahu (TOC) pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce a příkladu kódu.
type: docs
weight: 100
url: /cs/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
V tomto tutoriálu prozkoumáme, jak přizpůsobit čísla stránek při přidávání obsahu (TOC) pomocí Aspose.PDF pro .NET. Poskytneme vám podrobné pokyny spolu s příkladem kódu, které vám pomohou toho dosáhnout.

## Krok 1: Načtení existujícího souboru PDF

Nejprve musíme načíst existující soubor PDF. Pro tento tutoriál použijeme soubor "42824.pdf" umístěný v adresáři "VAŠE DOKUMENTY ADRESÁŘ". Nahraďte tuto cestu k adresáři skutečnou cestou k adresáři vašeho dokumentu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Krok 2: Přidání stránky TOC

 Dále musíme na začátek dokumentu přidat novou stránku, která bude sloužit jako TOC stránka. Toho můžeme dosáhnout pomocí`Insert()` metoda`Pages` sbírka`Document` objekt.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Krok 3: Vytvoření objektu TOC

 Chcete-li vytvořit objekt TOC, musíme nejprve vytvořit a`TocInfo` objekt a nastavit jeho vlastnosti. V tomto tutoriálu nastavíme název obsahu na "Table Of Contents" a předponu čísla stránky na "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Krok 4: Vytvoření položek TOC

Chcete-li vytvořit položky TOC, musíme projít všechny stránky dokumentu, kromě stránky TOC, a vytvořit objekt nadpisu pro každou stránku. Poté můžeme přidat objekt nadpisu na stránku TOC a určit jeho cílovou stránku.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Vytvořit objekt nadpisu
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Zadejte cílovou stránku pro objekt nadpisu
    heading2.DestinationPage = doc.Pages[i + 1];
    // Cílová stránka
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Souřadnice cíle
    segment2.Text = "Page " + i.ToString();
    // Přidejte nadpis na stránku obsahující TOC
    tocPage.Paragraphs.Add(heading2);
}
```

## Krok 5: Uložení aktualizovaného dokumentu

Nakonec musíme aktualizovaný dokument uložit do nového souboru. Toho můžeme dosáhnout pomocí`Save()` metoda`Document` objekt.

```csharp
doc.Save(outFile);
```

### Příklad zdrojového kódu pro přizpůsobení čísel stránek při přidávání obsahu pomocí Aspose.PDF pro .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Načtěte existující soubory PDF
Document doc = new Document(inFile);
// Získejte přístup k první stránce souboru PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Vytvořte objekt, který bude reprezentovat informace TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Nastavte název pro TOC
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Vytvořit objekt nadpisu
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Zadejte cílovou stránku pro objekt nadpisu
	heading2.DestinationPage = doc.Pages[i + 1];
	// Cílová stránka
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Souřadnice cíle
	segment2.Text = "Page " + i.ToString();
	// Přidejte nadpis na stránku obsahující TOC
	tocPage.Paragraphs.Add(heading2);
}

// Uložte aktualizovaný dokument
doc.Save(outFile);
```

## Závěr

V tomto tutoriálu jsme poskytli podrobné pokyny, jak přizpůsobit čísla stránek při přidávání obsahu pomocí Aspose.PDF pro .NET. Poskytli jsme také příklad kódu, který můžete použít jako referenci při implementaci této funkce ve svém

### FAQ

#### Otázka: Co je obsah (TOC) v dokumentu PDF?

Odpověď: Obsah (TOC) v dokumentu PDF je navigační pomůcka, která poskytuje uspořádaný seznam oddílů nebo kapitol dokumentu spolu s odpovídajícími čísly stránek. Umožňuje čtenářům rychle přejít na konkrétní části dokumentu.

#### Otázka: Proč bych měl chtít přizpůsobit čísla stránek v obsahu?

Odpověď: Přizpůsobení čísel stránek v obsahu může být užitečné, když chcete použít konkrétní formát číslování stránek nebo zahrnout další informace spolu s čísly stránek. Umožňuje vám vytvořit personalizovanější a informativnější obsah.

#### Otázka: Mohu do obsahu obsahu zahrnout hypertextové odkazy, které odkazují na konkrétní sekce nebo stránky v dokumentu PDF?

Odpověď: Ano, Aspose.PDF for .NET vám umožňuje vytvářet hypertextové odkazy v obsahu, které odkazují na konkrétní sekce nebo stránky v dokumentu PDF. To zlepšuje interaktivitu a navigaci dokumentu PDF.

#### Otázka: Je Aspose.PDF for .NET kompatibilní se standardy PDF/A?

Odpověď: Ano, Aspose.PDF for .NET podporuje standardy PDF/A, včetně PDF/A-1, PDF/A-2 a PDF/A-3. Umožňuje vytvářet dokumenty PDF, které splňují požadavky na archivaci a dlouhodobé uchování.

#### Otázka: Mohu přidat další formátování položek obsahu, jako jsou styly písma nebo barvy?

Odpověď: Ano, k položkám obsahu můžete přidat další formátování, jako jsou styly písma, barvy a velikosti písma, pomocí Aspose.PDF pro .NET. To vám umožní upravit vzhled TOC podle vašich požadavků.
