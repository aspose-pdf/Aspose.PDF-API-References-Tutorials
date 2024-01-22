---
title: Sloučit formuláře v dokumentu PDF
linktitle: Sloučit formuláře v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Formuláře v dokumentu PDF můžete snadno sloučit pomocí Aspose.PDF pro .NET.
type: docs
weight: 100
url: /cs/net/programming-with-forms/flatten-forms/
---
V tomto tutoriálu vám ukážeme, jak sloučit formuláře pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Nejprve se ujistěte, že jste naimportovali potřebné knihovny a nastavili cestu k adresáři dokumentů:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte zdrojový formulář PDF

Načtěte zdrojový formulář PDF:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 3: Vyrovnejte formuláře

Nejprve zkontrolujte, zda jsou v dokumentu nějaká pole formuláře. Pokud ano, iterujte každé pole a použijte zploštění:

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Krok 4: Uložte aktualizovaný dokument

Uložte aktualizovaný dokument PDF:

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Ukázkový zdrojový kód pro Flatten Forms pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načíst zdrojový formulář PDF
Document doc = new Document(dataDir + "input.pdf");
// Zploštěné formuláře
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Uložte aktualizovaný dokument
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak sloučit formuláře pomocí Aspose.PDF pro .NET. Pomocí těchto kroků můžete snadno sloučit formuláře v dokumentech PDF, takže pole nebudou upravitelná a sloučíte anotace s obsahem dokumentu.

### FAQ

#### Otázka: Co znamená "zploštění formulářů" v Aspose.PDF pro .NET?

Odpověď: Sloučení formulářů v Aspose.PDF pro .NET se týká procesu, kdy pole formuláře v dokumentu PDF nebudou upravitelná a sloučení anotací (jako jsou pole formuláře, anotace a digitální podpisy) s obsahem dokumentu. Jakmile jsou formuláře sloučeny, uživatelé nemohou upravovat pole formuláře a vizuální vzhled polí formuláře se stává součástí statického obsahu dokumentu PDF.

#### Otázka: Mohu obrátit proces sloučení a znovu upravit pole formuláře?

Odpověď: Ne, jakmile jsou pole formuláře sloučena, proces je nevratný pomocí Aspose.PDF pro .NET. Sloučení trvale sloučí vzhled polí formuláře s obsahem PDF a jednotlivé prvky polí formuláře již nebudou přístupné ani upravitelné.

#### Otázka: Kdy mám sloučit formuláře v dokumentu PDF?

Odpověď: Sloučení formulářů je užitečné, když chcete zachovat vizuální vzhled polí formuláře a anotací v dokumentu PDF a zároveň zabránit uživatelům v úpravách dat. To se běžně provádí, když chcete sdílet dokument PDF s předem vyplněnými daty formuláře nebo anotacemi, které by příjemci neměli měnit.

#### Otázka: Ovlivní sloučení formulářů další anotace, jako jsou digitální podpisy?

Odpověď: Ano, sloučení formulářů sloučí všechny anotace, včetně digitálních podpisů, s obsahem PDF. Jakmile jsou formuláře sloučeny, všechny existující digitální podpisy se stanou trvalou součástí dokumentu a uživatelé je nemohou upravovat ani odstraňovat.

#### Otázka: Mohu selektivně sloučit konkrétní pole formuláře a nechat ostatní upravitelná?

Odpověď: Ano, můžete selektivně sloučit konkrétní pole formuláře v dokumentu PDF a ostatní ponechat upravitelná. Namísto použití kódu ke sloučení všech polí formuláře se můžete rozhodnout sloučit pouze požadovaná pole formuláře na základě jejich názvů nebo jiných kritérií.