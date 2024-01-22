---
title: Odebrat veškerý text z PDF
linktitle: Odebrat veškerý text z PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak odstranit veškerý text z dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 290
url: /cs/net/programming-with-text/remove-all-text-from-pdf/
---
 V tomto tutoriálu vysvětlíme, jak odstranit veškerý text z dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces otevření PDF pomocí a`TextFragmentAbsorber` k odstranění veškerého textu a uložení upraveného PDF pomocí poskytnutého zdrojového kódu C#.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve musíte nastavit cestu k adresáři, kde jsou umístěny vaše soubory PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k souborům PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument PDF

 Dále otevřeme dokument PDF pomocí`Document` třídy z knihovny Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Krok 3: Odstraňte veškerý text

 Inicializujeme a`TextFragmentAbsorber`objekt a použijte jej k odstranění veškerého absorbovaného textu z dokumentu PDF.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Krok 4: Uložte upravený PDF

Nakonec upravený PDF dokument uložíme do zadaného výstupního souboru.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Ukázka zdrojového kódu pro Remove All Text From PDF pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Spusťte TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Odstraňte veškerý absorbovaný text
absorber.RemoveAllText(pdfDocument);
// Uložte dokument
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Závěr

 V tomto tutoriálu jste se naučili, jak odstranit veškerý text z dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a provedením poskytnutého kódu C# můžete otevřít PDF a odstranit veškerý text pomocí`TextFragmentAbsorber`a uložte upravené PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Odebrat veškerý text z PDF“?

 Odpověď: Výukový program "Odebrat veškerý text z PDF" poskytuje pokyny, jak používat knihovnu Aspose.PDF pro .NET k odstranění veškerého textu z dokumentu PDF. Výukový program vás provede procesem otevření PDF pomocí a`TextFragmentAbsorber` k odstranění veškerého textu a uložení upraveného PDF.

#### Otázka: Proč bych měl chtít odstranit veškerý text z dokumentu PDF?

Odpověď: Odstranění veškerého textu z dokumentu PDF může být užitečné ve scénářích, kdy potřebujete vytvořit verzi dokumentu bez jakéhokoli textového obsahu. To může být užitečné z důvodů ochrany osobních údajů nebo pro generování vizuální reprezentace rozvržení dokumentu bez zobrazení jeho textových informací.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kde jsou umístěny vaše soubory PDF.

#### Otázka: Jak odstraním veškerý text z dokumentu PDF pomocí knihovny Aspose.PDF?

Odpověď: Výukový program vás provede procesem krok za krokem:

1.  Otevřete dokument PDF pomocí`Document` třída.
2.  Inicializovat a`TextFragmentAbsorber` objekt.
3. Použijte absorbér k odstranění veškerého absorbovaného textu z dokumentu PDF.
4. Uložte upravený dokument PDF.

#### Otázka: Mohu selektivně odstranit text z určitých oblastí dokumentu?

Odpověď: Výukový program se zaměřuje na odstranění veškerého textu z celého dokumentu PDF. Pokud chcete selektivně odstranit text z konkrétních oblastí, budete muset upravit přístup a použít složitější logiku k identifikaci a odstranění konkrétních fragmentů textu.

####  Otázka: Jak to`TextFragmentAbsorber` work to remove text?

 A:`TextFragmentAbsorber`je třída poskytovaná knihovnou Aspose.PDF, která dokáže absorbovat textové fragmenty z dokumentu PDF. Pomocí`RemoveAllText` metoda`TextFragmentAbsorber` třídy, můžete z dokumentu odstranit všechny absorbované fragmenty textu.

#### Otázka: Jaký je očekávaný výsledek spuštění poskytnutého kódu?

Odpověď: Podle návodu a spuštěním poskytnutého kódu C# odstraníte veškerý text ze vstupního dokumentu PDF a uložíte upravenou verzi jako výstupní soubor PDF.

#### Otázka: Mohu upravit kód tak, aby byl odstraněn text pouze z určitých stránek nebo oblastí?

Odpověď: Ano, můžete kód upravit, abyste toho dosáhli. Pro selektivní odstranění textu musíte upravit kód tak, aby cílil na konkrétní stránky nebo oblasti v dokumentu PDF.

#### Otázka: Je pro tento výukový program vyžadována platná licence Aspose?

Odpověď: Ano, pro úspěšné spuštění kódu v tomto tutoriálu je nutná platná licence Aspose. Na webu Aspose můžete získat plnou licenci nebo 30denní dočasnou licenci.