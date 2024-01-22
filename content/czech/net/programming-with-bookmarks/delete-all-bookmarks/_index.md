---
title: Smazat všechny záložky v souboru PDF
linktitle: Smazat všechny záložky v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno odstraňte všechny záložky v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 30
url: /cs/net/programming-with-bookmarks/delete-all-bookmarks/
---
# Odstraňte všechny záložky pomocí Aspose.PDF pro .NET

některých případech může být nutné odstranit záložky v souboru PDF. S Aspose.PDF pro .NET můžete snadno odstranit všechny záložky podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, ze kterého chcete odstranit záložky. Nahradit`"YOUR DOCUMENT DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otevřete dokument PDF

Nyní otevřeme dokument PDF, ze kterého chceme odstranit záložky, pomocí následujícího kódu:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Krok 4: Odstraňte všechny záložky

 V tomto kroku odstraníme všechny záložky z dokumentu pomocí`Delete` metoda`Outlines` vlastnictví. Zde je odpovídající kód:

```csharp
pdfDocument.Outlines.Delete();
```

## Krok 5: Uložte aktualizovaný soubor

 Nakonec uložíme aktualizovaný soubor PDF pomocí`Save` metoda`pdfDocument` objekt. Zde je odpovídající kód:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro Delete All Bookmarks pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Smazat všechny záložky
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Uložte aktualizovaný soubor
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce odstraněním všech záložek pomocí Aspose.PDF pro .NET. Tento kód můžete použít k vyčištění dokumentů PDF odstraněním všech existujících záložek.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích manipulace se záložkami.

### Časté dotazy pro odstranění všech záložek v souboru PDF

#### Otázka: Co jsou záložky v souboru PDF?

Odpověď: Záložky v souboru PDF jsou navigační pomůcky, které uživatelům umožňují rychle přejít na určité části nebo stránky v dokumentu. Pomáhají organizovat a vylepšovat uživatelskou zkušenost při procházení zdlouhavým obsahem.

#### Otázka: Proč bych měl ze souboru PDF odstranit všechny záložky?

Odpověď: Mohou nastat případy, kdy chcete z dokumentu PDF odstranit všechny záložky, abyste zjednodušili jeho navigaci, reorganizovali jeho strukturu nebo jej připravili pro konkrétní účel, kdy záložky nejsou potřeba.

#### Otázka: Jak naimportuji potřebné knihovny pro můj projekt C#?

Odpověď: Chcete-li importovat požadovanou knihovnu pro váš projekt C#, můžete použít následující importní direktivu:

```csharp
using Aspose.Pdf;
```

Tato knihovna poskytuje třídy a metody potřebné pro práci s dokumenty PDF.

#### Otázka: Jak určím cestu ke složce dokumentů?

 Odpověď: V poskytnutém zdrojovém kódu je třeba nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou ke složce obsahující soubor PDF, ze kterého chcete odstranit záložky. To zajistí, že kód dokáže najít cílový soubor PDF.

#### Otázka: Jak mohu otevřít dokument PDF pro odstranění záložky?

Odpověď: Chcete-li otevřít dokument PDF pro odstranění záložky, použijte následující kód:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

 Nahradit`"DeleteAllBookmarks.pdf"` se skutečným názvem souboru.

#### Otázka: Jak odstraním všechny záložky z dokumentu PDF?

 A: Chcete-li odstranit všechny záložky z dokumentu PDF, použijte`Delete` metoda`Outlines` vlastnictví:

```csharp
pdfDocument.Outlines.Delete();
```

#### Otázka: Co se stane se zbytkem obsahu po odstranění záložek?

Odpověď: Odstranění záložek neovlivní obsah ani rozvržení dokumentu PDF. Odstraní se pouze navigační záložky a skutečný obsah zůstane nedotčen.

#### Otázka: Jak uložím aktualizovaný soubor PDF po odstranění záložek?

Odpověď: Chcete-li uložit aktualizovaný soubor PDF po odstranění záložek, použijte následující kód:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

#### Otázka: Mohu selektivně odstranit konkrétní záložky místo všech?

Odpověď: Ano, můžete selektivně odstranit konkrétní záložky tak, že na ně zacílíte pomocí jejich indexu nebo jiných vlastností. Poskytnutý zdrojový kód ukazuje, jak odstranit všechny záložky, ale můžete jej upravit tak, aby vyhovoval vašim potřebám.

#### Otázka: Existují nějaká opatření, která bych měl před smazáním záložek učinit?

Odpověď: Před odstraněním záložek nezapomeňte zkontrolovat dokument, abyste se ujistili, že odstranění záložek neovlivní použitelnost nebo navigaci dokumentu. Než budete pokračovat, zvažte vytvoření zálohy původního dokumentu.