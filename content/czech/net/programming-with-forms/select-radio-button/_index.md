---
title: Vyberte přepínač v dokumentu PDF
linktitle: Vyberte přepínač v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vybrat přepínač v dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 250
url: /cs/net/programming-with-forms/select-radio-button/
---
Zde je podrobný návod, jak vybrat přepínač pomocí Aspose.PDF pro .NET. Postupujte takto:

##  Krok 1: Začněte definováním adresáře vašich dokumentů zadáním cesty v`dataDir` variable.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  Krok 2: Otevřete dokument PDF pomocí`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## Krok 3: Získejte pole přepínače z formuláře dokumentu.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## Krok 4: Zadejte index přepínače, který chcete vybrat ze skupiny.

```csharp
radioField. Selected = 2;
```

## Krok 5: Nastavte výstupní cestu pro upravený soubor PDF.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## Krok 6: Uložte upravený soubor PDF.

```csharp
pdfDocument.Save(dataDir);
```

## Krok 7: Zobrazte potvrzovací zprávu a umístění uloženého souboru.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Ukázkový zdrojový kód pro Select Radio Button pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Otevřete dokument
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Získejte pole
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Zadejte index přepínacího tlačítka ze skupiny
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Uložte soubor PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak vybrat přepínač pomocí Aspose.PDF pro .NET. Podle výše uvedených kroků můžete manipulovat a upravovat přepínače v dokumentech PDF pomocí Aspose.PDF for .NET.


### FAQ

#### Otázka: Mohu vybrat více přepínačů ve skupině pomocí Aspose.PDF pro .NET?

Odpověď: Ne, přepínače ve skupině jsou navrženy tak, aby se vzájemně vylučovaly. V rámci skupiny můžete vybrat vždy pouze jeden přepínač a jeho výběrem automaticky zrušíte výběr jakéhokoli dříve vybraného přepínače ve stejné skupině.

#### Otázka: Jak získám vybraný přepínač ve skupině pomocí Aspose.PDF pro .NET?

 A: Chcete-li načíst vybraný přepínač ve skupině, můžete použít`Selected` majetek z`RadioButtonField` třída. Vrátí index vybraného přepínače ve skupině.

#### Otázka: Mohu upravit vzhled vybraného přepínače v dokumentu PDF?

Odpověď: Ano, vzhled vybraného přepínače můžete upravit pomocí Aspose.PDF pro .NET. Můžete upravit jeho barvu, velikost, styl ohraničení a další vizuální atributy tak, aby odpovídaly požadovanému vzhledu.

#### Otázka: Je možné vytvořit nové skupiny přepínačů programově pomocí Aspose.PDF pro .NET?

Odpověď: Ano, můžete vytvořit nové skupiny přepínačů programově pomocí Aspose.PDF pro .NET. Do formuláře dokumentu můžete přidat nové přepínače a zadat stejný název skupiny pro každý přepínač, abyste vytvořili novou skupinu.

#### Otázka: Podporuje Aspose.PDF for .NET práci s interaktivními formuláři PDF?

Odpověď: Ano, Aspose.PDF for .NET plně podporuje práci s interaktivními formuláři PDF, včetně přepínačů, textových polí, zaškrtávacích políček a dalších prvků formuláře. Pomocí knihovny můžete snadno číst, upravovat a vytvářet interaktivní formuláře PDF.