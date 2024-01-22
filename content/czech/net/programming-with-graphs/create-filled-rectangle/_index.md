---
title: Vytvořte vyplněný obdélník
linktitle: Vytvořte vyplněný obdélník
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit vyplněný obdélník pomocí Aspose.PDF pro .NET. Krok za krokem průvodce přizpůsobením barvy výplně.
type: docs
weight: 50
url: /cs/net/programming-with-graphs/create-filled-rectangle/
---
V tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, abyste vytvořili vyplněný obdélník pomocí Aspose.PDF for .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

## Krok 1: Nastavení adresáře dokumentů

poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit výsledný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření instance dokumentu a přidání stránky

Vytvoříme instanci třídy Document a do tohoto dokumentu přidáme stránku.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Vytvoření objektu grafu a jeho přidání na stránku

Vytvoříme objekt Graph se zadanými rozměry a přidáme jej do kolekce odstavců stránky.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Krok 4: Vytvořte obdélníkový objekt a přidejte jej do grafu

Vytvoříme objekt Rectangle se zadanými rozměry a přidáme jej do kolekce tvarů grafu.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Krok 5: Nastavení barvy výplně

Barvu výplně pro obdélník můžeme určit pomocí vlastnosti FillColor objektu GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Krok 6: Uložení výsledného souboru PDF

Nakonec výsledný soubor PDF s názvem „CreateFilledRectangle_out.pdf“ uložíme do zadaného adresáře.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Ukázka zdrojového kódu pro Create Filled Rectangle pomocí Aspose.PDF for .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořit instanci dokumentu
Document doc = new Document();
// Přidat stránku do kolekce stránek souboru PDF
Page page = doc.Pages.Add();
// Vytvořte instanci Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Přidejte objekt grafu do kolekce odstavců instance stránky
page.Paragraphs.Add(graph);
// Vytvořte instanci obdélníku
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Určete barvu výplně pro objekt Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Přidejte obdélníkový objekt do kolekce tvarů objektu Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak vytvořit vyplněný obdélník pomocí Aspose.PDF pro .NET. Tyto znalosti nyní můžete využít k vytváření geometrických tvarů s vlastními barvami výplně ve vašich souborech PDF.

## FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Účelem tohoto tutoriálu je provést vás procesem vytváření vyplněného obdélníku pomocí Aspose.PDF for .NET, což vám umožní přidávat do souborů PDF vlastní geometrické tvary s barvami výplně.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

A: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili vaše vývojové prostředí. Kromě toho se doporučuje základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: V poskytnutém zdrojovém kódu můžete upravit proměnnou "dataDir" tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jaký je účel objektu Graph?

A: Objekt Graph funguje jako kontejner pro prvky kreslení. Je vytvořen se zadanými rozměry a přidán do kolekce odstavců stránky.

#### Otázka: Jak mohu přidat vyplněný obdélník do dokumentu PDF?

Odpověď: Chcete-li přidat vyplněný obdélník, vytvořte instanci třídy Rectangle se zadanými rozměry a barvou výplně a přidejte ji do kolekce tvarů grafu.

#### Otázka: Mohu přizpůsobit rozměry a barvu výplně obdélníku?

 Odpověď: Ano, můžete upravit rozměry a barvu výplně obdélníku úpravou parametrů předávaných do`Aspose.Pdf.Drawing.Rectangle` konstruktor a nastavení vlastnosti FillColor.

#### Otázka: Jak uložím výsledný soubor PDF po vytvoření vyplněného obdélníku?

 Odpověď: Po vytvoření vyplněného obdélníku můžete výsledný soubor PDF uložit pomocí`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` řádek v poskytnutém zdrojovém kódu.