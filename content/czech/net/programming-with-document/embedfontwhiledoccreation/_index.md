---
title: Vložit písmo při vytváření dokumentu PDF
linktitle: Vložit písmo při vytváření dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vkládat písma do dokumentů PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce. Vylepšete vzhled svého PDF.
type: docs
weight: 140
url: /cs/net/programming-with-document/embedfontwhiledoccreation/
---
## Zavedení

Vytváření dokumentů PDF, které vypadají profesionálně a uhlazeně, je v dnešním digitálním světě zásadní. Jedním z klíčových aspektů dosažení tohoto uhlazeného vzhledu je zajištění správného vložení písem použitých ve vašem PDF. To nejen zachová vzhled vašeho dokumentu na různých zařízeních, ale také zlepší čitelnost. V tomto tutoriálu se ponoříme do toho, jak vkládat písma při vytváření dokumentů PDF pomocí Aspose.PDF pro .NET. 

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše, co potřebujete, abyste mohli začít:

1.  Aspose.PDF for .NET: Budete muset mít nainstalovanou knihovnu Aspose.PDF. Můžete si jej stáhnout z[webové stránky](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Vývojové prostředí, kde můžete psát a testovat svůj kód.
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.

## Importujte balíčky

Chcete-li ve svém projektu použít Aspose.PDF, musíte importovat potřebné jmenné prostory. Můžete to udělat takto:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Tyto jmenné prostory vám umožní přístup ke třídám a metodám potřebným pro vytváření a manipulaci s dokumenty PDF.

Nyní, když máme naše předpoklady vyřešené, pojďme si proces vkládání písem do dokumentu PDF rozdělit na zvládnutelné kroky.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte definovat cestu, kam se váš dokument PDF uloží. To je zásadní, protože to říká vaší aplikaci, kam uložit výstupní soubor.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"`se skutečnou cestou ve vašem systému, kam chcete soubor PDF uložit.

## Krok 2: Vytvořte instanci dokumentu Pdf

 Dále vytvoříte instanci souboru`Document` třída. Tato třída představuje váš dokument PDF.

```csharp
// Vytvořte instanci objektu Pdf voláním jeho prázdného konstruktoru
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Voláním prázdného konstruktoru vytvoříte nový, prázdný dokument PDF připravený pro obsah.

## Krok 3: Vytvořte stránku v dokumentu PDF

Nyní přidejte stránku do vašeho dokumentu PDF. Každý PDF potřebuje alespoň jednu stránku, takže tento krok je nezbytný.

```csharp
// Vytvořte sekci v objektu Pdf
Aspose.Pdf.Page page = doc.Pages.Add();
```

Tento řádek kódu přidá do dokumentu novou stránku a umožní vám začít přidávat obsah.

## Krok 4: Vytvořte textový fragment

 Chcete-li do souboru PDF přidat text, musíte vytvořit soubor`TextFragment`. Tento objekt bude obsahovat text, který chcete zobrazit.

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
```

 Zde inicializujeme nový`TextFragment`. Můžete si to představit jako kontejner pro váš text.

## Krok 5: Přidejte textové segmenty

Nyní vytvořte textový segment, který obsahuje skutečný text, který chcete zobrazit. Zde si můžete upravit text.

```csharp
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment("This is a sample text using Custom font.");
```

Text si klidně změňte na cokoliv chcete. Toto je váš obsah!

## Krok 6: Definujte stav textu a vložte písmo

 Abyste zajistili, že vaše písmo bude vloženo do PDF, musíte v souboru nastavit vlastnosti písma`TextState` objekt.

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
```

V tomto kódu určujeme, že chceme použít písmo Arial a že by mělo být vloženo do PDF. Toto je zásadní krok k zajištění toho, aby váš dokument vypadal na všech zařízeních stejně.

## Krok 7: Přidejte segment do fragmentu

Nyní, když máte svůj textový segment připravený, je čas jej přidat do textového fragmentu.

```csharp
fragment.Segments.Add(segment);
```

Tento řádek přidá segment k fragmentu, čímž se stane součástí textu, který se zobrazí na stránce.

## Krok 8: Přidejte fragment na stránku

Dále budete muset přidat fragment textu na stránku, kterou jste vytvořili dříve.

```csharp
page.Paragraphs.Add(fragment);
```

Tento krok zajistí, že se váš text objeví na stránce dokumentu PDF.

## Krok 9: Uložte dokument PDF

Konečně je čas uložit dokument PDF. Zadáte cestu, kam ji chcete uložit.

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);
```

Tento kód zřetězí název výstupního souboru s cestou k adresáři vašeho dokumentu a uloží PDF. 

## Závěr

A tady to máte! Úspěšně jste vytvořili dokument PDF s vloženými fonty pomocí Aspose.PDF pro .NET. Tento proces nejen zvyšuje vizuální přitažlivost vašich dokumentů, ale také zajišťuje, že si zachovají své formátování na různých platformách. 

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Proč bych měl do svého PDF vkládat písma?
Vkládání písem zajistí, že váš dokument bude vypadat stejně na všech zařízeních a zachová si svůj zamýšlený design a čitelnost.

### Mohu používat vlastní písma s Aspose.PDF?
Ano, můžete používat vlastní písma, pokud jsou k dispozici ve vašem systému a jsou správně uvedeny ve vašem kódu.

### Je k dispozici bezplatná zkušební verze pro Aspose.PDF?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[Aspose webové stránky](https://releases.aspose.com/).

### Kde najdu podporu pro Aspose.PDF?
 Podporu a dotazy můžete najít na[Aspose fórum](https://forum.aspose.com/c/pdf/10).