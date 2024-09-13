---
title: Nahradit tabulku v dokumentu PDF
linktitle: Nahradit tabulku v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nahradit tabulku v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 180
url: /cs/net/programming-with-tables/replace-table/
---
V tomto tutoriálu vás krok za krokem provedeme nahrazením tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat.

## Krok 1: Načtení existujícího dokumentu PDF
Nejprve musíte načíst existující dokument PDF pomocí následujícího kódu:

```csharp
// Cesta k adresáři dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte existující dokument PDF
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## Krok 2: Vytvoření objektu TableAbsorber pro nalezení tabulek
Dále vytvoříme objekt TableAbsorber, abychom našli tabulky v dokumentu PDF:

```csharp
// Vytvořte objekt TableAbsorber pro nalezení tabulek
TableAbsorber absorber = new TableAbsorber();
```

## Krok 3: Navštivte první stránku s absorbérem
Nyní navštívíme první stránku dokumentu PDF pomocí absorbéru:

```csharp
// Navštivte první stránku s absorbérem
absorb.Visit(pdfDocument.Pages[1]);
```

## Krok 4: Získání první tabulky na stránce
Abychom mohli tabulku nahradit, získáme první tabulku stránky:

```csharp
// Získejte první tabulku na stránce
AbsorbedTable table = absorb.TableList[0];
```

## Krok 5: Vytvoření nové tabulky
Nyní vytvoříme novou tabulku s požadovanými sloupci a buňkami:

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## Krok 6: Nahrazení stávající tabulky novou tabulkou
Nyní nahradíme stávající tabulku novou tabulkou na první stránce dokumentu:

```csharp
// Vyměňte tabulku za novou
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## Krok 7: Uložení dokumentu
Nakonec upravený dokument PDF uložíme:

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### Příklad zdrojového kódu pro tabulku nahradit pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načíst existující dokument PDF
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

// Vytvořte objekt TableAbsorber a vyhledejte tabulky
TableAbsorber absorber = new TableAbsorber();

// Navštivte první stránku s absorbérem
absorber.Visit(pdfDocument.Pages[1]);

// Získejte první tabulku na stránce
AbsorbedTable table = absorber.TableList[0];

// Vytvořte novou tabulku
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

// Vyměňte stůl za nový
absorber.Replace(pdfDocument.Pages[1], table, newTable);

// Uložit dokument
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## Závěr
gratuluji! Nyní jste se naučili, jak nahradit tabulku v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce vám ukázal, jak načíst dokument, najít existující tabulku, vytvořit novou tabulku a nahradit ji. Nyní můžete tyto znalosti aplikovat na své vlastní projekty.

### Časté dotazy k nahrazení tabulky v dokumentu PDF

#### Otázka: Mohu pomocí tohoto přístupu nahradit více tabulek ve stejném dokumentu PDF?

 Odpověď: Ano, můžete nahradit více tabulek ve stejném dokumentu PDF stejným postupem pro každou tabulku, kterou chcete nahradit. Po získání`AbsorbedTable` objekt pro každou tabulku pomocí`TableAbsorber` , můžete vytvořit odpovídající nové tabulky a poté použít`absorber.Replace()` způsob nahrazení každé existující tabulky příslušnou novou tabulkou.

#### Otázka: Co se stane, pokud má nová tabulka jiný počet sloupců než původní tabulka?

Odpověď: Pokud má nová tabulka jiný počet sloupců než původní tabulka, může to mít za následek neočekávané chování nebo problémy s rozložením v upraveném dokumentu PDF. Pro bezproblémovou výměnu je nezbytné zajistit, aby struktura nové tabulky (počet sloupců a jejich šířky) odpovídala struktuře původní tabulky.

#### Otázka: Mohu nahradit tabulku na konkrétní stránce jiné než první?

 Odpověď: Ano, tabulku na konkrétní stránce jiné než první můžete nahradit změnou indexu stránky v`pdfDocument.Pages[]` volání metody při získávání`AbsorbedTable` objekt. Chcete-li například nahradit tabulku na druhé stránce, použijte`pdfDocument.Pages[2]`.

#### Otázka: Mohu upravit vzhled nové tabulky, například přidat barvu pozadí nebo ohraničení?

 Odpověď: Ano, vzhled nové tabulky si můžete přizpůsobit nastavením různých vlastností`Table` a její buňky. Můžete například nastavit`BackgroundColor` vlastnost buněk přidat barvu pozadí. Můžete také nastavit`DefaultCellBorder` vlastnosti nové tabulky nebo jednotlivých buněk pro přidání ohraničení.

#### Otázka: Má nahrazení tabulky vliv na rozložení obsahu zbytku dokumentu PDF?

Odpověď: Nahrazení tabulky může ovlivnit rozložení obsahu, pokud se velikost nebo struktura nové tabulky výrazně liší od původní tabulky. Zbytek obsahu na stránce se přeformátuje, aby se přizpůsobil nové tabulce. Je nezbytné pečlivě navrhnout nový stůl tak, aby hladce zapadl do stávajícího rozvržení, aby se předešlo problémům s rozvržením.