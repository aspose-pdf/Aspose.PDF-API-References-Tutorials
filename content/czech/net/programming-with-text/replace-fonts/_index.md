---
title: Nahradit písma v souboru PDF
linktitle: Nahradit písma v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nahradit písma v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 340
url: /cs/net/programming-with-text/replace-fonts/
---
V tomto tutoriálu vysvětlíme, jak nahradit konkrétní písma v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces načítání dokumentu PDF, hledání fragmentů textu, identifikace písem k nahrazení, nahrazení písem a uložení upraveného PDF pomocí poskytnutého zdrojového kódu C#.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve je potřeba nastavit cestu k adresáři, kde máte vstupní PDF soubor. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k vašemu PDF souboru.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument PDF

 Dále načteme dokument PDF pomocí`Document` třídy z knihovny Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Krok 3: Vyhledejte a nahraďte písma

 Vytváříme a`TextFragmentAbsorber`objekt a nastavte možnost úpravy pro odstranění nepoužívaných písem. Poté přijmeme absorbér pro všechny stránky dokumentu PDF, abychom vyhledávali textové fragmenty.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Krok 4: Nahraďte písma

Procházíme všechny textové fragmenty identifikované absorbérem. Pokud název písma části textu odpovídá požadovanému písmu, které má být nahrazeno, nahradíme jej novým písmem.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Krok 5: Uložte upravený PDF

Nakonec upravený PDF dokument uložíme do zadaného výstupního souboru.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Ukázkový zdrojový kód pro Nahradit písma pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Načíst zdrojový soubor PDF
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Prohledejte fragmenty textu a nastavte možnost úprav na odstranění nepoužívaných písem
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Přijměte absorbér pro všechny stránky
	pdfDocument.Pages.Accept(absorber);
	// Projděte všechny TextFragmenty
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Pokud je název písma ArialMT, nahraďte název písma Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Uložit aktualizovaný dokument
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak nahradit konkrétní písma v dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a spuštěním poskytnutého kódu C# můžete načíst dokument PDF, hledat fragmenty textu, identifikovat a nahradit konkrétní písma a uložit upravený PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Nahradit písma v souboru PDF"?

Odpověď: Výukový program "Nahradit písma v souboru PDF" ukazuje, jak používat knihovnu Aspose.PDF pro .NET k nahrazení určitých písem v dokumentu PDF. Poskytuje podrobného průvodce, jak načíst dokument PDF, vyhledávat fragmenty textu, identifikovat písma, která se mají nahradit, nahradit písma a uložit upravený PDF.

#### Otázka: Proč bych měl chtít nahradit písma v dokumentu PDF?

Odpověď: Nahrazení písem v dokumentu PDF může být nezbytné, když chcete standardizovat vzhled textu nebo zlepšit kompatibilitu dokumentu mezi různými zařízeními a platformami. Umožňuje vám zajistit konzistentní typografii a formátování.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kde se nachází váš vstupní soubor PDF.

#### Otázka: Jak nahradím konkrétní písma v dokumentu PDF?

Odpověď: Výukový program vás provede procesem krok za krokem:

1.  Načtěte dokument PDF pomocí`Document` třída.
2.  Vytvořit`TextFragmentAbsorber` objekt a nastavte možnost úpravy pro odstranění nepoužívaných písem. Přijměte absorbér pro všechny stránky a vyhledejte fragmenty textu.
3. Procházejte identifikované fragmenty textu. Pokud název písma části textu odpovídá písmu, které chcete nahradit, nahraďte jej novým písmem.

####  Otázka: Jaký je účel použití`TextFragmentAbsorber` with font replacement options?

 A:`TextFragmentAbsorber` s možnostmi nahrazení písem vám umožní najít fragmenty textu a současně odstranit nepoužívaná písma. To je důležité, aby se zajistilo, že nahrazená písma nebudou přidána jako další zdroje do PDF.

#### Otázka: Jak zjistím konkrétní písma, která se mají nahradit?

Odpověď: Procházením fragmentů textu identifikovaných absorbérem získáte přístup k informacím o písmu pro každý fragment textu. Pokud se název písma shoduje s písmem, které chcete nahradit, můžete provést nahrazení.

#### Otázka: Co se stane, když písmo, které má být nahrazeno, není ve fragmentu textu nalezeno?

Odpověď: Pokud písmo, které má být nahrazeno, není ve fragmentu textu nalezeno, písmo fragmentu textu zůstane nezměněno. K nahrazení dojde pouze v případě, že se název písma shoduje.

#### Otázka: Je v tomto kurzu nějaké omezení nahrazování písem?

Odpověď: Tento výukový program se zaměřuje na nahrazení konkrétních písem ve fragmentech textu. Pokud potřebujete nahradit písma v jiných kontextech, jako jsou poznámky nebo pole formuláře, budete muset odpovídajícím způsobem rozšířit přístup.

#### Otázka: Jaký je očekávaný výsledek spuštění poskytnutého kódu?

Odpověď: Podle návodu a spuštěním poskytnutého kódu C# nahradíte konkrétní písma v dokumentu PDF. Písma určená kritérii, která nastavíte, budou nahrazena novým písmem, které určíte.

#### Otázka: Mohu tento přístup použít k nahrazení písem v celém dokumentu PDF?

Odpověď: Ano, kód můžete upravit tak, aby nahradil písma v celém dokumentu PDF procházením všech textových fragmentů a použitím logiky nahrazení písem.