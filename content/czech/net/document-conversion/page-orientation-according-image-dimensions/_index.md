---
title: Orientace stránky podle rozměrů obrázku
linktitle: Orientace stránky podle rozměrů obrázku
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném průvodci se dozvíte, jak vytvářet soubory PDF pomocí Aspose.PDF for .NET a nastavit orientaci stránky na základě rozměrů obrázku.
type: docs
weight: 80
url: /cs/net/document-conversion/page-orientation-according-image-dimensions/
---
## Zavedení

Vítejte ve světě Aspose.PDF pro .NET! Pokud chcete vytvářet, manipulovat nebo převádět dokumenty PDF programově, jste na správném místě. Aspose.PDF je výkonná knihovna, která umožňuje vývojářům bezproblémově pracovat se soubory PDF. V této příručce vás provedeme procesem nastavení orientace stránky na základě rozměrů obrázku. Ať už jste zkušený vývojář nebo teprve začínáte, tento tutoriál vám poskytne znalosti, které potřebujete, abyste mohli začít s Aspose.PDF.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte vše, co potřebujete:

1. Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Je to nejlepší IDE pro vývoj .NET.
2. .NET Framework: Tato příručka předpokládá, že používáte .NET Framework. Ujistěte se, že máte nainstalovanou příslušnou verzi.
3.  Aspose.PDF pro .NET: Knihovnu si můžete stáhnout z[Aspose webové stránky](https://releases.aspose.com/pdf/net/) . Pokud si to chcete nejprve vyzkoušet, můžete získat a[zkušební verze zdarma](https://releases.aspose.com/).
4. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět příkladům.

## Importujte balíčky

Chcete-li začít, musíte importovat potřebné balíčky. Můžete to udělat takto:

1. Otevřete projekt sady Visual Studio.
2. Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3.  Hledat`Aspose.PDF` a nainstalujte jej.

Nyní, když máme vše nastaveno, pojďme si příklad rozebrat krok za krokem.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte zadat cestu k adresáři dokumentů, kde jsou obrázky uloženy. Zde bude Aspose hledat soubory JPG.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se vaše obrázky nacházejí. To je zásadní, protože pokud Aspose nemůže najít vaše obrázky, nebude moci vytvořit PDF.

## Krok 2: Vytvořte nový dokument PDF

Dále vytvoříte nový objekt dokumentu PDF. Zde budou přidány všechny vaše obrázky.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Tento řádek inicializuje novou instanci souboru`Document` třídy, která představuje váš soubor PDF.

## Krok 3: Načtěte soubory obrázků

 Nyní načteme všechny soubory JPG ze zadaného adresáře. To se provádí pomocí`Directory.GetFiles` metoda.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

Tento řádek vám poskytne pole názvů souborů, které odpovídají formátu JPG. Ujistěte se, že váš adresář obsahuje nějaké obrázky JPG, aby to fungovalo!

## Krok 4: Projděte každý obrázek

Budete muset projít každý soubor obrázku a přidat ho do dokumentu PDF. Můžete to udělat takto:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
    // Vytvořte objekt stránky
    Aspose.Pdf.Page page = doc.Pages.Add();
```

 V této smyčce vytváříte pro každý obrázek novou stránku. The`doc.Pages.Add()` přidá do vašeho dokumentu PDF novou stránku.

## Krok 5: Vytvořte objekt obrázku

 Pro každý obrázek je třeba vytvořit`Image` objekt, který bude obsahovat obrazová data.

```csharp
    Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
    image1.File = fileEntries[counter];
```

 Zde přiřadíte aktuální soubor obrázku k`Image` objekt. To je nezbytné pro přidání obrázku do PDF.

## Krok 6: Zkontrolujte rozměry obrázku

Před přidáním obrázku do PDF musíte zkontrolovat jeho rozměry, abyste určili orientaci stránky.

```csharp
    Bitmap myimage = new Bitmap(fileEntries[counter]);
    if (myimage.Width > page.PageInfo.Width)
        page.PageInfo.IsLandscape = true;
    else
        page.PageInfo.IsLandscape = false;
```

Tento fragment kódu kontroluje, zda je šířka obrázku větší než šířka stránky. Pokud je, orientace stránky je nastavena na šířku; jinak zůstane v režimu na výšku.

## Krok 7: Přidejte obrázek do PDF

Nyní, když máte nastavenou orientaci, je čas přidat obrázek do dokumentu PDF.

```csharp
    page.Paragraphs.Add(image1);
}
```

Tento řádek přidá obrázek do kolekce odstavců aktuální stránky. Je to jako umístit obrázek do rámu!

## Krok 8: Uložte dokument PDF

Nakonec musíte uložit dokument PDF do určeného adresáře.

```csharp
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Tento řádek uloží dokument s názvem`SetPageOrientation_out.pdf`. Ujistěte se, že v adresáři dokumentů naleznete nově vytvořené PDF!

## Závěr

A tady to máte! Úspěšně jste vytvořili dokument PDF pomocí Aspose.PDF for .NET, přičemž jste nastavili orientaci stránky na základě rozměrů obrázků. Tato výkonná knihovna otevírá svět možností pro práci se soubory PDF ve vašich aplikacích. Ať už generujete zprávy, faktury nebo jakýkoli jiný typ dokumentu, Aspose.PDF vám pomůže.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Jak nainstaluji Aspose.PDF?
 Aspose.PDF můžete nainstalovat přes NuGet Package Manager ve Visual Studiu nebo si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/pdf/net/).

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí a[zkušební verze zdarma](https://releases.aspose.com/) abyste si knihovnu před zakoupením otestovali.

### Kde najdu podporu pro Aspose.PDF?
Podporu najdete na[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Jaké typy souborů mohu převést do PDF pomocí Aspose?
Aspose.PDF podporuje širokou škálu formátů souborů, včetně obrázků, dokumentů Word, tabulek Excelu a dalších.