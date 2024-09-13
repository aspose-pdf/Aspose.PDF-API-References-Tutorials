---
title: Délka pomlčky
linktitle: Délka pomlčky
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přizpůsobit vzory čárových čárek v PDF pomocí Aspose.PDF for .NET s naším podrobným průvodcem. Ideální pro přidání stylu do vašich dokumentů.
type: docs
weight: 70
url: /cs/net/programming-with-graphs/dash-length/
---
## Zavedení

Chcete svým dokumentům PDF dodat nádech kreativity přizpůsobením čar s různými vzory čárek? S Aspose.PDF for .NET můžete snadno upravit styly čar tak, aby vyhovovaly potřebám vašeho dokumentu. V tomto tutoriálu prozkoumáme, jak upravit délku čárek v dokumentu PDF pomocí Aspose.PDF pro .NET. Ať už míříte na přerušovanou čáru nebo tečkovaný vzor, tato příručka vám poskytne nástroje a kroky nezbytné k dosažení požadovaného výsledku.

## Předpoklady

Než se pustíte do výukového programu, budete potřebovat několik věcí:

1. Aspose.PDF pro .NET: Ujistěte se, že máte nainstalovaný Aspose.PDF pro .NET. Pokud jste jej ještě nenainstalovali, můžete si jej stáhnout z[Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/).
2. Základní znalost C#: Tento tutoriál předpokládá, že máte základní znalosti o programování v C#. Pokud s C# začínáte, možná budete chtít nejprve oprášit základy.
3. Visual Studio: I když můžete použít libovolné IDE, tato příručka předpokládá, že používáte Visual Studio k psaní a spouštění kódu C#.
4.  Účet Aspose: Pro další zdroje a podporu se ujistěte, že máte účet u Aspose. Můžete se přihlásit na a[zkušební verze zdarma](https://releases.aspose.com/) nebo zakoupit licenci[zde](https://purchase.aspose.com/buy).

## Importujte balíčky

Chcete-li začít pracovat s Aspose.PDF pro .NET, budete muset importovat příslušné jmenné prostory. Můžete to udělat takto:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Tyto jmenné prostory zahrnují třídy a metody potřebné pro práci s dokumenty PDF, kresbami a čarami.

## Krok 1: Nastavte svůj projekt

Než začnete kódovat, nastavte nový projekt C# v sadě Visual Studio. Přidejte knihovnu Aspose.PDF for .NET do svého projektu pomocí NuGet nebo ručním odkazem na DLL. 

## Krok 2: Inicializujte dokument

Začněte vytvořením nového dokumentu PDF a přidáním stránky do něj. Toto je plátno, na které budete kreslit čáry.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancia dokumentu instance
Document doc = new Document();

// Přidat stránku do kolekce stránek objektu Document
Page page = doc.Pages.Add();
```

 Zde vytvoříme a`Document` objekt a přidejte nový`Page` k tomu. Tím vytvoříte základ pro kreslení čáry.

## Krok 3: Vytvořte objekt kreslení

 Dále vytvořte a`Graph` objekt, který představuje oblast, kde budete kreslit. Definujte si jeho rozměry podle svých požadavků.

```csharp
// Vytvořte nakreslený objekt s určitými rozměry
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// Přidejte nakreslený objekt do kolekce odstavců instance stránky
page.Paragraphs.Add(canvas);
```

 The`Graph` objekt funguje jako kontejner pro vaše prvky výkresu. Zde je nastavena na šířku 100 jednotek a výšku 400 jednotek.

## Krok 4: Definujte čáru

 Nyní je čas vytvořit`Line`objekt. Určete počáteční a koncový bod čáry a přizpůsobte její styl.

```csharp
// Vytvořit objekt Line
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

Tato čára začíná na souřadnicích (100, 100) a končí na (200, 100). Tyto souřadnice můžete upravit tak, aby vyhovovaly vašim konkrétním potřebám.

## Krok 5: Přizpůsobte styl čáry

Nastavte barvu a čárkovaný vzor čáry. Zde můžete nechat svou linii vyniknout.

```csharp
// Nastavte barvu pro objekt Line
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// Zadejte pole čárek pro objekt line
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Nastavte fázi pomlčky pro instanci Line
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: Nastaví barvu čáry. V tomto případě je to červená.
- `line.GraphInfo.DashArray` : Definuje vzor čárky. Zde,`{ 0, 1, 0 }` představuje čárkovaný vzor.
- `line.GraphInfo.DashPhase`: Upraví počáteční bod čárkovaného vzoru.

## Krok 6: Přidejte čáru do výkresu

 S nastylovanou čárou ji přidejte do`Graph` objekt.

```csharp
// Přidejte čáru do kolekce tvarů nakresleného objektu
canvas.Shapes.Add(line);
```

Tím se čára integruje do vašeho kreslicího plátna.

## Krok 7: Uložte dokument

Nakonec uložte dokument do zadané cesty. Zde se vytvoří soubor PDF.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// Uložit dokument PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

Tento řádek kódu uloží dokument PDF a poskytne potvrzovací zprávu, která uvádí, kam byl soubor uložen.

## Závěr

Přizpůsobení stylů čar v dokumentech PDF může vašim sestavám, prezentacím a dalším dokumentům dodat profesionální vzhled. Podle tohoto návodu jste se naučili, jak upravit délku čárek pomocí Aspose.PDF pro .NET. Ať už vytváříte jednoduché přerušované čáry nebo složitější vzory, Aspose.PDF poskytuje flexibilitu, kterou potřebujete, aby vaše dokumenty vynikly. Experimentujte s různými vzory a barvami čárek, abyste našli styl, který nejlépe vyhovuje vašim potřebám.

## FAQ

### Jak nainstaluji Aspose.PDF pro .NET?
 Můžete si jej nainstalovat přes NuGet ve Visual Studiu nebo si jej stáhnout z[Web Aspose](https://releases.aspose.com/pdf/net/).

### Mohu používat Aspose.PDF pro .NET zdarma?
 Ano, Aspose nabízí a[zkušební verze zdarma](https://releases.aspose.com/) takže si můžete vyzkoušet jeho funkce před zakoupením licence.

### Jaké další úpravy mohu provést na řádcích v PDF?
 Můžete upravit tloušťku čáry, barvu a vzory čárek. Viz[dokumentace](https://reference.aspose.com/pdf/net/) pro více podrobností.

### Jak mohu získat podporu, pokud narazím na problémy?
 K podpoře se můžete dostat přes[Fórum Aspose](https://forum.aspose.com/c/pdf/10).

### Kde si mohu zakoupit licenci pro Aspose.PDF pro .NET?
Můžete si zakoupit licenci[zde](https://purchase.aspose.com/buy).