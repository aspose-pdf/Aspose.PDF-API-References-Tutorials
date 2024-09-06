---
title: Vytvořte místní hypertextový odkaz v souboru PDF
linktitle: Vytvořte místní hypertextový odkaz v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno vytvářejte místní hypertextové odkazy v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 40
url: /cs/net/programming-with-links-and-actions/create-local-hyperlink/
---
Vytváření lokálních hypervazeb v souboru PDF vám umožňuje vytvářet odkazy, na které lze kliknout a které uživatele zavedou na jiné stránky ve stejném dokumentu PDF. S Aspose.PDF pro .NET můžete snadno vytvořit takové odkazy podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku je potřeba zadat cestu ke složce, kam chcete výsledný soubor PDF uložit. Nahradit`"YOUR DOCUMENT DIRECTORY"` v následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Vytvořte instanci dokumentu

 Vytvoříme instanci`Document` třídy reprezentovat náš dokument PDF. Zde je odpovídající kód:

```csharp
Document doc = new Document();
```

## Krok 4: Přidejte stránku a text pomocí hypertextových odkazů

tomto kroku přidáme stránku do našeho dokumentu PDF a přidáme nějaký text obsahující místní hypertextové odkazy. Pro každý odkaz definujeme cílové stránky. Zde je odpovídající kód:

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Krok 5: Uložte aktualizovaný dokument

Nyní uložme aktualizovaný soubor PDF pomocí`Save` metoda`doc` objekt. Zde je odpovídající kód:

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Ukázkový zdrojový kód pro Create Local Hyperlink using Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořit instanci dokumentu
Document doc = new Document();
// Přidat stránku do kolekce stránek souboru PDF
Page page = doc.Pages.Add();
// Vytvořte instanci textového fragmentu
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Vytvořte místní instanci hypertextového odkazu
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Nastavit cílovou stránku pro instanci odkazu
link.TargetPageNumber = 7;
// Nastavit hypertextový odkaz TextFragment
text.Hyperlink = link;
// Přidejte text do kolekce odstavců stránky
page.Paragraphs.Add(text);
// Vytvořte novou instanci TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment by měl být přidán na novou stránku
text.IsInNewPage = true;
// Vytvořte další místní instanci hypertextového odkazu
link = new LocalHyperlink();
// Nastavte cílovou stránku pro druhý hypertextový odkaz
link.TargetPageNumber = 1;
// Nastavit odkaz pro druhý TextFragment
text.Hyperlink = link;
// Přidejte text do kolekce odstavců objektu stránky
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Uložit aktualizovaný dokument
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce vytvořením místních hypertextových odkazů v PDF pomocí Aspose.PDF pro .NET. Tento kód můžete použít k vytvoření klikatelných odkazů, které uživatele přesměrují na jiné stránky ve stejném dokumentu.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích hypertextových odkazů.

### Časté dotazy pro vytvoření místního hypertextového odkazu v souboru PDF

#### Otázka: Co jsou místní hypertextové odkazy v souboru PDF?

Odpověď: Místní hypertextové odkazy v souboru PDF jsou klikací odkazy, které uživatele navigují na různé stránky v rámci stejného dokumentu. Tyto odkazy zlepšují navigaci a umožňují čtenářům rychlý přístup k relevantním sekcím.

#### Otázka: Jak mohou místní hypertextové odkazy prospět mému dokumentu PDF?

Odpověď: Místní hypertextové odkazy poskytují účinný způsob, jak propojit související obsah v rámci stejného dokumentu PDF. Zlepšují uživatelskou zkušenost tím, že umožňují čtenářům rychle přejít na konkrétní sekce, aniž by museli procházet celým dokumentem.

#### Otázka: Jak Aspose.PDF pro .NET podporuje vytváření místních hypertextových odkazů?
Odpověď: Aspose.PDF pro .NET nabízí komplexní podporu pro vytváření místních hypertextových odkazů. Výukový program krok za krokem uvedený v této příručce ukazuje, jak přidat místní hypertextové odkazy do dokumentu PDF pomocí jazyka C#.

#### Otázka: Mohu přizpůsobit vzhled místních hypertextových odkazů?

Odpověď: Ano, můžete přizpůsobit vzhled místních hypertextových odkazů, včetně barvy a stylu textu, abyste zajistili, že budou odpovídat designu vašeho dokumentu a budou poskytovat konzistentní vizuální zážitek.

#### Otázka: Je možné vytvořit více lokálních hypertextových odkazů v rámci jedné stránky PDF?

A: Rozhodně! V rámci jedné stránky PDF můžete vytvořit více lokálních hypertextových odkazů, což čtenářům umožní podle potřeby přeskakovat na různé sekce nebo stránky. Každý místní hypertextový odkaz lze přizpůsobit příslušnému cíli.

#### Otázka: Mohu odkazovat na konkrétní části stránky pomocí místních hypertextových odkazů?

Odpověď: Zatímco místní hypertextové odkazy obvykle navigují na celé stránky, můžete v dokumentu PDF vytvořit kotvy nebo záložky, abyste dosáhli cíleného propojení. Aspose.PDF for .NET podporuje různé možnosti hypertextových odkazů.

#### Otázka: Jak mohu ověřit, že moje místní hypertextové odkazy fungují správně?

Odpověď: Podle poskytnutého kurzu a ukázkového kódu můžete s jistotou vytvářet funkční místní hypertextové odkazy. Odkazy můžete otestovat otevřením vygenerovaného dokumentu PDF a kliknutím na text s hypertextovým odkazem.

#### Otázka: Existují nějaká omezení při používání místních hypertextových odkazů?

Odpověď: Místní hypertextové odkazy jsou účinným způsobem, jak zlepšit navigaci v dokumentu, ale je důležité zajistit, aby struktura dokumentu zůstala jasná a intuitivní. Správně označené hypertextové odkazy a kotvy přispívají k pozitivní uživatelské zkušenosti.

#### Otázka: Mohu vytvořit místní hypertextové odkazy v tabulkách nebo obrázcích?

Odpověď: Ano, můžete vytvořit místní hypertextové odkazy v rámci různých prvků vašeho dokumentu PDF, včetně tabulek, obrázků a textu. Aspose.PDF for .NET nabízí flexibilitu při přidávání hypertextových odkazů na různé typy obsahu.