---
title: Vložit konec stránky do souboru PDF
linktitle: Vložit konec stránky do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vložit konec stránky do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 110
url: /cs/net/programming-with-tables/insert-page-break/
---
V tomto tutoriálu se naučíme, jak vložit konec stránky do souboru PDF pomocí Aspose.PDF for .NET. Vysvětlíme si zdrojový kód v C# krok za krokem. Na konci tohoto tutoriálu budete vědět, jak přidat konec stránky po určitém počtu řádků v tabulce dokumentu PDF. Začněme!

## Krok 1: Nastavení prostředí
Ujistěte se, že jste své vývojové prostředí C# nakonfigurovali pomocí Aspose.PDF pro .NET. Přidejte odkaz do knihovny a importujte potřebné jmenné prostory.

## Krok 2: Vytvoření dokumentu a tabulky
Vytvoříme novou instanci dokumentu a přidáme do tohoto dokumentu stránku. Dále vytvoříme instanci tabulky, která bude reprezentovat naši tabulku v dokumentu PDF. Definujeme také styly ohraničení tabulky.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## Krok 3: Přidejte řádky do tabulky
Pomocí smyčky přidáme do pole 200 řádků. Pro každý řádek vytvoříme instanci Row a přidáme dvě buňky s textovým obsahem.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // Po přidání 10 řádků vložíme nový konec stránky
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## Krok 4: Přidání tabulky do dokumentu
Tabulku přidáme do kolekce odstavců na stránce dokumentu.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## Krok 5: Uložte dokument
PDF dokument uložíme s vloženým koncem stránky.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Příklad zdrojového kódu pro Insert Page Break pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancia dokumentu instance
Document doc = new Document();
// Přidat stránku do kolekce stránek souboru PDF
doc.Pages.Add();
// Vytvořte instanci tabulky
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Nastavte styl ohraničení tabulky
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Nastavte výchozí styl ohraničení pro tabulku s barvou ohraničení jako červená
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Zadejte šířku sloupců tabulky
tab.ColumnWidths = "100 100";
// Vytvořte smyčku pro přidání 200 řádků pro tabulku
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// Když je přidáno 10 řádků, vykreslí se nový řádek na nové stránce
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Přidejte tabulku do kolekce odstavců souboru PDF
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Uložte dokument PDF
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vložit konec stránky do dokumentu PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce můžete použít k přidání konce stránky za určitý počet řádků v tabulce v dokumentu PDF pomocí jazyka C#.

### Časté dotazy pro vložení konce stránky do souboru PDF

#### Otázka: Jak mohu změnit velikost stránky pro nové stránky vytvořené po přerušení stránky?

 A: Chcete-li změnit velikost stránky pro nové stránky vytvořené po zalomení stránky, můžete nastavit`PageSize` vlastnictví`Page` objekt. Můžete například použít následující kód k nastavení velikosti stránky na A4:

```csharp
// Nastavte velikost stránky na A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Otázka: Mohu ovládat okraje stránek pro nové stránky po přerušení stránky?

 Odpověď: Ano, můžete ovládat okraje stránek pro nové stránky po zalomení stránky. Použijte`Margin` vlastnictví`Page` objekt pro nastavení okrajů stránky. Chcete-li například nastavit všechny okraje na 10 bodů, můžete použít následující kód:

```csharp
// Nastavte všechny okraje na 10 bodů
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Otázka: Je možné přidat záhlaví a zápatí na nové stránky po přerušení stránky?

 Odpověď: Ano, po zalomení stránky můžete na nové stránky přidat záhlaví a zápatí. Použijte`Page.Header` a`Page.Footer` vlastnosti pro přidání obsahu do záhlaví a zápatí stránky. Například:

```csharp
// Přidejte záhlaví na nové stránky
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Přidejte zápatí na nové stránky
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### Otázka: Mohu vložit konce stránek na určitá místa mimo určitý počet řádků?

 Odpověď: Ano, konce stránek můžete vkládat na určitá místa i jinde než po určitém počtu řádků. Můžete nastavit`IsInNewPage` vlastnost řady k`true` vynutit, aby tabulka začala novou stránku po tomto řádku.

#### Otázka: Jak mohu upravit chování zalomení stránky na základě výšky obsahu?

 A: Můžete použít`IsBroken` vlastnost tabulky pro povolení nebo zakázání automatického zalamování řádků mezi stránkami. Při nastavení na`true`umožňuje rozdělit řádky na stránky na základě výšky obsahu.