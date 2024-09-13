---
title: Kontrolní obdélník Z pořadí v souboru PDF
linktitle: Kontrolní obdélník Z pořadí v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném návodu krok za krokem se dozvíte, jak ovládat Z-pořadí obdélníku v PDF pomocí Aspose.PDF for .NET. Ideální pro vývojáře, kteří chtějí vylepšit dokumenty PDF.
type: docs
weight: 40
url: /cs/net/programming-with-graphs/control-rectangle-z-order/
---
## Zavedení

Vytváření souborů PDF s bohatými vizuálními komponentami může být náročné i obohacující. Stalo se vám někdy, že jste potřebovali manipulovat s vizuálními prvky PDF, třeba jste potřebovali vrstvit tvary nebo upravit pořadí, ve kterém se zobrazují? Tento výukový program se ponoří do fascinujícího světa manipulace s PDF pomocí Aspose.PDF pro .NET, se zaměřením konkrétně na ovládání Z-pořadí obdélníků v dokumentu PDF. 

## Předpoklady 

Než se pustíme do kódu, je několik věcí, které budete potřebovat, abyste se ujistili, že jste nastavili:

1. IDE pro vývoj .NET: Pokud jste to ještě neudělali, vyberte a nainstalujte integrované vývojové prostředí (IDE), jako je Visual Studio nebo JetBrains Rider. Tyto nástroje vám pomohou efektivně psát, testovat a ladit váš kód.
2.  Aspose.PDF for .NET Library: Můžete začít stažením knihovny Aspose.PDF. Navštivte[stránka ke stažení](https://releases.aspose.com/pdf/net/) získat nejnovější verzi. Tato knihovna je nezbytná pro vytváření a manipulaci s dokumenty PDF.
3. Základní znalost C#: I když vás tato příručka provede vším, základní znalost C# vám pomůže rychleji porozumět pojmům.
4.  .NET Framework: Ujistěte se, že máte na svém počítači nainstalovaný .NET Framework. Potřebné požadavky najdete v[Založte dokumentaci](https://reference.aspose.com/pdf/net/).

Nyní, když jsme pokryli předpoklady, přejděme k zábavnější části – importu balíčků, se kterými budeme pracovat.

## Importujte balíčky

našich projektech musíme importovat potřebný jmenný prostor Aspose.PDF pro přístup k jeho třídám a metodám. To nám umožní bezproblémově manipulovat se soubory PDF. Postup je následující:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Zahrnutím těchto jmenných prostorů do horní části souboru kódu získáte přístup ke všem funkcím, které poskytuje Aspose.PDF.

Nyní si tutoriál rozdělíme na zvládnutelné kroky. Každý krok vás provede procesem přidávání obdélníků do PDF a ovládáním jejich Z-pořadí.

## Krok 1: Nastavte svůj dokument

Než budeme moci přidávat tvary, musíme nastavit základy našeho dokumentu PDF. To zahrnuje definování, kde je dokument uložen, a jeho inicializaci.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objekt třídy Instantiate Document
Document doc1 = new Document();
```
 Zde začněte definováním adresáře, kam chcete soubor PDF uložit. The`Document` třída z Aspose.PDF se poté vytvoří instancí, která bude sloužit jako hlavní objekt pro váš soubor PDF.

## Krok 2: Přidejte do dokumentu stránku

Každý PDF potřebuje k zobrazení obsahu alespoň jednu stránku. Přidáme stránku a nastavíme její rozměry.

```csharp
// Přidat stránku do kolekce stránek souboru PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
//Nastavit velikost stránky PDF
page1.SetPageSize(375, 300);
```
 V tomto kroku použijeme`Add()` způsob vytvoření nové stránky v našem dokumentu. Nastavili jsme také velikost stránky na 375 x 300 pixelů, což nám dává plátno, se kterým můžeme pracovat.

## Krok 3: Nastavte okraje stránky 

Okraje jsou zásadní, protože definují využitelný prostor na stránce PDF. Můžete je nastavit takto:

```csharp
// Nastavte levý okraj pro objekt stránky na 0
page1.PageInfo.Margin.Left = 0;
// Nastavit horní okraj objektu stránky na 0
page1.PageInfo.Margin.Top = 0;
```
Nastavením levého a horního okraje na nulu zajistíme, že naše tvary zaberou celou plochu stránky.

## Krok 4: Přidejte obdélníky pomocí ovládání pořadí Z

Nyní ta vzrušující část – přidávání obdélníků! Každý obdélník může mít určené pořadí Z. Pořadí Z určuje, který obdélník se zobrazí nad ostatními. Definujeme metodu pro přidávání obdélníků.

```csharp
void AddRectangle(Aspose.Pdf.Page page, float x, float y, float width, float height, Aspose.Pdf.Color color, int zOrder)
{
    // Vytvořte nový obdélník
    Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(x, y, x + width, y + height);
    // Vytvořte graf pro stránku
    Aspose.Pdf.Operators.Graph graph = new Aspose.Pdf.Operators.Graph(page);
    graph.ZOrder = zOrder; // Nastavte Z-Pořadí obdélníku
    // Vytvořte barevný štětec
    Pen pen = new Pen(color);
    graph.DrawRectangle(pen, rectangle);
}
```
Tato metoda přebírá parametry pro umístění, velikost, barvu a Z-pořadí, což umožňuje flexibilitu při kreslení tvarů na stránce.

## Krok 5: Použijte metodu AddRectangle

Nyní můžeme na naší stránce vytvořit obdélníky pomocí výše definované metody.

```csharp
// Vytvořte nový obdélník s Color as Red, Z-Order jako 0 a určitými rozměry
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Vytvořte nový obdélník s Color as Blue, Z-Order jako 0 a určitými rozměry
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Vytvořte nový obdélník s Color as Green, Z-Order jako 0 a určitými rozměry
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```
Zde přidáváme tři obdélníky s různými barvami a hodnotami Z-pořadí. Obdélník s nejvyšším Z-pořadím se při prohlížení v PDF zobrazí nahoře.

## Krok 6: Uložte dokument 

Konečně je čas zachránit své mistrovské dílo! Jak na to:

```csharp
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Uložte výsledný soubor PDF
doc1.Save(dataDir);
```
 Stačí zadat název souboru a zavolat`Save()` způsob vytvoření dokumentu PDF.

## Závěr 

právě tak jste se naučili, jak ovládat pořadí Z obdélníků v PDF pomocí Aspose.PDF pro .NET! Schopnost vrstvit tvary a manipulovat s jejich vizuálním pořadím může výrazně zlepšit použitelnost a estetiku vašich dokumentů PDF. Ať už vytváříte zprávy, vytváříte výukové materiály nebo se dokonce jen bavíte grafikou, tyto techniky lze použít široce.

Pamatujte, že praxe je klíčová! Pohrajte si s různými tvary, velikostmi a barvami. Čím více budete experimentovat, tím pohodlnější budete s nástroji, které máte k dispozici.

## FAQ

### Co je Z-pořadí v PDF?
Z-pořadí odkazuje na pořadí zásobníku vizuálních prvků. Prvky s vyšším Z-řádem se objeví nad těmi s nižším Z-řádem.

### Kde si mohu stáhnout Aspose.PDF pro .NET?
 Můžete si jej stáhnout z[stránka ke stažení](https://releases.aspose.com/pdf/net/).

### Je k dispozici bezplatná zkušební verze pro Aspose?
 Ano, můžete získat bezplatnou zkušební verzi[zde](https://releases.aspose.com/).

### Jak mohu získat podporu pro Aspose.PDF?
 Můžete navštívit[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10) o pomoc.

### Mohu získat dočasnou licenci pro Aspose.PDF?
 Absolutně! Můžete požádat o dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/).