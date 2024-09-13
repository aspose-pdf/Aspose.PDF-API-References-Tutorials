---
title: Přidat objekt SVG do souboru PDF
linktitle: Přidat objekt SVG do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno přidávejte objekty SVG do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 30
url: /cs/net/programming-with-tables/add-svg-object/
---
tomto tutoriálu se naučíme, jak přidat objekt SVG do souboru PDF pomocí knihovny Aspose.PDF for .NET. SVG (Scalable Vector Graphics) je oblíbený formát pro vektorovou grafiku, který lze snadno škálovat bez ztráty kvality. Pomocí Aspose.PDF můžete do dokumentů PDF přidávat objekty SVG programově.

## Požadavky

Než začneme, ujistěte se, že máte následující:

- Visual Studio nainstalováno
- Nainstalovaná knihovna Aspose.PDF pro .NET

## Krok 1: Nastavte prostředí

Nejprve nastavíme prostředí vytvořením nového projektu C# ve Visual Studiu. Otevřete Visual Studio a postupujte takto:

1. Klikněte na "Soubor" > "Nový" > "Projekt" pro vytvoření nového projektu.
2. Vyberte šablonu „Console App (.NET Framework)“ nebo „Console App (.NET Core)“ v závislosti na vašem nastavení.
3. Vyberte vhodný název a umístění pro svůj projekt a klikněte na „Vytvořit“.

## Krok 2: Vytvořte objekty dokumentu a obrázků

tomto kroku vytvoříme potřebné objekty pro náš dokument PDF a obrázek SVG. Otevřete soubor C# vašeho projektu a přidejte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objekt okamžitého dokumentu
Document doc = new Document();
// Vytvořte instanci obrázku
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Krok 3: Nastavte vlastnosti obrázku

Dále nastavíme vlastnosti pro náš obrázek SVG. Zadáme typ souboru jako SVG, cestu k souboru SVG a rozměry obrázku. Po předchozím kroku přidejte následující kód:

```csharp
// Nastavte typ obrázku jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Cesta ke zdrojovému souboru
img.File = dataDir + "SVGToPDF.svg";
// Nastavte šířku instance obrázku
img. FixWidth = 50;
// Nastavte výšku instance obrázku
img.FixHeight = 50;
```

## Krok 4: Vytvořte a nakonfigurujte tabulku

Nyní vytvoříme objekt tabulky a nastavíme šířky sloupců. Vytvoříme tabulku se dvěma sloupci, každý o šířce 100 jednotek. Přidejte následující kód:

```csharp
// Vytvořte tabulku instancí
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Nastavte šířku buněk tabulky
table. ColumnWidths = "100 100";
```

## Krok 5: Přidejte buňky do tabulky

V tomto kroku přidáme do tabulky řádek a buňky. Každý řádek představuje vodorovný řádek v tabulce a do řádků se přidávají buňky. Přidejte následující kód:

```csharp
//Vytvořte objekt řádku a přidejte jej do instance tabulky
Aspose.Pdf.Row row = table.Rows.Add();
// Vytvořte objekt buňky a přidejte jej do instance řádku
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Krok 6: Přidejte text a obrázek do buněk

Dále přidáme text a obrázek SVG do buněk tabulky. Do první buňky přidáme text "První buňka" a do druhé buňky SVG obrázek. Přidejte následující kód:

```csharp
// Přidejte textový fragment do kolekce odstavců objektu buňky
cell.Paragraphs.Add(new TextFragment("First cell"));
// Přidejte další buňku do řádku objektu
cell = row. Cells. Add();
// Přidejte obrázek SVG do kolekce odstavců nedávno přidané instance buňky
cell.Paragraphs.Add(img);
```

## Krok 7: Vytvořte a přidejte stránku do dokumentu

Nyní vytvoříme objekt stránky a přidáme jej do dokumentu. Tabulka bude přidána do kolekce odstavců na stránce. Přidejte následující kód:

```csharp
// Vytvořte objekt stránky a přidejte jej do kolekce stránek instance dokumentu
Page page = doc.Pages.Add();
// Přidejte tabulku do kolekce odstavců objektu stránky
page.Paragraphs.Add(table);
```

## Krok 8: Uložte soubor PDF

Nakonec soubor PDF uložíme na určené místo. Přidejte následující kód:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Příklad zdrojového kódu pro přidání objektu SVG pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objekt okamžitého dokumentu
Document doc = new Document();
// Vytvořte instanci obrázku
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Nastavte typ obrázku jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Cesta ke zdrojovému souboru
img.File = dataDir + "SVGToPDF.svg";
// Nastavte šířku instance obrázku
img.FixWidth = 50;
// Nastavte výšku instance obrázku
img.FixHeight = 50;
// Vytvořte instanci tabulky
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Nastavte šířku buněk tabulky
table.ColumnWidths = "100 100";
//Vytvořte objekt řádku a přidejte jej do instance tabulky
Aspose.Pdf.Row row = table.Rows.Add();
// Vytvořte objekt buňky a přidejte jej do instance řádku
Aspose.Pdf.Cell cell = row.Cells.Add();
// Přidejte textový fragment do kolekce odstavců objektu buňky
cell.Paragraphs.Add(new TextFragment("First cell"));
// Přidejte další buňku do řádku objektu
cell = row.Cells.Add();
// Přidejte obrázek SVG do kolekce odstavců nedávno přidané instance buňky
cell.Paragraphs.Add(img);
// Vytvořte objekt stránky a přidejte jej do kolekce stránek instance dokumentu
Page page = doc.Pages.Add();
// Přidejte tabulku do kolekce odstavců objektu stránky
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přidat objekt SVG do souboru PDF pomocí knihovny Aspose.PDF for .NET. Probrali jsme krok za krokem proces vytvoření dokumentu, nastavení prostředí, přidání obrázku SVG do buňky tabulky a uložení souboru PDF. Nyní můžete do dokumentů PDF začlenit objekty SVG programově.

### Časté dotazy pro přidání objektu SVG do souboru PDF

#### Otázka: Mohu do dokumentu PDF přidat více objektů SVG?

 Odpověď: Ano, do dokumentu PDF můžete přidat více objektů SVG. Jednoduše vytvořte a nakonfigurujte další`Aspose.Pdf.Image` instance pro každý obraz SVG, který chcete přidat, a poté je přidejte do požadovaných buněk tabulky nebo odstavců v dokumentu PDF.

#### Otázka: Jak mohu upravit velikost a polohu obrázku SVG v buňce tabulky?

 A: Chcete-li upravit velikost a polohu obrázku SVG v buňce tabulky, můžete upravit`FixWidth` a`FixHeight` vlastnosti`Aspose.Pdf.Image`instance. Můžete použít i další vlastnosti, např`HorizontalAlignment` a`VerticalAlignment` buňky tabulky pro ovládání polohování.

#### Otázka: Je možné přidat text vedle obrázku SVG do stejné buňky tabulky?

 Odpověď: Ano, je možné přidat text vedle obrázku SVG do stejné buňky tabulky. Můžete použít`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` způsob přidání textu do buňky spolu s obrázkem SVG.

#### Otázka: Mohu k obrázku SVG přidat hypertextové odkazy?

 Odpověď: Ano, k obrázku SVG můžete přidat hypertextové odkazy pomocí`Hyperlink` vlastnictví`Aspose.Pdf.Image` instance. Nastavte URL hypertextového odkazu nebo akci, aby bylo možné na obrázek kliknout.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s .NET Core 3.1 nebo novějšími verzemi?

Odpověď: Ano, Aspose.PDF pro .NET je kompatibilní s .NET Core 3.1 a novějšími verzemi. Můžete jej použít v aplikacích .NET Framework i .NET Core.