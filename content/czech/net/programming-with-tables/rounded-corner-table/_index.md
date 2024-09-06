---
title: Zaoblený rohový stůl v dokumentu PDF
linktitle: Zaoblený rohový stůl v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit zaoblený rohový stůl v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 190
url: /cs/net/programming-with-tables/rounded-corner-table/
---
V tomto tutoriálu vás krok za krokem provedeme vytvořením zaobleného rohového stolu v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat.

## Krok 1: Vytvoření tabulky
Nejprve vytvoříme tabulku pomocí následujícího kódu:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 2: Nastavení stylu zaobleného rohu
Dále nakonfigurujeme styl zaobleného rohu pro stůl:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## Krok 3: Nastavení ohraničení tabulky
Chcete-li dát tabulce zaoblený rohový okraj, musíme vytvořit objekt BorderInfo a nakonfigurovat jej s příslušnými parametry:

```csharp
// Vytvořte objekt GraphInfo pro nastavení barvy ohraničení
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Vytvořte prázdný objekt BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Nastavte poloměr zaobleného okraje na 15
bInfo.RoundedBorderRadius = 15;

// Použijte na tabulku informace o ohraničení
tab1.Border = bInfo;
```

### Příklad zdrojového kódu pro stůl se zaoblenými rohy pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Vytvořte prázdný objekt BorderInfo
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Nastavte ohraničení kulatější, kde poloměr zaoblení je 15
bInfo.RoundedBorderRadius = 15;
// Nastavte styl rohu stolu jako Kulatý.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Nastavte informace o ohraničení tabulky
tab1.Border = bInfo;
```

## Závěr
gratuluji! Nyní jste se naučili, jak vytvořit zaoblený rohový stůl v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce vám ukázal, jak nastavit styl zaobleného rohu a ohraničení stolu. Nyní můžete tyto znalosti aplikovat na své vlastní projekty.

### Nejčastější dotazy pro stůl se zaobleným rohem v dokumentu PDF

#### Otázka: Mohu přizpůsobit poloměr zaoblených rohů stolu?

Odpověď: Ano, můžete upravit poloměr zaoblených rohů pro stůl úpravou hodnoty`bInfo.RoundedBorderRadius` vlastnost v poskytnutém zdrojovém kódu C#. Jednoduše nastavte požadovanou hodnotu poloměru (v bodech), abyste dosáhli požadovaného vzhledu zaobleného rohu.

#### Otázka: Mohu použít zaoblené rohy na jednotlivé buňky v tabulce?

Odpověď: Ne, styl zaoblených rohů se použije na celý stůl jako celek. Aspose.PDF for .NET aktuálně neposkytuje vestavěnou podporu pro použití zaoblených rohů na jednotlivé buňky v tabulce.

#### Otázka: Mohu změnit barvu okraje se zaobleným rohem?

 Odpověď: Ano, můžete změnit barvu okraje se zaoblenými rohy úpravou hodnoty`graph.Color` vlastnost ve zdrojovém kódu C#. Jednoduše poskytněte požadovanou barvu, jako je např`Aspose.Pdf.Color.Red` nebo jakékoli jiné platné barevné znázornění.

#### Otázka: Je možné použít různé styly rohů (např. čtvercový a zaoblený) na různé tabulky ve stejném dokumentu PDF?

Odpověď: Ano, je možné použít různé styly rohů na různé tabulky ve stejném dokumentu PDF. Můžete vytvořit více stolů a nakonfigurovat jejich styly rohů individuálně podle vašich požadavků.

#### Otázka: Mohu upravit tloušťku okraje se zaoblenými rohy?

 Odpověď: Ano, tloušťku zaobleného okraje můžete upravit úpravou`BorderInfo` vlastnosti objektu ve zdrojovém kódu C#. Můžete například nastavit`bInfo.Width` vlastnost pro úpravu tloušťky ohraničení.