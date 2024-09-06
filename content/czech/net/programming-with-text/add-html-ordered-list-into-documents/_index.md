---
title: Přidejte HTML uspořádaný seznam do dokumentů
linktitle: Přidejte HTMLOrdered List do dokumentů
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat uspořádaný seznam HTML do dokumentu pomocí Aspose.PDF pro .NET.
type: docs
weight: 30
url: /cs/net/programming-with-text/add-html-ordered-list-into-documents/
---
V tomto tutoriálu se naučíte, jak používat knihovnu Aspose.PDF for .NET k přidání seznamu seřazeného v HTML do dokumentu. Poskytnutý kód ukazuje nezbytné kroky k provedení tohoto úkolu.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete přidat uspořádaný seznam HTML, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte adresář dokumentu a cestu k výstupnímu souboru
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

 Dále vyhledejte řádek, který říká`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` a nahradit`"AddHTMLOrderedListIntoDocuments_out.pdf"` s požadovaným názvem pro váš výstupní soubor PDF.

## Krok 4: Vytvořte nový objekt dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

## Krok 5: Vytvořte objekt HtmlFragment s obsahem HTML
 Instantovat an`HtmlFragment` objekt s obsahem HTML, který chcete přidat do dokumentu. V poskytnutém kódu je obsah HTML přiřazen k proměnné`t`. Obsah HTML můžete upravit podle potřeby.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## Krok 6: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages`sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 7: Přidejte na stránku HtmlFragment
 Přidejte`HtmlFragment` objekt na stránku pomocí`Add` metoda`Paragraphs` sbírka.

```csharp
page.Paragraphs.Add(t);
```

## Krok 8: Uložte dokument PDF
 Uložte výsledný soubor PDF pomocí`Save` metoda`Document` objekt. Zadejte cestu k výstupnímu souboru, kterou jste nastavili v kroku 3.

```csharp
doc.Save(outFile);
```

### Ukázkový zdrojový kód pro Add HTMLOrdered List Into Documents pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Cesta k výstupnímu dokumentu.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Objekt okamžitého dokumentu
Document doc = new Document();
// Vytvořte instanci objektu HtmlFragment s odpovídajícím fragmentem HTML
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Přidat stránku do kolekce stránek
Page page = doc.Pages.Add();
// Přidejte HtmlFragment na stránku
page.Paragraphs.Add(t);
// Uložte výsledný soubor PDF
doc.Save(outFile);
```

## Závěr
Úspěšně jste přidali uspořádaný seznam HTML do dokumentu pomocí Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

Nezapomeňte upravit obsah HTML a upravit kód podle vašich konkrétních požadavků.

### FAQ

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem přidávání uspořádaného seznamu HTML do dokumentu pomocí knihovny Aspose.PDF for .NET. Poskytuje podrobné pokyny a úryvky kódu, které vám pomohou dosáhnout tohoto úkolu.

#### Otázka: Které jmenné prostory musím pro tento výukový program importovat?

Odpověď: Musíte importovat následující jmenné prostory v horní části souboru kódu:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Otázka: Jak určím adresář dokumentu a cestu k výstupnímu souboru?

 Odpověď: V kódu vyhledejte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů. Také najděte čáru`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` a nahradit`"AddHTMLOrderedListIntoDocuments_out.pdf"` s požadovaným názvem výstupního souboru PDF.

#### Otázka: Mohu přizpůsobit obsah HTML přidávaný do dokumentu?

 A: Rozhodně! V kroku 5 vytvoříte soubor`HtmlFragment` objekt pojmenovaný`t` která obsahuje obsah HTML. Obsah HTML v backticks můžete upravit tak, aby vyhovoval vašim požadavkům.

#### Otázka: Jak přidám uspořádaný seznam HTML na stránku v dokumentu?

 Odpověď: V kroku 7 přidáte`HtmlFragment` objekt (`t` ) na stránku pomocí`Add` metoda`Paragraphs`sbírka. To hladce integruje uspořádaný seznam HTML do dokumentu.

#### Otázka: Jak uložím výsledný dokument PDF?

 Odpověď: Po přidání obsahu HTML a jeho uspořádání na stránku můžete uložit dokument PDF pomocí`Save` metoda`Document` objekt. Ujistěte se, že jste zadali správnou cestu k výstupnímu souboru, kterou jste nastavili dříve.

#### Otázka: Můžete poskytnout shrnutí ukázkového zdrojového kódu pro referenci?

A: Určitě! Zde je souhrnná verze ukázkového zdrojového kódu poskytnutého v tomto tutoriálu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Sledováním tohoto kurzu jste se úspěšně naučili, jak využít knihovnu Aspose.PDF for .NET k začlenění uspořádaného seznamu HTML do dokumentu. Tyto nově nabyté znalosti lze použít k vylepšení procesů tvorby a manipulace s dokumenty.