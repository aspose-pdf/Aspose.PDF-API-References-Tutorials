---
title: Ilustrace prvky struktury
linktitle: Ilustrace prvky struktury
second_title: Aspose.PDF pro .NET API Reference
description: Vytvářejte strukturované soubory PDF s prvky ilustrací v Aspose.PDF pro .NET podle našeho podrobného návodu.
type: docs
weight: 100
url: /cs/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## Zavedení

Jste připraveni vytvářet úžasné, strukturované soubory PDF ve svých aplikacích .NET? Ať už pracujete na projektu, který vyžaduje tagování obsahu, nebo jednoduše chcete posunout své PDF na další úroveň, Aspose.PDF for .NET má všechny nástroje, které potřebujete pro práci s prvky struktury ilustrace. V tomto tutoriálu vás provedu procesem krok za krokem a zajistím, že i ty nejsložitější části budou křišťálově čisté.

## Předpoklady

Než se ponoříme do podrobností, ujistěte se, že máte vše, co potřebujete, abyste mohli hladce sledovat.

1.  Aspose.PDF for .NET – Budete potřebovat nainstalovanou knihovnu Aspose.PDF. Ještě ho nemáte? Můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/) . Pokud to chcete nejprve otestovat, můžete si vzít a[zkušební verze zdarma](https://releases.aspose.com/).
2. Visual Studio – Budeme kódovat v C#, takže se ujistěte, že je nainstalováno Visual Studio nebo jakékoli kompatibilní IDE.
3. .NET Framework – Ujistěte se, že máte verzi kompatibilní s Aspose.PDF pro .NET.
4.  Dočasná licence – Aspose.PDF přichází s určitými omezeními ve zkušebním režimu, takže si a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro odemknutí všech funkcí.

To je vše! Nyní importujme potřebné jmenné prostory a pokročíme v kódování.

## Importovat jmenné prostory

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

To je základ – bez importu těchto jmenných prostorů nemůžeme interagovat s funkcemi Aspose.PDF ani zpracovávat tagovaný obsah PDF. Pojďme si nyní jednotlivé kroky podrobně rozebrat.

## Krok 1: Nastavení adresáře dokumentů

Než začnete vytvářet PDF, musíte zadat cestu k adresáři vašeho dokumentu, kam bude soubor uložen. Toto je složka ve vašem systému, kde jsou uloženy vaše obrázky nebo jiné položky.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Tento krok je jednoduchý, ale nezbytný. Říkáte programu, kde má najít a uložit soubory, se kterými budete pracovat. Je to jako mít domácí základnu pro vaše soubory PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou na vašem počítači.

## Krok 2: Vytvoření nového dokumentu PDF

Nyní je čas vytvořit dokument PDF. V tomto kroku spustíme prázdný dokument PDF, který v následujících krocích upravíme a vylepšíme.
 Vytvořte dokument

```csharp
Document document = new Document();
```

Tato řada dělá všechna kouzla. Vytvoří nový soubor PDF, který je zcela prázdný a čeká, až do něj přidáte obsah. Berte to jako otevření nového plátna.

## Krok 3: Přístup k označenému obsahu PDF

Abychom mohli pracovat s prvky struktury ilustrace, musíme klepnout na Tagovaný obsah dokumentu. To nám umožňuje definovat specifické tagy, díky čemuž je PDF strukturovanější a přístupnější.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Tady se děje kouzlo! The`TaggedContent` objekt nám umožňuje definovat, jak jsou prvky v PDF interpretovány. Pokud pracujete s přístupností nebo strukturou, je tento krok zásadní.

## Krok 4: Nastavení názvu a jazyka dokumentu

Vytváříme strukturované PDF, takže je nezbytné definovat název a jazyk. To nejen pomáhá s přístupností, ale také činí dokument profesionálnějším a umožňuje vyhledávat.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

Zadáním názvu a jazyka v podstatě dáte svému PDF nějakou osobitost. Název se zobrazí ve vlastnostech dokumentu a nastavení jazyka zajišťuje kompatibilitu se čtečkami obrazovky a dalšími nástroji pro usnadnění.

## Krok 5: Vytvoření prvku ilustrace (obrázku).

Nyní přichází ta vzrušující část – přidání ilustrace! V tomto případě vytvoříme prvek obrázku, který bude obsahovat obrázek, alternativní textový popis a nadpis.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

Tento kód vytvoří nový prvek obrázku a připojí ho ke kořenovému prvku dokumentu. Představte si to jako přidání zástupného symbolu obrázku do dokumentu.

## Krok 6: Přidání alternativního textu, názvu a obrázku

Abyste zajistili, že váš PDF bude přístupný, budete chtít zahrnout alternativní text a název pro vaši ilustraci. Přikládáme i obrázek.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 Toto je poslední dotek. Dáváme našemu obrázku popisný alternativní text (který je užitečný pro čtečky obrazovky), název a nastavení skutečného souboru obrázku. The`SetTag`metoda označí obrázek, což usnadňuje pozdější odkazování.

 Důležitá poznámka: Ujistěte se, že cesta k obrázku je v`SetImage` ukazuje na platný obrazový soubor na vašem počítači.

## Krok 7: Uložení označeného dokumentu PDF

Jakmile je veškerý obsah přidán a strukturován, je čas uložit PDF. Tento krok vše dokončí a vygeneruje skutečný soubor.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

Jednoduché, že? Tento příkaz převezme veškerou práci, kterou jste udělali, a vytvoří nový soubor PDF v adresáři, který jste zadali dříve. Nyní zkontrolujte svou složku a voila – máte strukturované PDF s ilustračními prvky!

## Závěr

Gratuluji! Právě jste se naučili, jak vytvořit tagované PDF s prvky struktury ilustrace pomocí Aspose.PDF pro .NET. Tento přístup zajišťuje, že vaše soubory PDF budou nejen vizuálně přitažlivé, ale také strukturované a přístupné. Označením obsahu a přidáním alternativního textu zajistíte, že si vaše dokumenty budou moci užít všichni, včetně těch, kteří používají pomocné technologie.

## FAQ

### Co je to označený obsah PDF?
Tagované PDF je PDF, které obsahuje tagy nebo štítky k identifikaci různých prvků, jako jsou nadpisy, odstavce a obrázky, díky čemuž je dokument dostupnější.

### Jak pomáhá nastavení alternativního textu?
Alternativní text poskytuje popisy obrázků, které mohou číst programy pro čtení z obrazovky, což zlepšuje přístupnost pro zrakově postižené uživatele.

### Mohu do tagovaného PDF přidat více obrázků?
 Ano! Můžete vytvořit více`FigureElement` objekty a každý z nich připojte k dokumentu, stejně jako jsme to udělali s jedním obrázkem.

### Potřebuji licenci k používání Aspose.PDF pro .NET?
 Ano, Aspose.PDF je placená knihovna, ale můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) nebo začít s a[zkušební verze zdarma](https://releases.aspose.com/).

### Je možné upravit prvek obrázku po vytvoření PDF?
Jakmile je PDF uložen, nemůžete jej přímo upravovat, ale můžete dokument znovu otevřít, provést změny a znovu jej uložit pomocí Aspose.PDF.