---
title: PDF do SVG
linktitle: PDF do SVG
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem PDF do SVG pomocí Aspose.PDF pro .NET.
type: docs
weight: 180
url: /cs/net/document-conversion/pdf-to-svg/
---
tomto tutoriálu vás provedeme procesem převodu PDF do formátu SVG pomocí Aspose.PDF pro .NET. SVG (Scalable Vector Graphics) je formát vektorových obrázků, který pomáhá udržovat kvalitu a měřítko grafiky. Podle níže uvedených kroků budete moci převést soubor PDF do formátu SVG.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtení dokumentu PDF
V tomto kroku načteme zdrojový soubor PDF pomocí Aspose.PDF for .NET. Postupujte podle níže uvedeného kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načtěte dokument PDF
Document doc = new Document(dataDir + "input.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Zjištění možností uložení SVG
Po načtení souboru PDF vytvoříme instanci možností uložení SVG. Použijte následující kód:

```csharp
// Vytvořte instanci objektu SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Nekomprimujte obrázek SVG v archivu ZIP
saveOptions.CompressOutputToZipArchive = false;
```

## Krok 3: Uložení výsledného souboru SVG
Nyní uložíme převedený soubor PDF ve formátu SVG. Použijte následující kód:

```csharp
// Uložte výstup do souborů SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 Výše uvedený kód uloží převedený PDF do formátu SVG s názvem souboru`"PDFToSVG_out.svg"`.

### Příklad zdrojového kódu pro PDF do SVG pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načíst dokument PDF
Document doc = new Document(dataDir + "input.pdf");
// Vytvořte instanci objektu SvgSaveOptions
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Nekomprimujte obrázek SVG do archivu ZIP
saveOptions.CompressOutputToZipArchive = false;
// Uložte výstup do souborů SVG
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## Závěr
tomto tutoriálu jsme probrali krok za krokem proces převodu souboru PDF do formátu SVG pomocí Aspose.PDF for .NET. Podle výše uvedených pokynů byste nyní měli být schopni převést soubor PDF do formátu SVG. Tato funkce je užitečná, když chcete zachovat kvalitu grafiky a měřítko při převodu na vektorové obrázky.

### FAQ

#### Otázka: Mohu ovládat rozlišení nebo velikost výsledných souborů SVG během převodu PDF na SVG?

 Odpověď: Ano, můžete ovládat rozlišení nebo velikost výsledných souborů SVG během převodu PDF na SVG pomocí Aspose.PDF for .NET. The`SvgSaveOptions` třída poskytuje vlastnosti jako`PageSavingCallback` a`SaveFormat` které umožňují nastavit rozlišení, velikost stránky nebo další parametry související s výstupem SVG. Tyto možnosti můžete upravit podle svých požadavků a řídit tak kvalitu a velikost souborů SVG.

#### Otázka: Podporuje Aspose.PDF for .NET převod šifrovaných nebo heslem chráněných PDF do SVG?

Odpověď: Ano, Aspose.PDF pro .NET podporuje převod šifrovaných nebo heslem chráněných PDF do formátu SVG. Když načtete soubor PDF chráněný heslem, můžete zadat heslo pomocí`Document` konstruktoru třídy nebo nastavením`Password` vlastnost před načtením PDF. Aspose.PDF for .NET zvládne dešifrování během procesu převodu PDF na SVG.

#### Otázka: Mohu převést pouze určité stránky PDF do SVG místo celého dokumentu?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete převést pouze konkrétní stránky PDF do SVG namísto celého dokumentu. Před uložením výstupu jako soubory SVG můžete vybrat stránky, které chcete převést, zadáním jejich čísel nebo rozsahů stránek. Tímto způsobem můžete extrahovat a převést pouze požadované stránky z formátu PDF do formátu SVG.

#### Otázka: Je Aspose.PDF for .NET kompatibilní se všemi verzemi SVG?

A: Aspose.PDF for .NET je navržen tak, aby byl kompatibilní se specifikací SVG 1.1 (Scalable Vector Graphics). Podporuje generování souborů SVG podle standardu SVG 1.1. Upozorňujeme však, že SVG 2.0 byla představena jako nejnovější verze specifikace SVG. Přestože Aspose.PDF for .NET může v mnoha případech stále dobře fungovat se SVG 2.0, doporučujeme zkontrolovat kompatibilitu a potenciální omezení se specifickými funkcemi SVG, které hodláte používat.