---
title: Označit obrázek ve stávajícím PDF
linktitle: Označit obrázek ve stávajícím PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak označit obrázek v existujícím PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce přidáváním značek k obrázkům.
type: docs
weight: 210
url: /cs/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
V tomto podrobném tutoriálu vás provedeme dodaným zdrojovým kódem C# krok za krokem k označení obrázku v existujícím PDF pomocí Aspose.PDF for .NET. Postupujte podle pokynů níže, abyste pochopili, jak přidat tagy k obrázku v PDF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste své vývojové prostředí nakonfigurovali pro použití Aspose.PDF pro .NET. To zahrnuje instalaci knihovny Aspose.PDF a konfiguraci vašeho projektu tak, aby na něj odkazoval.

## Krok 2: Otevřete existující dokument PDF

tomto kroku otevřeme existující PDF dokument pomocí Aspose.PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vstupní a výstupní cesty k souboru
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otevřete dokument
Document document = new Document(inFile);
```

Stávající dokument PDF jsme otevřeli pomocí Aspose.PDF.

## Krok 3: Získejte označený obsah a prvek kořenové struktury

Nyní získáme tagovaný obsah dokumentu PDF a odpovídající prvek kořenové struktury.

```csharp
// Získejte tagovaný obsah a prvek kořenové struktury
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Získali jsme tagovaný obsah dokumentu PDF a odpovídající prvek kořenové struktury.

## Krok 4: Nastavení názvu pro tagovaný dokument PDF

Nyní nastavíme název pro tagovaný dokument PDF.

```csharp
// Definujte název pro tagovaný dokument PDF
taggedContent.SetTitle("Document with images");
```

Nastavili jsme název pro tagovaný dokument PDF.

## Krok 5: Přiřaďte obrázku alternativní texty a ohraničovací rámeček

Nyní každému prvku obrázku přiřadíme alternativní text a ohraničovací rámeček.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Přiřaďte obrázku alternativní text
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Vytvořte a přiřaďte ohraničovací rámeček (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Ke každému prvku obrázku v dokumentu PDF jsme přiřadili alternativní text a ohraničovací rámeček.

## Krok 6: Přesunutí prvku Span do odstavce

Nyní přesuneme prvek Span do odstavce.

```csharp
// Přesunout prvek Span do odstavce (najít nesprávný rozsah a odstavec v prvním TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Přesuňte prvek Span v odstavci
spanElement.ChangeParentElement(paragraph);
```

Element Span jsme přesunuli do určeného odstavce.

## Krok 7: Uložení upraveného dokumentu PDF

Nyní, když jsme provedli potřebné změny, uložíme upravený dokument PDF.

```csharp
// Uložte dokument PDF
document. Save(outFile);
```

Upravený PDF dokument jsme uložili do určeného adresáře.

### Ukázkový zdrojový kód pro Tag Image In Existing PDF pomocí Aspose.PDF for .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Otevřete dokument
Document document = new Document(inFile);

// Získá tagovaný obsah a prvek kořenové struktury
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Nastavit název pro označený dokument pdf
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Nastavte alternativní text pro obrázek
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Vytvořte a nastavte atribut Bbox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Přesunout prvek Span do odstavce (najít nesprávný rozsah a odstavec v prvním TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Přesunout prvek Span do odstavce
spanElement.ChangeParentElement(paragraph);

// Uložit dokument
document.Save(outFile);

//Kontrola shody s PDF/UA pro váš dokument
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Závěr

V tomto tutoriálu jsme se naučili, jak označit obrázek v existujícím PDF pomocí Aspose.PDF pro .NET. Nyní můžete použít Aspose.PDF k přidávání tagů a úpravám obrázků v dokumentech PDF.

### FAQ

#### Otázka: Co je hlavním cílem tohoto tutoriálu o označování obrázků v existujícím PDF pomocí Aspose.PDF pro .NET?

Odpověď: Primárním cílem tohoto tutoriálu je provést vás procesem označení obrázku v existujícím dokumentu PDF pomocí Aspose.PDF for .NET. Výukový program poskytuje podrobné pokyny a příklady zdrojového kódu C#, které vám pomohou pochopit, jak přiřadit alternativní text a ohraničovací rámečky k obrázkům, přesouvat prvky v dokumentu a přidávat k obrázkům tagy.

#### Otázka: Jaké jsou předpoklady pro následující tutoriál o označování obrázků v PDF pomocí Aspose.PDF pro .NET?

A: Než začnete, ujistěte se, že jste nastavili své vývojové prostředí pro použití Aspose.PDF pro .NET. To zahrnuje instalaci knihovny Aspose.PDF a konfiguraci vašeho projektu tak, aby na ni odkazoval.

#### Otázka: Jak mohu otevřít existující dokument PDF a získat přístup k jeho označenému obsahu pomocí Aspose.PDF for .NET?

Odpověď: Výukový program poskytuje příklady zdrojového kódu C#, které demonstrují, jak otevřít existující dokument PDF pomocí Aspose.PDF pro .NET a přistupovat k jeho označenému obsahu pro další manipulaci.

#### Otázka: Jaký je účel přiřazení alternativního textu a ohraničovacích rámečků k obrázkům v dokumentu PDF?

Odpověď: Přiřazení alternativního textu a ohraničovacích rámečků k obrázkům zlepšuje dostupnost tím, že poskytuje popisný text pro obrázky a definuje jejich rozvržení a umístění v dokumentu. Tyto informace jsou klíčové pro čtečky obrazovky a další pomocné technologie.

#### Otázka: Jak mohu nastavit název pro tagovaný dokument PDF pomocí Aspose.PDF pro .NET?

Odpověď: Výukový program obsahuje příklady zdrojového kódu C#, které ilustrují, jak nastavit název pro tagovaný dokument PDF pomocí Aspose.PDF pro .NET.

#### Otázka: Co zahrnuje proces přesouvání prvků v dokumentu PDF?

Odpověď: Přesouvání prvků v dokumentu PDF zahrnuje změnu nadřazeného prvku určitého prvku. V tomto kurzu se naučíte, jak přesunout prvek Span do zadaného prvku odstavce v tabulce.

#### Otázka: Jak uložím upravený dokument PDF po přidání tagů a úpravách obrázků?

 Odpověď: Jakmile přidáte tagy, přiřadíte alternativní text, nastavíte ohraničovací rámečky a provedete úpravy v dokumentu PDF, můžete použít poskytnuté příklady zdrojového kódu C# k uložení upraveného dokumentu PDF pomocí`Save()` metoda.

#### Otázka: Jaký je účel ukázkového zdrojového kódu poskytnutého v tutoriálu?

Odpověď: Ukázkový zdrojový kód slouží jako praktická reference pro implementaci označování obrázků a manipulaci s nimi pomocí Aspose.PDF pro .NET. Tento kód můžete použít jako výchozí bod a upravit jej tak, aby vyhovoval vašim specifickým požadavkům.

#### Otázka: Mohu tyto techniky použít na jiné typy prvků v dokumentu PDF, nejen na obrázky?

Odpověď: Ano, techniky uvedené v tomto tutoriálu lze upravit pro práci s různými typy prvků v dokumentu PDF. Podobné principy můžete použít pro označování a manipulaci s dalšími prvky, jako je text, tabulky a další.

#### Otázka: Jak mohu ověřit shodu upraveného dokumentu PDF s PDF/UA?

 Odpověď: Výukový program poskytuje příklady zdrojového kódu C#, které ukazují, jak ověřit shodu upraveného dokumentu PDF s PDF/UA pomocí`Validate()` a generování XML reportu.

#### Otázka: Jaké další funkce nabízí Aspose.PDF for .NET pro práci s dokumenty PDF?

Odpověď: Aspose.PDF for .NET nabízí širokou škálu funkcí pro práci s dokumenty PDF, včetně manipulace s textem, vkládání obrázků, vytváření tabulek, správy polí formuláře, digitálních podpisů, anotací a dalších. Pro další průzkum nahlédněte do oficiální dokumentace a zdrojů.