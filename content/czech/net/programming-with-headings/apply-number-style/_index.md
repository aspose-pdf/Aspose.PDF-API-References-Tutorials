---
title: Použít styl čísel v souboru PDF
linktitle: Použít styl čísel v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak použít styl číslování na nadpisy v souboru PDF pomocí Aspose.PDF pro .NET. Průvodce krok za krokem.
type: docs
weight: 10
url: /cs/net/programming-with-headings/apply-number-style/
---
V tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, jak použít styl číslování v souboru PDF pomocí Aspose.PDF pro .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

### Krok 1: Nastavení adresáře dokumentů

poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit vygenerovaný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Krok 2: Vytvoření dokumentu PDF

Vytvoříme nový PDF dokument se zadanými rozměry a okraji.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Krok 3: Vytvoření stránky a plovoucího kontejneru

Do dokumentu přidáme stránku a vytvoříme plovoucí kontejner pro uspořádání obsahu.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Krok 4: Přidejte nadpisy s číslováním

Vytvoříme hlavičky se zadaným číslováním a přidáme je do plovoucího kontejneru.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Krok 5: Uložení dokumentu PDF

Vygenerovaný PDF dokument uložíme do zadaného adresáře.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Ukázkový zdrojový kód pro Použít styl čísel pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak použít styl číslování na nadpisy v dokumentu PDF pomocí Aspose.PDF pro .NET. Tyto znalosti nyní můžete využít k vytváření dokumentů PDF s vlastním číslováním nadpisů.

### Časté dotazy k použití stylu čísel v souboru PDF

#### Otázka: Co je styl číslování v dokumentu PDF?

Odpověď: Styl číslování se týká formátu, ve kterém jsou číslovány nadpisy nebo sekce v dokumentu PDF. Může obsahovat číslice, písmena nebo jiné znaky pro vytvoření hierarchické struktury.

#### Otázka: Proč bych potřeboval použít styl číslování na nadpisy v dokumentu PDF?

Odpověď: Použití stylu číslování na nadpisy zlepšuje čitelnost a organizaci vašeho dokumentu PDF. Pomáhá čtenářům snadno se orientovat a pochopit hierarchickou strukturu obsahu.

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je knihovna, která umožňuje vývojářům pracovat se soubory PDF programově v aplikacích .NET. Poskytuje širokou škálu funkcí pro vytváření, úpravy, převod a manipulaci s dokumenty PDF.

#### Otázka: Jak naimportuji požadované knihovny pro svůj projekt C#?

A: Chcete-li importovat potřebné knihovny pro váš projekt C#, zahrňte následující importní direktivy:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Tyto direktivy vám umožňují přístup ke třídám a metodám potřebným pro práci s dokumenty PDF a použití stylů číslování.

#### Otázka: Jak určím adresář pro uložení vygenerovaného souboru PDF?

Odpověď: V poskytnutém zdrojovém kódu upravte proměnnou "dataDir" tak, aby určovala adresář, kam chcete uložit vygenerovaný soubor PDF.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři.

#### Otázka: Jak vytvořím dokument PDF se zadanými rozměry a okraji?

Odpověď: Chcete-li vytvořit dokument PDF se zadanými rozměry a okraji, použijte následující kód:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### Otázka: Jak přidám nadpisy se stylem číslování do dokumentu PDF?

Odpověď: Chcete-li do dokumentu PDF přidat nadpisy se stylem číslování, použijte dodané ukázky kódu k vytvoření nadpisů a přizpůsobení jejich stylů číslování. Podle potřeby upravte vlastnosti, jako je text, styl číslování, počáteční číslo a automatické pořadí.

#### Otázka: Jak uložím vygenerovaný dokument PDF?

 A: Chcete-li uložit vygenerovaný dokument PDF, použijte`Save` metoda`pdfDoc` objekt:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### Otázka: Jak mohu potvrdit, že byl použit styl číslování?

Odpověď: Otevřete vygenerovaný soubor PDF a ověřte, zda byl na nadpisy použit zadaný styl číslování.

#### Otázka: Mohu dále přizpůsobit styl číslování?

 Odpověď: Ano, styl číslování můžete dále upravit úpravou vlastností souboru`Heading` objekty, jako je typ stylu číslování, počáteční číslo a automatická sekvence.

#### Otázka: Mohu použít různé styly číslování na různé části dokumentu?

 Odpověď: Ano, na různé části dokumentu můžete použít různé styly číslování vytvořením více`Heading` objekty s různými styly a sekvencemi.