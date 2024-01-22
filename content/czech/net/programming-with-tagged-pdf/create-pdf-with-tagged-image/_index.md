---
title: Vytvořte PDF s tagovaným obrázkem
linktitle: Vytvořte PDF s tagovaným obrázkem
second_title: Aspose.PDF pro .NET API Reference
description: Průvodce krok za krokem k vytvoření PDF s tagovaným obrázkem pomocí Aspose.PDF pro .NET.
type: docs
weight: 40
url: /cs/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
V tomto tutoriálu vám poskytneme podrobný návod, jak vytvořit dokument PDF s tagovaným obrázkem pomocí Aspose.PDF for .NET. Aspose.PDF je výkonná knihovna, která vám umožňuje programově vytvářet, manipulovat a převádět dokumenty PDF. Pomocí funkcí struktury tagovaného obsahu Aspose.PDF můžete do dokumentu PDF přidat tagované obrázky.

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

## Krok 3: Vytvoření dokumentu PDF s tagovaným obrázkem

K vytvoření dokumentu PDF s tagovaným obrázkem použijte následující kód:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Tento kód vytvoří prázdný dokument PDF a přidá tagovaný obrázek pomocí metod poskytovaných Aspose.PDF. Obrázek je specifikován pomocí alternativního textu, názvu a značky.

## Krok 4: Uložení dokumentu PDF

K uložení dokumentu PDF použijte následující kód:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Tento kód uloží dokument PDF s tagovaným obrázkem do určeného souboru.

### Ukázkový zdrojový kód pro Create PDFwith Tagged Image pomocí Aspose.PDF for .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Přidat obrázek s rozlišením 300 DPI (ve výchozím nastavení)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Uložit dokument PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit dokument PDF s tagovaným obrázkem pomocí Aspose.PDF for .NET. Tagované obrázky přidávají do vašeho dokumentu PDF další, strukturované informace.

### FAQ

#### Otázka: Jaký je účel vytvoření dokumentu PDF s tagovaným obrázkem pomocí Aspose.PDF pro .NET?

Odpověď: Vytvoření dokumentu PDF s tagovaným obrázkem pomocí Aspose.PDF for .NET vám umožňuje přidat tagované obrázky k obsahu dokumentu. Označené obrázky poskytují strukturované informace, jako je alternativní text a názvy, což zlepšuje dostupnost a organizaci.

#### Otázka: Jak pomáhá knihovna Aspose.PDF při vytváření dokumentu PDF s tagovaným obrázkem?

Odpověď: Aspose.PDF for .NET je robustní knihovna, která poskytuje funkce pro vytváření, manipulaci a převod dokumentů PDF programově. V tomto kurzu se funkce struktury tagovaného obsahu knihovny používají k přidání tagovaného obrazu do dokumentu PDF.

#### Otázka: Jaké jsou předpoklady pro vytvoření dokumentu PDF s tagovaným obrázkem pomocí Aspose.PDF for .NET?

Odpověď: Než začnete, ujistěte se, že máte nainstalované Visual Studio s rozhraním .NET a že máte ve svém projektu odkaz na knihovnu Aspose.PDF pro .NET.

#### Otázka: Jak poskytnutý kód C# vytvoří dokument PDF s tagovaným obrázkem?

Odpověď: Kód ukazuje, jak vytvořit dokument PDF, definovat tagovaný obrazový prvek a přidat jej do obsahu dokumentu. Tagovaný obrázek obsahuje alternativní text, nadpis a tag pomocí metod poskytovaných Aspose.PDF.

#### Otázka: Mohu pro označený obrázek použít různé formáty obrázků?

Odpověď: Ano, pro označený obrázek můžete použít různé formáty obrázků, jako je JPEG, PNG, GIF atd. Příklad kódu uvedený v tutoriálu používá obrázek JPEG, ale můžete ho nahradit cestou k souboru obrázku v váš preferovaný formát.

#### Otázka: Jak se v označených obrázcích používá alternativní text (alt text)?

 Odpověď: Alternativní text poskytuje textový popis obrázku, který je nahlas čten čtečkami obrazovky pro zrakově postižené uživatele. V poskytnutém kódu je alternativní text nastaven pomocí`AlternativeText` vlastnictvím`IllustrationElement` představující označený obrázek.

####  Otázka: Jak to`SetTitle` method contribute to the PDF document's tagged image?

 A:`SetTitle` metoda nastavuje název tagovaného obsahu dokumentu PDF a poskytuje další kontext pro tagovaný obraz. Tento název může pomoci identifikovat účel nebo předmět označeného obsahu.

#### Otázka: Mohu upravit značku a název označeného obrázku?

 Odpověď: Ano, značku a název označeného obrázku můžete upravit pomocí`SetTag` a`Title` metody`IllustrationElement`. Příklad kódu ukazuje, jak nastavit značku na „Obr“ a název na „Obrázek 1“.

#### Otázka: Jak mohu zajistit, aby byl označený obrázek přístupný a v souladu se standardy přístupnosti?

Odpověď: Používáním funkcí struktury tagovaného obsahu Aspose.PDF a poskytováním alternativního textu a dalších relevantních informací přispíváte k přístupnosti tagovaného obrázku. Zajištění souladu se standardy přístupnosti zahrnuje dodržování osvědčených postupů pro alternativní text a strukturu dokumentů.

#### Otázka: Je možné přidat více tagovaných obrázků do stejného dokumentu PDF pomocí podobných technik?

 Odpověď: Ano, pomocí podobných technik můžete do stejného dokumentu PDF přidat více tagovaných obrázků. Vytvořili byste další`IllustrationElement` instance pro každý tagovaný obrázek a upravte jejich vlastnosti podle potřeby.