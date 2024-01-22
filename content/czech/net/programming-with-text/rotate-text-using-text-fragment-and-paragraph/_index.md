---
title: Otočit Text pomocí fragmentu textu a odstavce
linktitle: Otočit Text pomocí fragmentu textu a odstavce
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se otáčet text pomocí fragmentu textu a odstavce v dokumentu PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 400
url: /cs/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Tento tutoriál vysvětluje, jak používat Aspose.PDF pro .NET k otáčení textu pomocí fragmentu textu a odstavce. Poskytnutý zdrojový kód C# demonstruje proces krok za krokem.

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

 Vytvořte více`TextFragment` objektů, nastavte jejich text a vlastnosti a určete úhel otočení:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Podle potřeby upravte text, úhel otočení a další vlastnosti.

## Krok 6: Přidejte na stránku fragmenty textu

 Přidejte vytvořené textové fragmenty na stránku jejich připojením ke stránce`Paragraphs` sbírka:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Krok 7: Uložte dokument PDF

 Uložte upravený dokument PDF do souboru pomocí`Save` metoda:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Nezapomeňte vyměnit`"TextFragmentTests_Rotated3_out.pdf"` s požadovaným názvem výstupního souboru.

### Ukázka zdrojového kódu pro otáčení textu pomocí fragmentu textu a odstavce pomocí Aspose.PDF pro .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inicializujte objekt dokumentu
Document pdfDocument = new Document();
// Získejte konkrétní stránku
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Vytvořte fragment textu
TextFragment textFragment1 = new TextFragment("main text");
// Nastavte vlastnosti textu
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Vytvořte fragment textu
TextFragment textFragment2 = new TextFragment("rotated text");
// Nastavte vlastnosti textu
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Nastavte rotaci
textFragment2.TextState.Rotation = 315;
// Vytvořte fragment textu
TextFragment textFragment3 = new TextFragment("rotated text");
// Nastavte vlastnosti textu
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Nastavte rotaci
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Uložit dokument
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Závěr

Gratulujeme! Úspěšně jste se naučili otáčet text pomocí textových fragmentů a odstavců v dokumentu PDF pomocí Aspose.PDF for .NET. Tento výukový program poskytuje podrobného průvodce od vytvoření dokumentu po uložení upravené verze. Nyní můžete tento kód začlenit do svých vlastních projektů C# a manipulovat s rotací textu v souborech PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Otáčení textu pomocí fragmentu textu a odstavce"?

Odpověď: Výukový program "Otáčení textu pomocí textového fragmentu a odstavce" si klade za cíl vás provést procesem používání knihovny Aspose.PDF pro .NET k otáčení textu pomocí textových fragmentů i odstavců v dokumentu PDF. Kurz poskytuje podrobné pokyny a ukázkový kód k dosažení této funkce.

#### Otázka: Jak se tento kurz liší od předchozích kurzů otáčení textu?

Odpověď: Tento výukový program kombinuje použití textových fragmentů a odstavců k dosažení rotace textu v dokumentu PDF. Ukazuje, jak otočit fragmenty textu jednotlivě a poté je přidat na stránku`Paragraphs` kolekce pro dosažení komplexnějšího efektu rotace textu.

#### Otázka: Jaké jsou výhody používání fragmentů textu a odstavců pro otáčení textu?

Odpověď: Společné používání fragmentů textu a odstavců umožňuje větší flexibilitu při otáčení textu. Fragmenty textu umožňují individuální nastavení otáčení a formátování, zatímco odstavce poskytují strukturu pro uspořádání a umístění fragmentů textu na stránce.

#### Otázka: Mohu použít různé úhly otočení na různé části textu v rámci stejného odstavce?

 Odpověď: Ano, na různé můžete použít různé úhly otáčení`TextFragment` objekty ve stejném odstavci. Každý textový fragment může mít svůj vlastní úhel otočení určený pomocí`TextState.Rotation` vlastnictví.

#### Otázka: Je možné pomocí této metody dosáhnout složitých efektů rotace textu?

Odpověď: Ano, kombinací textových fragmentů s různými úhly natočení a jejich uspořádáním v odstavcích můžete dosáhnout komplexních a přizpůsobených efektů rotace textu, čímž zvýšíte vizuální přitažlivost vašich dokumentů PDF.

#### Otázka: Jaké kroky se týkají otáčení textu pomocí fragmentů textu a odstavců?

Odpověď: Tyto kroky zahrnují:

1. Nastavení projektu vytvořením nového projektu C# a přidáním odkazu na knihovnu Aspose.PDF for .NET.
2. Vytvoření dokumentu PDF a přidání stránky.
3. Vytváření fragmentů textu, nastavení jejich vlastností a určení úhlů natočení.
4.  Přidání textových fragmentů na stránku pomocí`Paragraphs` sbírka.
5. Uložení upraveného dokumentu PDF.

#### Otázka: Mohu použít rotaci na celé odstavce?

 Odpověď: Ano, můžete použít rotaci na celé odstavce nastavením`TextState.Rotation` vlastnost samotného odstavce. Tím se otočí všechny části textu v tomto odstavci.