---
title: Vyškrtněte slova
linktitle: Vyškrtněte slova
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vyškrtávat slova v PDF pomocí Aspose.PDF for .NET s tímto komplexním průvodcem krok za krokem. Vylepšete své dovednosti v oblasti úpravy dokumentů.
type: docs
weight: 150
url: /cs/net/annotations/strikeoutwords/
---
## Zavedení

Už jste někdy zjistili, že potřebujete zdůraznit konkrétní text v PDF přeškrtnutím? Ať už kontrolujete dokumenty, označujete text nebo prostě potřebujete zvýraznit určité části, vyškrtávání slov může být cenným nástrojem. V tomto tutoriálu prozkoumáme, jak to udělat pomocí Aspose.PDF pro .NET. Tento komplexní průvodce vás provede každým krokem a zajistí, že budete mít všechny informace potřebné k efektivní implementaci této funkce ve vašich aplikacích .NET. 

## Předpoklady

Než se pustíme do kódu, existuje několik předpokladů, které musíte splnit, abyste mohli postupovat spolu s tímto tutoriálem:

1.  Aspose.PDF for .NET Library: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF for .NET. Můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).

2. .NET Framework: Ujistěte se, že máte na svém počítači nainstalované rozhraní .NET Framework. Tento tutoriál je určen pro aplikace .NET.

3. Vývojové prostředí: K psaní a spouštění kódu budete potřebovat IDE, jako je Visual Studio.

4. Dokument PDF: Připravte si vzorový soubor PDF, se kterým chcete pracovat. Toto bude dokument, kde text přeškrtneme.

5. Základní znalosti C#: Pro pochopení a implementaci kroků v tomto tutoriálu je nezbytná znalost programování C#.

## Importujte balíčky

Než začneme kódovat, musíme do našeho .NET projektu naimportovat potřebné jmenné prostory. To nám umožní přístup ke třídám a metodám potřebným pro manipulaci se soubory PDF pomocí Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Tyto jmenné prostory jsou nezbytné pro práci s dokumenty PDF, práci s textem a přidávání anotací, jako jsou přeškrtnutí.

této části rozdělíme proces vyškrtávání slov v dokumentu PDF do jednoduchých, zvládnutelných kroků. Každý krok bude doprovázen podrobným vysvětlením, abyste pochopili, jak vše funguje.

## Krok 1: Načtěte dokument PDF

Prvním krokem je načtení dokumentu PDF, který chcete upravit. Tento dokument bude ten, kde budete vyškrtávat konkrétní slova nebo fráze.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Tato proměnná obsahuje cestu k adresáři vašeho dokumentu. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš soubor PDF.
- `Document` : The`Document` třída představuje dokument PDF. Předáním cesty k souboru jeho konstruktoru otevřeme soubor PDF ke zpracování.

## Krok 2: Vytvořte absorbér textových fragmentů pro vyhledání konkrétního textu

 Dále vytvoříme instanci`TextFragmentAbsorber` pro vyhledání určitého fragmentu textu v dokumentu PDF. To nám umožňuje najít text, který chceme přeškrtnout.

```csharp
// Vytvořte instanci TextFragment Absorber a vyhledejte konkrétní fragment textu
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Tato třída se používá k vyhledání a práci s konkrétními fragmenty textu v dokumentu PDF. V tomto příkladu hledáme slovo „Estoque“. Nahraďte „Estoque“ slovem nebo frází, kterou chcete ve svém dokumentu najít.

## Krok 3: Iterujte stránky dokumentu PDF

 Nyní, když máme své`TextFragmentAbsorber`, musíme procházet každou stránku dokumentu PDF, abychom našli zadaný text.

```csharp
// Iterujte stránky dokumentu PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Získejte aktuální stránku dokumentu PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Tato smyčka prochází každou stránku dokumentu PDF.
- `document.Pages[i]`: Načte aktuální stránku, která se zpracovává.
- `page.Accept(textFragmentAbsorber)` : Tato metoda platí`TextFragmentAbsorber` na aktuální stránku vyhledáním zadaného textu.

## Krok 4: Sbírejte a zpracujte textové fragmenty

Po iteraci stránek shromáždíme nalezené fragmenty textu a připravíme je k dalšímu zpracování.

```csharp
// Vytvořte kolekci absorbovaných fragmentů textu
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Tato kolekce ukládá všechny fragmenty textu, které byly v dokumentu nalezeny. Tuto kolekci použijeme v dalším kroku k přeškrtnutí textu.

## Krok 5: Opakujte textové fragmenty a vyškrtněte je

V tomto kroku projdeme každý textový fragment v naší kolekci a použijeme na něj přeškrtnutou anotaci.

```csharp
// Iterujte sbírku textových fragmentů
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Získejte pravoúhlé rozměry objektu TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Instantiate Instance StrikeOut Annotation
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Nastavte vlastnosti přeškrtnuté anotace
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Přidejte anotaci do kolekce anotací na stránce fragmentu textu
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Tento řádek načte aktuální fragment textu.
- `Aspose.Pdf.Rectangle`: Vypočítáme pravoúhlé rozměry fragmentu textu, abychom určili, kde použít přeškrtnutí.
- `StrikeOutAnnotation`: Tato třída představuje přeškrtnutou anotaci. Instanciujeme jej s vypočítaným obdélníkem a aktuální stránkou.
- `strikeOut.Opacity`: Tato vlastnost nastavuje neprůhlednost přeškrtnutí, takže je z 80 % viditelné.
- `strikeOut.Color`Barvu přeškrtnutí nastavíme na červenou. Tuto barvu můžete změnit na libovolnou barvu.
- `textFragment.Page.Annotations.Add(strikeOut)`: Tím se na stránku přidá přeškrtnutá anotace.

## Krok 6: Uložte upravený dokument PDF

Posledním krokem je uložit upravený dokument PDF s použitými přeškrtnutími.

```csharp
// Uložte aktualizovaný dokument PDF
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Tím se vytvoří nový název souboru pro upravený dokument. Původní soubor zůstane nezměněn.
- `document.Save(dataDir)`: Uloží dokument PDF s přeškrtnutím do určeného umístění.

## Závěr

Gratuluji! Úspěšně jste vyškrtli konkrétní slova v dokumentu PDF pomocí Aspose.PDF pro .NET. Podle tohoto podrobného průvodce si nyní můžete přizpůsobit dokumenty PDF zvýrazněním nebo přeškrtnutím textu, čímž se stanou dynamičtějšími a přizpůsobenými vašim potřebám. Ať už přidáváte poznámky k právním dokumentům, připravujete zprávy nebo jen označujete text ke kontrole, tento výukový program vás vybaví dovednostmi, jak to udělat efektivně.

## FAQ

### Mohu změnit barvu přeškrtnutí?

 Ano, můžete změnit barvu úpravou`strikeOut.Color`vlastnictví. Můžete jej nastavit například na`Aspose.Pdf.Color.Blue` pro modré přeškrtnutí.

### Je možné vyškrtnout více slov najednou?

 Absolutně! The`TextFragmentAbsorber` lze použít k vyhledání libovolného slova nebo fráze v dokumentu. Přeškrtnutí můžete použít na více instancí iterací přes`TextFragmentCollection`.

### Co když chci přeškrtnout text pouze na konkrétních stránkách?

 Smyčku, která prochází stránkami, můžete upravit tak, aby zahrnovala pouze stránky, které chcete upravit. Například,`for (int i = 1; i <= 3; i++)` přeškrtne pouze první tři stránky.

### Jak mohu upravit tloušťku přeškrtnuté čáry?

 Tloušťku přeškrtnuté čáry můžete upravit úpravou`Border` vlastnictvím`StrikeOutAnnotation`. To umožňuje přizpůsobení vzhledu přeškrtnutí.

### Existuje způsob, jak zrušit přeškrtnutí po uložení dokumentu?

Jakmile je dokument uložen, přeškrtnutí je trvalé. Pokud potřebujete zachovat původní text bez přeškrtnutí, zvažte uložení zálohy původního dokumentu před použitím jakýchkoli úprav.