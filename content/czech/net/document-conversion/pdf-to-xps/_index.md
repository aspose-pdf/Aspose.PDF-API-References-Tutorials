---
title: PDF do XPS
linktitle: PDF do XPS
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem PDF do XPS pomocí Aspose.PDF pro .NET.
type: docs
weight: 220
url: /cs/net/document-conversion/pdf-to-xps/
---
V tomto tutoriálu vás provedeme procesem převodu souboru PDF do formátu XPS (XML Paper Specification) pomocí Aspose.PDF for .NET. Formát XPS je formát souboru založený na XML používaný k elektronické reprezentaci dokumentů. Podle níže uvedených kroků budete moci převést soubor PDF do formátu XPS.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Vytvořte možnosti ukládání XPS
Po načtení souboru PDF vytvoříme instanci možností uložení XPS. Použijte následující kód:

```csharp
// Okamžité možnosti ukládání XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## Krok 3: Uložení výsledného souboru XPS
Nyní uložíme převedený soubor PDF ve formátu XPS. Použijte následující kód:

```csharp
// Uložte dokument XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

 Výše uvedený kód uloží převedený soubor PDF ve formátu XPS s názvem souboru`"PDFToXPS_out.xps"`.


### Příklad zdrojového kódu pro PDF do XPS pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načíst dokument PDF
Document pdfDocument = new Document(dataDir + "input.pdf");

// Okamžité možnosti ukládání XPS
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

// Uložte dokument XPS
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## Závěr
tomto tutoriálu jsme probrali krok za krokem proces převodu souboru PDF do formátu XPS pomocí Aspose.PDF for .NET. Podle výše uvedených pokynů byste nyní měli být schopni převést soubor PDF do formátu XPS. Tato funkce je užitečná, když chcete prohlížet nebo tisknout dokumenty PDF ve formátu XPS.

### FAQ

#### Otázka: Je formát XPS vhodný pro kompatibilitu napříč platformami?

Odpověď: Formát XPS, který je formátem souborů založeným na XML, je nezávislý na platformě a lze jej zobrazit na různých operačních systémech a zařízeních. Soubory XPS jsou standardně podporovány na platformách Windows a některé aplikace a prohlížeče třetích stran mohou být dostupné pro jiné platformy.

#### Otázka: Dokáže Aspose.PDF for .NET zpracovat složité soubory PDF s více stránkami a obrázky během převodu XPS?

Odpověď: Ano, Aspose.PDF for .NET dokáže zpracovat složité soubory PDF s více stránkami a obrázky během převodu XPS. Při převodu do formátu XPS přesně zachovává rozvržení, obrázky a textový obsah PDF.

#### Otázka: Je možné zadat další nastavení nebo možnosti během procesu převodu XPS?

 Odpověď: Ano, Aspose.PDF pro .NET poskytuje různé možnosti a nastavení, která lze upravit během procesu převodu XPS. Kompresi obrazu, vkládání písem a další nastavení můžete ovládat pomocí`XpsSaveOptions` třída.

#### Otázka: Lze soubory PDF chráněné heslem převést do formátu XPS pomocí Aspose.PDF for .NET?

 Odpověď: Ano, Aspose.PDF for .NET podporuje převod souborů PDF chráněných heslem do formátu XPS. Při načítání souboru PDF chráněného heslem můžete zadat heslo pomocí`Document` konstruktoru třídy nebo nastavením`Password` vlastnost před načtením PDF.