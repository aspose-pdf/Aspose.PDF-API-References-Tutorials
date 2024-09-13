---
title: Přidat kresbu s přechodovou výplní
linktitle: Přidat kresbu s přechodovou výplní
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat úžasné přechodové kresby do PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného průvodce, který je ideální pro vylepšení vizuálů dokumentů.
type: docs
weight: 20
url: /cs/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
## Zavedení

Vytváření vizuálně přitažlivých dokumentů je v dnešním digitálním světě zásadní. Jednou z pozoruhodných technik pro vylepšení vašich dokumentů PDF je přidávání kreseb s přechodovými výplněmi. Pokud chcete zlepšit své dovednosti v oblasti tvorby dokumentů, jste na správném místě! V této příručce vás provedu procesem použití Aspose.PDF pro .NET k přidání úžasné kresby s přechodem do vašeho PDF.

## Předpoklady

Než se ponoříme do toho nejnutnějšího, tady je několik věcí, které musíte mít na svém místě:

1.  Aspose.PDF for .NET Library: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF. Můžete to získat z[odkaz ke stažení](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Mějte nastavené vývojové prostředí .NET, jako je Visual Studio, kde můžete psát a spouštět svůj kód.
3. Základní porozumění C#: Znalost programování v C# vám usnadní sledování.

Jakmile budete mít všechny výše uvedené předpoklady připravené, vrhněme se na implementaci!

## Importujte balíčky

Nejprve musíte do projektu importovat požadované balíčky. Zde je postup:

- Otevřete svůj projekt C# ve Visual Studiu.
- Přidejte odkaz na knihovnu Aspose.PDF. Můžete to udělat pomocí Správce balíčků NuGet:
  
```csharp
using Aspose.Pdf.Drawing;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní si tento proces rozdělíme na stravitelné kroky. 

## Krok 1: Nastavte adresář dokumentů

Chcete-li začít, musíte pro své dokumenty nastavit cestu. To pomáhá při organizaci, kam uložit vytvořené soubory PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Nahraďte svou cestu k adresáři
```
 Tento řádek kódu vytváří proměnnou`dataDir` , která bude obsahovat cestu k adresáři, kam se uloží výstupní PDF. Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` s vaší skutečnou cestou k adresáři.

## Krok 2: Vytvořte nový dokument PDF

Dále vytvoříme nový dokument PDF pomocí knihovny Aspose.PDF.

```csharp
Document doc = new Document();
```
 Zde vytvoříme instanci a`Document` objekt. Tento objekt představuje váš dokument PDF a bude fungovat jako kontejner pro všechny prvky, které plánujete přidat.

## Krok 3: Přidejte stránku do dokumentu

Nyní, když máme náš dokument hotový, je čas přidat do něj stránku.

```csharp
Page page = doc.Pages.Add();
```
Tento řádek přidá do dokumentu novou stránku. Poskytuje prostor pro veškerou grafiku a text, které chcete zahrnout.

## Krok 4: Vytvořte grafický objekt

Pro kreslení tvarů musíme nejprve vytvořit grafickou plochu na stránce.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300.0, 300.0);
page.Paragraphs.Add(graph);
```
V tomto případě vytvoříme grafický objekt o šířce a výšce 300 jednotek. Přidáním do odstavců stránky položíme základy pro naše kresby.

## Krok 5: Definujte tvar obdélníku

Dále definujeme tvar obdélníku, který chceme vyplnit barvou přechodu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```
Zde vytvoříme obdélník začínající na souřadnicích (0,0) a přesahující 300 jednotek na šířku a výšku. Tento obdélník je poté přidán do našeho grafického objektu.

## Krok 6: Aplikujte přechodovou výplň na obdélník

Nyní přichází ta zábavná část! Na náš obdélník použijeme přechodovou výplň.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
    PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
    {
        Start = new Point(0, 0),
        End = new Point(300, 300)
    }
};
```
 V tomto bloku kódu určujeme barvu výplně obdélníku jako přechod od červené k modré. The`GradientAxialShading`třída umožňuje definici přechodové výplně, kde můžete určit počáteční a koncové body pro vytvoření hladkého přechodu mezi barvami.

## Krok 7: Uložte dokument PDF

Nakonec musíme náš dokument uložit do definovaného adresáře.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```
 Tento příkaz uloží váš PDF s konkrétním názvem do dříve definovaného`dataDir`. Výsledkem je nádherně zpracované PDF s obdélníkem vyplněným přechodem.

## Závěr

A tady to máte! Právě jste se naučili, jak přidat kresbu s přechodovou výplní do vašeho dokumentu PDF pomocí Aspose.PDF pro .NET. Není úžasné, jak pár řádků kódu dokáže přeměnit jednoduché PDF na něco vizuálně pozoruhodného? Ať už vytváříte sestavy, faktury nebo jakýkoli jiný dokument, použití grafiky může výrazně zlepšit čtenářský zážitek.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům programově vytvářet a manipulovat s dokumenty PDF.

### Mohu používat Aspose.PDF zdarma?
 Můžete začít s a[zkušební verze zdarma](https://releases.aspose.com/) prozkoumat jeho funkce, ale mohou existovat omezení použití.

### Kde najdu další dokumentaci?
Podrobná dokumentace je k dispozici na[Aspose PDF referenční stránku](https://reference.aspose.com/pdf/net/).

### Jak koupím Aspose.PDF?
 Knihovnu Aspose.PDF si můžete zakoupit prostřednictvím jejich[odkaz na nákup](https://purchase.aspose.com/buy).

### Co když potřebuji pomoc s používáním Aspose.PDF?
 Pokud narazíte na nějaké problémy, můžete vyhledat pomoc na[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10).