---
title: MHT do PDF
linktitle: MHT do PDF
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem MHT do PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 70
url: /cs/net/document-conversion/mht-to-pdf/
---
V tomto tutoriálu vás provedeme procesem převodu souboru MHT do PDF pomocí Aspose.PDF for .NET. MHT (MIME HTML) je formát používaný k uložení kompletní webové stránky, včetně obrázků a souvisejícího obsahu. Podle níže uvedených kroků budete moci převést soubory MHT do formátu PDF.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtení souboru MHT
tomto kroku načteme soubor MHT pomocí Aspose.PDF pro .NET. Postupujte podle níže uvedeného kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Vložte dokument
Document document = new Document(dataDir + "test.mht", options);
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor MHT.

## Krok 2: Převod MHT do PDF
Po načtení MHT souboru můžeme přistoupit k převodu do PDF. Použijte následující kód:

```csharp
// Uložte výstup jako dokument PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 Výše uvedený kód převede soubor MHT do formátu PDF a uloží jej jako název souboru`"MHTToPDF_out.pdf"`.

### Příklad zdrojového kódu pro MHT do PDF pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Načíst dokument
Document document = new Document(dataDir  + "test.mht", options);
// Uložte výstup jako dokument PDF
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Závěr
V tomto tutoriálu jsme se zabývali procesem převodu MHT souboru do PDF pomocí Aspose.PDF for .NET krok za krokem. Podle výše uvedených pokynů byste nyní měli být schopni převést soubory MHT do formátu PDF. Tato funkce může být užitečná, když potřebujete převést celé webové stránky na dokumenty PDF.

### FAQ

#### Otázka: Podporuje Aspose.PDF for .NET převod souborů MHT s vloženými obrázky do PDF?

Odpověď: Ano, Aspose.PDF pro .NET podporuje převod souborů MHT s vloženými obrázky do PDF. Knihovna dokáže zpracovat kompletní obsah webových stránek, včetně obrázků a souvisejících zdrojů, a převést jej na dokument PDF.

#### Otázka: Mohu přizpůsobit výstup PDF během procesu převodu MHT do PDF?

Odpověď: Ano, Aspose.PDF for .NET poskytuje různé možnosti přizpůsobení výstupu PDF během procesu převodu MHT do PDF. Můžete nastavit vlastnosti, jako je velikost stránky, orientace, okraje a další, abyste řídili vzhled výsledného dokumentu PDF.

#### Otázka: Zachová Aspose.PDF for .NET ve výstupu PDF hypertextové odkazy a formátování z původního souboru MHT?

Odpověď: Ano, Aspose.PDF for .NET zachovává hypertextové odkazy a formátování z původního souboru MHT ve výstupu PDF. Knihovna zajišťuje, že převedené PDF zachová stejné rozvržení a obsah jako zdrojový soubor MHT.

#### Otázka: Mohu pomocí Aspose.PDF for .NET převést více souborů MHT na samostatné dokumenty PDF?

Odpověď: Ano, pomocí Aspose.PDF pro .NET můžete převést více souborů MHT na samostatné dokumenty PDF. Jednoduše načtěte každý soubor MHT a uložte jej jako samostatný dokument PDF s jedinečným názvem souboru.