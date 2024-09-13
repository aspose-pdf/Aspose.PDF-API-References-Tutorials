---
title: Kreslení Linka
linktitle: Kreslení Linka
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se kreslit čáry v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento průvodce krok za krokem popisuje nastavení dokumentu, přidávání řádků a ukládání souboru.
type: docs
weight: 80
url: /cs/net/programming-with-graphs/drawing-line/
---
## Zavedení

Kreslení čar v dokumentu PDF se může zdát jako jednoduchý úkol, ale může to být mocný nástroj pro vytváření vizuálních pomůcek, diagramů a zdůraznění klíčových oblastí. V této příručce vás provedeme procesem kreslení čar v dokumentu PDF pomocí Aspose.PDF for .NET. Tento tutoriál pokryje vše od nastavení vašeho prostředí až po spuštění kódu pro vytvoření PDF s nakreslenými čarami.

## Předpoklady

Než se ponoříte do kódu, budete potřebovat několik věcí:

1.  Aspose.PDF pro .NET: Musíte mít nainstalovaný Aspose.PDF pro .NET. Můžete si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí .NET: Ujistěte se, že máte nastavené vývojové prostředí pro aplikace .NET. Visual Studio je pro to dobrou volbou.
3. Základní znalost C#: Pro pochopení úryvků kódu a příkladů v tomto tutoriálu vám pomůže znalost programování v C#.

## Importujte balíčky

Chcete-li pracovat s Aspose.PDF pro .NET, musíte importovat příslušné jmenné prostory. Přidejte následující pomocí direktivy v horní části souboru C#:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro manipulaci s dokumenty PDF a kreslení tvarů.

Rozdělme proces kreslení čar do série kroků. Každý krok vás provede konkrétní částí kódu a pomůže vám pochopit, jak dosáhnout požadovaného výsledku.

## Krok 1: Nastavte svůj dokument a stránku

Prvním krokem je vytvořit nový dokument PDF a přidat do něj stránku. Můžete to udělat takto:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořit instanci dokumentu
Document pDoc = new Document();

// Přidat stránku do kolekce stránek dokumentu PDF
Page pg = pDoc.Pages.Add();
```

 Zde,`dataDir` je cesta, kam se uloží vaše výstupní PDF.`Document` je hlavní třída pro práci s PDF a`Page` představuje jednu stránku v dokumentu PDF.

## Krok 2: Nakonfigurujte okraje stránky

Abyste zajistili, že se vaše čáry rozšíří od okraje k okraji, budete muset nastavit okraje stránky na nulu:

```csharp
// Nastavte okraj stránky na všech stranách na 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

Tím se odstraní všechny výchozí okraje a získáte celostránkové plátno pro kreslení.

## Krok 3: Vytvořte objekt Graph

 Dále vytvořte a`Graph` objekt, který odpovídá rozměrům stránky. Tento objekt bude sloužit jako kontejner pro vaše tvary:

```csharp
// Vytvořte objekt Graph se šířkou a výškou rovnou rozměrům stránky
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(pg.PageInfo.Width, pg.PageInfo.Height);
```

 The`Graph` objekt umožňuje přidávat a manipulovat s tvary na stránce.

## Krok 4: Nakreslete první řádek

Nyní je čas nakreslit první čáru. Tento příklad nakreslí čáru z levého dolního rohu do pravého horního rohu stránky:

```csharp
// Vytvořte objekt prvního řádku od levého dolního do pravého horního rohu stránky
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });

// Přidejte čáru do kolekce tvarů objektu Graph
graph.Shapes.Add(line);
```

 The`Line` třída bere souřadnice pro počáteční a koncový bod čáry. Zde,`pg.Rect.LLX` a`pg.Rect.URY` představují levý dolní a pravý horní roh stránky.

## Krok 5: Nakreslete druhou čáru

druhého řádku budeme kreslit z levého horního rohu do pravého dolního rohu:

```csharp
// Nakreslete čáru z levého horního rohu stránky do pravého dolního rohu stránky
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });

// Přidejte čáru do kolekce tvarů objektu Graph
graph.Shapes.Add(line2);
```

Tato čára bude protínat stránku diagonálně v opačném směru.

## Krok 6: Přidejte graf na stránku

 S nakreslenými čarami nyní musíte přidat`Graph` námitky proti kolekci odstavců stránky:

```csharp
// Přidejte objekt Graph do kolekce odstavců stránky
pg.Paragraphs.Add(graph);
```

 Tento krok integruje`Graph` objekt (s vašimi řádky) na stránku PDF.

## Krok 7: Uložte dokument

Nakonec uložte dokument do souboru:

```csharp
dataDir = dataDir + "DrawingLine_out.pdf";

// Uložit soubor PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);
```

 Tím se uloží PDF s nakreslenými čarami a`Console.WriteLine` prohlášení potvrzuje, že operace byla úspěšná.

## Závěr

Kreslení čar v dokumentu PDF pomocí Aspose.PDF for .NET je jednoduchý proces, jakmile jej rozdělíte do zvládnutelných kroků. Podle tohoto kurzu jste se naučili, jak nastavit dokument PDF, nakreslit přes něj čáry a uložit konečný produkt. Ať už vytváříte diagramy, zdůrazňujete text nebo jednoduše experimentujete s manipulací s PDF, tato příručka poskytuje solidní základ pro práci s čarami v PDF.

 Pokud máte nějaké dotazy nebo potřebujete další pomoc, neváhejte se obrátit na[Dokumentace Aspose.PDF](https://reference.aspose.com/pdf/net/) nebo navštivte[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10).

## FAQ

### Mohu kreslit různé tvary kromě čar?
 Ano, můžete kreslit různé tvary, jako jsou obdélníky, elipsy a mnohoúhelníky pomocí`Aspose.Pdf.Drawing` jmenný prostor.

### Jak upravím barvu a tloušťku čar?
 Můžete nastavit`Line` objektu`StrokeColor` a`LineWidth` vlastnosti pro přizpůsobení vzhledu vašich čar.

### Je možné kreslit čáry na určité oblasti stránky?
 Absolutně! Stačí upravit souřadnice`Line` objekt pro umístění čar podle potřeby.

### Mohu k řádkům přidat text?
 Ano, můžete přidat text vytvořením`TextFragment` předměty a jejich umístění do`Paragraphs` kolekce stránky.

### Co když chci přidat řádky do existujícího PDF místo vytváření nového?
 Stávající PDF můžete načíst pomocí`Document` a poté použijte podobné metody k přidání řádků na existující stránky.