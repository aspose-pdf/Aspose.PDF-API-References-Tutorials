---
title: Název vlastní značky
linktitle: Název vlastní značky
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce používáním vlastního názvu tagu s Aspose.PDF pro .NET. Vylepšete strukturu svých PDF pomocí vlastních značek.
type: docs
weight: 90
url: /cs/net/programming-with-tagged-pdf/custom-tag-name/
---
## Zavedení

dnešní digitální době jsou soubory PDF všudypřítomné. Od zpráv po manuály slouží mnoha účelům v různých odvětvích. Je však zásadní zajistit, aby tyto dokumenty byly přístupné všem, včetně osob se zdravotním postižením. Zde přicházejí do hry označené soubory PDF. Usnadňují čtečkám obrazovky a dalším podpůrným technologiím efektivní interpretaci obsahu dokumentu.

## Předpoklady

Než se pustíme do kódování, je nezbytné se ujistit, že máte vše připraveno. Zde je to, co budete potřebovat:

1. Visual Studio – bude stačit jakákoli nejnovější verze, ale pro optimální funkčnost je nejlepší mít nejnovější verzi.
2.  Aspose.PDF pro .NET - Nejnovější verzi si můžete snadno stáhnout z webu[odkaz ke stažení](https://releases.aspose.com/pdf/net/).
3. Základní znalost C# – Při implementaci kódu bude prospěšná znalost základů programování v C#.

## Importujte balíčky

Jakmile máte prostředí nastaveno, další krok zahrnuje import potřebných balíčků pro použití Aspose.PDF. Můžete to udělat přidáním knihovny Aspose.PDF do vašeho projektu.

### Nainstalujte Aspose.PDF přes NuGet

1. Otevřete svůj projekt Visual Studio: Pokud jste ještě nevytvořili projekt, pokračujte a vytvořte nový.
2. Otevřete Správce balíčků NuGet: Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3. Hledat Aspose.PDF: Do vyhledávacího pole zadejte „Aspose.PDF“.
4. Instalace balíčku: Kliknutím na „Instalovat“ přidáte balíček do svého projektu. Po instalaci můžete začít!

### Přidat Směrnici použití

Chcete-li ve svém kódu využít funkci Aspose, musíte na začátek souboru přidat nezbytnou direktivu using:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Po dokončení těchto kroků jste připraveni pustit se do vytváření vašeho tagovaného PDF!

Nyní, když máte vše nastaveno, pojďme se vrhnout na hlavní úkol: vytvoření tagovaného dokumentu PDF. Zde je podrobný návod, jak to udělat pomocí Aspose.PDF pro .NET.

## Krok 1: Definujte adresář dokumentů

Nejprve budete muset určit cestu, kam bude váš PDF uložen. Zde definujete svůj datový adresář.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Vysvětlení: Nahraďte "VÁŠ ADRESÁŘ DOKUMENTŮ" skutečnou cestou, kam chcete uložit soubor PDF. Je důležité mít v tomto adresáři oprávnění k zápisu, abyste se vyhnuli jakýmkoli výjimkám za běhu.

## Krok 2: Vytvořte nový dokument PDF

 Dále vytvoříme instanci`Document` třída.

```csharp
Document document = new Document();
```

Vysvětlení: Tento řádek inicializuje nový dokument PDF. Berte to jako vytvoření prázdného plátna, na které budete malovat obsah vašeho PDF.

## Krok 3: Vytvořte označený obsah

Nyní je čas přejít k jádru značkování. Načteme označený obsah dokumentu.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Vysvětlení: The`TaggedContent` objekt nám umožňuje manipulovat s logickou strukturou a přístupností PDF pomocí hierarchického uspořádání obsahu.

## Krok 4: Nastavte název a jazyk

Dále můžete nastavit název dokumentu a atribut jazyka. To pomáhá čtečkám obrazovky zpracovat dokument správně.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Vysvětlení: Zde informujeme každého, kdo čte tento PDF, o jeho názvu a jazyce, což pomáhá v porozumění, zejména u nástrojů pro usnadnění.

## Krok 5: Vytvořte prvky logické struktury

Nyní je čas vytvořit strukturované prvky ve vašem PDF.

```csharp
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
```

 Vysvětlení: Tento krok představuje prvek sekce, kde můžete začít přidávat obsah. The`RootElement` je vaše domovská základna.

## Krok 6: Vytvořte prvky odstavce

Nyní vytváříme různé prvky odstavce a nastavujeme jejich textový obsah.

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
```

Vysvětlení: Každý odstavec se podobá větě v příběhu, vytváří scénu a poskytuje vašemu dokumentu smysl.

## Krok 7: Přiřaďte značky k odstavcům

Pro usnadnění přístupu k PDF je důležité každý odstavec vhodně označit.

```csharp
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
```

Vysvětlení: Označením pomocí značek umožňujeme asistenčním technologiím porozumět struktuře obsahu – je to jako poskytnout jim plán pro navigaci v daném území.

## Krok 8: Přidejte odstavce do oddílu

Tyto odstavce nyní připojíme k dříve vytvořené sekci.

```csharp
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
```

Vysvětlení: Tato akce uspořádá odstavce v sekci, takže tok je logický a snadno sledovatelný.

## Krok 9: Vytvořte prvky rozpětí

Stejně jako odstavce i rozpětí přidávají našemu textovému obsahu podrobné podrobnosti.

```csharp
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
```

Popis: Rozpětí je jako dolaďování detailů; dodávají specifičnost tomu, co v každém odstavci sdělujete.

## Krok 10: Přiřaďte tagy Span Elements

Stejně jako u odstavců bychom měli označit naše prvky span, abychom lépe porozuměli.

```csharp
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
```

Vysvětlení: Správné rozpětí značek zajišťuje, že jsou všechny nuance přesně reprezentovány, a vytváří tak bohatý dokument pro každého, kdo se s tím setká.

## Krok 11: Přidejte rozpětí k odstavcům

Nyní připojíme naše prvky span k jejich příslušným odstavcům.

```csharp
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Vysvětlení: Tato integrace vylepšuje vaše odstavce vrstvením dalších informací, stejně jako přidáváním poznámek pod čarou do knihy pro hlubší porozumění.

## Krok 12: Uložte tagovaný dokument PDF

Konečně je čas zachránit své mistrovské dílo!

```csharp
document.Save(dataDir + "CustomTag.pdf");
```

Vysvětlení: Tento řádek uloží vaše tagované PDF do určeného adresáře. Tím jste dokončili vytváření vašeho tagovaného dokumentu PDF!

## Závěr

Vytváření tagovaných dokumentů PDF pomocí Aspose.PDF for .NET není pouze o přidávání obsahu; jde o vytvoření přístupného zážitku pro všechny uživatele. Pomocí pouhých několika kroků můžete zajistit, že vaše dokumenty budou mluvit s každým, odstraníte překážky a zlepšíte porozumění. 

## FAQ

### Co je to tagovaný PDF?  
Tagované PDF obsahuje další metadata, která popisují strukturu a dostupnost obsahu dokumentu, což usnadňuje interpretaci pomocných technologií.

### Proč potřebuji Aspose.PDF pro .NET?  
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat a manipulovat s dokumenty PDF programově s rozsáhlými funkcemi.

### Jak mohu získat zkušební verzi Aspose.PDF?  
 Můžete získat bezplatnou zkušební verzi Aspose.PDF návštěvou[tento odkaz](https://releases.aspose.com/).

### Mohu získat podporu pro Aspose.PDF?  
 Ano, můžete se obrátit na podporu prostřednictvím[na fóru Aspose](https://forum.aspose.com/c/pdf/10).

### Kde najdu podrobnou dokumentaci Aspose.PDF?  
 Kompletní dokumentaci naleznete[zde](https://reference.aspose.com/pdf/net/).