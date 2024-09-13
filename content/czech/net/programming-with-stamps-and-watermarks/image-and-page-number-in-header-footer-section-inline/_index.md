---
title: Obrázek a číslo stránky v záhlaví Zápatí v řádku
linktitle: Obrázek a číslo stránky v záhlaví Zápatí v řádku
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném průvodci se dozvíte, jak přidat obrázek a číslo stránky do záhlaví souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 120
url: /cs/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Zavedení

Aspose.PDF for .NET je výkonný nástroj, který poskytuje rozsáhlé možnosti pro manipulaci a generování souborů PDF. Ať už potřebujete přidat obrázky, upravit záhlaví a zápatí nebo spravovat text, Aspose.PDF vám pomůže. V tomto tutoriálu prozkoumáme, jak přidat obrázek a číslo stránky do záhlaví nebo zápatí dokumentu PDF. Pojďme se do toho ponořit a rozebrat si proces krok za krokem.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše, co můžete sledovat:

-  Aspose.PDF pro .NET: Stáhněte si nejnovější verzi z[Aspose PDF Download Page](https://releases.aspose.com/pdf/net/).
- Vývojové prostředí: Budete potřebovat C# IDE, jako je Visual Studio.
-  Licence: Pokud ještě nemáte licenci, můžete získat a[dočasná licence zde](https://purchase.aspose.com/temporary-license/) nebo si kupte plnou od[Aspose obchod](https://purchase.aspose.com/buy).

Nyní, když máte připravené předpoklady, můžeme začít.

## Importujte balíčky

Než začnete kódovat, nezapomeňte importovat potřebné jmenné prostory:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Tyto balíčky umožňují práci se soubory PDF a manipulaci s textem.

## Krok 1: Nastavte adresář dokumentů

První věc, kterou musíme udělat, je definovat cestu k adresáři, kam bude náš soubor PDF uložen. Tuto cestu lze přizpůsobit složce vašeho projektu nebo libovolnému umístění na vašem počítači.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Tato proměnná obsahuje umístění, kde bude dokument uložen. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou.

## Krok 2: Vytvořte instanci dokumentu PDF

 V tomto kroku vytvoříme novou instanci`Aspose.Pdf.Document` objekt. Tento objekt bude sloužit jako páteř vašeho souboru PDF.

```csharp
// Vytvořte instanci objektu Document voláním jeho prázdného konstruktoru
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Zde vytváříme prázdný soubor PDF, který můžeme později naplnit obsahem.

## Krok 3: Přidejte stránku do PDF

Váš PDF potřebuje alespoň jednu stránku, na kterou můžete přidat záhlaví, zápatí a obsah. Přidejme do našeho dokumentu prázdnou stránku.

```csharp
// Vytvořte stránku v objektu Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Zavoláním`pdf1.Pages.Add()`je do dokumentu přidána nová stránka připravená pro přizpůsobení záhlaví a zápatí.

## Krok 4: Vytvořte a nastavte záhlaví

Nyní je čas vytvořit záhlaví dokumentu. Zde přidáme text, obrázek a číslo stránky.

```csharp
// Vytvořte sekci záhlaví dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Nastavte záhlaví pro soubor PDF
page.Header = header;
```

 Vytváříme a`HeaderFooter` objektu a přiřaďte jej k`Header` vlastnost stránky, která zajistí, že vše, co přidáme do záhlaví, se objeví v horní části stránky.

## Krok 5: Přidejte vložený text do záhlaví

 Přidání textu je stejně jednoduché jako vytvoření a`TextFragment` a specifikovat jeho vlastnosti. Přidejme do záhlaví nějaký barevný text.

```csharp
// Vytvořte textový objekt
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Určete barvu
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 V tomto kroku vytvoříme a`TextFragment` s obsahem "Aspose.Pdf is a Robust component by" a nastavte jeho barvu na modrou. The`IsInLineParagraph` vlastnost zajišťuje, že text je vložený, což znamená, že se zobrazí na stejném řádku jako ostatní prvky (jako obrázek a další text).

## Krok 6: Vložte vložený obrázek do záhlaví

Aby bylo záhlaví vizuálně přitažlivé, můžete do textu přidat obrázek. Může to být logo vaší společnosti nebo jakákoli jiná grafika.

```csharp
// V sekci vytvořte objekt obrázku
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Nastavte cestu k souboru obrázku
image1.File = dataDir + "aspose-logo.jpg";
// Nastavte šířku obrázku Information
image1.FixWidth = 50;
image1.FixHeight = 20;
// Označte, že InlineParagraph seg1 je obrázek.
image1.IsInLineParagraph = true;
```

 Zde přidáme obrázek do záhlaví vytvořením`Image` objektu, nastavení jeho cesty a nastavení šířky a výšky. The`IsInLineParagraph` zajišťuje zarovnání obrázku s textem.

## Krok 7: Přidejte další vložený text k dokončení záhlaví

Přidáme další text k dokončení vložené hlavičky.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 V této části vytváříme další`TextFragment` s obsahem "Pty Ltd." a nastavte jeho barvu na kaštanovou. Do záhlaví jsou přidány jak fragmenty textu, tak obrázek.

## Krok 8: Uložte soubor PDF

Jakmile nastavíte záhlaví, je čas uložit PDF.

```csharp
// Uložte Pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 The`Save` metoda zapíše konečný soubor PDF do určeného umístění.

## Závěr

Gratuluji! Úspěšně jste přidali obrázek a text do záhlaví dokumentu PDF pomocí Aspose.PDF pro .NET. Tento výukový program vás provede základními kroky, včetně vytvoření dokumentu, přidání stránek, vložení záhlaví a umístění vloženého obsahu, jako je text a obrázky. Aspose.PDF vám poskytuje neuvěřitelnou flexibilitu při správě vašich PDF, ať už jde o manipulaci se záhlavím, zápatím nebo složitým obsahem. 

## FAQ

### Mohu do záhlaví přidat také číslo stránky?
 Ano! Číslo stránky můžete snadno přidat pomocí`TextFragment` třídy a podle potřeby jej naformátujte. Stačí jej vložit do sekce záhlaví jako vložený obsah.

### Jak nastavím obrázek na pozadí v záhlaví?
 Můžete použít`BackgroundImage` vlastnictví`HeaderFooter` třídy pro nastavení obrázku na pozadí. Nejedná se však o vložený obsah a pokryje celou oblast záhlaví.

### Je možné použít jiné obrazové formáty kromě JPEG?
Absolutně! Aspose.PDF podporuje různé formáty obrázků, jako jsou PNG, BMP a GIF.

### Mohu přizpůsobit písmo textu v záhlaví?
 Ano, můžete použít`TextState`objekt pro změnu písma, velikosti a stylu textu.

### Potřebuji licenci k používání Aspose.PDF pro .NET?
 Ano, Aspose.PDF vyžaduje licenci pro produkční použití, ale můžete začít s a[zkušební verze zdarma zde](https://releases.aspose.com/).