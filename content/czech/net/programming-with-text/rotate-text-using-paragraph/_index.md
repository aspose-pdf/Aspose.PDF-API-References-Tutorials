---
title: Otočit text pomocí odstavce v souboru PDF
linktitle: Otočit text pomocí odstavce v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se otáčet text pomocí odstavců v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 380
url: /cs/net/programming-with-text/rotate-text-using-paragraph/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k otáčení textu pomocí odstavců. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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

## Krok 5: Vytvořte textový odstavec

 Vytvořit`TextParagraph` objekt a nastavte jeho pozici na stránce:

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Upravte hodnoty polohy podle svých požadavků.

## Krok 6: Vytvořte a nakonfigurujte textové fragmenty

 Vytvořte více`TextFragment` objektů a nastavte jejich text a vlastnosti:

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

Upravte text a další vlastnosti podle potřeby.

## Krok 7: Přidejte k odstavci fragmenty textu

 Připojte vytvořené textové fragmenty k odstavci pomocí`AppendLine` metoda:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Krok 8: Vytvořte TextBuilder a připojte odstavec

 Vytvořit`TextBuilder` objekt pomocí`pdfPage` a připojte textový odstavec na stránku PDF:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Krok 9: Uložte dokument PDF

 Uložte upravený dokument PDF do souboru pomocí`Save` metoda:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Nezapomeňte vyměnit`"TextFragmentTests_Rotated2_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázka zdrojového kódu pro otáčení textu pomocí odstavce pomocí Aspose.PDF pro .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializujte objekt dokumentu
Document pdfDocument = new Document();
// Získejte konkrétní stránku
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Vytvořte fragment textu
TextFragment textFragment1 = new TextFragment("rotated text");
// Nastavte vlastnosti textu
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Nastavte rotaci
textFragment1.TextState.Rotation = 45;
// Vytvořte fragment textu
TextFragment textFragment2 = new TextFragment("main text");
// Nastavte vlastnosti textu
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Vytvořte fragment textu
TextFragment textFragment3 = new TextFragment("another rotated text");
// Nastavte vlastnosti textu
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Nastavte rotaci
textFragment3.TextState.Rotation = -45;
// Připojte fragmenty textu k odstavci
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Vytvořte objekt TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Připojte odstavec textu ke stránce PDF
textBuilder.AppendParagraph(paragraph);
// Uložit dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Závěr

Gratulujeme! Úspěšně jste se naučili otáčet text pomocí odstavců v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento výukový program poskytuje podrobného průvodce od vytvoření dokumentu po uložení upravené verze. Nyní můžete tento kód začlenit do svých vlastních projektů C# a manipulovat s rotací textu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel kurzu "Otočit text pomocí odstavce"?

Odpověď: Výukový program "Otočit text pomocí odstavce" má za cíl vás provést procesem používání knihovny Aspose.PDF pro .NET k otáčení textu pomocí odstavců textu v dokumentu PDF. Kurz poskytuje podrobné pokyny a ukázkový kód k dosažení této funkce.

#### Otázka: Co znamená „otočení textu pomocí odstavců“?

Odpověď: Otáčení textu pomocí odstavců se týká možnosti použít otočení textu v dokumentu PDF pomocí odstavců textu. Tato technika vám umožňuje orientovat text v různých úhlech nebo pozicích v obsahu PDF.

#### Otázka: Proč bych měl chtít otáčet text v dokumentu PDF?

Odpověď: Otáčení textu v dokumentu PDF může být užitečné pro různé účely, jako je zvýraznění konkrétního obsahu, vytváření uměleckých návrhů nebo zlepšení rozvržení a čitelnosti.

#### Otázka: Jak mohu vytvořit nový dokument PDF?

 A: Chcete-li vytvořit nový dokument PDF, inicializujte a`Document`objekt z knihovny Aspose.PDF. Tento objekt můžete použít k přidání stránek a obsahu do PDF.

#### Otázka: Jak mohu otočit text pomocí odstavců?

A: Otáčení textu pomocí odstavců:

1.  Vytvořit`TextParagraph` objekt.
2.  Vytvořit`TextFragment` objekty s požadovaným textem a úhly natočení.
3. Připojte fragmenty textu k odstavci textu.
4.  Vytvořit`TextBuilder` objekt a připojit odstavec textu ke konkrétní stránce PDF.

#### Otázka: Mohu ovládat úhel otočení jednotlivých fragmentů textu?

 Odpověď: Ano, můžete ovládat úhel natočení jednotlivce`TextFragment` objektů nastavením`TextState.Rotation` vlastnictví. Kladné hodnoty označují otáčení ve směru hodinových ručiček, zatímco záporné hodnoty označují otáčení proti směru hodinových ručiček.

#### Otázka: Mohu použít různé úhly otočení na různé části textu v rámci stejného odstavce?

 Odpověď: Ano, na různé můžete použít různé úhly otáčení`TextFragment` objektů ve stejném odstavci nastavením`TextState.Rotation` vlastnost každého fragmentu.

#### Otázka: Jak uložím otočený dokument PDF?

A: Chcete-li uložit otočený dokument PDF, použijte`Save` metoda`Document` objekt a zadejte požadovanou cestu a název výstupního souboru.