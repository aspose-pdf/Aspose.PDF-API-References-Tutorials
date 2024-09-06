---
title: Přidat čárový objekt do souboru PDF
linktitle: Přidat čárový objekt do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat vlastní čárový objekt do souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 30
url: /cs/net/programming-with-graphs/add-line-object/
---
tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, jak přidat objekt řádku pomocí Aspose.PDF for .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit výsledný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření instance dokumentu a přidání stránky

Vytvoříme instanci třídy Document a do tohoto dokumentu přidáme stránku.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Vytvoření objektu Graph a jeho přidání na stránku

Vytvoříme objekt Graph se zadanými rozměry a přidáme jej do kolekce odstavců stránky.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Krok 4: Vytvořte čárový objekt a přidejte jej do grafu

Vytvoříme objekt Line se zadanými souřadnicemi a přidáme jej do kolekce tvarů grafu.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Krok 5: Nastavení linky

Můžeme zadat vlastnosti pro čáru, jako je typ čárky a fáze čárky.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Krok 6: Uložení souboru PDF

Nakonec výsledný PDF soubor s názvem „AddLineObject_out.pdf“ uložíme do zadaného adresáře.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Ukázkový zdrojový kód pro Add Line Object pomocí Aspose.PDF pro .NET 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Určete barvu výplně pro objekt Graph
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Přidejte obdélníkový objekt do kolekce tvarů objektu Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Závěr

tomto tutoriálu jsme krok za krokem vysvětlili, jak přidat čárový objekt pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k vytváření dokumentů PDF s vlastními řádky ve vašich aplikacích.

### Časté dotazy pro přidání čárového objektu do souboru PDF

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem přidávání čárového objektu pomocí Aspose.PDF for .NET pro vylepšení vašich dokumentů PDF.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

A: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili vaše vývojové prostředí. Kromě toho se doporučuje základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: V poskytnutém zdrojovém kódu můžete upravit proměnnou "dataDir" tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jaký je účel objektu Graph?

A: Objekt Graph slouží jako kontejner pro kreslení prvků. Je vytvořen se zadanými rozměry a přidán do kolekce odstavců stránky.

#### Otázka: Jak mohu přidat čárový objekt do dokumentu PDF?

Odpověď: Chcete-li přidat objekt linie, vytvořte instanci třídy Line se zadanými souřadnicemi a přidejte ji do kolekce tvarů grafu.

#### Otázka: Mohu přizpůsobit vzhled linky?

Odpověď: Ano, vzhled čáry můžete přizpůsobit nastavením vlastností, jako je typ čárky a fáze čárky, pomocí vlastnosti GraphInfo objektu Čára.

#### Otázka: Jaký je účel specifikace pole pomlčky a fáze pomlčky?

Odpověď: Vlastnosti pole pomlčky a fáze pomlčky umožňují vytvářet přerušované nebo tečkované čáry se specifickými vzory.

#### Otázka: Jak mohu uložit soubor PDF po přidání čárového objektu?

 Odpověď: Po přidání čárového objektu můžete výsledný soubor PDF uložit pomocí`doc.Save(dataDir + "AddLineObject_out.pdf");` řádek v poskytnutém zdrojovém kódu.

#### Otázka: Je k dispozici ukázkový zdrojový kód?

Odpověď: Ano, výukový program obsahuje ukázkový zdrojový kód, na který se můžete odkázat při implementaci popsaných kroků.