---
title: Odstraňte nepoužívaná písma v souboru PDF
linktitle: Odstraňte nepoužívaná písma v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak odstranit nepoužívaná písma v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 300
url: /cs/net/programming-with-text/remove-unused-fonts/
---
tomto tutoriálu vysvětlíme, jak odstranit nepoužívaná písma v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces načtení PDF, identifikaci a odstranění nepoužívaných písem a uložení aktualizovaného PDF pomocí poskytnutého zdrojového kódu C#.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve musíte nastavit cestu k adresáři, kde jsou umístěny vaše soubory PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k souborům PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte zdrojový soubor PDF

 Dále načteme zdrojový dokument PDF pomocí`Document` třídy z knihovny Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Krok 3: Identifikujte a odstraňte nepoužívaná písma

 Vytváříme a`TextFragmentAbsorber` objekt s`TextEditOptions` parametr nastaven na`TextEditOptions.FontReplace.RemoveUnusedFonts` . Tato možnost nám umožňuje identifikovat a odstranit nepoužívaná písma v dokumentu PDF. Poté iterujeme všechny`TextFragments` a nastavte písmo na požadované písmo.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Krok 4: Uložte aktualizované PDF

Nakonec aktualizovaný dokument PDF uložíme do zadaného výstupního souboru.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Ukázkový zdrojový kód pro Remove Unused Fonts using Aspose.PDF for .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Načíst zdrojový soubor PDF
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Iterujte všechny TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Uložit aktualizovaný dokument
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Závěr

tomto tutoriálu jste se naučili, jak odstranit nepoužívaná písma z dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a spuštěním poskytnutého kódu C# můžete načíst PDF, identifikovat a odstranit nepoužívaná písma a uložit aktualizované PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Odstranit nepoužívaná písma v souboru PDF“?

Odpověď: Výukový program "Odstranit nepoužívaná písma v souboru PDF" vysvětluje, jak používat knihovnu Aspose.PDF pro .NET k odstranění nepoužívaných písem z dokumentu PDF. Výukový program vás provede procesem načítání PDF, identifikace a odstraňování nepoužívaných písem a ukládání aktualizovaného PDF.

#### Otázka: Proč bych měl chtít odstranit nepoužívaná písma z dokumentu PDF?

Odpověď: Odstranění nepoužívaných písem z dokumentu PDF může pomoci snížit velikost souboru a optimalizovat dokument pro lepší výkon. To je užitečné zejména při práci s PDF, které obsahují vložená písma, která nejsou ve skutečnosti použita v obsahu dokumentu.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kde jsou umístěny vaše soubory PDF.

#### Otázka: Jak odstraním nepoužívaná písma z dokumentu PDF pomocí knihovny Aspose.PDF?

Odpověď: Výukový program vás provede procesem krok za krokem:

1.  Otevřete dokument PDF pomocí`Document` třída.
2.  Vytvořit`TextFragmentAbsorber` objekt s`TextEditOptions` nastaven na`FontReplace.RemoveUnusedFonts`.
3. Přijměte absorbér k identifikaci a odstranění nepoužívaných písem z PDF.
4.  Iterujte skrz všechny`TextFragments` a nastavte písmo na požadované písmo.
5. Uložte aktualizovaný dokument PDF.

####  Otázka: Jaký je účel`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A:`TextEditOptions.FontReplace.RemoveUnusedFonts` parametr dává pokyn`TextFragmentAbsorber` k identifikaci a odstranění nepoužívaných písem z dokumentu PDF.

#### Otázka: Mohu nahradit nepoužívaná písma písmem podle mého výběru?

Odpověď: Ano, kód můžete upravit tak, aby se nepoužívané fonty nahradily fontem dle vašeho výběru. V poskytnutém ukázkovém kódu je jako náhrada použito písmo "Arial, Bold".

####  Otázka: Jak to`TextFragmentAbsorber` work to remove unused fonts?

 A:`TextFragmentAbsorber` je nakonfigurován s`TextEditOptions.FontReplace.RemoveUnusedFonts` parametr, který identifikuje nepoužívaná písma v textových fragmentech PDF. Po absorpci můžete iterovat přes`TextFragments` a nastavte jejich písma na požadovaná náhradní písma.

#### Otázka: Jaký je očekávaný výsledek spuštění poskytnutého kódu?

Odpověď: Podle návodu a spuštěním poskytnutého kódu C# odstraníte nepoužívaná písma ze vstupního dokumentu PDF a uložíte aktualizovanou verzi jako výstupní soubor PDF.

#### Otázka: Mohu upravit kód a odstranit písma pouze z určitých stránek nebo oblastí?

Odpověď: Poskytnutý kód se zaměřuje na odstranění nepoužívaných písem z celého dokumentu PDF. Pokud chcete zacílit na konkrétní stránky nebo oblasti pro odstranění písem, budete muset upravit přístup a použít složitější logiku k identifikaci nepoužívaných písem v těchto oblastech.