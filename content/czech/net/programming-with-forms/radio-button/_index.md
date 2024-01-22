---
title: Přepínač
linktitle: Přepínač
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF pro .NET můžete do dokumentů PDF snadno přidat přepínače.
type: docs
weight: 220
url: /cs/net/programming-with-forms/radio-button/
---
V tomto tutoriálu vám ukážeme, jak přidat přepínač do dokumentu PDF pomocí Aspose.PDF pro .NET. Vysvětlíme vám zdrojový kód C# krok za krokem, který vás provede tímto procesem.

## Krok 1: Příprava

Ujistěte se, že jste importovali potřebné knihovny a nastavili cestu k adresáři vašich dokumentů:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvořte instanci objektu dokumentu

Vytvořte instanci objektu dokumentu pro vytvoření nového dokumentu PDF:

```csharp
Document pdfDocument = new Document();
```

## Krok 3: Přidejte stránku

Přidejte stránku do dokumentu PDF:

```csharp
pdfDocument.Pages.Add();
```

## Krok 4: Vytvořte instanci objektu RadioButtonField

Vytvořte instanci objektu RadioButtonField s uvedením čísla stránky jako argumentu:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Krok 5: Přidejte možnosti přepínače

Přidejte možnosti přepínače do objektu RadioButtonField zadáním souřadnic každé možnosti pomocí objektu Rectangle:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## Krok 6: Přidejte přepínač do formuláře

Přidejte přepínač do objektu Form dokumentu:

```csharp
pdfDocument.Form.Add(radio);
```

## Krok 7: Uložte dokument PDF

Uložte vytvořený dokument PDF:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro Radio Button pomocí Aspose.PDF pro .NET 
```csharp
try
{
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Objekt okamžitého dokumentu
	Document pdfDocument = new Document();
	// Přidejte stránku do souboru PDF
	pdfDocument.Pages.Add();
	// Vytvořte objekt RadioButtonField s číslem stránky jako argumentem
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Přidejte první možnost přepínače a také určete jeho počátek pomocí objektu Rectangle
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Přidat druhou možnost přepínače
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Přidat přepínač k vytvoření objektu objektu dokumentu
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Uložte soubor PDF
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak přidat přepínač do dokumentu PDF pomocí Aspose.PDF pro .NET. Podle těchto kroků můžete snadno vytvořit přepínač a umístit jej na konkrétní stránku v dokumentu PDF.


### FAQ

#### Otázka: Mohu upravit vzhled přepínače, jako je jeho velikost a barva?

 Odpověď: Ano, vzhled přepínače si můžete přizpůsobit pomocí`Rectangle` souřadnice objektu k definování jeho velikosti a polohy. Aspose.PDF for .NET vám umožňuje upravit vzhled přepínače tak, aby vyhovoval vašim potřebám.

#### Otázka: Mohu přidat více přepínačů s různými skupinami na stejnou stránku?

Odpověď: Ano, na stejnou stránku můžete přidat více přepínačů s různými skupinami. Každá skupina přepínacích tlačítek může mít jedinečný název a v každé skupině lze vybrat vždy pouze jednu možnost.

#### Otázka: Jak mohu přidat štítek nebo textový popis k možnostem přepínače?

 A: Chcete-li přidat štítek nebo textový popis k možnostem přepínače, můžete použít`TextStamp`třídy z Aspose.PDF pro .NET k překrytí textu v dokumentu PDF na konkrétních souřadnicích.

#### Otázka: Je Aspose.PDF for .NET kompatibilní se všemi verzemi .NET Framework?

Odpověď: Ano, Aspose.PDF pro .NET je kompatibilní se všemi verzemi .NET Framework, včetně .NET Core a .NET Standard.

#### Otázka: Mohu programově ovládat výběr možnosti přepínače v dokumentu PDF?

 Odpověď: Ano, můžete programově ovládat výběr možnosti přepínače pomocí`IsSelected` vlastnictvím`RadioButtonOption` třída. Tato vlastnost umožňuje nastavit konkrétní možnost jako vybranou.