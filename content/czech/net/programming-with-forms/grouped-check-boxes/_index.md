---
title: Seskupená zaškrtávací políčka v dokumentu PDF
linktitle: Seskupená zaškrtávací políčka v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF for .NET můžete snadno vytvářet seskupená zaškrtávací políčka v dokumentu PDF.
type: docs
weight: 170
url: /cs/net/programming-with-forms/grouped-check-boxes/
---
V tomto tutoriálu vám ukážeme, jak vytvořit seskupená zaškrtávací políčka v dokumentu PDF pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvořte instanci objektu dokumentu

Vytvořit instanci objektu dokumentu:

```csharp
Document pdfDocument = new Document();
```

## Krok 3: Přidejte stránku do dokumentu PDF

Přidejte stránku do dokumentu PDF:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Krok 4: Vytvořte instanci objektu RadioButtonField

Vytvořte instanci objektu RadioButtonField s číslem stránky jako argumentem:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Krok 5: Přidejte možnosti přepínače

Přidejte možnosti přepínače pomocí objektu RadioButtonOptionField a určete jejich polohu pomocí objektu Rectangle:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Krok 6: Přizpůsobte možnosti přepínače

Přizpůsobte možnosti přepínačů nastavením jejich stylu, ohraničení a vzhledu:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Krok 7: Přidejte přepínače do formuláře

Přidejte přepínače do objektu formuláře dokumentu:

```csharp
pdfDocument.Form.Add(radio);
```

## Krok 8: Uložte dokument

Uložte dokument PDF:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro seskupená zaškrtávací políčka pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Objekt okamžitého dokumentu
	Document pdfDocument = new Document();
	// Přidejte stránku do souboru PDF
	Page page = pdfDocument.Pages.Add();
	// Vytvořte objekt RadioButtonField s číslem stránky jako argumentem
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Přidejte první možnost přepínače a také určete jeho počátek pomocí objektu Rectangle
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Přidat přepínač k vytvoření objektu objektu dokumentu
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Uložte dokument PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak vytvořit seskupená zaškrtávací políčka v dokumentu PDF pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno přidat vlastní volby přepínačů a seskupit je do dokumentů PDF pomocí Aspose.PDF.

### FAQ

#### Otázka: Co jsou seskupená zaškrtávací políčka v dokumentu PDF?

Odpověď: Seskupená zaškrtávací políčka v dokumentu PDF odkazují na sadu voleb přepínačů, které jsou seskupeny. Přepínače umožňují uživatelům vybrat pouze jednu možnost ze skupiny vzájemně se vylučujících možností. Když je vybráno jedno přepínací tlačítko, ostatní ve stejné skupině se automaticky zruší. Toto seskupování je užitečné, když chcete uživatelům nabídnout více možností, ale omezit jejich výběr pouze na jednu možnost.

#### Otázka: Mohu upravit vzhled seskupených zaškrtávacích políček v Aspose.PDF pro .NET?

Odpověď: Ano, vzhled seskupených zaškrtávacích políček v Aspose.PDF pro .NET si můžete přizpůsobit. Rozhraní API poskytuje různé možnosti nastavení stylu, ohraničení a vzhledu možností přepínače. Můžete definovat polohu každé možnosti, vybrat si mezi různými styly rámečků (např. čtverec, kruh, kříž) a upravit vlastnosti ohraničení, abyste dosáhli požadované vizuální reprezentace.

#### Otázka: Jak přidám seskupená zaškrtávací políčka na konkrétní stránku v dokumentu PDF?

A: Chcete-li přidat seskupená zaškrtávací políčka na konkrétní stránku v dokumentu PDF, musíte vytvořit instanci a`RadioButtonField` objekt s požadovaným číslem stránky jako argumentem. Poté vytvořte`RadioButtonOptionField` objekty představující každou možnost přepínače a určete jejich polohu pomocí`Rectangle` objekt. Nakonec přidejte tyto možnosti do`RadioButtonField` a před přidáním upravte jejich vzhled podle potřeby`RadioButtonField` do formuláře dokumentu.

#### Otázka: Mohu přidat více skupin zaškrtávacích políček do jednoho dokumentu PDF?

 Odpověď: Ano, do jednoho dokumentu PDF můžete přidat více skupin zaškrtávacích políček. Každá skupina by měla mít něco jedinečného`RadioButtonField` objekt a`RadioButtonOptionField` objekty v každé skupině by měly sdílet stejnou stránku a jedinečné názvy svých možností. Tím je zajištěno, že přepínače v každé skupině fungují správně a výběry se vzájemně vylučují.

#### Otázka: Jsou seskupená zaškrtávací políčka podporována ve všech prohlížečích a aplikacích PDF?

Odpověď: Ano, seskupená zaškrtávací políčka jsou podporována ve všech prohlížečích a aplikacích PDF vyhovujících standardu. Specifikace PDF definuje přepínače a jejich chování při seskupování, díky čemuž jsou ve formátu PDF všeobecně uznávané. Je však nezbytné otestovat funkčnost v různých prohlížečích PDF, abyste zajistili konzistentní chování na různých platformách.