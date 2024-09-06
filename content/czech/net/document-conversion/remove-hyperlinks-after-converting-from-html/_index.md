---
title: Odebrat hypertextové odkazy po převodu z HTML
linktitle: Odebrat hypertextové odkazy po převodu z HTML
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném průvodci se dozvíte, jak odstranit hypertextové odkazy z dokumentů HTML po převodu do PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 250
url: /cs/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Zavedení

V digitálním věku je převod HTML dokumentů do PDF běžným úkolem. Někdy však můžete chtít odstranit hypertextové odkazy z převedeného PDF z různých důvodů, jako je zlepšení čitelnosti nebo zabránění nechtěné navigaci. V tomto tutoriálu prozkoumáme, jak toho dosáhnout pomocí Aspose.PDF pro .NET. 

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte následující předpoklady:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Toto bude vaše vývojové prostředí.
2.  Aspose.PDF pro .NET: Musíte mít knihovnu Aspose.PDF. Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět kódu.

## Importujte balíčky

Chcete-li začít, musíte do svého projektu C# importovat potřebné balíčky. Můžete to udělat takto:

1. Otevřete projekt sady Visual Studio.
2. Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3.  Hledat`Aspose.PDF` a nainstalujte jej.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Nyní, když máte vše nastaveno, pojďme si rozebrat proces odstraňování hypertextových odkazů ze souboru HTML po jeho převedení do PDF.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte zadat cestu k adresáři dokumentů. Zde se nachází váš soubor HTML a kde se uloží výstupní PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde je uložen váš soubor HTML.

## Krok 2: Načtěte dokument HTML

 Dále načtete HTML dokument pomocí`Document` třídy z Aspose.PDF. Tato třída vám umožní snadno pracovat s dokumenty PDF.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Zde načítáme soubor HTML s názvem`SampleHtmlFile.html`. Ujistěte se, že tento soubor existuje ve vašem zadaném adresáři.

## Krok 3: Uložte dokument do Memory Stream

Než začneme zpracovávat anotace, musíme dokument uložit do paměťového streamu. Tento krok je zásadní, protože připravuje dokument pro další manipulaci.

```csharp
doc.Save(new MemoryStream());
```

Tento řádek ukládá dokument do paměti a umožňuje nám s ním pracovat, aniž bychom ho zatím zapisovali na disk.

## Krok 4: Iterujte prostřednictvím anotací

Nyní si projdeme anotace v dokumentu. Anotace jsou prvky, jako jsou odkazy, komentáře a zvýraznění. Konkrétně nás zajímají anotace odkazů.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // Zpracujte anotaci odkazu
    }
}
```

V této smyčce zkontrolujeme, zda typ anotace je odkaz. Pokud ano, přistoupíme k dalším krokům.

## Krok 5: Odeberte akci hypertextového odkazu

U každé anotace odkazu musíme zkontrolovat, zda má akci hypertextového odkazu. Pokud ano, odstraníme hypertextový odkaz nastavením jeho URI na prázdný řetězec.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Tento fragment kódu zajišťuje účinné odstranění akce hypertextového odkazu.

## Krok 6: Absorbujte textové fragmenty

Dále budeme absorbovat fragmenty textu spojené s anotací odkazu. To nám umožňuje manipulovat se vzhledem textu.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Zde vytvoříme a`TextFragmentAbsorber` a nastavte jeho možnosti vyhledávání na obdélník poznámky. To nám pomáhá najít text, který byl propojen.

## Krok 7: Upravte vzhled textu

Jakmile máme textové fragmenty, můžeme upravit jejich vzhled. V tomto případě odstraníme podtržení a změníme barvu textu na černou.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Tento krok zlepšuje čitelnost textu odstraněním stylu hypertextového odkazu.

## Krok 8: Odstraňte anotaci

Po úpravě textu můžeme anotaci odkazu z dokumentu bezpečně smazat.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Tento řádek odstraní hypertextový odkaz z PDF a zajistí, že v konečném výstupu již neexistuje.

## Krok 9: Uložte upravený dokument

Nakonec musíme upravený dokument uložit do nového souboru PDF. Toto je poslední krok v našem procesu.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Tento řádek uloží dokument s odstraněnými hypertextovými odkazy a vytvoří nový soubor PDF s názvem`RemoveHyperlinksFromText_out.pdf`.

## Závěr

A tady to máte! Úspěšně jste odstranili hypertextové odkazy z dokumentu HTML po jeho převedení do PDF pomocí Aspose.PDF for .NET. Tento proces nejen zlepšuje čitelnost vašeho PDF, ale také vám dává kontrolu nad obsahem, který prezentujete. 

## FAQ

### Mohu odstranit hypertextové odkazy z jakéhokoli dokumentu PDF?
Ano, hypertextové odkazy můžete odstranit z jakéhokoli dokumentu PDF pomocí Aspose.PDF for .NET.

### Je Aspose.PDF zdarma k použití?
 Aspose.PDF nabízí bezplatnou zkušební verzi, ale pro plné funkce si musíte zakoupit licenci. Zkontrolujte[koupit stránku](https://purchase.aspose.com/buy).

### Co když narazím na problémy při používání Aspose.PDF?
 Pomoc můžete hledat na[fórum podpory](https://forum.aspose.com/c/pdf/10).

### Mohu pomocí Aspose převést jiné formáty souborů do PDF?
Ano, Aspose podporuje různé formáty souborů pro převod do PDF.

### Kde si mohu stáhnout Aspose.PDF pro .NET?
 Můžete si jej stáhnout z[odkaz ke stažení](https://releases.aspose.com/pdf/net/).