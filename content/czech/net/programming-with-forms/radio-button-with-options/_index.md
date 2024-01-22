---
title: Přepínač S Možnosti
linktitle: Přepínač S Možnosti
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF pro .NET můžete do dokumentu PDF snadno přidat přepínač s možnostmi.
type: docs
weight: 230
url: /cs/net/programming-with-forms/radio-button-with-options/
---

V tomto tutoriálu vám ukážeme, jak přidat přepínač s možnostmi do dokumentu PDF pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvořte instanci objektu dokumentu

Vytvořte instanci objektu dokumentu pro vytvoření nového dokumentu PDF:

```csharp
Document doc = new Document();
```

## Krok 3: Přidejte stránku a tabulku

Přidejte do dokumentu stránku a vytvořte tabulku, která bude obsahovat možnosti přepínače:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## Krok 4: Vytvořte instanci objektu RadioButtonField

Vytvořte instanci objektu RadioButtonField, který bude reprezentovat přepínač:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## Krok 5: Přidejte možnosti přepínače

Přidejte možnosti přepínače do objektu RadioButtonField:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## Krok 6: Přizpůsobte možnosti přepínače

Přizpůsobte možnosti přepínače nastavením atributů, jako je ohraničení, barva textu a text titulku:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Opakujte stejné kroky pro opt2 a opt3

```

## Krok 7: Přidejte možnosti přepínače do tabulky

Přidejte možnosti přepínače do tabulky, abyste je zobrazili:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## Krok 8: Uložte dokument PDF

Uložte vytvořený dokument PDF:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Ukázka zdrojového kódu pro Radio Button With Options pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// Uložte soubor PDF
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

gratuluji! Úspěšně jste přidali přepínač s možnostmi do dokumentu PDF pomocí Aspose.PDF pro .NET. Tuto metodu nyní můžete použít k vytváření interaktivních formulářů v dokumentech PDF.