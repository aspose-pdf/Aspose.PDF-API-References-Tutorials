---
title: Nastavte titulek přepínače
linktitle: Nastavte titulek přepínače
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit popisky přepínačů v PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce vás provede načítáním, úpravou a ukládáním formulářů PDF.
type: docs
weight: 280
url: /cs/net/programming-with-forms/set-radio-button-caption/
---
## Zavedení

Pokud se ponoříte do manipulace s PDF pomocí Aspose.PDF pro .NET, máte na co těšit! Dnes se zaměřujeme na praktickou funkci: nastavení popisků přepínačů ve formulářích PDF. Přepínací tlačítka jsou nezbytná pro uživatelské formuláře, kde potřebujete výběr ze sady možností. Představte si je jako otázky s více možnostmi, kde je povolena pouze jedna odpověď. Tento výukový program vás provede procesem aktualizace popisků přepínačů ve formátu PDF, takže vaše dokumenty budou interaktivní a uživatelsky přívětivé. 

## Předpoklady

Než se ponoříte do kódu, musíte se ujistit, že máte několik věcí:

1. Aspose.PDF pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF. Tato knihovna vám pomůže programově manipulovat se soubory PDF.
2. Vývojové prostředí: Měli byste mít nastavené vývojové prostředí .NET, jako je Visual Studio.
3. Ukázkový formulář PDF: Pro tento výukový program budete potřebovat vzorový formulář PDF s přepínači. Můžete použít jakýkoli existující formulář PDF nebo vytvořit nový pomocí přepínačů.
4. Základní znalost C#: Tato příručka předpokládá, že máte základní znalosti o programování C# a .NET.

 Pokud jste ještě nenainstalovali Aspose.PDF pro .NET nebo potřebujete dočasnou licenci, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/) nebo[získat dočasnou licenci](https://purchase.aspose.com/temporary-license/).

## Importujte balíčky

Chcete-li začít, musíte do svého projektu C# importovat potřebné balíčky. Zde je návod, jak zahrnout knihovnu Aspose.PDF:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Ujistěte se, že jste tyto balíčky přidali do svého projektu prostřednictvím NuGet nebo vaší preferované metody.

## Krok 1: Načtěte formulář PDF

 Nejprve musíte načíst formulář PDF, který obsahuje přepínače. The`Aspose.Pdf.Facades.Form` tomuto účelu slouží třída. Postup je následující:

```csharp
// Definujte cestu k adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Načtěte zdrojový formulář PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

V tomto fragmentu kódu:
- `dataDir` určuje cestu, kde se nachází vaše PDF.
- `Form` třída se používá k interakci s poli formuláře v PDF.
- `Document` class poskytuje přístup ke stránkám dokumentu PDF.

## Krok 2: Iterujte přes pole přepínacích tlačítek

Dále budete muset iterovat pole ve formuláři, abyste identifikovali a manipulovali s poli přepínacích tlačítek:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

V této smyčce:
- `FieldNames` poskytuje seznam všech názvů polí v PDF.
- `GetButtonOptionValues(item)` načte možnosti dostupné pro každý přepínač.

## Krok 3: Upravte možnosti přepínače

 Jakmile určíte pole přepínačů, můžete upravit jejich možnosti. K tomu musíte pole přenést na`RadioButtonField` a aktualizovat jeho možnosti:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Zde:
- Zkontrolujeme, zda název pole obsahuje „radio1“, abychom identifikovali konkrétní pole přepínače, které chceme upravit.
- `RadioButtonField`se přelije z polí formuláře za účelem provedení konkrétních úprav.

## Krok 4: Nastavte titulek pro přepínač

 Chcete-li nastavit nebo aktualizovat titulek pro přepínač, budete muset vytvořit a`TextFragment` a používat`TextBuilder` pro umístění na požadované místo:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // Vytvořte objekt TextParagraph
        TextParagraph par = new TextParagraph();
        // Nastavit pozici odstavce
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Určete režim zalamování slov
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Přidejte nový TextFragment do odstavce
        par.AppendLine(updatedFragment);
        // Přidejte TextParagraph pomocí TextBuilder
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

V této části:
- `TextFragment` se používá k definování textu a jeho vzhledu.
- `TextParagraph` pomáhá umístit a formátovat text.
- `TextBuilder` přidá text na zadanou stránku PDF.

## Krok 5: Uložte aktualizované PDF

Nakonec uložte aktualizované PDF do nového souboru:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

To zajistí, že:
- Změny se použijí na PDF.
- Původní možnost přepínače je odstraněna, jak je uvedeno.

## Závěr

Úprava titulků přepínačů ve formátu PDF pomocí Aspose.PDF for .NET může výrazně zlepšit interaktivitu a použitelnost vašich dokumentů. Pomocí kroků uvedených v tomto kurzu můžete snadno načíst soubor PDF, aktualizovat možnosti přepínače a uložit změny. Tento přístup je užitečný pro správu formulářů a zajišťuje, že vaše soubory PDF splňují přesné potřeby vašich uživatelů. Ponořte se do Aspose.PDF a prozkoumejte jeho možnosti pro další manipulace s PDF!

## FAQ

### Mohu aktualizovat více polí přepínačů najednou?
Ano, můžete procházet všechna pole přepínačů a podle potřeby aplikovat změny.

### Potřebuji licenci k používání Aspose.PDF?
 Můžete začít s bezplatnou zkušební verzí, ale pro rozšířené použití je vyžadována licence.[Získejte licenci zde](https://purchase.aspose.com/buy).

### Jak mohu otestovat změny před uložením PDF?
PDF si můžete prohlédnout ve svém vývojovém prostředí nebo použít prohlížeč PDF ke kontrole úprav.

### Je Aspose.PDF kompatibilní se všemi verzemi .NET?
Aspose.PDF podporuje různé verze .NET. Ujistěte se, že jste zkontrolovali kompatibilitu s vaší konkrétní verzí .NET.

### Mohu podobně manipulovat s jinými poli formuláře?
Ano, podobné techniky lze použít i na jiné typy polí formuláře v dokumentech PDF.