---
title: Vytvořte prvky struktury
linktitle: Vytvořte prvky struktury
second_title: Aspose.PDF pro .NET API Reference
description: V tomto tutoriálu se naučíte, jak používat Aspose.PDF pro .NET k vytváření strukturních prvků v tagovaném dokumentu PDF.
type: docs
weight: 60
url: /cs/net/programming-with-tagged-pdf/create-structure-elements/
---
Následující zdrojový kód C# používá Aspose.PDF pro .NET k vytvoření prvků struktury. Chcete-li pochopit, jak kód funguje, postupujte podle následujících kroků.

## Krok 1: Importujte potřebné knihovny

```csharp
using Aspose.Pdf;
```

## Krok 2: Definujte adresář vašich dokumentů

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Nezapomeňte zadat správnou cestu k adresáři dokumentů.

## Krok 3: Vytvořte dokument PDF

```csharp
Document document = new Document();
```

Vytvoříme nový objekt Document, který představuje dokument PDF.

## Krok 4: Získejte obsah pro práci s TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Načteme označený obsah dokumentu PDF. To nám umožní manipulovat s konstrukčními prvky.

## Krok 5: Nastavte název dokumentu a jazyk

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Nastavíme název a jazyk tagovaného PDF dokumentu. To zlepšuje přístupnost dokumentu.

## Krok 6: Vytvořte seskupovací prvky

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Vytváříme různé strukturální prvky pro seskupování obsahu v dokumentu PDF.

## Krok 7: Vytvořte prvky struktury odstavce

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Vytváříme strukturní prvky na úrovni bloků pro odstavce a nadpisy. Výše uvedený příklad ukazuje vytvoření záhlaví 1. úrovně.

## Krok 8: Vytvořte prvky struktury inline úrovně

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Vytváříme vložené prvky struktury úrovně pro části textu, které se objevují uvnitř odstavce nebo nadpisu.

## Krok 9: Vytvořte prvky struktury kresby

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Vytváříme strukturní prvky pro ilustrace a matematické vzorce obsažené v dokumentu.

## Krok 10: Uložte označený dokument PDF

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Tagovaný PDF dokument uložíme s vytvořenými prvky struktury.

### Ukázkový zdrojový kód pro Create Structure Elements pomocí Aspose.PDF pro .NET 

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
// Vytvořit prvky seskupení
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Vytvářejte prvky struktury na úrovni bloku textu
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
// Vytvářejte prvky struktury na úrovni textu
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Vytvořte prvky struktury obrázku
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Metody jsou ve vývoji
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Uložit označený dokument PDF
document.Save(dataDir + "StructureElements.pdf");

```

## Závěr

V tomto tutoriálu jsme se naučili používat Aspose.PDF pro .NET k vytvoření prvků struktury v tagovaném dokumentu PDF. Strukturální prvky pomáhají zlepšit dostupnost dokumentů a smysluplným způsobem organizovat obsah. Nyní můžete tyto znalosti využít k vytváření strukturovaných dokumentů PDF se snadnou navigací.

### FAQ

#### Otázka: Jaký je účel vytváření prvků struktury v dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Vytváření prvků struktury v dokumentu PDF pomocí Aspose.PDF for .NET zlepšuje dostupnost a organizaci obsahu dokumentu. Prvky struktury poskytují hierarchickou strukturu, která zlepšuje navigaci, sémantiku a kompatibilitu s asistenčními technologiemi.

#### Otázka: Jak poskytnutý kód C# vytváří prvky struktury v dokumentu PDF?

Odpověď: Příklad kódu ukazuje, jak vytvořit různé typy prvků struktury, včetně prvků seskupení (jako jsou části, sekce a div), prvků na úrovni bloku (jako jsou odstavce a nadpisy), prvků na úrovni řádků (rozpětí, citace, poznámka ) a prvky kresby (jako jsou obrázky a vzorce). Tyto prvky struktury pomáhají organizovat obsah.

####  Otázka: Proč je důležité nastavit název a jazyk dokumentu pomocí`SetTitle` and `SetLanguage` methods?

 A: Nastavení názvu a jazyka dokumentu pomocí`SetTitle` a`SetLanguage`metody zlepšují dostupnost a sémantiku dokumentů. Název poskytuje stručný popis účelu dokumentu, zatímco atribut language zlepšuje vykreslování a dostupnost specifické pro daný jazyk.

####  Otázka: Jak funguje seskupování prvků, jako např`PartElement` and `SectElement`, contribute to the structure of the PDF document?

Odpověď: Seskupování prvků vytváří v dokumentu PDF hierarchickou strukturu, která vám umožňuje logicky organizovat a seskupovat související obsah. To zlepšuje navigaci a poskytuje uživatelům jasnou strukturu.

#### Otázka: Co jsou prvky struktury na úrovni bloku a na úrovni řádku a jak se liší?

Odpověď: Prvky struktury na úrovni bloku představují větší bloky obsahu, jako jsou odstavce a nadpisy, zatímco prvky na úrovni řádku představují části textu v odstavci nebo nadpisu, jako jsou rozpětí, uvozovky a poznámky. Pomáhají definovat hierarchii a vztahy obsahu.

####  Otázka: Jak se podobají prvkům struktury uměleckého díla`FigureElement` and `FormulaElement`, contribute to the document?

Odpověď: Prvky struktury kresby umožňují přidávat do dokumentu ilustrace, obrázky a matematické vzorce. Poskytují strukturovaný způsob, jak zahrnout vizuální a matematický obsah.

#### Otázka: Mohu použít podobné techniky k vytvoření jiných typů prvků struktury, jako jsou seznamy, tabulky nebo anotace?

Odpověď: Ano, podobné techniky můžete použít k vytvoření jiných typů prvků struktury, jako jsou seznamy, tabulky, anotace, odkazy a další. Aspose.PDF poskytuje širokou škálu metod vytváření prvků struktury.

####  Otázka: Jak se uloží tagovaný dokument PDF pomocí`Save` method ensure the preservation of structure elements?

 A:`Save` metoda uloží dokument PDF spolu s vytvořenými prvky struktury, čímž zajistí zachování hierarchické a sémantické struktury dokumentu pro usnadnění přístupu a navigaci.

#### Otázka: Jaké výhody přinášejí prvky struktury dokumentům PDF z hlediska přístupnosti a kompatibility s asistenčními technologiemi?

Odpověď: Prvky struktury zvyšují dostupnost tím, že poskytují dokumentu smysluplnou strukturu a sémantiku. To umožňuje pomocným technologiím, jako jsou čtečky obrazovky, efektivněji interpretovat a zprostředkovat obsah dokumentu uživatelům s postižením.

#### Otázka: Jak mohu dále přizpůsobit a kombinovat různé typy prvků struktury v dokumentech PDF?

Odpověď: Prvky struktury můžete kombinovat a přizpůsobovat pomocí vhodných metod vytváření, které poskytuje Aspose.PDF. Experimentujte s různými prvky a jejich vlastnostmi, abyste vytvořili dobře strukturovaný a organizovaný dokument PDF.