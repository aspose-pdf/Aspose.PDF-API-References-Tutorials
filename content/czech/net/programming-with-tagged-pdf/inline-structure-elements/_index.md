---
title: Inline prvky struktury
linktitle: Inline prvky struktury
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce používáním online konstrukčních prvků s Aspose.PDF pro .NET. Uspořádejte své PDF pomocí nadpisů a odstavců.
type: docs
weight: 110
url: /cs/net/programming-with-tagged-pdf/inline-structure-elements/
---
tomto podrobném průvodci vám ukážeme, jak používat prvky inline struktury s Aspose.PDF pro .NET. Aspose.PDF je výkonná knihovna, která vám umožní programově manipulovat s dokumenty PDF. Vložené prvky struktury umožňují vytvořit hierarchickou strukturu v dokumentu PDF pomocí nadpisů různých úrovní a odstavců.

Pojďme se ponořit do kódu a naučit se používat prvky inline struktury s Aspose.PDF pro .NET.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Nainstalovaná knihovna Aspose.PDF pro .NET.
2. Základní znalost programovacího jazyka C#.

## Krok 1: Nastavení prostředí

Chcete-li začít, otevřete vývojové prostředí C# a vytvořte nový projekt. Ujistěte se, že jste do svého projektu přidali odkaz na knihovnu Aspose.PDF pro .NET.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu

 Prvním krokem je vytvoření nového dokumentu PDF pomocí`Document` třída.

```csharp
// Vytvořte dokument PDF
Document document = new Document();
```

## Krok 3: Práce s označeným obsahem

Poté dostaneme označený obsah dokumentu, se kterým můžeme pracovat.

```csharp
// Získejte označený obsah dokumentu
ITaggedContent taggedContent = document.TaggedContent;
```

## Krok 4: Nastavte název dokumentu a jazyk

Nyní můžeme nastavit název dokumentu a jazyk.

```csharp
// Definujte název dokumentu a jazyk
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Krok 5: Přidejte konstrukční prvky online

Nyní do našeho dokumentu přidáme prvky inline struktury, jako jsou nadpisy různých úrovní a odstavce.

```csharp
// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;

// Přidejte záhlaví různých úrovní
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Přidejte obsah do každého záhlaví
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Přidejte odstavec
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Přidejte obsah do odstavce
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Zde vytváříme prvky inline struktury, jako jsou nadpisy různých úrovní a odstavec, a přidáváme k nim obsah.

## Krok 6: Uložte označený dokument PDF

Nakonec tagovaný dokument PDF uložíme.

```csharp
// Uložte tagovaný dokument PDF
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Ukázkový zdrojový kód pro prvky Inline Structure Elements pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořit dokument Pdf
Document document = new Document();

// Získejte obsah pro práci s TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Nastavte název a jazyk pro síť dokumentů
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Získejte prvek kořenové struktury
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Uložit označený dokument PDF
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Závěr

gratuluji! Naučili jste se používat prvky inline struktury s Aspose.PDF pro .NET. Nyní můžete v dokumentu PDF vytvořit hierarchickou strukturu pomocí nadpisů různých úrovní a odstavců. Prozkoumejte další funkce Aspose.PDF a objevte jeho plný potenciál.

### FAQ

#### Otázka: Co jsou prvky vložené struktury v dokumentu PDF a jak přispívají k vytvoření hierarchické struktury?

Odpověď: Prvky vložené struktury v dokumentu PDF, jako jsou nadpisy různých úrovní a odstavce, se používají k vytvoření hierarchické struktury, která organizuje a prezentuje obsah strukturovaným způsobem. Tyto prvky umožňují vytvořit jasnou hierarchii a tok informací v dokumentu.

#### Otázka: Jak mohou prvky vložené struktury zlepšit čitelnost a organizaci dokumentu PDF?

Odpověď: Vložené prvky struktury, zejména nadpisy a odstavce, pomáhají zlepšit čitelnost a organizaci dokumentu PDF tím, že poskytují logickou strukturu. Nadpisy označují různé úrovně důležitosti a pomáhají čtenářům orientovat se v obsahu, zatímco odstavce seskupují související informace dohromady.

#### Otázka: Jak Aspose.PDF pro .NET usnadňuje použití prvků inline struktury?

A: Aspose.PDF for .NET nabízí třídy a metody pro vytváření a manipulaci s prvky vložené struktury, jako jsou nadpisy a odstavce. Tyto prvky lze přizpůsobit, hierarchicky organizovat a obohatit o obsah, aby se zlepšila vizuální prezentace a dostupnost dokumentu.

####  Otázka: Jaký je účel`taggedContent` object in relation to inline structure elements?

 A:`taggedContent` objekt, získaný z`TaggedContent` majetek a`Document`, umožňuje pracovat se strukturovanými prvky, včetně prvků inline struktury. Umožňuje vytvářet, přizpůsobovat a organizovat nadpisy a odstavce v dokumentu.

#### Otázka: Jak pomáhají prvky vložené struktury při vytváření jasné hierarchie dokumentů?

Odpověď: Prvky vložené struktury, jako jsou nadpisy různých úrovní, přispívají k vytvoření jasné a dobře definované hierarchie v dokumentu. Čtenáři mohou rychle identifikovat hlavní témata, podtémata a související obsah, což usnadňuje orientaci v dokumentu a jeho pochopení.

#### Otázka: Mohu upravit vzhled a formátování prvků vložené struktury pomocí Aspose.PDF pro .NET?

Odpověď: Ano, vzhled a formátování prvků inline struktury můžete přizpůsobit. Můžete nastavit vlastnosti, jako jsou styly písma, velikosti, barvy, zarovnání, odsazení a mezery, abyste dosáhli požadované vizuální prezentace nadpisů a odstavců.

#### Otázka: Jak vytvořím a přidám nadpisy různých úrovní do dokumentu PDF pomocí prvků vložené struktury v Aspose.PDF pro .NET?

 Odpověď: Můžete vytvořit nadpisy různých úrovní pomocí`CreateHeaderElement` a poté je připojit ke kořenovému prvku struktury. Následně můžete ke každému prvku nadpisu přidat obsah pomocí`CreateSpanElement` způsob vytváření rozsahů textu.

#### Otázka: Mohu použít prvky vložené struktury k vytvoření seznamů, odrážek nebo jiných typů organizace obsahu v dokumentu PDF?

Odpověď: I když se samotné prvky vložené struktury primárně používají pro nadpisy a odstavce, můžete je použít v kombinaci s dalšími funkcemi nabízenými Aspose.PDF pro .NET k vytváření seznamů, odrážek, tabulek a dalších typů organizace obsahu pro komplexní struktura dokumentu.

#### Otázka: Jak přispívají prvky inline struktury k usnadnění přístupu k dokumentu?

Odpověď: Prvky inline struktury hrají klíčovou roli při zlepšování dostupnosti dokumentů. Správně strukturované nadpisy a odstavce poskytují jasnou hierarchii dokumentů, která pomáhá čtečkám obrazovky a dalším pomocným technologiím přesně interpretovat a zprostředkovávat obsah uživatelům s postižením.

#### Otázka: Mohu prozkoumat pokročilejší použití prvků inline struktury, jako je vytváření interaktivních prvků nebo vkládání multimédií?

A: Rozhodně! Zatímco tento tutoriál se zaměřuje na vytváření nadpisů a odstavců, Aspose.PDF for .NET nabízí pokročilé funkce pro vytváření interaktivních prvků, vkládání multimédií, přidávání hypertextových odkazů a další. Podívejte se do dokumentace a příkladů knihovny a ponořte se do těchto pokročilých funkcí.