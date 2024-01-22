---
title: Upravit pole formuláře v dokumentu PDF
linktitle: Upravit pole formuláře v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno upravujte pole formuláře v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 190
url: /cs/net/programming-with-forms/modify-form-field/
---
V tomto tutoriálu vám ukážeme, jak upravit pole formuláře v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vložte dokument

Načíst existující dokument PDF:

```csharp
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
```

## Krok 3: Získejte pole formuláře

Získejte pole formuláře, které chcete upravit:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Krok 4: Změňte hodnotu pole

Změňte hodnotu pole formuláře:

```csharp
textBoxField.Value = "New Value";
```

## Krok 5: Upravte vlastnosti pole

Podle potřeby upravte další vlastnosti pole formuláře. Můžete jej například nastavit pouze pro čtení:

```csharp
textBoxField.ReadOnly = true;
```

## Krok 6: Uložte upravený dokument

Uložte upravený dokument PDF:

```csharp
dataDir = dataDir + "ModifyFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro Upravit pole formuláře pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "ModifyFormField.pdf");
// Získejte pole
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Upravit hodnotu pole
textBoxField.Value = "New Value";
textBoxField.ReadOnly = true;
dataDir = dataDir + "ModifyFormField_out.pdf";
// Uložit aktualizovaný dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field modified successfully.\nFile saved at " + dataDir);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak upravit pole formuláře v dokumentu PDF pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno přejít na konkrétní pole, změnit jeho hodnotu a upravit jeho vlastnosti podle potřeby.


### FAQ

#### Otázka: Mohu upravit více polí formuláře v rámci jednoho dokumentu PDF pomocí Aspose.PDF for .NET?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete upravit více polí formuláře v rámci jednoho dokumentu PDF. Jednoduše opakujte proces pro každé pole formuláře, které chcete upravit.

#### Otázka: Je Aspose.PDF for .NET kompatibilní se všemi verzemi .NET Framework?

Odpověď: Ano, Aspose.PDF pro .NET je kompatibilní se všemi verzemi .NET Framework, včetně .NET Core a .NET Standard.

#### Otázka: Mohu pomocí Aspose.PDF for .NET upravit jiné typy polí formuláře, jako jsou zaškrtávací políčka nebo přepínače?

Odpověď: Ano, Aspose.PDF pro .NET podporuje úpravy různých typů polí formuláře, včetně zaškrtávacích políček, přepínačů a dalších.

#### Otázka: Jak mohu přidat nová pole formuláře do dokumentu PDF pomocí Aspose.PDF pro .NET?

 Odpověď: Chcete-li do dokumentu PDF přidat nová pole formuláře, můžete použít`Form` vlastnictvím`Document` třídy pro přístup k`Field` kolekce a poté programově přidat nová pole formuláře.

#### Otázka: Podporuje Aspose.PDF pro .NET další programovací jazyky kromě C#?

Odpověď: Ano, Aspose.PDF pro .NET podporuje kromě C# různé programovací jazyky, jako je VB.NET a ASP.NET.