---
title: Přidat kresbu s přechodovou výplní
linktitle: Přidat kresbu s přechodovou výplní
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat kresbu s přechodovou výplní pomocí Aspose.PDF pro .NET. Návod krok za krokem k vytváření atraktivních dokumentů PDF.
type: docs
weight: 20
url: /cs/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
V tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, jak přidat kresbu s přechodovou výplní do programování s grafikou pomocí Aspose.PDF for .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit výsledný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření instance objektu dokumentu a přidání stránky

Vytvoříme instanci třídy Document a do tohoto dokumentu přidáme stránku.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Vytvoření objektu grafu a jeho přidání na stránku

Vytvoříme objekt Graph se zadanými rozměry a přidáme jej do kolekce odstavců stránky.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## Krok 4: Vytvořte obdélníkový objekt a přidejte jej do grafu

Vytvoříme objekt Rectangle se zadanými rozměry a přidáme jej do kolekce tvarů grafu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## Krok 5: Konfigurace přechodové výplně

Přechodovou výplň pro obdélník nakonfigurujeme pomocí třídy GradientAxialShading.

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

Tím se vytvoří přechodová výplň od červené k modré, od bodu (0, 0) k bodu (300, 300).

## Krok 6: Uložení souboru PDF

Nakonec výsledný PDF soubor s názvem "AddDrawingWithGradientFill_out.pdf" uložíme do zadaného adresáře.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Ukázkový zdrojový kód pro Add Drawing With Gradient Fill pomocí Aspose.PDF for .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Závěr

V tomto tutoriálu jsme krok za krokem vysvětlili, jak přidat kresbu s přechodovou výplní do programování s grafikou pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k vytváření atraktivních dokumentů PDF s vlastními návrhy a přechodovými výplněmi.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem přidávání výkresu s přechodovou výplní do programování s grafikou pomocí Aspose.PDF pro .NET.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

A: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili vaše vývojové prostředí. Kromě toho se doporučuje základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: V poskytnutém zdrojovém kódu můžete změnit hodnotu proměnné "dataDir" tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jaký je účel objektu Graph?

A: Objekt Graph slouží jako kontejner pro prvky výkresu. Je vytvořen se zadanými rozměry a přidán do kolekce odstavců stránky.

#### Otázka: Jak mohu nakonfigurovat přechodovou výplň pro tvar?

Odpověď: Chcete-li nakonfigurovat přechodovou výplň, můžete nastavit vlastnost FillColor GraphInfo tvaru pomocí třídy GradientAxialShading. To vám umožní definovat počáteční a koncové body přechodu a barvy, mezi kterými se bude přecházet.

#### Otázka: Mohu přizpůsobit barvy a směr přechodové výplně?

Odpověď: Ano, můžete přizpůsobit barvy a směr přechodové výplně úpravou objektů Color a určením počátečního a koncového bodu GradientAxialShading.

#### Otázka: Jaký je poslední krok tutoriálu?

Odpověď: Poslední krok zahrnuje uložení výsledného souboru PDF s názvem "AddDrawingWithGradientFill_out.pdf" do určeného adresáře.

#### Otázka: Je k dispozici ukázkový zdrojový kód?

Odpověď: Ano, výukový program poskytuje ukázkový zdrojový kód, který můžete použít jako referenci k implementaci popsaných kroků.

#### Otázka: Mohu použít přechodovou výplň na jiné tvary kromě obdélníků?

Odpověď: Ano, přechodovou výplň můžete použít i na jiné tvary. Proces zahrnuje konfiguraci vlastnosti FillColor GraphInfo tvaru pomocí třídy GradientAxialShading.