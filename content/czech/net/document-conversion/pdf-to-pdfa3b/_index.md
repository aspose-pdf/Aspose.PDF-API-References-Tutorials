---
title: PDF do PDFA3b
linktitle: PDF do PDFA3b
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem PDF do PDF/A-3b pomocí Aspose.PDF pro .NET.
type: docs
weight: 150
url: /cs/net/document-conversion/pdf-to-pdfa3b/
---
tomto tutoriálu vás provedeme procesem převodu souboru PDF do formátu PDF/A-3b pomocí Aspose.PDF for .NET. PDF/A-3b je norma ISO pro vkládání souborů a dat do dokumentu PDF. Podle níže uvedených kroků budete moci převést soubory PDF do formátu PDF/A-3b.

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Převeďte do PDF/A-3b
Po otevření souboru PDF můžeme přistoupit k převodu do formátu PDF/A-3b. Použijte následující kód:

```csharp
// Převést do formátu PDF/A-3b
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

Výše uvedený kód převede soubor PDF do formátu PDF/A-3b a odstraní všechny chyby převodu.

## Krok 3: Uložení výsledného souboru PDF/A-3b
Po dokončení převodu musíme výsledný soubor PDF/A-3b uložit. Zde je poslední krok:

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Uložte výstupní dokument
pdfDocument.Save(dataDir);
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` s požadovaným adresářem, kam chcete uložit výstupní soubor PDF/A-3b.

### Příklad zdrojového kódu pro PDF do PDFA3b pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
// Uložit výstupní dokument
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## Závěr
tomto tutoriálu jsme probrali krok za krokem proces převodu souboru PDF do formátu PDF/A-3b pomocí Aspose.PDF pro .NET. Podle výše uvedených pokynů byste nyní měli být schopni převádět soubory PDF do formátu PDF/A-3b. Tato funkce je užitečná, když chcete vložit další soubory a data do dokumentu PDF, který odpovídá standardu PDF/A-3b.

### FAQ

#### Otázka: Co je PDF/A-3b a jak se liší od jiných standardů PDF/A?

Odpověď: PDF/A-3b je norma ISO, která umožňuje vkládání souborů a dat do dokumentu PDF, čímž se stává samostatným a zajišťuje dlouhodobé uchování. Na rozdíl od jiných standardů PDF/A, jako jsou PDF/A-1 a PDF/A-2, PDF/A-3b umožňuje zahrnutí dalších souborů a dat do dokumentu PDF. Díky této funkci je vhodný pro archivaci a výměnu složitých a interaktivních dokumentů.

#### Otázka: Mohu do dokumentu PDF/A-3b zahrnout více souborů a dat?

Odpověď: Ano, jednou z hlavních výhod PDF/A-3b je jeho schopnost zahrnout do dokumentu PDF více souborů a dat. Spolu s hlavním obsahem PDF můžete vložit různé typy souborů, jako jsou XML, tabulky, obrázky nebo jiné soubory PDF. Výsledkem je, že dokument PDF/A-3b se stává samostatným balíkem obsahujícím všechny potřebné prvky.

#### Otázka: Co se stane, když se během procesu převodu PDF na PDF/A-3b vyskytnou chyby?

 Odpověď: Při převodu PDF do formátu PDF/A-3b pomocí Aspose.PDF for .NET máte kontrolu nad tím, jak jsou chyby zpracovávány. The`Convert` metody`ConvertErrorAction` Parametr určuje akci, která se má provést, když dojde k chybě. V uvedeném příkladu kódu je`ConvertErrorAction.Delete` je použit parametr, což znamená, že jakékoli chyby zjištěné během převodu budou mít za následek smazání stránek s chybami.

#### Otázka: Je PDF/A-3b vhodný pro dlouhodobé uchovávání dokumentů?

Odpověď: Ano, PDF/A-3b je navržen speciálně pro dlouhodobé uchovávání elektronických dokumentů. Vložením dalších souborů a dat zajišťuje, že všechny potřebné součásti jsou zahrnuty do samotného dokumentu PDF, čímž se snižuje riziko ztráty informací nebo externích závislostí v průběhu času. Díky této funkci je vhodný pro archivaci dokumentů způsobem, který zaručuje dlouhodobou dostupnost a konzistenci.