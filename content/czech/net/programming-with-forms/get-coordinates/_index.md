---
title: Získejte souřadnice pole formuláře PDF
linktitle: Získejte souřadnice pole formuláře PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno získejte souřadnice pole formuláře PDF ve svých dokumentech PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 120
url: /cs/net/programming-with-forms/get-coordinates/
---
V tomto tutoriálu vám ukážeme, jak získat souřadnice pole formuláře PDF pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vložte výstupní dokument

Načtěte výstupní PDF dokument:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Krok 3: Najděte přidaná pole

Najděte přidaná pole formuláře (v tomto příkladu používáme pole "Položka1", "Položka2" a "Položka3"):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Krok 4: Zobrazte pozice podpoložek pro každé pole

Procházejte možnosti pro každé pole a zobrazte souřadnice pro každou podpoložku:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Ukázkový zdrojový kód pro Get Coordinates pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Vložte výstupní dokument
	Document doc1 = new Document( dataDir + "input.pdf");
	// Najděte přidaná pole
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// A zobrazit pozice dílčích položek pro každou z nich.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak získat souřadnice pole formuláře pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno získat souřadnice dílčích prvků polí formuláře ve vašich dokumentech PDF pomocí Aspose.PDF.

### FAQ

#### Otázka: Mohu použít tuto metodu k získání souřadnic pro jakýkoli typ pole formuláře v Aspose.PDF pro .NET?

Odpověď: Ano, tuto metodu můžete použít k získání souřadnic pro různé typy polí formuláře v Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje, jak získat souřadnice pro pole RadioButton, ale stejný přístup můžete upravit pro jiné typy polí formuláře, jako je TextBox, CheckBox, ListBox a další.

#### Otázka: Jak mohu upravit nebo upravit souřadnice pole formuláře?

Odpověď: Souřadnice pole formuláře jsou založeny na souřadnicovém systému dokumentu PDF, kde je počátek (0,0) umístěn v levém dolním rohu stránky. Chcete-li upravit nebo upravit souřadnice pole formuláře, můžete aktualizovat`Rect` vlastnost příslušného pole formuláře nebo jeho podpoložek, jako je RadioButtonOptionField.

#### Otázka: Mohu získat souřadnice polí formuláře přidané programově do dokumentu PDF?

Odpověď: Ano, můžete získat souřadnice polí formuláře, která byla programově přidána do dokumentu PDF. Aspose.PDF for .NET vám umožňuje dynamicky přidávat pole formuláře a po přidání můžete načíst jejich souřadnice pomocí přístupu popsaného v tomto tutoriálu.

#### Otázka: Jaký je účel načítání souřadnic pole formuláře?

Odpověď: Načtení souřadnic polí formuláře může být užitečné, když potřebujete provést specifické operace související s rozvržením nebo ověření polí formuláře v dokumentu PDF. Umožňuje vám přesně umístit a zarovnat pole formuláře na základě jejich souřadnic, čímž zajistíte, že se v dokumentu zobrazí správně a zajistí bezproblémovou uživatelskou zkušenost.

#### Otázka: Jsou souřadnice pole formuláře vyjádřeny v bodech nebo v jiných jednotkách?

A: Souřadnice pole formuláře v Aspose.PDF pro .NET jsou vyjádřeny v bodech. Jeden bod odpovídá 1/72 palce, což z něj činí standardní měrnou jednotku ve formátu PDF.