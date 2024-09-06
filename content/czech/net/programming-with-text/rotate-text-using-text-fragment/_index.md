---
title: Otočit text pomocí fragmentu textu v souboru PDF
linktitle: Otočit text pomocí fragmentu textu v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se otáčet text pomocí textových fragmentů v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 390
url: /cs/net/programming-with-text/rotate-text-using-text-fragment/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k otáčení textu pomocí textových fragmentů v souboru PDF. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

## Předpoklady

Než budete pokračovat ve výukovém programu, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#.
- Nainstalovaná knihovna Aspose.PDF pro .NET. Můžete jej získat z webu Aspose nebo jej pomocí NuGet nainstalovat do svého projektu.

## Krok 1: Nastavte projekt

Začněte vytvořením nového projektu C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE) a přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte potřebné jmenné prostory

Chcete-li importovat požadované jmenné prostory, přidejte následující pomocí direktiv na začátek souboru C#:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Krok 3: Vytvořte dokument PDF

 Inicializujte`Document` objekt pro vytvoření nového dokumentu PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 4: Přidejte stránku

 Získejte konkrétní stránku z dokumentu pomocí`Pages.Add()` metoda:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 5: Vytvořte fragmenty textu

 Vytvořte více`TextFragment` objektů, nastavte jejich text a vlastnosti a určete jejich umístění na stránce:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Upravte text, pozice a další vlastnosti podle potřeby.

## Krok 6: Vytvořte TextBuilder a připojte textové fragmenty

 Vytvořte a`TextBuilder` objekt pomocí`pdfPage` a připojte textové fragmenty na stránku PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## Krok 7: Uložte dokument PDF

 Uložte upravený dokument PDF do souboru pomocí`Save` metoda:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Nezapomeňte vyměnit`"TextFragmentTests_Rotated1_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázka zdrojového kódu pro otáčení textu pomocí fragmentu textu pomocí Aspose.PDF pro .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializovat objekt dokumentu
Document pdfDocument = new Document();
// Získejte konkrétní stránku
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Vytvořte fragment textu
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Nastavte vlastnosti textu
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Vytvořte otočený fragment textu
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Nastavte vlastnosti textu
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Vytvořte otočený fragment textu
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Nastavte vlastnosti textu
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// vytvořit objekt TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Připojte fragment textu na stránku PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Uložit dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Závěr

Gratuluji! Úspěšně jste se naučili otáčet text pomocí textových fragmentů v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento výukový program poskytuje podrobného průvodce od vytvoření dokumentu po uložení upravené verze. Nyní můžete tento kód začlenit do svých vlastních projektů C# a manipulovat s rotací textu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Otáčení textu pomocí fragmentu textu"?

Odpověď: Výukový program "Otáčení textu pomocí textového fragmentu" si klade za cíl vás provést procesem používání knihovny Aspose.PDF pro .NET k otáčení textu pomocí textových fragmentů v dokumentu PDF. Kurz poskytuje podrobné pokyny a ukázkový kód k dosažení této funkce.

#### Otázka: Co znamená „otočení textu pomocí textových fragmentů“?

Odpověď: Otáčení textu pomocí textových fragmentů odkazuje na schopnost aplikovat rotaci na jednotlivé textové fragmenty v dokumentu PDF pomocí knihovny Aspose.PDF. Tato technika vám umožňuje ovládat orientaci textu v různých úhlech nebo pozicích v obsahu PDF.

#### Otázka: Proč bych měl chtít otáčet fragmenty textu v dokumentu PDF?

Odpověď: Otáčení fragmentů textu v dokumentu PDF může být užitečné pro různé účely, jako je zdůraznění konkrétního obsahu, vytváření uměleckých návrhů nebo zlepšení rozvržení a čitelnosti.

#### Otázka: Jak nastavím projekt pro tutoriál?

A: Chcete-li nastavit projekt:

1. Vytvořte nový projekt C# ve vašem preferovaném integrovaném vývojovém prostředí (IDE).
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.
3. Přidejte potřebné direktivy using do svého souboru C#.

#### Otázka: Jak mohu vytvořit nový dokument PDF?

 A: Chcete-li vytvořit nový dokument PDF, inicializujte a`Document`objekt z knihovny Aspose.PDF. Tento objekt můžete použít k přidání stránek a obsahu do PDF.

#### Otázka: Jak mohu otočit fragmenty textu pomocí fragmentů textu?

A: Chcete-li otočit fragmenty textu pomocí fragmentů textu:

1.  Vytvořit`TextFragment` objektů.
2. Nastavte text a vlastnosti textových fragmentů.
3. Určete polohy fragmentů textu na stránce.
4.  Nastavte úhel otáčení pomocí`TextState.Rotation` vlastnost fragmentů textu.
5.  Vytvořte a`TextBuilder`objekt a připojit textové fragmenty na stránku PDF.

#### Otázka: Mohu použít různé úhly otočení na různé fragmenty textu?

 Odpověď: Ano, na různé můžete použít různé úhly otáčení`TextFragment` objektů. Každý textový fragment může mít svůj vlastní úhel otočení určený pomocí`TextState.Rotation` vlastnictví.

#### Otázka: Jak uložím dokument PDF s otočenými fragmenty textu?

 Odpověď: Chcete-li uložit dokument PDF s otočenými fragmenty textu, použijte`Save` metoda`Document` objekt a zadejte požadovanou cestu a název výstupního souboru.