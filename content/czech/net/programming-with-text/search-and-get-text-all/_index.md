---
title: Hledat a získat text vše
linktitle: Hledat a získat text vše
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vyhledávat a získávat text ze všech stránek dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 420
url: /cs/net/programming-with-text/search-and-get-text-all/
---
## Zavedení

Potřebovali jste někdy extrahovat konkrétní text z PDF, ale přišlo vám to složité? Soubory PDF se někdy mohou zdát jako uzamčené kontejnery, takže je obtížné získat informace, které potřebujete. Ale je tu dobrá zpráva: s Aspose.PDF pro .NET můžete snadno vyhledávat a načítat text z libovolného PDF. Tato výkonná knihovna poskytuje vše, co potřebujete pro práci s PDF ve vašich aplikacích .NET, díky čemuž je extrakce textu hračkou. V tomto tutoriálu vás provedeme procesem vyhledávání a extrahování textu ze souboru PDF pomocí Aspose.PDF for .NET. Ať už vytváříte nástroj pro analýzu textu, nebo jen potřebujete automatizovat extrakci dat ze zpráv ve formátu PDF, jste na správném místě!

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše nastaveno:

1. Aspose.PDF pro .NET: Budete si muset stáhnout a nainstalovat Aspose.PDF pro .NET. Můžete jej získat ze stránky ke stažení[zde](https://releases.aspose.com/pdf/net/).
2. Prostředí .NET: Ujistěte se, že máte na vývojovém počítači nastaveno rozhraní .NET Framework nebo .NET Core.
3. Základní znalost C##: Doporučuje se určitá znalost C# a práce s projekty .NET.
4.  Dokument PDF: Ukázkový soubor PDF, ze kterého budeme extrahovat text. V tomto příkladu použijeme`SearchAndGetTextFromAll.pdf`.

## Importujte balíčky

Než začnete psát jakýkoli kód, musíte do projektu importovat potřebné jmenné prostory, abyste mohli pracovat s Aspose.PDF.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Tyto jmenné prostory poskytují přístup k objektovému modelu dokumentu PDF a umožňují nám manipulovat s textem v souboru.

Pojďme si tento proces rozdělit do jednoduchých kroků, abyste jej mohli snadno sledovat.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte zadat cestu k adresáři, kde je umístěn váš PDF. To pomůže aplikaci najít soubor, ze kterého budete extrahovat text.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  The`dataDir` proměnná by měla ukazovat na adresář, kde je váš`SearchAndGetTextFromAll.pdf` soubor je uložen.
-  Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou na vašem počítači.

## Krok 2: Otevřete dokument PDF

Dále otevřeme dokument PDF pomocí souboru Aspose.PDF`Document` objekt.

```csharp
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Vytvoříme novou instanci`Document` třídy předáním úplné cesty k souboru PDF.
- Tím se PDF načte do paměti a bude připraveno ke zpracování.

## Krok 3: Vytvořte absorbér textu

 The`TextFragmentAbsorber` objekt se používá k hledání určitého textu v PDF. V tomto případě budeme hledat slovo „text“.

```csharp
// Vytvořte objekt TextAbsorber, abyste našli všechny výskyty vstupní hledané fráze
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  The`TextFragmentAbsorber` se inicializuje pomocí řetězce`"text"`. To znamená, že bude hledat jakýkoli výskyt slova „text“ v dokumentu PDF.

## Krok 4: Přijměte absorbér pro všechny stránky

Nyní dáme dokumentu PDF pokyn, aby přijal absorbér a hledal text na všech jeho stránkách.

```csharp
// Přijměte absorbér pro všechny stránky
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  The`Accept` metoda je aplikována na stránky dokumentu. Toto vyhledá zadaný text na všech stránkách.

## Krok 5: Extrahujte textové fragmenty

Jakmile absorbér naskenuje dokument, můžeme získat extrahované části textu.

```csharp
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  The`TextFragments` vlastnictvím`TextFragmentAbsorber` vrátí kolekci všech textových fragmentů, které odpovídají hledanému výrazu.

## Krok 6: Projděte textové fragmenty

Nyní, když máme sbírku textových fragmentů, projdeme je a extrahujeme podrobnosti.

```csharp
// Projděte fragmenty
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text : {0} ", textFragment.Text);
    Console.WriteLine("Position : {0} ", textFragment.Position);
    Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

-  The`foreach` smyčka prochází každou z nich`TextFragment` ve sbírce.
- Tiskneme různé vlastnosti každého fragmentu, jako je skutečný text, jeho pozice na stránce, detaily písma a velikost písma.
-  The`XIndent` a`YIndent` vlastnosti poskytují přesné souřadnice fragmentu textu v PDF.

## Závěr

A tady to máte! Pomocí několika řádků kódu jsme úspěšně prohledali a extrahovali text z PDF pomocí Aspose.PDF for .NET. Flexibilita Aspose.PDF vám umožňuje manipulovat s PDF mnoha způsoby, což z něj dělá vynikající volbu pro vývojáře, kteří potřebují robustní PDF řešení v prostředí .NET. Tento příklad můžete snadno rozšířit o hledání dalších slov, extrahování dalších podrobností nebo dokonce manipulaci s obsahem PDF podle vašich potřeb. Doufejme, že vám tato příručka poskytla jasný a přímý přístup k práci s PDF. Neváhejte a vyzkoušejte to se svými vlastními PDF!

## FAQ

### Mohu hledat více slov najednou?  
 Ano, můžete upravit`TextFragmentAbsorber` vyhledávat více frází odpovídajícím přizpůsobením vyhledávacího řetězce.

### Co když text zabírá více řádků?  
Aspose.PDF bude stále rozpoznávat a extrahovat text, i když zahrnuje více řádků. S těmito fragmenty můžete zacházet jednotlivě.

### Jak uložím extrahovaný text do souboru?  
 Extrahovaný text můžete zapsat do souboru pomocí standardních I/O operací se souborem C#, jako je např`StreamWriter`.

### Podporuje Aspose.PDF extrahování textu z naskenovaných PDF?  
Aspose.PDF nepodporuje OCR. U naskenovaných souborů PDF byste k rozpoznání textu potřebovali nástroj OCR.

### Jak zpracuji šifrované soubory PDF?  
Pokud je váš PDF chráněn heslem, můžete jej odemknout pomocí Aspose.PDF zadáním hesla při načítání dokumentu.