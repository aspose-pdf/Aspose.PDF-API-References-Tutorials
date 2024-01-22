---
title: Přidat dětskou záložku do souboru PDF
linktitle: Přidat dětskou záložku do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno přidejte podřízenou záložku do souboru PDF pro lépe organizované procházení s Aspose.PDF pro .NET.
type: docs
weight: 20
url: /cs/net/programming-with-bookmarks/add-child-bookmark/
---
Přidání podřízených záložek do souboru PDF umožňuje strukturovanější organizaci a navigaci. S Aspose.PDF pro .NET můžete snadno přidat podzáložku podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, do kterého chcete přidat dílčí záložku. Nahradit`"YOUR DOCUMENT DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otevřete dokument PDF

Nyní otevřeme dokument PDF, do kterého chceme přidat podzáložku, pomocí následujícího kódu:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Krok 4: Vytvořte nadřazený objekt záložky

 V tomto kroku vytvoříme nadřazený objekt záložky pomocí`OutlineItemCollection` třídy a nastavte její vlastnosti, jako je nadpis, atribut kurzíva a atribut tučného písma. Zde je odpovídající kód:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Krok 5: Vytvořte objekt podřízené záložky

 tomto kroku opět vytvoříme objekt podzáložky pomocí`OutlineItemCollection` třídy a nastavte její vlastnosti. Zde je odpovídající kód:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Krok 6: Přidejte podzáložku k nadřazené záložce

 Nakonec přidáme vytvořenou podzáložku do kolekce podzáložek nadřazené záložky pomocí`Add` metoda nadřazeného objektu. Zde je odpovídající kód:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Krok 7: Přidejte nadřazenou záložku do kolekce záložek dokumentu

 Nakonec přidáme nadřazenou záložku do kolekce záložek dokumentu pomocí`Add` metoda`Outlines` vlastnictví. Zde je odpovídající kód:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Ukázkový zdrojový kód pro Add Child Bookmark pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Vytvořte nadřazený objekt záložky
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Vytvořte podřízený objekt záložky
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Přidat podřízenou záložku do sbírky nadřazených záložek
pdfOutline.Add(pdfChildOutline);
// Přidejte nadřazenou záložku do kolekce osnovy dokumentu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Uložit výstup
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce přidáním podzáložky s Aspose.PDF pro .NET. Tento kód můžete použít k uspořádání a strukturování záložek v dokumentech PDF.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích manipulace se záložkami.

### Časté dotazy pro přidání dětské záložky do souboru PDF

#### Otázka: Co jsou podřízené záložky v souboru PDF?

Odpověď: Podřízené záložky, známé také jako dílčí záložky, jsou navigační prvky v dokumentu PDF, které jsou hierarchicky strukturovány pod nadřazenou záložkou. Poskytují způsob, jak vytvořit uspořádanější a podrobnější obsah dokumentu.

#### Otázka: Jak naimportuji potřebné knihovny pro můj projekt C#?

Odpověď: Chcete-li importovat požadované knihovny pro váš projekt C#, můžete použít následující importní direktivu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Tyto knihovny poskytují potřebné třídy a funkce pro práci s dokumenty PDF a interaktivní funkce.

#### Otázka: Jak určím cestu ke složce dokumentů?

 Odpověď: V poskytnutém zdrojovém kódu je třeba nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou ke složce obsahující soubor PDF, se kterým chcete pracovat. To zajistí, že kód správně najde cílový soubor PDF.

#### Otázka: Mohu vytvořit více úrovní podřízených záložek?

Odpověď: Ano, můžete vytvořit více úrovní podřízených záložek rozšířením procesu popsaného ve výukovém programu. Vytvořením nadřazených záložek s dílčími záložkami a jejich dalším vnořením můžete vytvořit hierarchickou strukturu záložek pro složité dokumenty PDF.

####  Otázka: Jaký je účel`OutlineItemCollection` class?

 A:`OutlineItemCollection` třída v Aspose.PDF pro .NET se používá k vytváření a správě obrysů, což jsou v podstatě záložky v dokumentu PDF. Tato třída vám umožňuje nastavit vlastnosti, jako je název, styl písma a akce pro záložky.

#### Otázka: Jak přidám podzáložku k nadřazené záložce?

 Odpověď: Chcete-li přidat podzáložku k nadřazené záložce, vytvořte novou`OutlineItemCollection` objekt pro podzáložku a nastavte její vlastnosti. Poté použijete`Add` metoda nadřazené záložky`OutlineItemCollection` přidat podzáložku do rodičovské sbírky.

#### Otázka: Mohu přizpůsobit vzhled podřízených záložek?

Odpověď: Ano, podobně jako u nadřazených záložek můžete upravit vzhled podřízených záložek nastavením vlastností, jako je nadpis, styl písma a další atributy. To vám umožní vytvářet vizuálně výrazné a informativní záložky.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s jinými programovacími jazyky?

A: Aspose.PDF pro .NET je speciálně navržen pro prostředí C# a .NET. Aspose však nabízí podobné knihovny pro jiné programovací jazyky, jako je Java a Android, z nichž každý je přizpůsoben jejich příslušným platformám.

#### Otázka: Jak podřízené záložky vylepšují navigaci PDF?

Odpověď: Podřízené záložky zlepšují navigaci PDF tím, že poskytují strukturovanější a organizovanější obsah. Uživatelé mohou rychle přistupovat ke konkrétním částem dokumentu prostřednictvím hierarchické struktury záložek.