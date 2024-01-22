---
title: Přidat záložku do souboru PDF
linktitle: Přidat záložku do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno přidejte záložku do souboru PDF pro lepší navigaci s Aspose.PDF pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-bookmarks/add-bookmark/
---
Přidání záložek do souboru PDF umožňuje snadnou a rychlou navigaci. S Aspose.PDF pro .NET můžete snadno přidat záložku do souboru PDF podle následujícího zdrojového kódu:

## Krok 1: Importujte požadované knihovny

Než začnete, musíte importovat potřebné knihovny pro váš projekt C#. Zde je nezbytná dovozní směrnice:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Krok 2: Nastavte cestu ke složce dokumentů

 V tomto kroku musíte zadat cestu ke složce obsahující soubor PDF, do kterého chcete přidat záložku. Nahradit`"YOUR DOCUMENT DIRECTORY"` následujícím kódu se skutečnou cestou ke složce dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 3: Otevřete dokument PDF

Nyní otevřeme dokument PDF, do kterého chceme přidat záložku, pomocí následujícího kódu:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Krok 4: Vytvořte objekt záložky

 V tomto kroku vytvoříme objekt záložky pomocí`OutlineItemCollection` třídu a nastavte její vlastnosti, jako je název, kurzíva, atribut tučného písma a akce, která se má provést po kliknutí. Zde je odpovídající kód:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Krok 5: Přidejte záložku do dokumentu

 Nakonec přidáme vytvořenou záložku do sbírky záložek dokumentu pomocí`Add` metoda`Outlines` vlastnictví. Zde je odpovídající kód:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Ukázkový zdrojový kód pro Přidat záložku pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Vytvořte objekt záložky
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Nastavte číslo cílové stránky
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Přidejte záložku do kolekce osnovy dokumentu.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Uložit výstup
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Závěr

gratuluji! Nyní máte krok za krokem průvodce přidáním záložky pomocí Aspose.PDF pro .NET. Tento kód můžete použít ke zlepšení navigace v dokumentech PDF přidáním vlastních záložek.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF, kde najdete další informace o pokročilých funkcích manipulace se záložkami.


### Časté dotazy pro přidání záložky do souboru PDF

#### Otázka: Co jsou záložky v souboru PDF?

Odpověď: Záložky, také známé jako obrysy, jsou interaktivní prvky, které poskytují navigaci a strukturu v dokumentu PDF. Umožňují uživatelům rychle přejít na konkrétní sekce nebo stránky.

#### Otázka: Proč bych měl do souboru PDF přidávat záložky?

Odpověď: Přidání záložek do souboru PDF zlepšuje uživatelskou zkušenost a usnadňuje čtenářům procházení obsahu dokumentu. Záložky mohou sloužit jako obsah nebo poskytovat rychlý přístup k důležitým sekcím.

#### Otázka: Jak naimportuji požadované knihovny pro svůj projekt C#?

A: Chcete-li importovat potřebné knihovny pro váš projekt C#, zahrňte následující importní direktivy:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Tyto direktivy vám umožňují přístup ke třídám a metodám potřebným pro práci s dokumenty PDF a záložkami.

#### Otázka: Jak určím cestu ke složce dokumentů?

 A: Vyměňte`"YOUR DOCUMENT DIRECTORY"` v dodaném zdrojovém kódu se skutečnou cestou ke složce obsahující soubor PDF, do kterého chcete přidat záložku.

#### Otázka: Jak mohu otevřít dokument PDF pro přidání záložek?

Odpověď: Chcete-li otevřít dokument PDF pro přidání záložek, použijte následující kód:

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 Nahradit`"AddBookmark.pdf"` se skutečným názvem souboru.

#### Otázka: Jak vytvořím objekt záložky?

 A: Chcete-li vytvořit objekt záložky, použijte`OutlineItemCollection` třída. Přizpůsobte jeho vlastnosti, jako je nadpis, kurzíva, styl tučného písma a akce, která se má provést po kliknutí.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  Otázka: Jaký je účel`Action` property in a bookmark?

 A:`Action` vlastnost určuje akci, která se provede po kliknutí na záložku. V tomto příkladu používáme`GoToAction`třídy pro přechod na konkrétní stránku (v tomto případě stránka 2).

#### Otázka: Jak přidám záložku do dokumentu?

 A: Použijte`Add` metoda`Outlines` vlastnost přidat vytvořenou záložku do kolekce záložek dokumentu.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### Otázka: Mohu pomocí této metody přidat více záložek?

Odpověď: Ano, opakováním kroků 4 až 8 můžete do dokumentu přidat více záložek. Přizpůsobte vlastnosti a akce každé záložky podle potřeby.

#### Otázka: Jak uložím aktualizovaný soubor PDF?

 A: Uložte aktualizovaný soubor PDF pomocí`Save` metoda`pdfDocument` objekt:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### Otázka: Jak mohu potvrdit, že záložky byly přidány?

Odpověď: Otevřete vygenerovaný soubor PDF a ověřte, zda byly do dokumentu přidány zadané záložky.

#### Otázka: Existuje nějaký limit na počet záložek, které mohu přidat?

Odpověď: Obecně neexistuje striktní omezení počtu záložek, které můžete přidat, ale pro optimální výkon zvažte velikost a složitost dokumentu.

#### Otázka: Mohu přizpůsobit vzhled záložek?

Odpověď: Ano, pomocí funkcí Aspose.PDF můžete dále upravit vzhled, barvu, styl a další atributy záložky.