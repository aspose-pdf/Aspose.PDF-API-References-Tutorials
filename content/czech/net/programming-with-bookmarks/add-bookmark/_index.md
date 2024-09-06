---
title: Přidat záložku do souboru PDF
linktitle: Přidat záložku do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném návodu se dozvíte, jak přidat záložky do souborů PDF pomocí Aspose.PDF for .NET. Vylepšete svou navigaci ve formátu PDF.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/add-bookmark/
---
## Zavedení

Přistihli jste se někdy, že procházíte dlouhým dokumentem PDF a zoufale hledáte tu jednu sekci, kterou potřebujete? Pokud ano, nejste sami! Procházení rozsáhlými dokumenty může být skutečným problémem. Ale co kdybych vám řekl, že existuje způsob, jak udělat vaše PDF uživatelsky přívětivější? Zadejte záložky! V tomto tutoriálu prozkoumáme, jak přidat záložky do souboru PDF pomocí Aspose.PDF pro .NET. Tato výkonná knihovna vám umožňuje snadno manipulovat s dokumenty PDF, takže váš život je mnohem jednodušší. Takže, pojďme se ponořit!

## Předpoklady

Než začneme, je potřeba mít připraveno několik věcí:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Je to výchozí IDE pro vývoj .NET.
2.  Aspose.PDF for .NET: Budete si muset stáhnout a nainstalovat knihovnu Aspose.PDF. Můžete to vzít z[odkaz ke stažení](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže hladce pokračovat.

## Importujte balíčky

Chcete-li začít s přidáváním záložek, budete muset importovat potřebné balíčky. Můžete to udělat takto:

### znovu vytvořit nový projekt

Otevřete Visual Studio a vytvořte nový projekt C#. Pro jednoduchost zvolte konzolovou aplikaci.

### Přidejte odkaz Aspose.PDF

Jakmile je váš projekt nastaven, musíte přidat odkaz na knihovnu Aspose.PDF. Můžete to udělat takto:

- Klepněte pravým tlačítkem myši na váš projekt v Průzkumníku řešení.
- Výběrem možnosti „Spravovat balíčky NuGet“.
- Vyhledání souboru „Aspose.PDF“ a jeho instalace.

### Importujte požadované jmenné prostory

 V horní části vašeho`Program.cs` soubor, importujte potřebné jmenné prostory:

```csharp
using System;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Nyní, když máme vše nastaveno, přejděme k samotnému kódu pro přidávání záložek!

## Krok 1: Definujte adresář dokumentů

Nejprve musíte zadat cestu k adresáři dokumentů. Zde bude umístěn váš soubor PDF. Můžete to udělat takto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde je uložen váš soubor PDF.

## Krok 2: Otevřete dokument PDF

Dále budete chtít otevřít dokument PDF, do kterého chcete přidat záložky. Použijte následující kód:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Tento řádek kódu inicializuje nový`Document` objekt s vaším souborem PDF.

## Krok 3: Vytvořte objekt záložky

Nyní je čas vytvořit objekt záložky. Zde definujete název a vzhled své záložky. Jak na to:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
```

V tomto příkladu vytváříme záložku s názvem "Testovací osnova" a zvýrazníme ji tučným písmem a kurzívou. Neváhejte a upravte si titul, jak chcete!

## Krok 4: Nastavte číslo cílové stránky

Každá záložka potřebuje cíl. Číslo stránky, na kterou bude záložka odkazovat, můžete nastavit pomocí následujícího kódu:

```csharp
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

Tento řádek nastavuje akci záložky pro přechod na první stránku PDF. Číslo stránky můžete podle potřeby změnit.

## Krok 5: Přidejte záložku do dokumentu

Nyní, když jste vytvořili záložku, je čas ji přidat do kolekce osnovy dokumentu:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

Tento řádek přidá vaši nově vytvořenou záložku do dokumentu PDF.

## Krok 6: Uložte výstup

Nakonec budete chtít uložit upravený dokument PDF. Můžete to udělat takto:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

Tento kód uloží PDF s přidanou záložkou jako „AddBookmark_out.pdf“ do vámi zadaného adresáře.

## Závěr

A tady to máte! Úspěšně jste přidali záložku do souboru PDF pomocí Aspose.PDF pro .NET. Tato jednoduchá, ale výkonná funkce může výrazně zlepšit použitelnost vašich dokumentů a usnadnit čtenářům jejich procházení. Takže až budete příště pracovat s PDF, nezapomeňte přidat tyto záložky!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Mohu do PDF přidat více záložek?
 Ano, můžete vytvořit více`OutlineItemCollection`objekty a přidejte je do kolekce obrysů dokumentu.

### Je Aspose.PDF zdarma k použití?
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro plnou funkčnost si budete muset zakoupit licenci. Podívejte se na[koupit odkaz](https://purchase.aspose.com/buy).

### Kde najdu další dokumentaci?
 Kompletní dokumentaci naleznete na Aspose.PDF pro .NET[zde](https://reference.aspose.com/pdf/net/).

### Jak získám podporu pro Aspose.PDF?
 Pro podporu můžete navštívit[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10).