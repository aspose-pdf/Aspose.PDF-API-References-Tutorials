---
title: Nastavte velikost obrázku v souboru PDF
linktitle: Nastavte velikost obrázku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce nastavením velikosti obrázku v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 270
url: /cs/net/programming-with-images/set-image-size/
---
V tomto tutoriálu vás provedeme tím, jak nastavit velikost obrázku v souboru PDF pomocí Aspose.PDF pro .NET. Chcete-li tuto operaci snadno provést, postupujte podle následujících kroků.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakékoli jiné vývojové prostředí nainstalované a nakonfigurované.
- Základní znalost programovacího jazyka C#.
- Nainstalovaná knihovna Aspose.PDF pro .NET. Můžete si jej stáhnout z oficiálních stránek Aspose.

## Krok 1: Vytvoření dokumentu PDF

Chcete-li začít, použijte následující kód k vytvoření nového dokumentu PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Vytvořte instanci objektu dokumentu
Document doc = new Document();

// Přidejte stránku do kolekce stránek souboru PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Krok 2: Přidán obrázek

Dále přidáme obrázek na stránku dokumentu PDF. Použijte následující kód:

```csharp
// Vytvořte instanci obrázku
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Nastavte šířku a výšku obrázku v bodech
img. FixWidth = 100;
img. FixHeight = 100;

//Nastavit typ obrázku na neznámý (Neznámý)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// Cesta ke zdrojovému souboru obrázku
img.File = dataDir + "aspose-logo.jpg";

// Přidejte obrázek do kolekce odstavců stránky
page.Paragraphs.Add(img);
```

Ujistěte se, že jste zadali správnou cestu ke zdrojovému souboru obrázku.

## Krok 3: Nastavení vlastností stránky

Nakonec nastavíme vlastnosti stránky včetně její šířky a výšky. Použijte následující kód:

```csharp
// Nastavte vlastnosti stránky
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Ukázkový zdrojový kód pro nastavení velikosti obrázku pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Objekt okamžitého dokumentu
Document doc = new Document();
// přidat stránku do kolekce stránek souboru PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Vytvořte instanci obrázku
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Nastavte šířku a výšku obrázku v bodech
img.FixWidth = 100;
img.FixHeight = 100;
// Nastavte typ obrázku jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// Cesta ke zdrojovému souboru
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Nastavte vlastnosti stránky
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// uložit výsledný soubor PDF
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Závěr

gratuluji! Úspěšně jste nastavili velikost obrázku v dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete tuto metodu použít na své vlastní projekty a upravit velikost obrázků v souborech PDF.

### Časté dotazy pro nastavení velikosti obrázku v souboru PDF

#### Otázka: Jaký je účel nastavení velikosti obrázku v dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Účelem nastavení velikosti obrázku v dokumentu PDF je řídit rozměry obrázku při jeho přidání do PDF. To vám umožní upravit vzhled a rozvržení obrázků v souborech PDF.

#### Otázka: Jak funguje proces nastavení velikosti obrázku v dokumentu PDF?

 A: Proces zahrnuje vytvoření`Aspose.Pdf.Image` instance, zadáním její šířky a výšky pomocí`FixWidth` a`FixHeight` vlastnosti a poté přidejte obrázek do dokumentu PDF. Navíc můžete nastavit rozměry samotné stránky tak, aby se přizpůsobila obrázku.

#### Otázka: Mohu nastavit velikost obrázku na určité procento rozměrů stránky?

Odpověď: Poskytnutý kód nastavuje absolutní šířku a výšku obrázku v bodech. Pokud chcete nastavit velikost obrázku na základě procenta rozměrů stránky, museli byste podle toho vypočítat rozměry a podle toho upravit kód.

####  Otázka: Jaký je význam`FileType` property when adding an image to the PDF document?

 A:`FileType`vlastnost určuje typ obrázku přidávaného do dokumentu PDF. V poskytnutém kódu hodnota`Unknown` označuje, že typ obrázku je neznámý a Aspose.PDF se pokusí určit typ obrázku na základě přípony souboru.

#### Otázka: Mohu pomocí této metody přidat více obrázků na jednu stránku?

 Odpověď: Ano, na jednu stránku můžete přidat více obrázků vytvořením více`Aspose.Pdf.Image` instance a jejich přidání do kolekce odstavců stránky. Ujistěte se, že jste podle potřeby upravili umístění a rozvržení obrázků.

#### Otázka: Jak mohu ovládat umístění a zarovnání přidaného obrázku na stránce?

 Odpověď: Umístění a zarovnání přidaného obrázku lze ovládat úpravou souřadnic a rozložení obrázku pomocí vlastností, jako je např.`img.Left`, `img.Top`a vlastnosti formátování odstavce.

####  Otázka: Jaký je účel použití nastavení vlastností stránky`page.PageInfo.Width` and `page.PageInfo.Height`?

Odpověď: Nastavení vlastností stránky umožňuje definovat rozměry samotné stránky. Tím zajistíte, že rozměry stránky se přizpůsobí přidanému obrázku a dalšímu obsahu, který na stránce můžete mít.

#### Otázka: Mohu nastavit různé velikosti pro různé obrázky ve stejném dokumentu PDF?

 Odpověď: Ano, můžete nastavit různé velikosti pro různé obrázky vytvořením samostatných`Aspose.Pdf.Image` instance a úprava`FixWidth`, `FixHeight`a vlastnosti umístění pro každý obrázek.

#### Otázka: Jak mohu integrovat tuto metodu do svých vlastních projektů pro nastavení velikosti obrázků v souborech PDF?

A: Chcete-li integrovat tuto metodu do svých projektů, postupujte podle uvedených kroků a upravte kód podle potřeby. Tuto metodu můžete použít k přidání obrázků určitých velikostí do dokumentů PDF na základě požadavků vaší aplikace.