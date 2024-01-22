---
title: SVG do PDF
linktitle: SVG do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadná a rychlá konverze SVG do PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 280
url: /cs/net/document-conversion/svg-to-pdf/
---
Tento tutoriál vás provede kroky k převodu souboru SVG na soubor PDF pomocí Aspose.PDF for .NET. Aspose.PDF nabízí jednoduché a efektivní řešení pro převod souborů SVG do PDF při zachování kvality obsahu a rozvržení. Chcete-li provést tento převod, postupujte podle následujících kroků.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtení souboru SVG
Prvním krokem je načtení souboru SVG do a`Document` objekt pomocí možnosti načtení SVG (`SvgLoadOptions`). Použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte instanci objektu LoadOption pomocí možnosti načtení SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Vytvořit objekt dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor SVG.

## Krok 2: Převeďte do PDF
 Druhým krokem je převedení dokumentu SVG na dokument PDF pomocí`Save` metoda`Document` objekt. Použijte následující kód:

```csharp
// Uložte výsledný dokument PDF
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

Nezapomeňte zadat požadovanou cestu a název souboru pro výsledný soubor PDF.

### Příklad zdrojového kódu pro SVG do PDF pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektu LoadOption pomocí možnosti načtení SVG
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// Vytvořit objekt dokumentu
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// Uložte výsledný dokument PDF
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak převést soubor SVG na soubor PDF pomocí Aspose.PDF for .NET. Podle výše uvedených kroků můžete tento převod snadno provést. Použijte tuto metodu k převodu souborů SVG do PDF a vychutnejte si flexibilitu a kvalitu Aspose.PDF.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Nabízí různé funkce, včetně převodu souborů SVG do PDF.

#### Otázka: Proč bych měl chtít převést soubor SVG na PDF?

Odpověď: Soubory SVG (Scalable Vector Graphics) se běžně používají pro vektorovou grafiku na webu. Převod souboru SVG do formátu PDF umožňuje snazší sdílení, tisk a vkládání grafického obsahu.

#### Otázka: Jak mohu načíst soubor SVG a převést jej do PDF pomocí Aspose.PDF pro .NET?

 A: Chcete-li načíst soubor SVG, můžete použít`SvgLoadOptions` třídy k určení možnosti načtení SVG. Poté vytvořte a`Document` objekt a nahrajte do něj soubor SVG. Nakonec použijte`Save` metoda`Document` objekt převést a uložit SVG jako PDF.

#### Otázka: Mohu přizpůsobit výstupní PDF během převodu?

Odpověď: Ano, výstupní PDF můžete přizpůsobit během procesu převodu. Aspose.PDF for .NET poskytuje různé možnosti a vlastnosti pro ovládání vzhledu a rozvržení dokumentu PDF.

#### Otázka: Je ve výsledném PDF zachována kvalita obsahu SVG?

Odpověď: Ano, Aspose.PDF for .NET zajišťuje zachování kvality obsahu a rozvržení během převodu SVG do PDF a zajišťuje bezproblémový přechod mezi formáty.