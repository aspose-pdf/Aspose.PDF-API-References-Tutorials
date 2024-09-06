---
title: Combo Box
linktitle: Combo Box
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF for .NET můžete ve svých dokumentech PDF snadno vytvářet seznam se seznamem.
type: docs
weight: 30
url: /cs/net/programming-with-forms/combo-box/
---
V tomto tutoriálu vám ukážeme, jak vytvořit seznam se seznamem pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Nejprve se ujistěte, že jste naimportovali potřebné knihovny a nastavili cestu k adresáři dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte objekt dokumentu

Vytvořte objekt dokumentu pro uložení formuláře PDF:

```csharp
Document doc = new Document();
```

## Krok 3: Přidejte stránku

Přidejte do dokumentu stránku:

```csharp
doc.Pages.Add();
```

## Krok 4: Vytvořte instanci objektu ComboBoxField

Vytvořte instanci objektu ComboBoxField s požadovanými rozměry:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Krok 5: Přidejte možnosti do rozevíracího seznamu

Přidejte požadované možnosti do rozevíracího seznamu:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Krok 6: Přidejte seznam pole se seznamem do formuláře

Přidejte objekt ComboBoxField do kolekce Pole formuláře dokumentu:

```csharp
doc.Form.Add(combo);
```

## Krok 7: Uložte dokument

Uložte dokument PDF:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Ukázkový zdrojový kód pro Combo Box pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Vytvořit objekt dokumentu
	Document doc = new Document();
	// Přidat stránku k objektu dokumentu
	doc.Pages.Add();
	// Vytvořit objekt ComboBox Field
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Přidat možnost do ComboBoxu
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Přidejte objekt pole se seznamem do kolekce polí formuláře objektu dokumentu
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Uložte dokument PDF
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit seznam se seznamem pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno přidat seznam polí se seznamem do dokumentů PDF pomocí Aspose.PDF.

### FAQ

#### Otázka: Mohu upravit vzhled seznamu se seznamem pomocí Aspose.PDF pro .NET?

Odpověď: Ano, vzhled seznamu se seznamem můžete upravit pomocí Aspose.PDF pro .NET. Můžete nastavit vlastnosti, jako je velikost písma, barva, barva pozadí, styl ohraničení a další, aby odpovídaly požadovanému vzhledu a dojmu.

#### Otázka: Mohu nastavit výchozí vybrané možnosti v seznamu se seznamem?

 Odpověď: Ano, můžete nastavit výchozí vybrané možnosti v seznamu pomocí Aspose.PDF pro .NET. Můžete použít`Selected` majetek z`ComboBoxField` objekt pro označení jedné nebo více možností jako standardně vybraných.

#### Otázka: Jak mohu získat vybranou hodnotu ze seznamu, když uživatel provede výběr?

 Odpověď: Vybranou hodnotu můžete získat ze seznamu pomocí Aspose.PDF pro .NET. Poté, co uživatel provede výběr, můžete získat přístup k`Value` majetek z`ComboBoxField`objekt k získání vybrané hodnoty.

#### Otázka: Je možné přidat obslužné rutiny událostí nebo akce do seznamu pole se seznamem?

 Odpověď: Ano, Aspose.PDF pro .NET vám umožňuje přidávat obslužné rutiny událostí nebo akce do seznamu se seznamem. Můžete přidružit akce JavaScriptu, jako např`OnValueChanged`, do seznamu pole se seznamem pro provedení konkrétních akcí, když uživatel vybere možnost.

#### Otázka: Mohu přidat nápovědu nebo popis k možnostem v seznamu pole se seznamem?

 Odpověď: Ano, pomocí Aspose.PDF pro .NET můžete k možnostem v seznamu se seznamem přidat popisky nebo popisy. Můžete nastavit`AlternateName` vlastnosti každé možnosti poskytující nápovědu nebo popis, který se zobrazí, když uživatel najede myší na možnost.