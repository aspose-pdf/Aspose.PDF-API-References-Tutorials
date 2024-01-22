---
title: Získejte rozměry SVG
linktitle: Získejte rozměry SVG
second_title: Aspose.PDF pro .NET API Reference
description: Průvodce krok za krokem k získání rozměrů SVG pomocí Aspose.PDF pro .NET.
type: docs
weight: 40
url: /cs/net/document-conversion/get-svg-dimensions/
---
## Úvod
V tomto tutoriálu vás provedeme procesem získání rozměrů souboru SVG pomocí Aspose.PDF pro .NET. SVG (Scalable Vector Graphics) je obrazový formát založený na XML používaný k reprezentaci vektorové grafiky. Pomocí níže uvedených kroků budete moci získat rozměry souboru SVG a uložit je jako PDF.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtení souboru SVG
tomto kroku načteme soubor SVG pomocí Aspose.PDF for .NET. Postupujte podle níže uvedeného kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor SVG.

## Krok 2: Úprava velikosti stránky
Nyní, když jsme načetli soubor SVG, můžeme upravit velikost stránky tak, aby vyhovovala obsahu SVG. Použijte následující kód:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

Výše uvedený kód nastavuje okraje stránky na nulu, což umožňuje přizpůsobit velikost stránky na základě obsahu SVG.

## Krok 3: Uložení výsledného PDF
Po úpravě velikosti stránky již můžeme výsledný PDF dokument uložit. Zde je poslední krok:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` s požadovaným adresářem, kam chcete uložit výstupní soubor PDF.
  
### Příklad zdrojového kódu pro Get SVG Dimensions using Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Závěr
V tomto tutoriálu jsme probrali krok za krokem proces získání rozměrů souboru SVG pomocí Aspose.PDF pro .NET. Podle výše uvedených pokynů byste nyní měli být schopni získat rozměry souboru SVG a uložit je do formátu PDF. Tato funkce může být užitečná, když potřebujete změřit rozměry vektorové grafiky.

### FAQ

#### Otázka: Co je SVG?

Odpověď: SVG (Scalable Vector Graphics) je obrazový formát založený na XML používaný k reprezentaci vektorové grafiky. Na rozdíl od rastrových obrázků jsou soubory SVG nezávislé na rozlišení a lze je škálovat bez ztráty kvality. SVG se široce používá pro zobrazování grafiky na webu a lze jej snadno upravovat a manipulovat s ním.

#### Otázka: Proč používat Aspose.PDF for .NET pro převod SVG do PDF?

Odpověď: Aspose.PDF for .NET poskytuje spolehlivý a efektivní způsob, jak zpracovávat soubory SVG a převádět je do formátu PDF. Nabízí různé možnosti a nastavení pro přizpůsobení procesu převodu, jako je úprava velikosti stránky, okrajů a dalších vlastností pro zajištění přesné reprezentace v PDF.

#### Otázka: Mohu převést soubory SVG se složitou grafikou a textem?

Odpověď: Ano, Aspose.PDF pro .NET zvládne soubory SVG se složitou grafikou, textem a vektorovými prvky. Během procesu převodu přesně zachovává detaily a kvalitu obsahu SVG, výsledkem čehož jsou vysoce kvalitní dokumenty PDF.

#### Otázka: Je možné extrahovat text ze souborů SVG pomocí Aspose.PDF pro .NET?

Odpověď: Ano, Aspose.PDF pro .NET vám umožňuje extrahovat text ze souborů SVG. K extrahování textových prvků z SVG a jejich samostatnému uložení pro další zpracování můžete použít funkce knihovny pro extrakci textu.