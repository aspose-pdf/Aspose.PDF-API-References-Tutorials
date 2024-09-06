---
title: Přizpůsobte si čísla stránek při přidávání obsahu
linktitle: Přizpůsobte si čísla stránek při přidávání obsahu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přizpůsobit čísla stránek při přidávání obsahu do dokumentů PDF pomocí Aspose.PDF for .NET v tomto komplexním kurzu.
type: docs
weight: 100
url: /cs/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Zavedení

Ve světě správy dokumentů kralují soubory PDF. Jedná se o výchozí formát pro sdílení a uchovávání dokumentů na různých platformách. Co se ale stane, když chcete vylepšit své dokumenty PDF funkcemi, jako je obsah (TOC)? To je místo, kde Aspose.PDF pro .NET přichází do hry! Tato výkonná knihovna umožňuje vývojářům snadno manipulovat se soubory PDF a umožňuje jim snadno přidávat, upravovat a přizpůsobovat obsah. V tomto tutoriálu se ponoříme do toho, jak upravit čísla stránek při přidávání obsahu do dokumentů PDF pomocí Aspose.PDF pro .NET. Takže popadněte svůj kódovací klobouk a můžeme začít!

## Předpoklady

Než se pustíme do kódu, je třeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Toto bude naše vývojové prostředí.
2. Aspose.PDF pro .NET: Musíte si stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete to najít[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.
4. Vzorový soubor PDF: Připravte si vzorový soubor PDF, se kterým můžeme pracovat. Můžete vytvořit jednoduchý soubor nebo si stáhnout existující PDF.

## Importujte balíčky

Abychom mohli začít, musíme importovat potřebné balíčky. Otevřete projekt sady Visual Studio a přidejte odkaz na knihovnu Aspose.PDF. Můžete to udělat pomocí NuGet Package Manager:

1. Klepněte pravým tlačítkem myši na svůj projekt v Průzkumníku řešení.
2. Vyberte „Spravovat balíčky NuGet“.
3. Vyhledejte "Aspose.PDF" a nainstalujte jej.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Jakmile máte knihovnu nainstalovanou, můžete začít kódovat!

## Krok 1: Nastavte adresář dokumentů

Nejprve musíme nastavit adresář dokumentů. Zde budeme ukládat naše vstupní a výstupní soubory PDF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

 tomto úryvku nahraďte`YOUR DOCUMENT DIRECTORY` se skutečnou cestou, kde jsou umístěny vaše soubory PDF. To nám pomůže načíst stávající PDF a uložit upravenou verzi.

## Krok 2: Načtěte existující soubor PDF

Nyní, když máme nastavený adresář dokumentů, načteme stávající soubor PDF. 

```csharp
Document doc = new Document(inFile);
```

 Zde vytvoříme nový`Document` objekt předáním cesty vstupního souboru. To nám umožňuje programově manipulovat s obsahem PDF.

## Krok 3: Vložte novou stránku pro obsah

Dále musíme vytvořit novou stránku v našem PDF, kde bude umístěn obsah.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Tento řádek vloží novou stránku na začátek dokumentu. Na této stránce se zobrazí TOC.

## Krok 4: Vytvořte informace o obsahu

Nyní vytvoříme objekt, který bude reprezentovat informace TOC.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 V tomto kroku vytvoříme a`TocInfo` objekt a nastavte jeho název na "Table Of Contents." Přizpůsobíme také velikost a styl písma. The`PageNumbersPrefix` je nastaveno na "P", což bude předčíslí stránek v obsahu.

## Krok 5: Přidejte nadpisy do obsahu

Nyní přichází ta zábavná část! Projdeme stránky dokumentu a přidáme nadpisy do našeho obsahu.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 V této smyčce vytvoříme nový`Heading` objekt pro každou stránku. Pro každý nadpis nastavíme cílovou stránku a určíme text, který se má zobrazit, což je „Stránka X“, kde X je číslo stránky. Nakonec přidáme nadpis na stránku TOC.

## Krok 6: Uložte aktualizovaný dokument

Po přidání všech potřebných nadpisů je čas uložit náš aktualizovaný dokument.

```csharp
doc.Save(outFile);
```

Tento řádek uloží upravené PDF s obsahem. Nyní můžete otevřít výstupní soubor a zobrazit svůj přizpůsobený obsah!

## Závěr

tady to máte! Úspěšně jste přizpůsobili čísla stránek při přidávání obsahu do vašeho dokumentu PDF pomocí Aspose.PDF for .NET. Tato výkonná knihovna usnadňuje manipulaci se soubory PDF a pomocí pouhých několika řádků kódu můžete své dokumenty výrazně vylepšit. Ať už vytváříte zprávy, elektronické knihy nebo jakýkoli jiný typ PDF, obsah obsahu může vašim čtenářům výrazně zlepšit navigaci. Tak na co čekáš? Ponořte se do Aspose.PDF a začněte vytvářet úžasné soubory PDF ještě dnes!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k prozkoumání funkcí knihovny. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Jak získám podporu pro Aspose.PDF?
 Podporu můžete získat návštěvou fóra Aspose[zde](https://forum.aspose.com/c/pdf/10).

### Je k dispozici dočasná licence?
 Ano, můžete požádat o dočasnou licenci pro Aspose.PDF[zde](https://purchase.aspose.com/temporary-license/).

### Kde si mohu koupit Aspose.PDF pro .NET?
 Můžete si zakoupit Aspose.PDF pro .NET[zde](https://purchase.aspose.com/buy).