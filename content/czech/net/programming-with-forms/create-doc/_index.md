---
title: Vytvořit dokument
linktitle: Vytvořit dokument
second_title: Aspose.PDF pro .NET API Reference
description: Snadno vytvořte dokument pomocí přepínačů pomocí Aspose.PDF pro .NET.
type: docs
weight: 40
url: /cs/net/programming-with-forms/create-doc/
---
V tomto tutoriálu vám ukážeme, jak vytvořit dokument s přepínači pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

##Krok 1: Příprava

Nejprve se ujistěte, že jste naimportovali potřebné knihovny a nastavili cestu k adresáři dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte nový dokument

Vytvořte nový objekt dokumentu pro uložení dokumentu PDF:

```csharp
Document doc = new Document();
```

## Krok 3: Přidejte stránku

Přidejte do dokumentu novou stránku:

```csharp
Page page = doc.Pages.Add();
```

## Krok 4: Přidejte pole s přepínačem

Vytvořte pole přepínače a nastavte jeho polohu a velikost:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Krok 5: Přidejte možnosti přepínače

Přidejte požadované možnosti do pole přepínače. Podle potřeby můžete nastavit souřadnice a velikost každé možnosti:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Krok 6: Přidejte do formuláře pole přepínače

Přidejte pole přepínače do kolekce Pole formuláře dokumentu:

```csharp
doc.Form.Add(field);
```

## Krok 7: Uložte dokument

Uložte dokument PDF:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Ukázka zdrojového kódu pro Create Doc pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Vytvořte nový dokument
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Přidat pole přepínače
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Přidat možnosti přepínače. Vezměte prosím na vědomí, že tyto možnosti jsou umístěny
	// Ani horizontálně, ani vertikálně.
	// Můžete jim zkusit nastavit libovolné souřadnice (a dokonce i velikost).
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Uložte dokument PDF
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit dokument s přepínači pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno přidat přepínače do dokumentů PDF pomocí Aspose.PDF.

### FAQ

#### Otázka: Mohu upravit vzhled přepínačů v dokumentu pomocí Aspose.PDF pro .NET?

Odpověď: Ano, vzhled přepínačů v dokumentu můžete upravit pomocí Aspose.PDF pro .NET. Můžete nastavit vlastnosti, jako je velikost, barva, styl ohraničení a další, abyste přizpůsobili vzhled přepínačů.

#### Otázka: Jak mohu přidat skupiny přepínačů se vzájemně se vylučujícími možnostmi?

Odpověď: Chcete-li vytvořit vzájemně se vylučující možnosti, můžete přidat více polí přepínacích tlačítek se stejným názvem. Tím zajistíte, že když je vybrána jedna možnost, ostatní možnosti se stejným názvem budou automaticky zrušeny.

#### Otázka: Je možné nastavit výchozí vybranou možnost pro přepínače?

Odpověď: Ano, můžete nastavit výchozí vybranou možnost pro přepínače pomocí Aspose.PDF pro .NET. Můžete použít`Selected` vlastnictvím`RadioButtonOptionField` objekt pro označení možnosti jako výchozího vybraného.

#### Otázka: Mohu k přepínačům přidat obslužné rutiny událostí?

 Odpověď: Ano, můžete přidat obslužné rutiny událostí do přepínačů pomocí Aspose.PDF pro .NET. Můžete přidružit akce JavaScriptu, jako např`OnValueChanged`, na přepínače pro provedení konkrétních akcí, když uživatel vybere možnost.

#### Otázka: Jak mohu získat vybranou možnost ze skupiny přepínačů poté, co uživatel provede výběr?

 Odpověď: Vybranou možnost můžete načíst ze skupiny přepínačů pomocí Aspose.PDF pro .NET. Poté, co uživatel provede výběr, můžete získat přístup k`Selected` vlastnictvím`RadioButtonOptionField` objekt pro kontrolu, která možnost je vybrána.