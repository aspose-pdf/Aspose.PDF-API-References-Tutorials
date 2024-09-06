---
title: Kreslení Linka
linktitle: Kreslení Linka
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se nakreslit čáru přes stránku pomocí Aspose.PDF for .NET. Podrobný průvodce vytvářením vlastních čar.
type: docs
weight: 80
url: /cs/net/programming-with-graphs/drawing-line/
---
V tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, jak nakreslit čáru pomocí Aspose.PDF for .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit výsledný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření instance dokumentu a přidání stránky

Vytvoříme instanci třídy Document a do tohoto dokumentu přidáme stránku.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Krok 3: Nastavení okrajů stránky

Okraje stránky nastavíme na 0 na všech stranách.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Krok 4: Vytvoření objektu grafu a prvního řádku

Vytvoříme objekt Graph s rozměry rovnými rozměrům stránky a nakreslíme první čáru vedoucí z levého dolního rohu do pravého horního rohu stránky.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Krok 5: Nakreslete druhou čáru

Nakreslíme druhou čáru z levého horního rohu do pravého dolního rohu stránky.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Krok 6: Přidání objektu Graph na stránku

Do kolekce odstavců stránky přidáme objekt Graph.

```csharp
pg.Paragraphs.Add(graph);
```

## Krok 7: Uložení výsledného souboru PDF

Nakonec výsledný soubor PDF s názvem „DrawingLine_out.pdf“ uložíme do zadaného adresáře.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Ukázkový zdrojový kód pro Drawing Line pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořit instanci dokumentu
Document pDoc = new Document();
// Přidat stránku do kolekce stránek dokumentu PDF
Page pg = pDoc.Pages.Add();
// Nastavte okraj stránky na všech stranách na 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Vytvořte objekt Graph se šířkou a výškou rovnou rozměrům stránky
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Vytvořte objekt prvního řádku od levého dolního do pravého horního rohu stránky
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Přidejte čáru do kolekce tvarů objektu Graph
graph.Shapes.Add(line);
// Nakreslete čáru z levého horního rohu stránky do pravého dolního rohu stránky
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Přidejte čáru do kolekce tvarů objektu Graph
graph.Shapes.Add(line2);
// Přidejte objekt Graph do kolekce odstavců stránky
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Uložit soubor PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Závěr

tomto tutoriálu jsme vysvětlili, jak nakreslit čáru pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k vytváření geometrických tvarů s vlastními čarami v souborech PDF.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Účelem tohoto tutoriálu je provést vás procesem kreslení čar pomocí Aspose.PDF pro .NET. Dozvíte se, jak vytvořit čáry na stránce PDF a upravit jejich vzhled.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

Odpověď: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Doporučuje se také základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: Upravte proměnnou "dataDir" v poskytnutém zdrojovém kódu tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jak vytvořím čáry na stránce PDF?

Odpověď: Výukový program ukazuje vytvoření objektu Graph s rozměry stránky a následné přidání objektů Line. Upravte souřadnice a vlastnosti objektů Line, abyste vytvořili požadované čáry.

#### Otázka: Mohu přizpůsobit vzhled čar?

Odpověď: Ano, vzhled čar můžete upravit úpravou vlastností objektů Line. To zahrnuje změnu jejich souřadnic, barvy, tloušťky a dalších grafických atributů.

#### Otázka: Jak uložím dokument PDF po nakreslení čar?

 Odpověď: Po přidání objektu Graph s objekty Line na stránku můžete výsledný dokument PDF uložit pomocí`pDoc.Save(dataDir + "DrawingLine_out.pdf");` řádek v poskytnutém zdrojovém kódu.

#### Otázka: Mohu kreslit čáry s různými úhly a orientací?

Odpověď: Ano, můžete kreslit čáry s různými úhly a orientací úpravou souřadnic a vlastností objektů Line v grafu.