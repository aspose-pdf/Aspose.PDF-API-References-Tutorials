---
title: Vytvořit odkaz na dokument
linktitle: Vytvořit odkaz na dokument
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF for .NET můžete snadno vytvářet odkazy na další dokumenty PDF.
type: docs
weight: 30
url: /cs/net/programming-with-links-and-actions/create-document-link/
---
Propojení s jiným dokumentem v souboru PDF umožňuje vytvářet odkazy, na které lze kliknout a které uživatele přesměrují na jiné dokumenty PDF. S Aspose.PDF pro .NET můžete snadno vytvořit takové odkazy podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, do kterého chcete přidat odkaz na jiný dokument. Nahradit`"YOUR DOCUMENT DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otevřete dokument PDF

Nyní otevřeme dokument PDF, do kterého chceme přidat odkaz na jiný dokument, pomocí následujícího kódu:

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Krok 4: Vytvořte odkaz na jiný dokument

 V tomto kroku vytvoříme odkaz na jiný dokument pomocí`LinkAnnotation` anotace. Zadáme souřadnice a oblast odkazu a také akci navigace na externí dokument. Zde je odpovídající kód:

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Krok 5: Uložte aktualizovaný soubor

 Nyní uložme aktualizovaný soubor PDF pomocí`Save` metoda`document` objekt. Zde je odpovídající kód:

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Ukázkový zdrojový kód pro Create Document Link pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Vytvořit odkaz
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Uložit aktualizovaný dokument
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Závěr

gratuluji! Nyní máte k dispozici podrobného průvodce propojením s jinými dokumenty pomocí Aspose.PDF pro .NET. Tento kód můžete použít k vytvoření klikacích odkazů v souborech PDF a přesměrování uživatelů na jiné dokumenty.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích interaktivních odkazů.

### Časté dotazy k vytvoření odkazu na dokument

#### Otázka: Co jsou odkazy na dokumenty v souborech PDF?

Odpověď: Odkazy na dokumenty v souborech PDF jsou klikací odkazy, které uživatele přesměrovávají na jiné dokumenty PDF. Tyto odkazy zlepšují navigaci tím, že poskytují efektivní způsob propojení souvisejícího obsahu a usnadňují bezproblémové čtení.

#### Otázka: Jak mohu využít vytváření odkazů na dokumenty?

Odpověď: Vytváření odkazů na dokumenty vám umožňuje vytvořit spojení mezi různými sekcemi nebo tématy v dokumentech PDF. Tato funkce umožňuje uživatelům snadný přístup k doplňkovým informacím nebo souvisejícím materiálům.

#### Otázka: Jak Aspose.PDF pro .NET podporuje vytváření odkazů na dokumenty?

Odpověď: Aspose.PDF for .NET zjednodušuje proces vytváření odkazů na dokumenty tím, že poskytuje komplexní sadu rozhraní API. Výukový program krok za krokem nastíněný v této příručce ukazuje, jak přidat odkazy na dokumenty do souborů PDF.

#### Otázka: Mohu přizpůsobit vzhled odkazů na dokumenty?

A: Rozhodně! Aspose.PDF for .NET nabízí možnosti přizpůsobení vzhledu odkazu dokumentu, včetně barev, stylu a efektů přechodu. Vzhled můžete přizpůsobit tak, aby odpovídal designu vašeho dokumentu.

#### Otázka: Je možné odkazovat na konkrétní sekce nebo stránky v rámci jiného dokumentu?

Odpověď: Ano, můžete vytvořit odkazy, které uživatele navigují na konkrétní stránky nebo sekce v jiném dokumentu PDF. Aspose.PDF for .NET poskytuje flexibilitu pro definování cílového umístění v rámci propojeného dokumentu.

#### Otázka: Jak mohu zajistit, aby odkazy na můj dokument byly funkční?

Odpověď: Podle poskytnutého kurzu a ukázkového kódu můžete s jistotou vytvářet funkční odkazy na dokumenty. Odkazy můžete otestovat otevřením vygenerovaného dokumentu PDF a kliknutím na odkazy.

#### Otázka: Mohu vytvořit více odkazů na dokument v rámci jednoho souboru PDF?

 A: Určitě! V rámci jednoho dokumentu PDF můžete vytvořit více odkazů na dokument pomocí`LinkAnnotation`anotace. To vám umožní poskytnout uživatelům přístup k různým souvisejícím dokumentům z různých sekcí.

#### Otázka: Existují nějaká omezení při odkazování na externí dokumenty?

Odpověď: Při propojování s externími dokumenty zajistěte, aby byly připojené dokumenty přístupné a umístěné v určených cestách. Je také důležité vzít v úvahu uživatelská oprávnění a kompatibilitu propojených dokumentů.

#### Otázka: Mohu odkazovat na dokumenty uložené na webu nebo v online úložištích?

Odpověď: I když se tento tutoriál zaměřuje na propojení s místními dokumenty, Aspose.PDF pro .NET také podporuje propojení na webové adresy URL nebo online úložiště. Poskytnutý kód můžete přizpůsobit pro vytváření odkazů na webové dokumenty.