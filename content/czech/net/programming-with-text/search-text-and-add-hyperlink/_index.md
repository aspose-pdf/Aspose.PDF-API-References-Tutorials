---
title: Vyhledejte text a přidejte hypertextový odkaz
linktitle: Vyhledejte text a přidejte hypertextový odkaz
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vyhledávat text a přidávat hypertextové odkazy do souborů PDF pomocí Aspose.PDF for .NET s naším podrobným výukovým programem.
type: docs
weight: 450
url: /cs/net/programming-with-text/search-text-and-add-hyperlink/
---
## Zavedení

Hledáte způsob, jak s PDF nejen manipulovat, ale také je vylepšit vložením hypertextových odkazů? Tak to jste na správném místě! S výkonnou knihovnou Aspose.PDF for .NET můžete vyhledávat vzory textu v dokumentech PDF a bez problémů přidávat hypertextové odkazy. Představte si, že máte dokument, který nejen předává informace, ale také propojuje čtenáře s relevantními zdroji pouhým kliknutím na odkaz. Zní to dobře, že? V tomto tutoriálu vás krok za krokem provedeme vyhledáváním textu pomocí regulárních výrazů a přidáváním hypertextových odkazů do souborů PDF. Ať už jste zkušený vývojář nebo teprve začínáte, tento proces bude pro vás jednoduchý a přínosný.

## Předpoklady

Než se ponoříme do toho nejzákladnějšího, ujistíme se, že máte vše, co potřebujete k dodržení. Zde je praktický kontrolní seznam:

- .NET Framework: Měli byste mít na svém počítači nainstalovaný .NET Framework (verze 4.0 nebo vyšší).
- Aspose.PDF for .NET Library: Nezapomeňte si stáhnout a přidat odkaz na knihovnu Aspose.PDF ve vašem projektu. Můžete to najít[zde](https://releases.aspose.com/pdf/net/).
- IDE: K psaní a spouštění kódu budete potřebovat integrované vývojové prostředí (IDE), jako je Visual Studio.
- Ukázkový soubor PDF: Získejte ukázkový soubor PDF, na kterém můžete otestovat kód. Můžete vytvořit jednoduchý PDF nebo použít některý z vašich stávajících dokumentů.

Jakmile zaškrtnete vše v tomto seznamu, jsme připraveni začít!

## Importujte balíčky

Prvním krokem na naší cestě je import potřebných balíčků. Zde říkáme našemu projektu, jaké nástroje budeme používat. Můžete to udělat takto:

V souboru C# začněte tím, že v horní části zahrnete následující jmenné prostory:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Importováním těchto jmenných prostorů dáte svému programu přístup ke všem skvělým funkcím, které Aspose.PDF nabízí.

Nyní, když jsme všichni připraveni, je čas pustit se do akce. Projdeme to v řadě kroků, takže je pozorně sledujte!

### Krok 1: Nastavte adresář dokumentů

Nejprve musíte určit, kde jsou soubory PDF uloženy. Upravte`dataDir` proměnná, aby ukazovala na adresář vašeho dokumentu. Postup je následující:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašim dokumentům.

### Krok 2: Vytvořte TextFragmentAbsorber

 Dále potřebujeme nástroj pro nalezení textu, který chceme propojit. Zadejte`TextFragmentAbsorber`. Tento malý chlapík nám pomůže vyhledat konkrétní vzor textu v našem PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Zde hledáme konkrétní vzor: čtyři číslice, pomlčku, po níž následují další čtyři číslice (například telefonní číslo nebo rok).

### Krok 3: Povolte vyhledávání regulárních výrazů

 K nalezení našeho textového vzoru již používáme regulární výraz, ale musíme se ujistit, že naše`absorber` ví, že je povoleno. To je pro správné vyhledávání klíčové.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Krok 4: Inicializujte PdfContentEditor

 Nyní, když máme náš absorbér připravený, potřebujeme a`PdfContentEditor` pracovat s naším souborem PDF. Tato třída nám umožňuje navázat se na naše PDF a manipulovat s ním.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Krok 5: Svažte zdrojový soubor PDF

připraveným editorem obsahu je čas jej svázat se skutečným souborem PDF, na kterém chceme pracovat.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Nezapomeňte vyměnit`"SearchRegularExpressionPage.pdf"` s názvem vašeho PDF souboru.

### Krok 6: Přijměte absorbér pro stránku

Musíme dát našemu editorovi vědět, že chceme hledat na konkrétní stránce dokumentu. V tomto případě pojďme na stránku 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Krok 7: Připravte se na procházení textových fragmentů

Nyní jsme připraveni projít všechny fragmenty textu nalezené naším absorbérem. Upravíme jejich vzhled a nastavíme náš hypertextový odkaz.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Zde nastavujeme některé parametry, jako je barva našeho hypertextového odkazu.

### Krok 8: Projděte každý textový fragment

Pro každý textový fragment, který odpovídá našemu hledání, změníme jeho barvu a vytvoříme hypertextový odkaz. Tady je to, jak to vypadá:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, modrá, název akce);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Krok 9: Uložte upravený soubor PDF

Už jsme skoro hotovi! Nyní je čas uložit naše změny do nového souboru PDF.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Krok 10: Zavřete Editor

Nakonec nezapomeňte dokument zavřít, abyste uvolnili zdroje!

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Nyní jste právě vytvořili PDF s hypertextovým odkazem, který byl dynamicky vygenerován na základě výsledků vyhledávání. Jak skvělé to je?

## Závěr

A tady to máte! Pomocí těchto kroků jste se naučili prohledávat PDF a přidávat hypertextové odkazy pomocí knihovny Aspose.PDF for .NET. To může otevřít svět možností, zejména pokud pracujete s dokumenty, které vyžadují interaktivitu. Představte si, že přidáváte odkazy na související zdroje, referenční webové stránky nebo dokonce interní stránky – to vše pomocí několika řádků kódu!
## FAQ

### Co je Aspose.PDF pro .NET?  
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a spravovat dokumenty PDF v aplikacích .NET.

### Jak si mohu stáhnout Aspose.PDF pro .NET?  
 Knihovnu si můžete stáhnout[zde](https://releases.aspose.com/pdf/net/).

### Mohu vyzkoušet Aspose.PDF zdarma?  
 Absolutně! Můžete získat bezplatnou zkušební verzi[zde](https://releases.aspose.com/).

### Je k dispozici podpora pro produkty Aspose?  
 Ano, můžete najít podporu a komunitní diskuse[zde](https://forum.aspose.com/c/pdf/10).

### Jak mohu získat dočasnou licenci pro Aspose.PDF?  
 Můžete požádat o dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/).