---
title: Přidat obrázek do buňky tabulky
linktitle: Přidat obrázek do buňky tabulky
second_title: Aspose.PDF pro .NET API Reference
description: Přidejte obrázek do buňky tabulky pomocí Aspose.PDF for .NET, průvodce krok za krokem pro přesnou manipulaci s obrázky v dokumentech PDF.
type: docs
weight: 10
url: /cs/net/programming-with-tables/add-image-in-a-table-cell/
---
tomto tutoriálu vás provedeme procesem přidání obrázku do buňky tabulky pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje, jak této funkce dosáhnout. Podle níže uvedených kroků budete schopni efektivně začlenit obrázky do buněk tabulky.

Než se ponoříme do kódu, ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF for .NET a odkazovanou ve vašem projektu.

## Krok 1: Nastavení dokumentu

 Pro začátek musíme vytvořit novou instanci`Document` třídy ze jmenného prostoru Aspose.Pdf. Tato třída představuje dokument PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektu dokumentu
Document pdfDocument = new Document();
```

## Krok 2: Vytvoření stránky

Dále musíme do dokumentu PDF přidat stránku. Stránka slouží jako kontejner pro tabulku a další prvky.

```csharp
// Vytvořte stránku v dokumentu pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Krok 3: Přidání tabulky

 V tomto kroku vytvoříme tabulku vytvořením instance`Table` třídy ze jmenného prostoru Aspose.Pdf.

```csharp
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Krok 4: Nastavení výchozího ohraničení buňky

 Abychom zajistili konzistenci, můžeme nastavit výchozí ohraničení buňky pomocí`DefaultCellBorder`vlastnost stolu`BorderInfo` objekt.

```csharp
// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Krok 5: Nastavení šířky sloupců

 Chcete-li definovat šířku každého sloupce v tabulce, můžeme nastavit`ColumnWidths` vlastnictví. Zadejte šířky jako řetězec s hodnotami oddělenými mezerami.

```csharp
// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "100 100 120";
```

## Krok 6: Přidání obrázku do buňky tabulky

Nyní přichází ta vzrušující část, přidání obrázku do buňky tabulky. K tomu budeme postupovat podle těchto dílčích kroků:

## Krok 6.1: Vytvoření objektu obrázku

 Vytvořte instanci souboru`Image` třídy ze jmenného prostoru Aspose.Pdf. Nastavte`File` vlastnost k cestě k souboru obrázku, který chcete přidat.

```csharp
// Vytvořte objekt Image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Krok 6.2: Vytvoření řádku a buněk

Pro přidání obrázku do tabulky musíme nejprve vytvořit řádek a potřebné buňky.

```csharp
// Vytvořte řádek v tabulce
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Přidejte do řádku textovou buňku
row1.Cells.Add("Sample text in cell");

// Přidejte buňku, která obsahuje obrázek
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Krok 6.3: Přidání obrázku do buňky tabulky

Nakonec můžeme obrázek přidat do buňky tabulky tak, že jej přidáme jako odstavec do buňky.

```csharp
// Přidejte obrázek do buňky tabulky
cell2.Paragraphs.Add(img);
```

## Krok 6.4: Přidání dalších buněk

Po přidání buňky obrázku můžeme v případě potřeby přidat další buňky do řádku.

```csharp
//Přidejte do řádku další buňku
row1.Cells.Add("Previous cell with image");

// Upravte svislé zarovnání třetí buňky
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Krok 7: Uložení dokumentu

 Nakonec můžeme upravený dokument uložit na určené místo pomocí`Save` metoda.

```csharp
// Uložte dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Gratuluji! Úspěšně jste se naučili, jak přidat obrázek do buňky tabulky pomocí Aspose.PDF pro .NET. Neváhejte prozkoumat další možnosti přizpůsobení a integrujte tuto funkci do svých projektů.

### Příklad zdrojového kódu pro přidání obrázku do buňky tabulky pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte instanci objektu dokumentu
Document pdfDocument = new Document();
// Vytvořte stránku v dokumentu pdf
Page sec1 = pdfDocument.Pages.Add();
// Vytvořte instanci objektu tabulky
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Přidejte tabulku do kolekce odstavců požadované stránky
sec1.Paragraphs.Add(tab1);
// Nastavte výchozí ohraničení buňky pomocí objektu BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Nastavte šířku sloupců tabulky
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Vytvořte řádky v tabulce a poté buňky v řádcích
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Přidejte buňku, která obsahuje obrázek
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Přidejte obrázek do buňky tabulky
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Uložte dokument
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Závěr

tomto tutoriálu jsme probrali podrobný návod, jak přidat obrázek do buňky tabulky pomocí Aspose.PDF pro .NET. Začali jsme nastavením dokumentu, vytvořením stránky a přidáním tabulky. Poté nastavíme výchozí ohraničení buňky a šířku sloupců. Ukázali jsme, jak přidat obrázek do buňky tabulky a upravit vertikální zarovnání buňky. Nakonec jsme upravený dokument uložili. Pomocí těchto kroků můžete efektivně vylepšit své dokumenty PDF pomocí obrázků v buňkách tabulky.

### FAQ

#### Otázka: Mohu přidat více obrázků do různých buněk ve stejné tabulce pomocí Aspose.PDF for .NET?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete přidat více obrázků do různých buněk ve stejné tabulce. Jednoduše postupujte stejným způsobem jako v tutoriálu pro každý obrázek, který chcete přidat do tabulky.

#### Otázka: Mohu upravit velikost a umístění obrázku v buňce tabulky?

 Odpověď: Ano, můžete upravit velikost a umístění obrázku v buňce tabulky úpravou vlastností`Image`objekt. Můžete nastavit šířku a výšku obrázku a také zarovnání v rámci buňky.

#### Otázka: Mohu přidat obrázky do tabulky s dynamickým počtem řádků a sloupců?

Odpověď: Ano, do tabulky můžete přidat obrázky s dynamickým počtem řádků a sloupců. Aspose.PDF for .NET poskytuje flexibilitu při vytváření tabulek s různými rozměry. Podle potřeby můžete přidávat řádky a buňky a podle toho pak přidávat obrázky do konkrétních buněk.

#### Otázka: Jaké formáty obrázků podporuje Aspose.PDF pro .NET pro přidávání obrázků do buněk tabulky?

A: Aspose.PDF for .NET podporuje širokou škálu obrazových formátů, včetně JPEG, PNG, GIF, BMP a TIFF. Obrázky libovolného z těchto formátů můžete použít k jejich přidání do buněk tabulky.

#### Otázka: Mohu přidat obrázky do tabulek ve stávajícím dokumentu PDF?

Odpověď: Ano, můžete přidat obrázky do tabulek ve stávajícím dokumentu PDF pomocí Aspose.PDF pro .NET. Jednoduše načtěte existující dokument a postupujte podle stejných kroků pro přidání obrázků do tabulky, jak je ukázáno v tutoriálu.