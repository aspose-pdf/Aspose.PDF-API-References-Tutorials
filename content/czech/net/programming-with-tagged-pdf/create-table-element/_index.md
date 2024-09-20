---
title: Vytvořit prvek tabulky
linktitle: Vytvořit prvek tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce vytvořením prvku pole pomocí Aspose.PDF pro .NET. Snadno generujte dynamické soubory PDF s tabulkami.
type: docs
weight: 80
url: /cs/net/programming-with-tagged-pdf/create-table-element/
---
## Zavedení

Přemýšleli jste někdy o tom, jak můžete bez námahy vytvářet a přizpůsobovat prvky tabulky v PDF pomocí .NET? Aspose.PDF pro .NET je vaším oblíbeným řešením! Ať už automatizujete generování sestav nebo dynamicky vytváříte tabulky pro různé dokumenty, Aspose.PDF poskytuje bohaté API pro práci s prvky tabulky. Tato příručka vás provede krok za krokem, jak vytvořit tabulku, upravit její styl a dokonce zajistit, aby splňovala standardy PDF/UA. Zní to vzrušující, že? Pojďme se do toho ponořit!

## Předpoklady

Než začneme, budete potřebovat několik věcí:
1.  Aspose.PDF pro .NET: Stáhněte si nejnovější verzi z[Aspose.PDF pro .NET ke stažení](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Jakékoli IDE s podporou .NET (např. Visual Studio).
3. Základní znalost C#: Doporučuje se znalost programování v C#.

 Nakonec nezapomeňte na licenci Aspose.PDF. Pokud žádný nemáte, můžete použít[zkušební verze zdarma](https://releases.aspose.com/) nebo požádat a[dočasná licence](https://purchase.aspose.com/temporary-license/) vše vyzkoušet.

## Importujte balíčky

První věci – importujme potřebné balíčky. To nám umožní pracovat se všemi relevantními třídami pro vytváření tabulek v dokumentech PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

V této části rozdělíme proces vytváření tabulky do několika kroků. Každý krok se zaměřuje na různé části procesu vytváření a přizpůsobení tabulky.

## Krok 1: Vytvořte nový dokument PDF

První věc, kterou musíme udělat, je vytvořit nový dokument PDF. To bude sloužit jako kontejner pro náš stůl.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte nový dokument PDF
Document document = new Document();
```

 Zde inicializujeme novou instanci souboru`Document` třídy, což bude náš prázdný soubor PDF. Nezapomeňte definovat cestu k souboru!

## Krok 2: Nastavení označeného obsahu

Dále musíme povolit označený obsah, který zajistí dostupnost pro tabulku. Tagované PDF jsou vyžadovány pro soulad s PDF/UA (Universal Accessibility).

```csharp
// Povolit označený obsah
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Table");
taggedContent.SetLanguage("en-US");
```

Tento krok nastavuje název a jazyk dokumentu a zajišťuje, že tabulka odpovídá standardům přístupnosti. Mít přístupné dokumenty je zásadní pro uživatelskou zkušenost a právní požadavky v některých odvětvích.

## Krok 3: Vytvořte prvek tabulky

Nyní přichází ta zábavná část – vytvoření samotného stolu!

```csharp
// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

 Zde používáme`RootElement` označeného obsahu k připojení naší tabulky. Jedná se v podstatě o přidání tabulky jako podřízeného uzlu do struktury dokumentu.

## Krok 4: Přizpůsobte ohraničení a záhlaví tabulky

Nechcete, aby váš stůl vypadal nevýrazně, že? Přidejme trochu stylu!

```csharp
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

 Definujeme ohraničení a přidáváme do tabulky záhlaví, tělo a zápatí. Všimněte si použití`BorderInfo` upravit okraje stolu tmavě modrou barvou.

## Krok 5: Přidejte do tabulky řádky a buňky

Nyní naplníme naši tabulku řádky a buňkami. V této části procesu definujeme rozložení naší tabulky.

### Krok 5.1: Vytvořte řádek záhlaví

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

 Vytváříme řádek záhlaví se 4 sloupci a každá buňka záhlaví má styl s barvou pozadí`GreenYellow`. Nastavili jsme také ohraničení a zarovnání pro záhlaví.

### Krok 5.2: Přidejte řádky těla

```csharp
for (int rowIndex = 0; rowIndex < 50; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < 4; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Alignment = HorizontalAlignment.Center;
    }
}
```

Zde dynamicky vytváříme 50 řádků a 4 sloupce, plníme je textem a upravujeme styly buněk. Barva pozadí je nastavena na žlutou a text je vycentrován.

### Krok 5.3: Přidejte řádek zápatí

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;

for (int colIndex = 0; colIndex < 4; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
    tdElement.Alignment = HorizontalAlignment.Center;
}
```

 Pro doplnění tabulky přidáme zápatí s textem na střed a a`LightSeaGreen` pozadí.

## Krok 6: Ověřte soulad s PDF/UA

Jakmile je tabulka vytvořena, je důležité zajistit, aby PDF bylo kompatibilní s PDF/UA.

```csharp
document.Save(dataDir + "CreateTableElement.pdf");

// Ověřte shodu s PDF/UA
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Tento úryvek uloží soubor PDF a zkontroluje, zda splňuje standardy PDF/UA. Pokud je dokument v souladu, je přístupný uživatelům se zdravotním postižením.

## Závěr

Gratuluji! Úspěšně jste vytvořili plně přizpůsobenou tabulku v PDF pomocí Aspose.PDF pro .NET. Od stylování tabulky až po zajištění souladu s PDF/UA, nyní máte robustní základ pro generování dynamických tabulek v dokumentech PDF. Nezapomeňte prozkoumat rozsáhlé funkce Aspose.PDF pro další vylepšení vašich dokumentů!

## FAQ

### Mohu přizpůsobit písmo a styl textu tabulky?
Ano, Aspose.PDF vám umožňuje plně přizpůsobit písma, styly textu a zarovnání pomocí`TextState` třída.

### Jak dynamicky přidám další sloupce nebo řádky?
 Počet sloupců nebo řádků můžete upravit úpravou`rowIndex` a`colIndex` ve smyčkách.

### Je možné sloučit buňky v tabulce?
 Ano, můžete použít`ColSpan` a`RowSpan` vlastnosti pro sloučení buněk napříč sloupci nebo řádky.

### Co je soulad s PDF/UA?
Soulad s PDF/UA zajišťuje, že dokument je přístupný uživatelům se zdravotním postižením v souladu s mezinárodními standardy přístupnosti.

### Jak otestuji shodu s PDF/UA v Aspose.PDF?
 Můžete použít`Validate` způsob kontroly, zda dokument vyhovuje standardům PDF/UA.