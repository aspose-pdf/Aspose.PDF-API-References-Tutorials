---
title: Přidat prvek struktury do prvku
linktitle: Přidat prvek struktury do prvku
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat prvky struktury usnadnění do souborů PDF pomocí Aspose.PDF for .NET v tomto komplexním podrobném tutoriálu.
type: docs
weight: 20
url: /cs/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## Zavedení

V dnešním digitálním světě je dostupnost klíčová. Každý by měl mít rovný přístup k informacím a zásadní je poskytovat je ve formátu, ve kterém se všichni jednotlivci mohou snadno orientovat. V tomto tutoriálu se ponoříme do toho, jak zlepšit dostupnost PDF přidáním prvků struktury pomocí Aspose.PDF pro .NET. Tato výkonná knihovna umožňuje vývojářům bezproblémově pracovat s dokumenty PDF a umožňuje jim vytvářet tagované soubory PDF, které jsou v souladu se standardy přístupnosti.

## Předpoklady

Než se pustíme do světa prvků struktury PDF, ujistěte se, že máte vše, co potřebujete:

1.  Visual Studio: Toto je vaše IDE, kde budete psát a spouštět svůj kód C#. Můžete si jej stáhnout z[Visual Studio](https://visualstudio.microsoft.com/) pokud jste to ještě neudělali.
2.  Aspose.PDF for .NET Library: K manipulaci s PDF budete potřebovat knihovnu. Stáhněte si nejnovější verzi z[Aspose webové stránky](https://releases.aspose.com/pdf/net/). Tato knihovna je pro náš projekt klíčová.
3. Základní znalost C#: Výhodou bude znalost syntaxe C# a objektově orientovaného programování. Pokud dokážete s radostí napsat pár řádků C#, můžete začít!
4. Adresář dokumentů PDF: Vytvořte ve svém systému adresář, kde budete uchovávat vstupní a výstupní soubory PDF pro tento výukový program.

Nyní, když máme naše nástroje a znalosti seřazené, pojďme přinést potřebné balíčky, abychom to mohli začít!

## Importujte balíčky

Nejprve importujme potřebné jmenné prostory. Ujistěte se, že máte v horní části souboru C# následující:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

Tyto jmenné prostory vám poskytují přístup ke třídám a metodám potřebným pro práci s dokumenty PDF a vytváření tagovaného obsahu. Nyní pojďme k jádru věci a začněme kódovat!

## Krok 1: Nastavte adresář dokumentů

Než dojde k jakémukoli kódování, musíme určit, kam budeme naše soubory ukládat. To je klíčové pro hladký běh našeho skriptu.

```csharp
// Definujte cestu k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kam chcete soubory PDF uložit. Tohle by mohlo být něco jako`C:\\PDFs\\`.

## Krok 2: Vytvořte nový dokument PDF

Nyní, když máme sadu adresářů, vytvoříme dokument PDF, do kterého přidáme prvky naší struktury.

```csharp
Document document = new Document();
```

 Tento řádek inicializuje novou instanci souboru`Document` třídy, což nám umožňuje začít pracovat s naším obsahem PDF.

## Krok 3: Přístup a nastavení označeného obsahu

Jakmile je váš dokument připraven, je čas nastavit označený obsah, který je nezbytný pro usnadnění přístupu.

### Inicializujte označený obsah

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Tento řádek poskytuje přístup k označenému obsahu vašeho PDF. Tagovaný obsah je nezbytný pro to, aby čtečky obrazovky interpretovaly váš dokument přesně.

### Nastavit metadata dokumentu

Budete chtít dát dokumentu správný název a definovat jazyk.

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

To zlepšuje metadata dokumentu a zlepšuje jeho dostupnost.

## Krok 4: Vytvořte a připojte prvky struktury

Pojďme přidat nějakou strukturu! To zahrnuje vytváření odstavců a prvků rozpětí, aby se vytvořil správně formátovaný a označený dokument.

### Vytvořit prvek kořenové struktury

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

Nyní vytvoříme naši první sadu odstavců a prvků span.

### Vytvořte první prvek odstavce

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

Zde inicializujeme nový prvek odstavce a připojíme jej ke kořenovému prvku struktury. Toto je výchozí bod vašeho obsahu!

### Přidejte do odstavce Span Elements

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

 The`span` prvky jsou jako miniodstavce v našem větším odstavci. Umožňují jemnější kontrolu nad formátováním textu.

### Zkombinujte to všechno

Nyní vytvoříme celý odstavec se všemi prvky dohromady:

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### Opakujte pro další odstavce

Tento postup zopakujete pro další odstavce:

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

 Tvořte dál`ParagraphElement` s a`SpanElement` s, jejich připojením k`rootElement` stejným způsobem, jak je uvedeno výše pro`p1`.

## Krok 5: Uložte dokument

Když jsou všechny prvky struktury na svém místě, je čas uložit dokument PDF.

### Zadejte cestu k výstupnímu souboru

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### Uložte dokument

```csharp
document.Save(outFile);
```

Tady se děje kouzlo! Váš dokument se uloží do zadané cesty k výstupnímu souboru.

## Krok 6: Ověřte soulad s PDF/UA

Poslední krok zahrnuje kontrolu, zda váš dokument vyhovuje standardům PDF/UA pro usnadnění.

Chcete-li zkontrolovat soulad, použijte následující kód:

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Tím se zobrazí, zda je váš dokument v souladu se standardy PDF/UA, což je nezbytné pro usnadnění přístupu.

## Závěr

A tady to máte! Právě jste se naučili, jak přidat prvky struktury do dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí těchto kroků můžete převést jakýkoli soubor PDF do přístupného formátu, který splňuje standardy, a zajistí tak všem rovný přístup k informacím. 

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Jak zjistím, zda je můj PDF přístupný?
Své PDF můžete ověřit podle standardů PDF/UA pomocí knihovny Aspose.PDF, abyste se ujistili, že splňuje pokyny pro usnadnění.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi, která vám umožní prozkoumat její funkce bez jakýchkoli nákladů. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Kde najdu dokumentaci k Aspose.PDF?
Můžete najít komplexní dokumentaci k Aspose.PDF[zde](https://reference.aspose.com/pdf/net/).

### Jak si koupím licenci pro Aspose.PDF?
 Licenci si můžete zakoupit přímo z webu Aspose[zde](https://purchase.aspose.com/buy).