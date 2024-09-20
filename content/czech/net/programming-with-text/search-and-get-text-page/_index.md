---
title: Vyhledejte a získejte textovou stránku v souboru PDF
linktitle: Vyhledejte a získejte textovou stránku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vyhledávat a získávat text z konkrétní stránky v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 430
url: /cs/net/programming-with-text/search-and-get-text-page/
---
## Zavedení

Stalo se vám někdy, že jste potřebovali vyhledat konkrétní text v dokumentu PDF a extrahovat jej pro další použití? Možná vytváříte aplikaci, která zpracovává dokumenty a vyžaduje přesnou extrakci dat, nebo možná jen potřebujete efektivně analyzovat soubory PDF. Ať už je váš případ jakýkoli, jste na správném místě! V tomto tutoriálu se ponoříme do toho, jak vyhledávat a získávat text ze stránky v souboru PDF pomocí Aspose.PDF for .NET. Ať už jste začátečník nebo zkušený vývojář, tento průvodce vás provede každým krokem konverzačním a poutavým způsobem. Jste připraveni? Začněme!

## Předpoklady

Než se pustíme do kódování, ujistěte se, že máte vše, co potřebujete:

1.  Aspose.PDF for .NET Library: Můžete si ji stáhnout z[zde](https://releases.aspose.com/pdf/net/) nebo získat bezplatnou zkušební verzi ze stejného odkazu. Pro nákup zamiřte na[Aspose obchod](https://purchase.aspose.com/buy).
2. .NET Framework: Budete potřebovat funkční vývojové prostředí .NET, jako je Visual Studio.
3. Soubor PDF: Budete potřebovat vzorový soubor PDF, ve kterém můžeme vyhledávat a extrahovat text. Pro tento tutoriál předpokládejme, že soubor je pojmenován`SearchAndGetTextPage.pdf`.

## Importujte balíčky

Nejprve musíme importovat potřebné jmenné prostory pro práci s Aspose.PDF pro .NET. Ujistěte se, že jsou uvedeny v horní části kódu.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Nyní, když jsme probrali předpoklady, pojďme si kód rozebrat krok za krokem. Každý krok byl jasně popsán, aby se dal snadno sledovat.

## Krok 1: Nastavte cestu k adresáři vašich dokumentů

Než začnete pracovat s vaším PDF, musíte definovat cestu, kde je váš dokument PDF uložen. To zajistí, že program bude mít přístup k souboru.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Toto je cesta ke složce, kde jsou uloženy vaše soubory PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se PDF nachází.

## Krok 2: Načtěte dokument PDF

Dalším krokem je načtení dokumentu PDF do paměti, abyste s ním mohli pracovat. Zde je postup:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Dokument: Toto je třída Aspose.PDF, která načte soubor PDF.
- pdfDocument: Proměnná, kam se uloží váš soubor PDF po načtení.

## Krok 3: Vytvořte objekt absorbéru textu

 The`TextFragmentAbsorber`třída umožňuje vyhledávat konkrétní text v PDF. Vytvořme instanci této třídy, abychom našli všechny výskyty dané hledané fráze.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Tato třída je zodpovědná za vyhledávání a extrahování textu z PDF.
- "Obrázek": Nahraďte jej jakýmkoli textem, který chcete v PDF hledat.

## Krok 4: Aplikujte Text Absorber na celé PDF

Jakmile je pohlcovač textu nastaven, musíte programu sdělit, aby prohledával všechny stránky PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Tato metoda aplikuje absorbér textu na PDF a naskenuje každou stránku na zadaný text.

## Krok 5: Načtěte a iterujte extrahovaný text

Nyní, když jsme naskenovali PDF, je čas načíst výsledky a zobrazit je. Budeme procházet extrahované části textu.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Tato kolekce obsahuje všechny instance textových fragmentů nalezených absorbérem textu.

## Krok 6: Projděte každý fragment a extrahujte data

Nyní projdeme přes`textFragmentCollection` a extrahovat různé vlastnosti každého textového segmentu, jako je jeho poloha, detaily písma a barva.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment: Každý fragment obsahuje části nalezeného textu.
- TextSegment: Každý fragment může mít více segmentů, které představují různé části textu.
- TextState: Poskytuje podrobné informace o písmu, velikosti a barvě textu.

V této smyčce tiskneme podrobnosti, jako je skutečný text, jeho poloha (souřadnice X a Y), písmo, zda je písmo vloženo do PDF a barva popředí textu.

## Závěr

A tady to máte! Nyní jste úspěšně vyhledali a extrahovali text ze souboru PDF pomocí Aspose.PDF for .NET. Je neuvěřitelné, jakou flexibilitu s touto knihovnou máte. Ať už potřebujete vyhledat konkrétní text ve velkém dokumentu, extrahovat jej nebo analyzovat jeho vlastnosti, s Aspose.PDF je to hračka. Navíc s kódem, který jsme pokryli, jste dobře vybaveni, abyste jej mohli přizpůsobit svým potřebám. 

## FAQ

### Mohu hledat více frází najednou?  
 Ano, kód můžete upravit tak, aby vyhledával více frází vytvořením více frází`TextFragmentAbsorber` objektů.

### Jak mohu extrahovat text z konkrétní stránky?  
 Můžete cílit na konkrétní stránku použitím`TextFragmentAbsorber` na jednu stránku místo celého dokumentu. Například:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Je Aspose.PDF pro .NET zdarma?  
 Aspose.PDF je komerční produkt, ale můžete jej použít s a[zkušební verze zdarma](https://releases.aspose.com/).

### Mohu extrahovat obrázky z PDF pomocí Aspose.PDF?  
 Ano, Aspose.PDF umožňuje extrahovat obrázky kromě textu. Zkontrolujte[dokumentace](https://reference.aspose.com/pdf/net/) pro více podrobností.

### Co když potřebuji další pomoc nebo podporu?  
 Vždy můžete získat pomoc od[Aspose Support Forum](https://forum.aspose.com/c/pdf/10).