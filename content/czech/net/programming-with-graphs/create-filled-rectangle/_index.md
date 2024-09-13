---
title: Vytvořte vyplněný obdélník
linktitle: Vytvořte vyplněný obdélník
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit vyplněný obdélník v PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného návodu. Ideální pro vývojáře všech úrovní.
type: docs
weight: 50
url: /cs/net/programming-with-graphs/create-filled-rectangle/
---
## Zavedení

Chtěli jste někdy programově vytvářet vizuálně atraktivní soubory PDF? Pokud ano, jste na správném místě! V tomto tutoriálu se ponoříme do světa Aspose.PDF for .NET, výkonné knihovny, která vám umožní snadno manipulovat s dokumenty PDF. Dnes se zaměříme na vytvoření vyplněného obdélníku v souboru PDF. Ať už jste zkušený vývojář nebo teprve začínáte, tento průvodce vás přátelsky a poutavě provede každým krokem. Takže popadněte svůj kódovací klobouk a můžeme začít!

## Předpoklady

Než se pustíme do kódu, je třeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Je to fantastické IDE pro vývoj .NET.
2.  Aspose.PDF for .NET: Budete si muset stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete to najít[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Malá znalost programování C# vám pomůže lépe porozumět úryvkům kódu.

## Importujte balíčky

Chcete-li začít, musíte do svého projektu C# importovat potřebné balíčky. Můžete to udělat takto:

### Vytvořit nový projekt

Otevřete Visual Studio a vytvořte nový projekt C#. Pro jednoduchost si můžete vybrat konzolovou aplikaci.

### Přidejte odkaz Aspose.PDF

1. Klepněte pravým tlačítkem myši na svůj projekt v Průzkumníku řešení.
2. Vyberte „Spravovat balíčky NuGet“.
3. Vyhledejte „Aspose.PDF“ a nainstalujte nejnovější verzi.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Nyní, když máme vše nastaveno, pojďme se ponořit do kódu!

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte určit cestu, kam bude váš PDF uložen. To je zásadní, protože to programu říká, kde má soubor vytvořit.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou na vašem počítači, kam chcete PDF uložit.

## Krok 2: Vytvořte instanci dokumentu

 Dále vytvoříme instanci`Document`třída. Tato třída představuje dokument PDF, se kterým budete pracovat.

```csharp
// Vytvořit instanci dokumentu
Document doc = new Document();
```

Tento řádek inicializuje nový dokument PDF, se kterým můžeme manipulovat.

## Krok 3: Přidejte stránku do dokumentu

Nyní přidáme stránku do našeho dokumentu. Každý PDF potřebuje alespoň jednu stránku, že?

```csharp
// Přidat stránku do kolekce stránek souboru PDF
Page page = doc.Pages.Add();
```

Tento kód přidá do dokumentu novou stránku a umožní nám na ni kreslit tvary.

## Krok 4: Vytvořte instanci grafu

 Abychom mohli kreslit tvary, musíme vytvořit a`Graph` instance. Představte si graf jako plátno, na kterém můžete kreslit různé tvary.

```csharp
// Vytvořte instanci Graph
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Zde vytváříme graf o šířce 100 a výšce 400.

## Krok 5: Přidejte graf na stránku

Nyní, když máme náš graf, přidáme jej na stránku, kterou jsme vytvořili dříve.

```csharp
// Přidejte objekt grafu do kolekce odstavců instance stránky
page.Paragraphs.Add(graph);
```

Tato čára připojí graf ke stránce a připraví jej ke kreslení.

## Krok 6: Vytvořte instanci obdélníku

Dále si vytvoříme obdélník, který chceme vyplnit barvou.

```csharp
// Vytvořte instanci obdélníku
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

V tomto kódu definujeme polohu a velikost obdélníku. Parametry představují souřadnice x a y, šířku a výšku.

## Krok 7: Zadejte barvu výplně

Nyní zvolíme barvu pro náš obdélník. Pro tento příklad jej vyplníme červenou barvou.

```csharp
// Určete barvu výplně pro objekt Graph
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Tento řádek nastaví barvu výplně obdélníku na červenou. Můžete si vybrat jakoukoli barvu, která se vám líbí!

## Krok 8: Přidejte obdélník do grafu

Když je náš obdélník připraven, je čas jej přidat do grafu.

```csharp
// Přidejte obdélníkový objekt do kolekce tvarů objektu Graph
graph.Shapes.Add(rect);
```

Tento kód přidá obdélník do grafu, čímž se stane součástí našeho výkresu.

## Krok 9: Uložte dokument PDF

Nakonec musíme dokument uložit do zadaného adresáře.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
```

 Tento kód uloží soubor PDF s názvem`CreateFilledRectangle_out.pdf` v adresáři, který jste zadali dříve.

## Krok 10: Potvrzující zpráva

Abychom věděli, že vše proběhlo hladce, můžeme vytisknout potvrzovací zprávu.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Tento řádek zobrazí v konzole zprávu potvrzující, že vyplněný obdélník byl úspěšně vytvořen.

## Závěr

tady to máte! Úspěšně jste vytvořili vyplněný obdélník v dokumentu PDF pomocí Aspose.PDF for .NET. Tato výkonná knihovna otevírá svět možností pro manipulaci s PDF a umožňuje vám vytvářet úžasné dokumenty programově. Ať už generujete zprávy, faktury nebo jakýkoli jiný typ PDF, Aspose.PDF vám pomůže.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k prozkoumání funkcí knihovny. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Existuje způsob, jak získat podporu pro Aspose.PDF?
 Absolutně! Podporu můžete získat prostřednictvím fóra Aspose[zde](https://forum.aspose.com/c/pdf/10).

### Jak mohu zakoupit Aspose.PDF?
 Aspose.PDF si můžete zakoupit na stránce nákupu[zde](https://purchase.aspose.com/buy).

### Jaké typy tvarů mohu vytvořit pomocí Aspose.PDF?
Pomocí knihovny Aspose.PDF můžete vytvářet různé tvary, včetně obdélníků, kruhů, čar a dalších.