---
title: Nastavit ohraničení v PDF do tabulky
linktitle: Nastavit ohraničení v PDF do tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit ohraničení tabulky v PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 200
url: /cs/net/programming-with-tables/set-border/
---
V tomto tutoriálu vás krok za krokem provedeme nastavením ohraničení v tabulce dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat.

## Krok 1: Vytvoření instance objektu dokumentu
Nejprve vytvoříme instanci objektu Document:

```csharp
Document doc = new Document();
```

## Krok 2: Přidání stránky do dokumentu PDF
Dále do dokumentu PDF přidáme stránku:

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Vytvoření objektu BorderInfo
Nyní vytvoříme objekt BorderInfo, který definuje hranici tabulky:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## Krok 4: Určení horního a dolního okraje
Zadáme, že horní a dolní ohraničení bude dvojité:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## Krok 5: Vytvoření instance objektu Table
Nyní vytvoříme instanci objektu Table:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## Krok 6: Určení šířky sloupců
Zadáme šířky sloupců tabulky:

```csharp
table. ColumnWidths = "100";
```

## Krok 7: Vytvoření objektu řádku
Vytvoříme objekt Row:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## Krok 8: Přidání buňky do řádku
Dále do řádku přidáme buňku:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## Krok 9: Nastavení ohraničení buňky
Budeme definovat hranici buňky (dvojité ohraničení):

```csharp
cell. Border = border;
```

## Krok 10: Přidání tabulky na stránku
Nyní přidáme tabulku na stránku dokumentu:

```csharp
page.Paragraphs.Add(table);
```

## Krok 11: Uložte dokument PDF
Nakonec dokument PDF uložíme:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Příklad zdrojového kódu pro Set Border pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objekt okamžitého dokumentu
Document doc = new Document();
// Přidat stránku do dokumentu PDF
Page page = doc.Pages.Add();
// Vytvořte objekt BorderInfo
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Určete, že horní okraj bude dvojitý
border.Top.IsDoubled = true;
// Určete, že spodní okraj bude dvojitý
border.Bottom.IsDoubled = true;
// Okamžitá tabulka objektu
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Zadejte informace o šířce sloupců
table.ColumnWidths = "100";
// Vytvořit objekt řádku
Aspose.Pdf.Row row = table.Rows.Add();
// Přidejte buňku tabulky do kolekce buněk řádku
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Nastavit ohraničení pro objekt buňky (dvojité ohraničení)
cell.Border = border;
// Přidejte tabulku do kolekce odstavců stránky
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Uložte dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Závěr
gratuluji! Nyní jste se naučili, jak nastavit ohraničení v tabulce dokumentu PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce vám ukázal, jak vytvořit dokument, přidat stránku, nakonfigurovat ohraničení tabulky a uložit dokument PDF. Nyní můžete tyto znalosti aplikovat na své vlastní projekty.

### FAQ

#### Otázka: Mohu nastavit různé styly ohraničení (např. přerušované nebo tečkované) pro horní a dolní ohraničení tabulky?

 Odpověď: Ano, můžete nastavit různé styly ohraničení pro horní a dolní ohraničení tabulky úpravou`border.Top.Style` a`border.Bottom.Style`vlastnosti v poskytnutém zdrojovém kódu C#. Aspose.PDF pro .NET vám umožňuje vybrat si z různých stylů ohraničení, včetně plného, čárkovaného, tečkovaného, dvojitého a dalších.

#### Otázka: Jak mohu nastavit barvu okraje tabulky?

 A: Můžete nastavit barvu okraje tabulky úpravou`border.Color` vlastnost ve zdrojovém kódu C#. Jednoduše poskytněte požadovanou barvu, jako je např`Aspose.Pdf.Color.Red` nebo jakékoli jiné platné barevné znázornění pro přizpůsobení barvy ohraničení.

#### Otázka: Je možné použít ohraničení na jednotlivé buňky v tabulce s různým nastavením (např. různé barvy nebo styly ohraničení)?

 Odpověď: Ano, můžete použít ohraničení na jednotlivé buňky v tabulce s různým nastavením pomocí konfigurace`cell.Border` vlastnost pro každou buňku jednotlivě. To vám umožní mít styly a barvy ohraničení specifické pro buňku na základě vašich požadavků.

#### Otázka: Mohu odstranit ohraničení z určitých stran tabulky (např. levé a pravé ohraničení)?

 Odpověď: Ano, můžete odstranit ohraničení z určitých stran tabulky úpravou`border.Left`, `border.Right`, `border.Top` a`border.Bottom`vlastnosti ve zdrojovém kódu C#. Nastavení těchto vlastností na`null` odstraní okraj z odpovídajících stran tabulky.

#### Otázka: Jak mohu upravit tloušťku okraje stolu?

 A: Tloušťku okraje tabulky můžete upravit úpravou`border.Width` vlastnost ve zdrojovém kódu C#. Jednoduše nastavte požadovanou šířku okraje (v bodech), abyste dosáhli požadované tloušťky.