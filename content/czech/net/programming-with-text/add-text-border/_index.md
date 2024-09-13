---
title: Přidat textový rámeček do souboru PDF
linktitle: Přidat textový rámeček do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat textové ohraničení do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 70
url: /cs/net/programming-with-text/add-text-border/
---
Tento tutoriál vás provede procesem přidání textového ohraničení do souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kam chcete přidat textové ohraničení, přidejte následující pomocí direktivy v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte nový objekt dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document pdfDocument = new Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Krok 6: Vytvořte TextFragment
 Vytvořte a`TextFragment`objekt a zadejte požadovaný text. Nastavte polohu textového fragmentu pomocí`Position` vlastnictví. V poskytnutém kódu je text nastaven na "hlavní text" a umístěn na stránce (100, 600).

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Krok 7: Nastavte vlastnosti textu
Přizpůsobte vlastnosti textu, jako je velikost písma, typ písma, barva pozadí, barva popředí atd. V poskytnutém kódu jsou pro fragment textu nastaveny vlastnosti, jako je velikost písma, písmo, barva pozadí, barva popředí a barva tahu.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Krok 8: Povolte ohraničení textu
 Chcete-li povolit ohraničení textu, nastavte`DrawTextRectangleBorder` vlastnost fragmentu textu`TextState` na`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Krok 9: Přidejte TextFragment na stránku
 Použijte`TextBuilder` třídy přidat`TextFragment` vznést námitku proti stránce.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Krok 10: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt. Zadejte cestu k výstupnímu souboru, kterou jste nastavili v kroku 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Ukázkový zdrojový kód pro Add Text Border pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořte nový objekt dokumentu
Document pdfDocument = new Document();
// Získejte konkrétní stránku
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Vytvořte fragment textu
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Nastavte vlastnosti textu
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Nastavte vlastnost StrokingColor pro kreslení ohraničení (tahu) kolem textového obdélníku
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Nastavte hodnotu vlastnosti DrawTextRectangleBorder na true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Uložte dokument
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Závěr
Úspěšně jste přidali textové ohraničení do dokumentu PDF pomocí Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Co je hlavním zaměřením tohoto tutoriálu?

Odpověď: Tento tutoriál vás provede procesem přidání textového ohraničení do souboru PDF pomocí knihovny Aspose.PDF for .NET. Poskytnutý zdrojový kód C# demonstruje nezbytné kroky k dosažení tohoto cíle.

#### Otázka: Které jmenné prostory musím pro tento výukový program importovat?

Odpověď: Do souboru kódu, kam chcete přidat textové ohraničení, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Otázka: Jak určím adresář dokumentů?

 Odpověď: V kódu vyhledejte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím objekt dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí následujícího řádku kódu:

```csharp
Document pdfDocument = new Document();
```

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Otázka: Jak vytvořím TextFragment a nastavím jeho pozici?

 Odpověď: V kroku 6 vytvoříte a`TextFragment` objektu a nastavte jeho pozici na stránce pomocí`Position` vlastnictví:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Otázka: Jak mohu přizpůsobit vlastnosti textu, včetně ohraničení textu?

Odpověď: V kroku 7 přizpůsobíte různé vlastnosti textu, jako je velikost písma, typ písma, barva pozadí, barva popředí a ohraničení textu:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Otázka: Jak přidám TextFragment do dokumentu PDF?

 Odpověď: V kroku 9 použijete`TextBuilder` třídy přidat`TextFragment` vznést námitku na stránku:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Otázka: Jak uložím výsledný dokument PDF?

A: Po přidání textu s okrajem použijte`Save` metoda`Document` objekt pro uložení dokumentu PDF:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Otázka: Jaký je hlavní poznatek z tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se úspěšně naučili, jak vylepšit dokument PDF přidáním ohraničení textu pomocí Aspose.PDF for .NET. To může být užitečné zejména pro zdůraznění konkrétního textového obsahu v souborech PDF.