---
title: Obrázek a číslo stránky v záhlaví Zápatí v řádku
linktitle: Obrázek a číslo stránky v záhlaví Zápatí v řádku
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat obrázek a číslo stránky do záhlaví a zápatí pomocí vložených odstavců pomocí Aspose.PDF pro .NET.
type: docs
weight: 120
url: /cs/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
V tomto tutoriálu vás krok za krokem provedeme, jak přidat obrázek a číslo stránky do sekce záhlaví a zápatí dokumentu PDF pomocí Aspose.PDF pro .NET. Dodaný zdrojový kód C# použijeme k vytvoření stránky, nastavení záhlaví a zápatí, přidání obrázku a textu pomocí vložených odstavců v záhlaví dokumentu PDF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Vytvoření dokumentu a stránky PDF

Prvním krokem je vytvoření nového objektu dokumentu a stránky v dokumentu PDF. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte nový objekt dokumentu
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Vytvořte stránku v dokumentu
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Výše uvedený kód vytvoří nový objekt dokumentu a prázdnou stránku v dokumentu PDF.

## Krok 3: Přidání záhlaví s obrázkem a vloženým textem

Nyní, když je stránka vytvořena, můžeme přidat sekci záhlaví s obrázkem a textem pomocí vložených odstavců. Zde je postup:

```csharp
// Vytvořte sekci záhlaví
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Nastavte záhlaví stránky
page. Header = header;

// Vytvořte objekt TextFragment pro první vložený text
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Určete barvu textu
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Vytvořte pro obrázek objekt Image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Nastavit cestu obrázku
image1.File = dataDir + "aspose-logo.jpg";

// Definujte rozměry obrázku
image1.FixWidth = 50;
image1.FixHeight = 20;

// Označte, že první vložený text je obrázek
image1.IsInLineParagraph = true;

// Vytvořte druhý vložený text
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Přidejte položky do záhlaví
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Výše uvedený kód vytvoří sekci záhlaví, nastaví záhlaví stránky s touto sekcí, přidá TextFragment s vloženým textem a vložený objekt Image.

## Krok 4: Uložení upraveného dokumentu PDF

Po přidání záhlaví s obrázkem a vloženým textem můžeme upravený PDF dokument uložit. Zde je postup:

```csharp
// Uložte upravený dokument PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro obrázek a číslo stránky v záhlaví zápatí vložený pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektu Document voláním jeho prázdného konstruktoru
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Vytvořte stránku v objektu Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Vytvořte sekci záhlaví dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Nastavte záhlaví pro soubor PDF
page.Header = header;

// Vytvořte textový objekt
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Určete barvu
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// V sekci vytvořte objekt obrázku
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Nastavte cestu k souboru obrázku
image1.File = dataDir + "aspose-logo.jpg";

//Nastavte šířku obrázku Information
image1.FixWidth = 50;
image1.FixHeight = 20;

// Označte, že InlineParagraph seg1 je obrázek.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Uložte Pdf
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Závěr

gratuluji! Naučili jste se, jak přidat obrázek a číslo stránky do sekce záhlaví a zápatí dokumentu PDF pomocí vložených odstavců pomocí Aspose.PDF pro .NET. Nyní můžete flexibilně přizpůsobit záhlaví a zápatí dokumentů PDF.

### FAQ

#### Otázka: Jaká je výhoda použití vložených odstavců pro přidání obrázku a textu do záhlaví dokumentu PDF?

Odpověď: Použití vkládaných odstavců umožňuje bezproblémovou integraci obrázků a textu do stejného odstavce a poskytuje přesnou kontrolu nad jejich umístěním a formátováním. Tato metoda je užitečná zejména pro vytváření přizpůsobených záhlaví s vizuálními prvky.

#### Otázka: Jak dodaný zdrojový kód C# dosáhne vložených odstavců pro záhlaví v dokumentu PDF?

Odpověď: Poskytnutý kód ukazuje, jak vytvořit dokument PDF, přidat stránku a upravit záhlaví pomocí vkládaných odstavců. Přidá TextFragment s vloženým textem, vloženým obrázkem a dalším vloženým TextFragmentem.

#### Otázka: Jak určím barvu vloženého textu v záhlaví?

 Odpověď: Barva vloženého textu se určuje pomocí`ForegroundColor` majetek z`TextState` z`TextFragment` objekt.

#### Otázka: Mohu upravit rozměry vloženého obrázku v záhlaví?

 Odpověď: Ano, můžete upravit rozměry vloženého obrázku pomocí`FixWidth` a`FixHeight` vlastnosti`Image` objekt. To vám umožní ovládat šířku a výšku obrázku v záhlaví.

#### Otázka: Mohu do záhlaví zahrnout další vložené prvky, jako jsou hypertextové odkazy nebo různé styly písma?

 Odpověď: Ano, vytvořením dalších můžete do záhlaví zahrnout další vložené prvky`TextFragment` nebo`Image` objekty s požadovanými vlastnostmi. To vám umožní upravit záhlaví dále, včetně hypertextových odkazů, různých stylů písma nebo jiných vizuálních prvků.

#### Otázka: Jak mohu zajistit, aby vložený obrázek a text zůstaly správně zarovnány a naformátovány na různých zařízeních a prohlížečích?

Odpověď: Aspose.PDF for .NET zajišťuje, že vložené obrázky a text jsou správně zarovnány a formátovány, což má za následek konzistentní vzhled na různých zařízeních a prohlížečích PDF.

#### Otázka: Mohu použít vložené odstavce také na sekci zápatí?

 Odpověď: Ano, můžete použít stejnou techniku použití vkládaných odstavců na sekci zápatí vytvořením a`Footer` objekt a přidávat k němu vložené prvky, jako je text a obrázky.

#### Otázka: Je možné kombinovat vložené odstavce s jinými metodami přizpůsobení záhlaví nebo zápatí?

Odpověď: Ano, můžete kombinovat vložené odstavce s jinými metodami přizpůsobení záhlaví nebo zápatí, které poskytuje Aspose.PDF pro .NET, a vytvořit tak složitější a přizpůsobené návrhy záhlaví nebo zápatí.

#### Otázka: Mohu v případě potřeby odstranit nebo vymazat vložené prvky ze záhlaví?

 Odpověď: Ano, můžete odstranit nebo vymazat vložené prvky úpravou obsahu souboru`HeaderFooter`objekt a odstranění příslušných vložených odstavců.

#### Otázka: Jak mohu použít vložené odstavce na konkrétní stránky dokumentu PDF?

 A: Chcete-li použít vložené odstavce na konkrétní stránky, můžete vytvořit samostatné`HeaderFooter` objekty pro každou stránku a přiřaďte je pomocí`Header` majetek příslušného`Aspose.Pdf.Page` objektů.