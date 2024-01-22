---
title: Vykreslování vyměnitelných symbolů v souboru PDF
linktitle: Vykreslování vyměnitelných symbolů v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vykreslovat vyměnitelné symboly v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 310
url: /cs/net/programming-with-text/rendering-replaceable-symbols/
---
V tomto tutoriálu vysvětlíme, jak vykreslit vyměnitelné symboly v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces vytvoření PDF, přidání textového fragmentu se značkami nového řádku, nastavení vlastností textu, umístění textu a uložení PDF pomocí poskytnutého zdrojového kódu C#.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve je potřeba nastavit cestu k adresáři, kam chcete vygenerovaný PDF soubor uložit. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir`proměnnou s cestou k požadovanému adresáři.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a stránku PDF

 Dále vytvoříme nový dokument PDF a přidáme do něj stránku pomocí`Document` třída a`Page` třídy z knihovny Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Krok 3: Přidejte textový fragment se značkami nového řádku

 Vytváříme a`TextFragment`objekt a nastavte jeho text tak, aby zahrnoval značky nového řádku (`Environment.NewLine`) reprezentovat více řádků textu.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Krok 4: Nastavte vlastnosti textového fragmentu

V případě potřeby můžeme pro fragment textu nastavit různé vlastnosti, jako je velikost písma, písmo, barva pozadí a barva popředí.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Krok 5: Vytvořte odstavec a pozici textu

 Vytváříme a`TextParagraph` objekt, připojte fragment textu k odstavci a nastavte pozici odstavce na stránce.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Krok 6: Přidejte na stránku textový odstavec

 Vytváříme a`TextBuilder` objekt se stránkou a přidejte textový odstavec do nástroje pro tvorbu textu.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Krok 7: Uložte dokument PDF

Nakonec dokument PDF uložíme do zadaného výstupního souboru.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Ukázka zdrojového kódu pro vykreslování vyměnitelných symbolů pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Inicializujte nový TextFragment textem obsahujícím požadované značky nového řádku
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// V případě potřeby nastavte vlastnosti fragmentu textu
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Vytvořte objekt TextParagraph
TextParagraph par = new TextParagraph();
// Přidejte nový TextFragment do odstavce
par.AppendLine(textFragment);
// Nastavit pozici odstavce
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Vytvořte objekt TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Přidejte TextParagraph pomocí TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Závěr

tomto tutoriálu jste se naučili, jak vykreslit vyměnitelné symboly v dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a provedením poskytnutého kódu C# můžete vytvořit PDF, přidat text se značkami nového řádku, nastavit vlastnosti textu, umístit text na stránku a uložit PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu „Vykreslování vyměnitelných symbolů v souboru PDF“?

Odpověď: Výukový program "Vykreslování vyměnitelných symbolů v souboru PDF" ukazuje, jak používat knihovnu Aspose.PDF pro .NET k vytvoření dokumentu PDF, který obsahuje vyměnitelné symboly. Tyto symboly jsou reprezentovány jako textové fragmenty se značkami nového řádku pro vytvoření víceřádkového obsahu.

#### Otázka: Proč bych měl chtít vykreslit vyměnitelné symboly v dokumentu PDF?

Odpověď: Vykreslování vyměnitelných symbolů je užitečné, když potřebujete dynamicky generovat obsah PDF, který obsahuje proměnné nebo informace specifické pro uživatele. Tyto symboly fungují jako zástupné symboly, které lze za běhu nahradit skutečnými daty, jako jsou hodnoty polí formuláře nebo personalizované podrobnosti.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kam chcete vygenerovaný PDF soubor uložit.

#### Otázka: Jak vykreslím vyměnitelné symboly v dokumentu PDF pomocí knihovny Aspose.PDF?

Odpověď: Výukový program vás provede procesem krok za krokem:

1.  Vytvořte nový dokument PDF pomocí`Document` třída.
2.  Přidejte stránku do dokumentu pomocí`Page` třída.
3.  Vytvořit`TextFragment` objekt se značkami nového řádku (`Environment.NewLine`) k reprezentaci víceřádkového obsahu.
4. Přizpůsobte vlastnosti fragmentu textu, jako je velikost písma, písmo, barva pozadí a barva popředí.
5.  Vytvořit`TextParagraph` objekt, připojte k němu fragment textu a nastavte pozici odstavce na stránce.
6.  Vytvořit`TextBuilder` objekt se stránkou a připojit k ní odstavec textu.
7. Uložte dokument PDF.

#### Otázka: Jaký je účel použití značek nového řádku (`Environment.NewLine`) in the text fragment?

 Odpověď: Značky nového řádku se používají k vytvoření víceřádkového obsahu v rámci jednoho textového fragmentu. Používáním`Environment.NewLine`, můžete určit, kde se má v textu vyskytovat zalomení řádků.

#### Otázka: Mohu upravit vzhled vyměnitelných symbolů?

Odpověď: Ano, můžete přizpůsobit různé vlastnosti fragmentu textu, jako je velikost písma, písmo, barva pozadí a barva popředí. Tyto vlastnosti určují vizuální vzhled vyměnitelných symbolů v dokumentu PDF.

#### Otázka: Jak určím pozici textu na stránce?

 Odpověď: Pozici textu můžete nastavit vytvořením a`TextParagraph` objektu a pomocí`Position` vlastnost k určení souřadnic X a Y na stránce, kde by měl být odstavec umístěn.

#### Otázka: Jaký je očekávaný výsledek spuštění poskytnutého kódu?

Odpověď: Podle návodu a spuštěním poskytnutého kódu C# vytvoříte dokument PDF, který obsahuje vyměnitelné symboly. Nahraditelné symboly budou reprezentovány jako textové fragmenty se značkami nového řádku a přizpůsobenými vlastnostmi.

#### Otázka: Mohu tento přístup použít k dynamickému generování personalizovaných dokumentů PDF?

Odpověď: Ano, tento přístup je vhodný pro dynamické generování dokumentů PDF s personalizovanými informacemi. Nahrazením vyměnitelných symbolů skutečnými daty můžete vytvořit přizpůsobený obsah PDF pro každého uživatele nebo scénář.