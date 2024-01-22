---
title: Přesunout pole formuláře
linktitle: Přesunout pole formuláře
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF for .NET můžete snadno přesouvat pole formuláře v dokumentech PDF.
type: docs
weight: 200
url: /cs/net/programming-with-forms/move-form-field/
---
V tomto tutoriálu vám ukážeme, jak přesunout pole formuláře v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vložte dokument

Načíst existující dokument PDF:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## Krok 3: Získejte pole formuláře

Získejte pole formuláře, které chcete přesunout:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Krok 4: Změňte umístění pole

Změňte umístění pole formuláře definováním nové obdélníkové oblasti:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## Krok 5: Uložte upravený dokument

Uložte upravený dokument PDF:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro Přesunout pole formuláře pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Získejte pole
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Upravte umístění pole
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Uložte upravený dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přesunout pole formuláře v dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí těchto kroků můžete snadno přejít na konkrétní pole a podle potřeby změnit jeho umístění.


### FAQ

#### Otázka: Mohu přesouvat více polí formuláře v rámci jednoho dokumentu PDF pomocí Aspose.PDF for .NET?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete přesunout více polí formuláře v rámci jednoho dokumentu PDF. Jednoduše opakujte proces pro každé pole formuláře, které chcete přemístit.

#### Otázka: Ovlivní přesunutí pole formuláře jeho přidružená data nebo funkce?

Odpověď: Ne, přesunutí pole formuláře neovlivní související data nebo funkce. Pole formuláře si po přesunutí do nového umístění zachová všechny své vlastnosti a hodnoty.

#### Otázka: Jak mohu určit přesné souřadnice pro nové umístění pole formuláře?

 Odpověď: Nové umístění můžete určit pomocí`Aspose.Pdf.Rectangle` třídy, kde definujete souřadnice X a Y levého horního rohu a souřadnice X a Y pravého dolního rohu obdélníkové oblasti.

#### Otázka: Je Aspose.PDF for .NET kompatibilní s prostředím Windows i Linux?

Odpověď: Ano, Aspose.PDF for .NET je kompatibilní s prostředím Windows i Linux a poskytuje vývojářům flexibilitu při práci v preferovaných operačních systémech.