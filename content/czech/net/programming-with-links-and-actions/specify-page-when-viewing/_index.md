---
title: Při prohlížení specifikujte stránku
linktitle: Při prohlížení specifikujte stránku
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak určit stránku při prohlížení PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 110
url: /cs/net/programming-with-links-and-actions/specify-page-when-viewing/
---
V tomto podrobném průvodci se dozvíte, jak určit stránku při prohlížení souboru PDF pomocí Aspose.PDF for .NET.

## Krok 1: Nastavení prostředí

Ujistěte se, že jste nastavili své vývojové prostředí s projektem C# a příslušnými odkazy Aspose.PDF.

## Krok 2: Načtení souboru PDF

Nastavte cestu k adresáři vašich dokumentů a nahrajte soubor PDF pomocí následujícího kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Načtěte soubor PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Krok 3: Určení cílové stránky

Získejte instanci cílové stránky pomocí následujícího kódu:

```csharp
Page page2 = doc.Pages[2];
```

 Index můžete upravit`[2]` pro výběr požadované stránky.

## Krok 4: Konfigurace nastavení zoomu

Vytvořte proměnnou pro nastavení faktoru přiblížení cílové stránky:

```csharp
double zoom = 1;
```

Hodnotu zoomu můžete upravit podle svých potřeb.

## Krok 5: Vytvořte akci navigace

Vytvořte instanci akce navigace pomocí zadané cílové stránky:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Krok 6: Nastavení cíle

Nastavte cíl pro přechod na cílovou stránku pomocí souřadnic a přiblížení:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Krok 7: Konfigurace akce otevření dokumentu

Nastavte akci otevření dokumentu s vytvořenou akcí navigace:

```csharp
doc. OpenAction = action;
```

## Krok 8: Uložte aktualizovaný dokument

 Uložte aktualizovaný dokument pomocí`Save` metoda:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Ukázkový zdrojový kód pro Specify Page When Viewing using Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načtěte soubor PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Získejte instanci druhé stránky dokumentu
Page page2 = doc.Pages[2];
// Vytvořte proměnnou pro nastavení faktoru přiblížení cílové stránky
double zoom = 1;
// Vytvořte instanci GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Přejděte na stránku 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Nastavte akci otevření dokumentu
doc.OpenAction = action;
// Uložit aktualizovaný dokument
doc.Save(dataDir + "goto2page_out.pdf");
```

## Závěr

gratuluji! Nyní víte, jak určit stránku při prohlížení PDF pomocí Aspose.PDF for .NET. Použijte tyto znalosti k přizpůsobení uživatelského prostředí pro prohlížení vašich dokumentů PDF.

Nyní, když jste dokončili tuto příručku, můžete tyto koncepty aplikovat na své vlastní projekty a dále prozkoumat funkce nabízené Aspose.PDF pro .NET.

### FAQ 

#### Otázka: Jaký je účel určení cílové stránky při prohlížení souboru PDF?

Odpověď: Určení cílové stránky vám umožňuje řídit, která stránka dokumentu PDF se zobrazí při otevření souboru. To může zlepšit uživatelský dojem tím, že je nasměruje na konkrétní stránku, která ho zajímá.

#### Otázka: Jak může být určení cílové stránky užitečné v dokumentech PDF?

Odpověď: Určení cílové stránky je výhodné, když chcete uživatele navést na konkrétní sekci nebo obsah v dokumentu PDF, aniž byste museli ručně procházet stránkami.

#### Otázka: Jak Aspose.PDF for .NET usnadňuje určení cílové stránky pro prohlížení?

Odpověď: Aspose.PDF for .NET poskytuje rozhraní API, která vám umožňují nastavit počáteční zobrazení dokumentu PDF, včetně cílové stránky, úrovně přiblížení a dalších vlastností zobrazení.

#### Otázka: Mohu určit libovolnou stránku jako cílovou stránku?

Odpověď: Ano, jako cílovou stránku pro zobrazení můžete zadat jakoukoli stránku v dokumentu PDF. Jednoduše použijte příslušný index pro výběr požadované stránky.

#### Otázka: Jaký je význam faktoru přiblížení při zadávání cílové stránky?

Odpověď: Faktor přiblížení určuje úroveň zvětšení aplikovaného na cílovou stránku při otevření dokumentu PDF. Řídí, kolik obsahu se zobrazí ve výřezu.

#### Otázka: Mohu nastavit různé faktory přiblížení pro různé cílové stránky?

Odpověď: Ano, můžete nastavit různé faktory přiblížení pro různé cílové stránky vytvořením samostatných stránek`GoToAction` instance a podle toho konfigurovat jejich cíle.

#### Otázka: Existují nějaká omezení pro určení cílové stránky?

Odpověď: Určení cílové stránky je omezeno na ovládání počátečního zobrazení při otevření PDF. Po zobrazení PDF to neovlivňuje uživatelské interakce ani navigaci.

#### Otázka: Mohu tuto funkci použít k vytváření prezentací v dokumentu PDF?

Odpověď: Ano, tuto funkci můžete použít k vytvoření zážitků podobných prezentacím v dokumentu PDF, které uživatele provedou různými sekcemi nebo tématy.

#### Otázka: Mohu přizpůsobit další aspekty úvodního zobrazení, jako je rozvržení stránky?

Odpověď: Ano, Aspose.PDF for .NET poskytuje vlastnosti pro přizpůsobení dalších aspektů počátečního zobrazení, včetně rozvržení stránky, režimu stránky a dalších.

#### Otázka: Jak mohu otestovat, zda zadaná cílová stránka a faktor přiblížení fungují podle očekávání?

Odpověď: Po použití poskytnutého kódu pro určení cílové stránky a faktoru přiblížení otevřete upravený soubor PDF a ověřte, zda se otevře se správnou úrovní stránky a přiblížení.