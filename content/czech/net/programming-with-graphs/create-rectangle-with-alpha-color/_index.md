---
title: Vytvořit Obdélník S Alfa Barvou
linktitle: Vytvořit Obdélník S Alfa Barvou
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit obdélník s průhlednou barvou pomocí Aspose.PDF pro .NET. Podrobný průvodce přizpůsobením průhlednosti.
type: docs
weight: 60
url: /cs/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, abyste vytvořili obdélník s barvou alfa pomocí Aspose.PDF pro .NET.

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
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 3: Vytvoření objektu grafu a obdélníku

Vytvoříme objekt Graph se zadanými rozměry a obdélník s konkrétními rozměry.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Krok 4: Nastavení barvy alfa pro obdélník

Barvu alfa pro obdélník můžeme určit pomocí metody FromArgb třídy System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Krok 5: Přidání obdélníku do objektu grafu

Obdélník přidáme do kolekce tvarů objektu Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Krok 6: Vytvoření druhého obdélníku s jinou barvou alfa

Vytvoříme druhý obdélník s konkrétními rozměry a další barvou alfa.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Krok 7: Přidání objektu Graph na stránku

Přidáme objekt Graph do kolekce Odstavec objektu Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Krok 8: Uložení výsledného souboru PDF

Nakonec výsledný PDF soubor s názvem „CreateRectangleWithAlphaColor_out.pdf“ uložíme do zadaného adresáře.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Ukázka zdrojového kódu pro Create Rectangle With Alpha Color pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancia dokumentu instance
Document doc = new Document();
// Přidat stránku do kolekce stránek souboru PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Vytvořte instanci Graph
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Vytvořte obdélníkový objekt se specifickými rozměry
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Nastavte barvu výplně grafu ze struktury System.Drawing.Color z 32bitové hodnoty ARGB
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Přidejte obdélníkový objekt do kolekce tvarů instance Graph
canvas.Shapes.Add(rect);
// Vytvořte druhý obdélníkový objekt
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Přidejte instanci grafu do kolekce odstavců objektu stránky
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak vytvořit obdélník s barvou alfa pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k vytváření geometrických tvarů s průhlednými barvami v souborech PDF.

## FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem vytváření obdélníku s barvou alfa pomocí Aspose.PDF pro .NET. Dozvíte se, jak do souborů PDF přidat geometrické tvary s průhlednými barvami.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

A: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili vaše vývojové prostředí. Kromě toho se doporučuje základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: V poskytnutém zdrojovém kódu můžete upravit proměnnou "dataDir" tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jaký je účel objektu Graph a Rectangle?

Odpověď: Objekt Graph funguje jako kontejner pro prvky kreslení, zatímco obdélník představuje geometrický tvar, který budete přidávat do PDF.

#### Otázka: Jak mohu nastavit barvu alfa pro obdélník?

 A: Můžete určit barvu alfa pro obdélník pomocí`FillColor` majetek z`GraphInfo` objekt a`Color.FromRgb` metoda s hodnotou ARGB.

#### Otázka: Mohu vytvořit více obdélníků s různými barvami alfa?

Odpověď: Ano, můžete vytvořit více obdélníků s různými barvami alfa podle podobných kroků, jak je ukázáno v tutoriálu.

#### Otázka: Jak uložím výsledný soubor PDF po vytvoření obdélníků s barvami alfa?

 Odpověď: Po vytvoření obdélníků s barvami alfa můžete výsledný soubor PDF uložit pomocí`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` řádek v poskytnutém zdrojovém kódu.