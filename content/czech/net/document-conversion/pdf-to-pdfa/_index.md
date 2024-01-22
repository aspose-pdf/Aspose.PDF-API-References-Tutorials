---
title: PDF do PDFA
linktitle: PDF do PDFA
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem PDF do PDFA pomocí Aspose.PDF pro .NET.
type: docs
weight: 140
url: /cs/net/document-conversion/pdf-to-pdfa/
---
V tomto tutoriálu vás provedeme procesem převodu souboru PDF do formátu PDF/A pomocí Aspose.PDF for .NET. Formát PDF/A je normou ISO, která zaručuje dlouhodobé uchování elektronických dokumentů. Podle níže uvedených kroků budete moci převádět soubory PDF do formátu PDF/A.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Otevření zdrojového dokumentu PDF
V tomto kroku otevřeme zdrojový soubor PDF pomocí Aspose.PDF for .NET. Postupujte podle níže uvedeného kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otevřete zdrojový dokument PDF
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Převod do formátu PDF/A
Po otevření souboru PDF můžeme přistoupit k převodu do formátu PDF/A. Použijte následující kód:

```csharp
// Převést na dokument kompatibilní s PDF/A
// Během procesu převodu se také provádí ověření
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Výše uvedený kód převede soubor PDF do formátu PDF/A-1b a také provede ověření během procesu převodu. Případné chyby jsou zaznamenány v`"log.xml"` soubor.

## Krok 3: Uložení výsledného souboru PDF/A
Po dokončení převodu musíme výsledný soubor PDF/A uložit. Zde je poslední krok:

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
// Uložte výstupní dokument
pdfDocument.Save(dataDir);
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` s požadovaným adresářem, kam chcete uložit výstupní soubor PDF/A.

### Příklad zdrojového kódu pro PDF do HTML pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

// Převést na dokument kompatibilní s PDF/A
// Během procesu převodu se také provádí ověření
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
// Uložit výstupní dokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## Závěr
V tomto tutoriálu jsme probrali krok za krokem proces převodu souboru PDF do formátu PDF/A pomocí Aspose.PDF pro .NET. Podle výše popsaných pokynů byste nyní měli být schopni převést soubory PDF do formátu PDF/A. Tato funkce je užitečná, když chcete zajistit dlouhodobou shodu vašich elektronických dokumentů.

### FAQ

#### Otázka: Co je PDF/A a proč je důležité?

A: PDF/A je norma ISO pro archivaci elektronických dokumentů. Zajišťuje, že dokumenty jsou samostatné a lze je spolehlivě uchovat po dlouhou dobu. Shoda s PDF/A zaručuje, že vizuální vzhled, obsah a struktura dokumentu zůstanou v průběhu času konzistentní, takže je vhodný pro archivační a právní účely.

#### Otázka: Jaké jsou různé úrovně shody PDF/A a jak se liší?

Odpověď: PDF/A je k dispozici v několika úrovních shody, například PDF/A-1a, PDF/A-1b, PDF/A-2a, PDF/A-2b, PDF/A-2u, PDF/A-3a, PDF /A-3b a PDF/A-3u. Hlavní rozdíl spočívá v úrovni shody a požadavcích na metadata, barevné prostory a další specifické aspekty dokumentu PDF. V tomto tutoriálu jsme se zaměřili na převod do PDF/A-1b, který je široce akceptován pro dlouhodobou archivaci.

#### Otázka: Jak Aspose.PDF for .NET zpracovává ověření během převodu PDF na PDF/A?

Odpověď: Aspose.PDF for .NET provádí ověření během procesu převodu PDF do PDF/A. Pokud se ve zdrojovém dokumentu PDF vyskytnou nějaké problémy nebo chyby, které brání tomu, aby byl v souladu se zvoleným standardem PDF/A, knihovna zaznamená chyby do souboru XML, jak určí uživatel. The`Convert` metody`ConvertErrorAction` Parametr určuje, jak zacházet s chybami, jako je jejich ignorování nebo mazání stránek s chybami.

#### Otázka: Mohu přizpůsobit nastavení převodu PDF/A tak, aby splňovalo specifické požadavky?

 Odpověď: Ano, Aspose.PDF for .NET poskytuje různé možnosti přizpůsobení nastavení převodu PDF/A. Můžete si vybrat různé úrovně shody PDF/A, určit název výstupního souboru, ovládat zpracování chyb a další. The`Convert` metoda umožňuje nastavit požadovaný formát PDF/A a další možnosti, což vám umožní přizpůsobit převod podle vašich specifických potřeb.