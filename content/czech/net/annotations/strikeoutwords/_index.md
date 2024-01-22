---
title: Vyškrtněte slova
linktitle: Vyškrtněte slova
second_title: Aspose.PDF pro .NET API Reference
description: Tento článek poskytuje podrobného průvodce používáním funkce Aspose.PDF pro .NET Strike Out Words, včetně průvodce krok za krokem a vysvětlení
type: docs
weight: 150
url: /cs/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET je knihovna pro manipulaci a zpracování dokumentů PDF, která poskytuje různé funkce pro vytváření, úpravu a převod souborů PDF. Jednou z užitečných funkcí, které Aspose.PDF poskytuje, je možnost vyškrtnout slova nebo fráze v dokumentu PDF pomocí zdrojového kódu C#. V tomto článku poskytneme podrobný návod, jak vyškrtnout slova pomocí Aspose.PDF pro .NET.

## Krok 1: Načtení dokumentu PDF
Prvním krokem je načtení dokumentu PDF, který chcete upravit. V tomto tutoriálu načteme PDF dokument s názvem "vstup.pdf" ze složky "VÁŠ DOKUMENTOVÝ ADRESÁŘ". 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Krok 2: Hledání fragmentů textu
Chcete-li v dokumentu PDF vyškrtnout konkrétní slova nebo fráze, musíte je nejprve vyhledat. Aspose.PDF poskytuje třídu TextFragmentAbsorber, kterou lze použít k vyhledání určitého fragmentu textu v dokumentu PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Ve výše uvedeném kódu hledáme textový fragment "Estoque" v dokumentu PDF. Toto můžete upravit a vyhledat jakékoli jiné slovo nebo frázi, které chcete přeškrtnout.

## Krok 3: Vyškrtněte fragmenty textu
Po nalezení fragmentů textu je dalším krokem jejich vyškrtnutí. Aspose.PDF poskytuje třídu StrikeOutAnnotation, kterou lze použít k vytvoření přeškrtávací anotace pro fragment textu. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Ve výše uvedeném kódu vytváříme přeškrtávací anotaci pro každý fragment textu, který jsme našli. Nastavujeme také neprůhlednost, ohraničení a barvu přeškrtnuté anotace.

## Krok 4: Uložení upraveného dokumentu PDF
Po odstranění fragmentů textu uložte upravený dokument.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Příklad zdrojového kódu pro Strike Out Words pomocí Aspose.PDF pro .NET


```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document document = new Document(dataDir + "input.pdf");

// Vytvořte instanci TextFragment Absorber pro hledání konkrétního textového fragmentu
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Iterujte stránky dokumentu PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Získejte první stránku dokumentu PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Vytvořte kolekci Absorbed textu
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Opakujte výše uvedenou kolekci
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Získejte obdélníkové rozměry objektu TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instantiate Instance StrikeOut Annotation
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Nastavte neprůhlednost pro anotaci
	strikeOut.Opacity = .80f;
	// Nastavte ohraničení pro instanci anotace
	strikeOut.Border = new Border(strikeOut);
	// Nastavte barvu anotace
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Přidejte anotaci do kolekce anotací TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Závěr

V tomto tutoriálu jsme se naučili používat Aspose.PDF pro .NET k vyškrtnutí konkrétních slov v dokumentu PDF. Podle podrobného průvodce a pomocí dodaného zdrojového kódu C# můžete snadno načíst dokument PDF, vyhledávat konkrétní fragmenty textu a vytvářet přeškrtávací anotace pro vizuální označení a přeškrtnutí těchto slov. Aspose.PDF for .NET poskytuje jednoduchý a efektivní způsob, jak programově manipulovat s dokumenty PDF, což z něj činí cenný nástroj pro vývojáře pracující se soubory PDF v aplikacích .NET.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

Odpověď: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat a manipulovat s dokumenty PDF programově v aplikacích .NET. Poskytuje širokou škálu funkcí pro práci se soubory PDF, včetně extrakce textu, zpracování anotací, vyplňování formulářů a mnoho dalšího.

#### Otázka: Mohu použít Aspose.PDF pro .NET k vyškrtnutí konkrétních slov v dokumentu PDF?

Odpověď: Ano, Aspose.PDF for .NET poskytuje funkce pro vyhledávání konkrétních textových fragmentů v dokumentu PDF a poté vytváření přeškrtávacích anotací pro vizuální označení a přeškrtnutí těchto slov.

#### Otázka: Jak určím text, který chci v dokumentu PDF přeškrtnout?

 A: Chcete-li zadat text, který chcete přeškrtnout, můžete použít`TextFragmentAbsorber` třídy poskytované Aspose.PDF pro .NET. Umožňuje vám vyhledat konkrétní část textu v dokumentu PDF na základě požadovaných kritérií.

#### Otázka: Mohu upravit vzhled přeškrtnuté anotace?

Odpověď: Ano, můžete přizpůsobit různé vlastnosti přeškrtnuté anotace, jako je neprůhlednost, styl ohraničení a barva. To vám umožní přizpůsobit vzhled přeškrtnuté anotace vašim konkrétním požadavkům.