---
title: Obrázek a číslo stránky v části Zápatí záhlaví
linktitle: Obrázek a číslo stránky v části Zápatí záhlaví
second_title: Aspose.PDF pro .NET API Reference
description: Zjistěte, jak přidat obrázek a číslo stránky do záhlaví a zápatí dokumentu PDF pomocí Aspose.
type: docs
weight: 110
url: /cs/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
tomto tutoriálu vás krok za krokem provedeme přidáním obrázku a čísla stránky do sekce záhlaví a zápatí dokumentu PDF pomocí Aspose.PDF for .NET. Ukážeme vám, jak pomocí poskytnutého zdrojového kódu C# vytvořit stránku, nastavit záhlaví a zápatí, přidat obrázek do záhlaví a text s číslem stránky do zápatí dokumentu PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Vytvořte stránku v dokumentu
Aspose.Pdf.Page page = doc.Pages.Add();
```

Výše uvedený kód vytvoří nový objekt dokumentu a prázdnou stránku v dokumentu PDF.

## Krok 3: Přidání záhlaví s obrázkem

Nyní, když je stránka vytvořena, můžeme přidat sekci záhlaví s obrázkem. Zde je postup:

```csharp
// Vytvořte sekci záhlaví
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Nastavte záhlaví stránky
page. Header = header;

// Vytvořte objekt Image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Nastavit cestu obrázku
image1.File = dataDir + "aspose-logo.jpg";

// Přidejte obrázek do záhlaví stránky dokumentu PDF
header.Paragraphs.Add(image1);
```

Výše uvedený kód vytvoří sekci záhlaví, nastaví záhlaví stránky s touto sekcí a přidá do záhlaví obrázek.

## Krok 4: Přidání zápatí s číslem stránky

Nyní, když je přidáno záhlaví, můžeme přidat sekci zápatí s číslem stránky. Zde je postup:

```csharp
// Vytvořte sekci zápatí
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Definujte zápatí dokumentu PDF
page. Footer = footer;

// Vytvořte objekt TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Přidejte text s číslem stránky do zápatí dokumentu PDF
footer.Paragraphs.Add(txt);
```

Výše uvedený kód vytvoří sekci zápatí, nastaví zápatí stránky s touto částí a přidá TextFragment obsahující text "Stránka: ($p z $P )"

  který zobrazuje číslo stránky.

## Krok 5: Uložení upraveného dokumentu PDF

Po přidání záhlaví a zápatí můžeme upravený dokument PDF uložit. Zde je postup:

```csharp
// Uložte upravený dokument PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro obrázek a číslo stránky v zápatí záhlaví pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Vytvořte stránku v objektu dokumentu
Aspose.Pdf.Page page = doc.Pages.Add();

// Vytvořte sekci záhlaví dokumentu
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Nastavte záhlaví pro soubor PDF
page.Header = header;

// Vytvořte na stránce objekt obrázku
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Nastavte cestu k souboru obrázku
image1.File = dataDir + "aspose-logo.jpg";

// Přidejte obrázek na stránku záhlaví souboru Pdf
header.Paragraphs.Add(image1);

//Vytvořte sekci zápatí dokumentu
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Nastavte zápatí souboru PDF
page.Footer = footer;

// Vytvořte textový objekt
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Přidejte text do části Záhlaví souboru Pdf
footer.Paragraphs.Add(txt);

// Uložte soubor Pdf
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Závěr

gratuluji! Naučili jste se, jak přidat obrázek a číslo stránky do sekce záhlaví a zápatí dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete tuto metodu použít k přizpůsobení záhlaví a zápatí v dokumentech PDF.

### FAQ

#### Otázka: Jaký je účel přidání obrázku a čísla stránky do části záhlaví a zápatí dokumentu PDF?

Odpověď: Přidání obrázku a čísla stránky do části záhlaví a zápatí dokumentu PDF může zlepšit jeho vizuální přitažlivost, branding a navigační prvky. Obrázek může představovat logo, vodoznak nebo jakýkoli grafický prvek, zatímco číslo stránky pomáhá uživatelům sledovat jejich pokrok a najít konkrétní stránky.

#### Otázka: Jak dodaný zdrojový kód C# pomáhá při přidávání obrázku a čísla stránky do záhlaví a zápatí dokumentu PDF?

Odpověď: Poskytnutý kód ukazuje, jak vytvořit dokument PDF, přidat stránku a poté upravit sekce záhlaví a zápatí. Ukazuje, jak přidat obrázek do záhlaví a textový fragment s číslováním stránek do zápatí.

#### Otázka: Mohu pro záhlaví použít jakýkoli formát obrázku a jak určím jeho cestu?

 Odpověď: Ano, pro obrázek záhlaví můžete použít různé formáty obrázků (jako JPEG, PNG, GIF atd.). Cesta k obrázku je určena pomocí`File` vlastnictvím`Aspose.Pdf.Image` objekt.

#### Otázka: Jak přizpůsobím vzhled a umístění obrázku v sekci záhlaví?

 Odpověď: Vzhled a umístění obrázku můžete upravit úpravou vlastností`Aspose.Pdf.Image` objekt před jeho přidáním do sekce záhlaví. Můžete například nastavit rozměry obrázku, zarovnání, otočení, krytí atd.

####  Otázka: Jaký je účel`TextFragment` object used for the footer?

 A:`TextFragment` objekt slouží k vytvoření a formátování textu, který se zobrazí v zápatí. V poskytnutém kódu se používá k zobrazení čísla stránky a celkového počtu stránek.

#### Otázka: Mohu upravit text zápatí tak, aby obsahoval další informace nebo formátování?

 Odpověď: Ano, text zápatí můžete upravit úpravou obsahu souboru`TextFragment` objekt. Můžete přidat další text, změnit písma, barvy a formátování podle svých požadavků.

#### Otázka: Mohu použít jiný obsah záhlaví a zápatí na různé stránky dokumentu PDF?

 Odpověď: Ano, můžete použít různé obsahy záhlaví a zápatí na různé stránky vytvořením samostatných stránek`HeaderFooter` objektů a jejich přiřazení ke konkrétním stránkám pomocí`Header` a`Footer` vlastnosti`Aspose.Pdf.Page` objekt.

#### Otázka: Jak mohu dále upravit záhlaví a zápatí, například změnit styly písma nebo přidat další prvky?

Odpověď: Záhlaví a zápatí můžete přizpůsobit pomocí různých tříd a vlastností poskytovaných Aspose.PDF pro .NET. Můžete například použít různé možnosti formátování textu, přidat více odstavců, obrázků nebo dokonce tabulek do částí záhlaví a zápatí.

#### Otázka: Mohu v případě potřeby odstranit nebo vymazat sekce záhlaví a zápatí?

Odpověď: Ano, můžete odstranit nebo vymazat sekce záhlaví a zápatí nastavením`Header` a`Footer` vlastnosti`Aspose.Pdf.Page` namítat proti`null`.

#### Otázka: Jak mohu zajistit, aby přidaný obrázek a číslo stránky zůstaly konzistentní na různých zařízeních a prohlížečích?

Odpověď: Aspose.PDF for .NET poskytuje funkce pro vytváření standardizovaných a konzistentních dokumentů PDF, což zajišťuje, že se přidaný obrázek a číslo stránky budou zobrazovat konzistentně na různých zařízeních a prohlížečích PDF.