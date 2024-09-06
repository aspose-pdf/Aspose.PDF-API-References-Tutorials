---
title: Integrace s databází v souboru PDF
linktitle: Integrace s databází v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Vložte data z databáze do souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 120
url: /cs/net/programming-with-tables/integrate-with-database/
---
V tomto tutoriálu se naučíme, jak vložit data z databáze do souboru PDF pomocí Aspose.PDF for .NET. Vysvětlíme si zdrojový kód v C# krok za krokem. Na konci tohoto tutoriálu budete vědět, jak importovat data tabulky z databáze do dokumentu PDF. Začněme!

## Krok 1: Nastavení prostředí
Ujistěte se, že jste své vývojové prostředí C# nakonfigurovali pomocí Aspose.PDF pro .NET. Přidejte odkaz do knihovny a importujte potřebné jmenné prostory.

## Krok 2: Vytvoření DataTable
Vytvoříme instanci DataTable, která bude reprezentovat data, která chceme vložit do dokumentu PDF. V tomto příkladu vytvoříme DataTable se třemi sloupci: Employee_ID, Employee_Name a Gender. Také přidáme dva řádky do DataTable s fiktivními daty.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## Krok 3: Vytvoření dokumentu a tabulky PDF
Vytvoříme instanci dokumentu a přidáme do tohoto dokumentu stránku. Dále vytvoříme instanci tabulky, která bude reprezentovat naši tabulku v dokumentu PDF. Definujeme šířky sloupců tabulky a styly ohraničení.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## Krok 4: Import dat z DataTable do tabulky
K importu dat z DataTable do tabulky v dokumentu PDF používáme metodu ImportDataTable.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## Krok 5: Přidání tabulky do dokumentu
Tabulku přidáme do kolekce odstavců na stránce dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## Krok 6: Uložte dokument
PDF dokument uložíme s daty z vložené databáze.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Gratuluji! Nyní víte, jak vložit data databáze do dokumentu PDF pomocí Aspose.PDF pro .NET.

### Příklad zdrojového kódu pro Integrate With Database using Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// Přidejte 2 řádky do objektu DataTable programově
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Vytvořit instanci dokumentu
Document doc = new Document();
doc.Pages.Add();
// Inicializuje novou instanci tabulky
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Nastavte šířku sloupců tabulky
table.ColumnWidths = "40 100 100 100";
// Nastavte barvu okraje tabulky jako LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Nastavte ohraničení buněk tabulky
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Přidejte objekt tabulky na první stránku vstupního dokumentu
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Uložte aktualizovaný dokument obsahující objekt tabulky
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Závěr
tomto tutoriálu jsme se naučili, jak vložit data z databáze do dokumentu PDF pomocí Aspose.PDF for .NET. Pomocí tohoto podrobného průvodce můžete importovat data z vlastní databáze a zobrazit je v dokumentech PDF. Prozkoumejte dále dokumentaci Aspose.PDF a objevte další funkce a možnosti, které nabízí tato výkonná knihovna.

### Časté dotazy pro integraci s databází v souboru PDF

#### Otázka: Mohu použít Aspose.PDF pro .NET s různými typy databází, jako je MySQL, SQL Server nebo Oracle?

Odpověď: Ano, můžete použít Aspose.PDF pro .NET s různými typy databází, jako je MySQL, SQL Server, Oracle a další. Aspose.PDF for .NET poskytuje funkce pro čtení dat z různých zdrojů dat, včetně databází, souborů XML a dalších. Můžete načíst data z požadovaného typu databáze a naplnit je do DataTable nebo jakékoli jiné datové struktury kompatibilní s Aspose.PDF pro .NET.

#### Otázka: Jak mohu přizpůsobit vzhled tabulky v dokumentu PDF?

Odpověď: Vzhled tabulky v dokumentu PDF můžete přizpůsobit pomocí různých vlastností poskytovaných knihovnou Aspose.PDF for .NET. Můžete například nastavit různé styly ohraničení, barvy pozadí, styly písma a zarovnání pro tabulku a její buňky. Další podrobnosti o přizpůsobení vzhledu tabulky naleznete v dokumentaci Aspose.PDF pro .NET.

#### Otázka: Je možné k datům importovaným z databáze přidat hypertextové odkazy nebo interaktivní prvky?

Odpověď: Ano, k datům importovaným z databáze můžete přidat hypertextové odkazy nebo jiné interaktivní prvky. Aspose.PDF for .NET podporuje přidávání hypertextových odkazů, záložek a dalších interaktivních prvků do dokumentu PDF. Před importem do tabulky můžete manipulovat s obsahem v DataTable a zahrnout hypertextové odkazy nebo jiné interaktivní funkce.

#### Otázka: Mohu stránkovat tabulku, pokud překračuje určitý počet řádků?

 Odpověď: Ano, můžete stránkovat tabulku, pokud přesáhne určitý počet řádků. Chcete-li toho dosáhnout, můžete použít`IsInNewPage`vlastnost objektu Row, která označuje, že nová stránka by měla začínat po určitém řádku. Můžete vypočítat počet řádků, které se mají zobrazit na stránce, a nastavit`IsInNewPage` majetek podle toho.

#### Otázka: Jak mohu exportovat dokument PDF s vloženými daty databáze do různých formátů souborů, jako je DOCX nebo XLSX?

Odpověď: Aspose.PDF for .NET vám umožňuje převádět dokumenty PDF do různých jiných formátů souborů, včetně DOCX (Microsoft Word) a XLSX (Microsoft Excel). K dosažení tohoto cíle můžete použít knihovnu Aspose.PDF for .NET v kombinaci s dalšími knihovnami Aspose, jako jsou Aspose.Words a Aspose.Cells. Nejprve uložte dokument PDF s vloženými daty databáze a poté pomocí příslušné knihovny Aspose jej převeďte do požadovaného formátu souboru.