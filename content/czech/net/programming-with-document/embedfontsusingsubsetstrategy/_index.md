---
title: Vložit písma do souboru PDF s podmnožinou strategie
linktitle: Vložit písma s podmnožinou strategie
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vkládat písma do souboru PDF pomocí Subset Strategy pomocí Aspose.PDF for .NET. Optimalizujte velikost PDF vložením pouze nezbytných znaků.
type: docs
weight: 130
url: /cs/net/programming-with-document/embedfontsusingsubsetstrategy/
---
V tomto tutoriálu probereme, jak vložit písma do souboru PDF se strategií podmnožiny pomocí Aspose.PDF pro .NET. Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat a manipulovat s dokumenty PDF programově. Vložení písem do souboru PDF je důležitým krokem k zajištění správného zobrazení dokumentu na různých zařízeních bez ohledu na to, zda jsou požadovaná písma na těchto zařízeních nainstalována či nikoli.

## Krok 1: Vytvořte novou aplikaci C# Console
Chcete-li začít, vytvořte novou aplikaci C# Console v sadě Visual Studio. Můžete si to pojmenovat, jak chcete. Jakmile je projekt vytvořen, musíte přidat odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte jmenný prostor Aspose.PDF
Chcete-li importovat jmenný prostor Aspose.PDF, přidejte následující řádek kódu na začátek souboru C#:

```csharp
using Aspose.Pdf;
```

## Krok 3: Načtěte existující soubor PDF
Chcete-li vložit písma do existujícího souboru PDF, musíte tento soubor načíst pomocí třídy Dokument. Následující kód ukazuje, jak načíst existující soubor PDF:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte existující soubor PDF
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 4: Vložení písem se strategií podmnožiny
Aspose.PDF for .NET poskytuje dvě strategie pro vkládání písem: SubsetAllFonts a SubsetEmbeddedFontsOnly.

Strategie SubsetAllFonts vloží všechna písma do dokumentu jako podmnožinu. Podmnožina je část písma, která obsahuje pouze znaky použité v dokumentu. Tato strategie je užitečná pro zmenšení velikosti souboru dokumentu PDF.

Strategie SubsetEmbeddedFontsOnly vloží pouze podmnožinu písem, která jsou již v dokumentu vložena. Pokud písmo není vloženo, nebude tato strategie ovlivněna.

Následující kód ukazuje, jak vložit písma do souboru PDF pomocí strategie podmnožiny:

```csharp
// Všechna písma budou vložena jako podmnožina do dokumentu v případě SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

// Podmnožina písem bude vložena pro plně vložená písma, ale písma, která nejsou vložena do dokumentu, nebudou ovlivněna.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## Krok 5: Uložte dokument PDF
Jakmile vložíte všechna písma do souboru PDF pomocí strategie podmnožiny, musíte dokument uložit. Následující kód ukazuje, jak uložit soubor PDF:

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### Příklad zdrojového kódu pro vkládání písem se strategií podmnožiny pomocí Aspose.PDF pro .NET. 

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
// Všechna písma budou vložena jako podmnožina do dokumentu v případě SubsetAllFonts.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
// Podmnožina písem bude vložena pro plně vložená písma, ale písma, která nejsou vložena do dokumentu, nebudou ovlivněna.
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## Závěr
tomto článku jsme diskutovali o tom, jak vložit písma do souboru PDF se strategií podmnožiny pomocí Aspose.PDF pro .NET. Aspose.PDF for .NET poskytuje jednoduché a snadno použitelné rozhraní API pro práci s dokumenty PDF, včetně přidávání a vkládání písem s různými strategiemi. Vkládání písem do souboru PDF je důležitým krokem k zajištění správného zobrazení dokumentu na různých zařízeních a strategie podmnožiny je užitečnou funkcí pro zmenšení velikosti souboru dokumentu PDF.

### Časté dotazy pro vkládání písem do souboru PDF se strategií podmnožin

#### Otázka: Jaká je strategie podmnožiny pro vkládání písem do souboru PDF?

Odpověď: Strategie podmnožiny pro vkládání písem do souboru PDF znamená, že bude vložena pouze část písma obsahující znaky použité v dokumentu. To pomáhá zmenšit velikost souboru dokumentu PDF odstraněním zbytečných dat písem.

#### Otázka: Jaký je rozdíl mezi strategiemi SubsetAllFonts a SubsetEmbeddedFontsOnly?

 A:`SubsetAllFonts`strategie vloží všechna písma do dokumentu jako podmnožinu, zatímco`SubsetEmbeddedFontsOnly` strategie vloží pouze podmnožinu písem, která jsou již v dokumentu vložena. Tato druhá strategie neovlivní písma, která ještě nejsou vložena.

#### Otázka: Proč je důležité vkládání písem se strategií podmnožiny?

Odpověď: Vkládání písem se strategií podmnožiny je důležité k zajištění toho, aby soubor PDF obsahoval potřebná data písem pro správné zobrazení textu a zároveň aby byla velikost souboru menší, protože obsahuje pouze znaky použité v dokumentu.

#### Otázka: Mohu použít Aspose.PDF pro .NET k vkládání písem s různými strategiemi?

 Odpověď: Ano, Aspose.PDF pro .NET poskytuje různé strategie pro vkládání písem, včetně`SubsetAllFonts` a`SubsetEmbeddedFontsOnly`. Na základě vašich požadavků si můžete zvolit vhodnou strategii.

#### Otázka: Je Aspose.PDF for .NET spolehlivou knihovnou pro práci s dokumenty PDF?

Odpověď: Ano, Aspose.PDF for .NET je spolehlivá a výkonná knihovna pro práci s dokumenty PDF. Poskytuje rozsáhlé funkce pro vytváření, úpravy a manipulaci se soubory PDF v aplikacích .NET.