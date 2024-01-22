---
title: Přidat prvek struktury do prvku
linktitle: Přidat prvek struktury do prvku
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce přidáním prvku struktury k prvku v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 20
url: /cs/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
V tomto tutoriálu vám poskytneme podrobný návod, jak přidat prvek struktury do prvku v dokumentu PDF pomocí Aspose.PDF pro .NET. Aspose.PDF je výkonná knihovna, která vám umožňuje programově vytvářet, manipulovat a převádět dokumenty PDF. Pomocí funkcí struktury označeného obsahu Aspose.PDF můžete vytvořit hierarchickou strukturu v dokumentu PDF.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio nainstalované s .NET frameworkem.
2. Knihovna Aspose.PDF pro .NET.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt v sadě Visual Studio a přidejte odkaz na knihovnu Aspose.PDF for .NET. Knihovnu si můžete stáhnout z oficiálních stránek Aspose a nainstalovat ji do svého počítače.

## Krok 2: Importujte potřebné jmenné prostory

Do souboru s kódem C# importujte jmenné prostory potřebné pro přístup ke třídám a metodám poskytovaným Aspose.PDF:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Krok 3: Vytvoření dokumentu PDF a definování strukturovaných prvků

Pomocí následujícího kódu vytvořte dokument PDF a definujte strukturované prvky:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Tento kód vytvoří prázdný dokument PDF a přidá strukturované prvky, jako jsou odstavce a rozpětí. Každý prvek struktury je vytvořen pomocí metod poskytovaných Aspose.PDF.

## Krok 4: Uložení dokumentu PDF

K uložení dokumentu PDF použijte následující kód:

```csharp
document. Save(outFile);
```

Tento kód uloží dokument PDF se strukturovanými prvky do určeného souboru.

### Ukázkový zdrojový kód pro Add Structure Element Into Element pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Vytvoření dokumentu a získání tagovaného obsahu PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Nastavení názvu a přirozeného jazyka pro dokument
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Získání prvku kořenové struktury (prvku struktury dokumentu)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Uložit označený dokument PDF
document.Save(outFile);
// Kontrola shody s PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

V tomto tutoriálu jste se naučili, jak přidat prvek struktury k prvku v dokumentu PDF pomocí Aspose.PDF for .NET. Pomocí funkcí struktury označeného obsahu souboru Aspose.PDF můžete ve svém dokumentu PDF vytvořit hierarchickou strukturu, která usnadňuje správu a procházení obsahu.

### FAQ

#### Otázka: Jaký je účel přidání prvku struktury k prvku v dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Přidání prvku struktury k prvku v dokumentu PDF pomocí Aspose.PDF for .NET vám umožní vytvořit hierarchickou strukturu v obsahu dokumentu. Tato hierarchická struktura zlepšuje organizaci a navigaci obsahu a usnadňuje správu a přístup ke konkrétním prvkům.

#### Otázka: Jak pomáhá knihovna Aspose.PDF při přidávání prvků struktury do dokumentu PDF?

A: Aspose.PDF for .NET je výkonná knihovna, která poskytuje možnosti pro vytváření, manipulaci a převod dokumentů PDF programově. V tomto kurzu jsou funkce struktury označeného obsahu knihovny využity k vytvoření a připojení prvků struktury k obsahu dokumentu PDF.

#### Otázka: Jaké jsou předpoklady pro přidání prvků struktury do dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Než začnete, ujistěte se, že máte nainstalované Visual Studio s rozhraním .NET a že máte ve svém projektu odkaz na knihovnu Aspose.PDF pro .NET.

#### Otázka: Jak poskytnutý kód C# vytváří a připojuje prvky struktury k obsahu dokumentu PDF?

Odpověď: Kód ukazuje, jak vytvořit dokument PDF, definovat prvek kořenové struktury a připojit k němu různé strukturované prvky, jako jsou odstavce a úseky. Každý strukturovaný prvek je vytvořen pomocí metod poskytovaných Aspose.PDF, což vám umožňuje vytvořit hierarchickou strukturu.

#### Otázka: Mohu přizpůsobit typy prvků struktury, které připojím k dokumentu PDF?

Odpověď: Ano, typy prvků struktury můžete přizpůsobit prozkoumáním různých metod poskytovaných knihovnou Aspose.PDF. Kód uvádí odstavce a rozsahy jako příklady, ale podle potřeby můžete vytvářet a přidávat další typy strukturovaných prvků.

#### Otázka: Jak mohu definovat hierarchický vztah mezi přidanými prvky struktury?

 Odpověď: Hierarchický vztah mezi prvky struktury je definován pořadím, ve kterém je připojujete k jejich nadřazeným prvkům. V kódu jsou vztahy rodič-dítě vytvořeny pomocí`AppendChild` metoda.

#### Otázka: Jaké jsou výhody vytvoření hierarchické struktury v dokumentu PDF?

Odpověď: Vytvoření hierarchické struktury v dokumentu PDF zlepšuje jeho dostupnost, navigaci a organizaci. Umožňuje asistenčním technologiím lépe interpretovat a zprostředkovat obsah dokumentu, díky čemuž je uživatelsky přívětivější pro osoby se zdravotním postižením.

#### Otázka: Jak mohu po přidání prvků struktury ověřit shodu s PDF/UA?

 Odpověď: Kód poskytnutý v tutoriálu ukazuje, jak ověřit shodu s PDF/UA pomocí`Validate` metoda. Ověřením dokumentu podle standardu PDF/UA můžete zajistit, že přidané prvky struktury odpovídají pokynům pro usnadnění.

#### Otázka: Mohu tento přístup použít k přidání prvků struktury do existujícího dokumentu PDF?

Odpověď: Ano, poskytnutý přístup můžete upravit a přidat prvky struktury do existujícího dokumentu PDF. Namísto vytvoření nového dokumentu byste načetli existující dokument pomocí Aspose.PDF a poté byste podle podobných kroků přidali prvky struktury.