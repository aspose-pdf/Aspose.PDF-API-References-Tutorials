---
title: Získejte číslo stránky záložky v souboru PDF
linktitle: Získejte číslo stránky záložky v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno získejte číslo stránky záložky v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 60
url: /cs/net/programming-with-bookmarks/get-bookmark-page-number/
---
Načítání čísel stránek spojených se záložkami v souboru PDF může být užitečné pro navigaci. S Aspose.PDF pro .NET můžete snadno získat počet stránek záložek podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf.Facades;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, ze kterého chcete extrahovat čísla stránek záložek. Nahradit`"YOUR DOCUMENT DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Vytvořte editor záložek

 Nyní vytvoříme a`PdfBookmarkEditor` objekt pro manipulaci se záložkami dokumentu. Použijte následující kód:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Krok 4: Otevřete soubor PDF

 V tomto kroku otevřeme soubor PDF pomocí`BindPdf` metoda editoru záložek. Zde je odpovídající kód:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Krok 5: Extrahujte záložky

 Nyní extrahujeme záložky z dokumentu pomocí`ExtractBookmarks` metoda editoru záložek. Zde je odpovídající kód:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Krok 6: Procházejte záložky a získejte čísla stránek

 Nakonec projdeme extrahované záložky a pomocí a získáme čísla stránek přidružená ke každé záložce`foreach` smyčka. Zde je odpovídající kód:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Ukázkový zdrojový kód pro Get Bookmark Page Number pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořte PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Otevřete soubor PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Extrahujte záložky
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce získáním čísel stránek záložek pomocí Aspose.PDF pro .NET. Tento kód můžete použít k načtení navigačních informací spojených s každou záložkou ve vašich dokumentech PDF.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích manipulace se záložkami.

### Časté dotazy pro získání čísla stránky záložky v souboru PDF

#### Otázka: Co jsou záložky v souboru PDF?

Odpověď: Záložky v souboru PDF jsou navigační pomůcky, které uživatelům umožňují rychle přejít na určité části nebo stránky v dokumentu. Vylepšují uživatelský zážitek tím, že poskytují zkratky k relevantnímu obsahu.

#### Otázka: Proč bych měl chtít načíst čísla stránek se záložkami ze souboru PDF?

Odpověď: Načtení čísel stránek záložek pomáhá uživatelům efektivněji procházet dokumentem a poskytuje jasnou informaci o tom, kam která záložka vede. To je užitečné zejména pro delší dokumenty s více oddíly.

#### Otázka: Jak naimportuji potřebné knihovny pro můj projekt C#?

Odpověď: Chcete-li importovat požadovanou knihovnu pro váš projekt C#, použijte následující importní direktivu:

```csharp
using Aspose.Pdf.Facades;
```

Tato směrnice vám umožňuje používat třídy a metody poskytované Aspose.PDF pro .NET.

#### Otázka: Jak určím cestu ke složce dokumentů?

 Odpověď: V poskytnutém zdrojovém kódu nahraďte`"YOUR DOCUMENT DIRECTORY"`se skutečnou cestou ke složce obsahující soubor PDF, ze kterého chcete extrahovat čísla stránek záložek. To zajistí, že kód dokáže najít cílový soubor PDF.

#### Otázka: Jak vytvořím editor záložek?

Odpověď: Chcete-li vytvořit editor záložek, použijte následující kód:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Otázka: Jak mohu otevřít soubor PDF pro manipulaci se záložkami?

Odpověď: Chcete-li otevřít soubor PDF pro extrahování informací o záložce, použijte následující kód:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Nahradit`"GetBookmarks.pdf"` se skutečným názvem souboru.

#### Otázka: Jak extrahuji záložky ze souboru PDF?

 A: Chcete-li extrahovat záložky ze souboru PDF, použijte`ExtractBookmarks` metoda editoru záložek:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Otázka: Jak mohu načíst a zobrazit čísla stránek se záložkami?

 A: Procházejte extrahované záložky pomocí a`foreach` smyčka a přístup k`PageNumber` vlastnost každé záložky pro načtení a zobrazení souvisejícího čísla stránky:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Otázka: Mohu upravit vlastnosti záložky pomocí tohoto přístupu?

 Odpověď: I když se tento výukový program zaměřuje na získávání čísel stránek záložek, můžete pomocí téhož upravit další vlastnosti záložek`Bookmark`objekt a související vlastnosti.

#### Otázka: Jak uložím aktualizovaný soubor PDF po extrahování informací o záložce?

Odpověď: Extrakce záložek nezmění původní soubor PDF. Pokud chcete uložit jakékoli změny, můžete tak učinit pomocí jiných metod poskytovaných Aspose.PDF pro .NET.