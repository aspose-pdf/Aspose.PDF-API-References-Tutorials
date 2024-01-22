---
title: Vodorovně a svisle Přepínače
linktitle: Vodorovně a svisle Přepínače
second_title: Aspose.PDF pro .NET API Reference
description: Snadno vytvářejte horizontální a vertikální přepínače v dokumentech PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 180
url: /cs/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
V tomto tutoriálu vám ukážeme, jak vytvořit vodorovně a svisle uspořádaná přepínací tlačítka v dokumentu PDF pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vložte dokument

Načíst existující dokument PDF:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Krok 3: Přizpůsobte možnosti přepínače

Přizpůsobte možnosti přepínače nastavením následujících vlastností:

```csharp
formEditor. RadioGap = 4; // Vzdálenost mezi dvěma možnostmi přepínače
formEditor. RadioHoriz = true; //Horizontální rozložení přepínačů
formEditor.RadioButtonItemSize = 20; // Velikost přepínacích tlačítek
formEditor.Facade.BorderWidth = 1; // Šířka okraje přepínače
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Barva ohraničení přepínače
```

## Krok 4: Přidejte horizontální přepínače

Přidejte přepínače uspořádané vodorovně zadáním možností a polohy pole:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Krok 5: Přidejte vertikální přepínače

Přidejte přepínače uspořádané svisle zadáním možností a polohy pole:

```csharp
formEditor. RadioHoriz = false; // Vertikální rozložení přepínačů
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Krok 6: Uložte dokument

Uložte upravený dokument PDF:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Ukázkový zdrojový kód pro vodorovně a svisle přepínače pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Vložte dříve uložený dokument
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap je vzdálenost mezi dvěma možnostmi přepínače.
	formEditor.RadioGap = 4;
	// Přidat horizontální přepínač
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize pokud velikost položky přepínače.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Přidat další přepínač umístěný svisle
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Uložte dokument PDF
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit vodorovně a svisle uspořádaná přepínací tlačítka v dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí těchto kroků můžete snadno přizpůsobit rozvržení přepínačů a přidat je do dokumentů PDF pomocí Aspose.PDF.

### FAQ

#### Otázka: Co jsou vodorovně a svisle uspořádané přepínače v dokumentu PDF?

Odpověď: Vodorovně a svisle uspořádané přepínače v dokumentu PDF odkazují na orientaci rozvržení voleb přepínačů. Horizontální rozložení umístí možnosti přepínače vedle sebe, což uživatelům umožňuje provádět výběr zleva doprava. Vertikální rozvržení na druhé straně naskládá možnosti přepínačů na sebe, což uživatelům umožňuje provádět výběr shora dolů.

#### Otázka: Jak přizpůsobím vzhled možností přepínače v Aspose.PDF pro .NET?

Odpověď: Vzhled možností přepínače v Aspose.PDF pro .NET můžete upravit úpravou několika vlastností. Rozhraní API poskytuje možnosti pro nastavení vzdálenosti mezi dvěma možnostmi přepínače (`RadioGap`), orientaci rozvržení (`RadioHoriz`), velikost položek přepínače (`RadioButtonItemSize`), šířku a barvu ohraničení přepínačů a další.

#### Otázka: Mohu přidat horizontální i vertikální přepínače do stejného dokumentu PDF?

Odpověď: Ano, do stejného dokumentu PDF můžete přidat horizontální i vertikální přepínače pomocí Aspose.PDF pro .NET. Ukázkový zdrojový kód poskytnutý ve výukovém programu ukazuje, jak nejprve přidat přepínače uspořádané vodorovně a poté přidat další sadu přepínačů uspořádaných svisle do stejného dokumentu PDF.

#### Otázka: Mohu nastavit různé možnosti přepínačů pro každou skupinu přepínačů?

 Odpověď: Ano, pro každou skupinu přepínačů můžete nastavit různé možnosti přepínačů. Každá skupina by měla mít něco jedinečného`RadioButtonField` objekt a`RadioButtonOptionField` objekty v každé skupině by měly sdílet stejnou stránku a jedinečné názvy svých možností. Tím je zajištěno, že přepínače v každé skupině fungují správně a výběry se vzájemně vylučují.

#### Otázka: Jsou nastavení rozvržení a vzhledu přepínačů podporována ve všech prohlížečích a aplikacích PDF?

Odpověď: Ano, nastavení rozvržení a vzhledu přepínačů je podporováno ve všech prohlížečích a aplikacích PDF vyhovujících standardu. Specifikace PDF definuje přepínače a jejich různé atributy, díky čemuž jsou ve formátu PDF všeobecně uznávané. Je však nezbytné otestovat vzhled a chování přepínačů v různých prohlížečích PDF, abyste zajistili konzistentní vykreslování na různých platformách.