---
title: HTML tagy uvnitř tabulky v souboru PDF
linktitle: HTML tagy uvnitř tabulky v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat HTML tagy uvnitř tabulky v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 100
url: /cs/net/programming-with-tables/html-tags-inside-table/
---
tomto tutoriálu se naučíme, jak používat HTML tagy uvnitř tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme si zdrojový kód v C# krok za krokem. Na konci tohoto tutoriálu budete vědět, jak vložit obsah HTML do tabulky v dokumentu PDF. Začněme!

## Krok 1: Nastavení prostředí
Ujistěte se, že jste své vývojové prostředí C# nakonfigurovali pomocí Aspose.PDF pro .NET. Přidejte odkaz do knihovny a importujte potřebné jmenné prostory.

## Krok 2: Vytvoření dat tabulky
Vytvoříme DataTable obsahující sloupec "data" typu String. Poté přidáme řádky do této DataTable pomocí obsahu HTML.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## Krok 3: Vytvoření dokumentu a tabulky
Vytvoříme nový dokument PDF a přidáme stránku do tohoto dokumentu. Dále inicializujeme instanci třídy Table a nastavíme vlastnosti tabulky.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## Krok 4: Import dat do tabulky
Data z DataTable importujeme do tabulky metodou "ImportDataTable". Parametry metody specifikujeme, abychom určili, který rozsah řádků a sloupců tabulky DataTable by měl být importován.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## Krok 5: Přidání tabulky do dokumentu
Tabulku přidáme na stránku dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## Fáze 6: Uložení dokumentu
PDF dokument uložíme s tabulkou obsahující obsah HTML.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Příklad zdrojového kódu pro HTML tagy uvnitř tabulky pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inicializuje novou instanci tabulky
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Nastavte šířku sloupců tabulky
tableProvider.ColumnWidths = "400 50 ";
// Nastavte barvu okraje tabulky jako LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Nastavte ohraničení buněk tabulky
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Závěr
V tomto tutoriálu jsme se naučili používat HTML tagy uvnitř tabulky v dokumentu PDF pomocí Aspose.PDF for .NET. Pomocí tohoto podrobného průvodce můžete vložit obsah HTML do buněk tabulky v dokumentu PDF pomocí jazyka C#.

### Časté dotazy pro HTML tagy uvnitř tabulky v PDF souboru

#### Otázka: Mohu použít jiné značky a atributy HTML uvnitř buněk tabulky?

 Odpověď: Ano, uvnitř buněk tabulky můžete použít různé HTML tagy a atributy, jako např`<b>`, `<i>`, `<a>`a mnoho dalších. Aspose.PDF for .NET podporuje širokou škálu prvků a stylů HTML, které můžete použít k formátování obsahu v buňkách tabulky.

#### Otázka: Mohu použít styly CSS na obsah HTML uvnitř buněk tabulky?

Odpověď: Ano, styly CSS můžete použít na obsah HTML uvnitř buněk tabulky. Aspose.PDF for .NET poskytuje podporu pro základní styly CSS, které lze použít na prvky HTML.

#### Otázka: Je možné přidat obrázky spolu s obsahem HTML do buněk tabulky?

 Odpověď: Ano, do buněk tabulky můžete přidat obrázky spolu s obsahem HTML. Můžete použít HTML`<img>` tagy pro zahrnutí obrázků z různých zdrojů, jako jsou místní soubory nebo adresy URL.

#### Otázka: Jak mohu zadat různé šířky sloupců pro tabulku?

 Odpověď: Můžete zadat různé šířky sloupců pro tabulku pomocí`ColumnWidths` vlastnost stolu. Vlastnost přebírá řetězec obsahující hodnoty oddělené mezerami, kde každá hodnota představuje šířku sloupce v bodech.

#### Otázka: Mohu použít vnořené tabulky uvnitř buňky s obsahem HTML?

Odpověď: Ano, v buňce s obsahem HTML můžete použít vnořené tabulky. Můžete vytvořit samostatné instance tabulky a přidat je jako součást obsahu HTML do buňky, abyste dosáhli efektu vnoření.