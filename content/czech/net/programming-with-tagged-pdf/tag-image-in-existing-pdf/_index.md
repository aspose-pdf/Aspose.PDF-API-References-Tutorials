---
title: Označit obrázek ve stávajícím PDF
linktitle: Označit obrázek ve stávajícím PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se označovat obrázky ve stávajících PDF pomocí Aspose.PDF for .NET. Podrobný průvodce pro zlepšení dostupnosti s PDF/UA.
type: docs
weight: 210
url: /cs/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Zavedení

tomto tutoriálu vás provedeme, jak označit obrázek v existujícím PDF pomocí Aspose.PDF pro .NET. Na konci této příručky budete schopni nastavit alternativní text pro obrázky, upravit atributy rozvržení a zajistit, aby vaše PDF odpovídalo standardům přístupnosti.

## Předpoklady

Než se do toho pustíme, pojďme si projít, co budete potřebovat, abyste mohli začít:

-  Aspose.PDF pro .NET: Ujistěte se, že jste si stáhli a nainstalovali nejnovější verzi Aspose.PDF pro .NET.[Stahujte zde](https://releases.aspose.com/pdf/net/).
- .NET Framework: Ujistěte se, že máte nastavené vývojové prostředí .NET, jako je Visual Studio.
- Základní pochopení struktury PDF: Seznámení s prvky struktury PDF, jako jsou odstavce, rozpětí, tabulky a obrázky.
-  Platná licence: Můžete si buď zakoupit licenci[zde](https://purchase.aspose.com/buy) nebo použijte dočasnou[zde](https://purchase.aspose.com/temporary-license/).

## Importujte balíčky

Chcete-li začít s kódováním, musíte importovat základní jmenné prostory z Aspose.PDF pro .NET. Ty vám umožní přístup k nezbytným třídám a metodám pro manipulaci s dokumentem PDF.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní, když jsme připravili scénu, rozdělme proces označování obrázku do několika kroků.

## Krok 1: Načtěte existující dokument PDF

Prvním krokem je načtení souboru PDF, se kterým chcete pracovat. Může to být jakýkoli soubor PDF s obrázkem, který chcete označit.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otevřete dokument
Document document = new Document(inFile);
```

-  Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu souboru.
-  The`Document` třída umožňuje načíst existující PDF. Tento soubor PDF upravíte tak, aby byl obrázek označen.

## Krok 2: Přístup k označenému obsahu a prvku kořenové struktury

Po otevření PDF je dalším krokem přístup k označenému obsahu a identifikace prvku kořenové struktury. To je zásadní, protože vám to umožňuje procházet prvky v PDF a provádět úpravy.

```csharp
// Získejte tagovaný obsah a prvek kořenové struktury
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` poskytuje přístup ke strukturovaným prvkům v PDF.
-  The`RootElement` je nejvyšší prvek struktury, ze kterého můžete přejít dolů k dalším prvkům, jako jsou odstavce, tabulky a obrázky.

## Krok 3: Nastavte název pro tagovaný dokument PDF

Přidáním názvu do tagovaného dokumentu PDF zajistíte, že váš dokument bude správně označen, což je užitečné pro usnadnění přístupu a shodu s PDF/UA.

```csharp
// Nastavte název pro tagovaný dokument PDF
taggedContent.SetTitle("Document with images");
```

- Nastavení názvu pro váš tagovaný PDF zlepšuje přístupnost a zlepšuje srozumitelnost dokumentu pro programy pro čtení z obrazovky a asistenční technologie.

## Krok 4: Najděte a označte obrázek

 Nyní najdeme prvek obrázku (označovaný jako a`FigureElement` v Aspose.PDF), nastavte pro něj alternativní text a nakonfigurujte jeho atributy rozvržení.

```csharp
// Procházejte všechny prvky obrázku (obrázky) a nastavte alternativní text a atributy rozvržení
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Nastavte alternativní text pro obrázek
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // Vytvořte a nastavte atribut BBox (ohraničující rámeček)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Nastavte atributy rozvržení obrázku
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Tento kód prochází všemi`FigureElement` objekty v kořenové struktuře, které představují obrázky.
- Nastaví alternativní text pro usnadnění (čtečky obrazovky jej použijí k popisu obrázku).
- Ohraničující rámeček (`BBox`určuje souřadnice rozvržení obrázku a zajišťuje, že se v dokumentu zobrazí správně.

## Krok 5: Upravte prvky rozpětí v tabulce

 V některých případech může být nutné upravit prvky span v tabulce. Zde si ukážeme, jak najít a`SpanElement` a přesunout jej do odstavce.

```csharp
// Najděte prvky tabulky, rozpětí a odstavce
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Přesuňte prvek span do odstavce
spanElement.ChangeParentElement(paragraph);
```

-  Zde najdeme`TableElement`, `SpanElement` a`ParagraphElement` v rámci PDF.
-  Pomocí`ChangeParentElement` přesuneme rozsah do odstavce, abychom zajistili správné označení a strukturu.

## Krok 6: Uložte dokument a ověřte shodu s PDF/UA

Po provedení všech změn je posledním krokem uložení aktualizovaného PDF a kontrola, zda vyhovuje standardům PDF/UA.

```csharp
// Uložte aktualizovaný dokument PDF
document.Save(outFile);

// Ověřte shodu s PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  The`Validate` metoda kontroluje PDF dokument podle standardů PDF/UA a zaznamenává výsledky.
- Zajištění souladu pomáhá zlepšit dostupnost a splnit regulační požadavky na publikování dokumentů.

## Závěr

tomto tutoriálu jsme vám ukázali, jak označit obrázky v existujícím PDF pomocí Aspose.PDF pro .NET. Nastavením alternativního textu, úpravou atributů rozvržení a ověřením souladu dokumentu s PDF/UA můžete zajistit, že vaše PDF budou přístupné a splňují moderní standardy. Aspose.PDF usnadňuje práci se strukturovanými prvky a poskytuje vám kontrolu nad rozložením a přístupností vašeho dokumentu.

## FAQ

### K čemu se používá Aspose.PDF for .NET?
Aspose.PDF for .NET je výkonná knihovna používaná pro vytváření, úpravy a manipulaci s dokumenty PDF programově v prostředí .NET.

### Jak zajistím soulad s PDF/UA?
 Můžete použít Aspose.PDF`Validate` způsob kontroly souladu s PDF/UA po provedení úprav dokumentu.

### Co je alternativní text v PDF?
Alternativní text je popis přidaný k obrázkům v PDF, aby se zlepšila dostupnost, zejména pro uživatele, kteří se spoléhají na čtečky obrazovky.

### Mohu manipulovat s tabulkami a rozpětími v PDF pomocí Aspose.PDF?
Ano, Aspose.PDF vám umožňuje manipulovat s tabulkami, rozpětími a dalšími strukturovanými prvky v dokumentu PDF.

### Kde si mohu stáhnout Aspose.PDF pro .NET?
 Můžete si stáhnout nejnovější verzi Aspose.PDF pro .NET[zde](https://releases.aspose.com/pdf/net/).