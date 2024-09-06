---
title: Odebrat veškerý text v souboru PDF
linktitle: Odebrat veškerý text v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak odstranit veškerý text v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 280
url: /cs/net/programming-with-text/remove-all-text/
---
V tomto tutoriálu vysvětlíme, jak odstranit veškerý text v souboru PDF pomocí knihovny Aspose.PDF pro .NET. Projdeme si krok za krokem proces otevření PDF, výběr a odstranění textu z každé stránky a uložení upraveného PDF pomocí poskytnutého zdrojového kódu C#.

## Požadavky

Než začnete, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.PDF for .NET.
- Základní znalost programování v C#.

## Krok 1: Nastavte adresář dokumentů

 Nejprve musíte nastavit cestu k adresáři, kde jsou umístěny vaše soubory PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k souborům PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument PDF

 Dále otevřeme dokument PDF pomocí`Document` třídy z knihovny Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Krok 3: Odstraňte text z každé stránky

 Procházíme všechny stránky dokumentu PDF a používáme an`OperatorSelector` pro výběr veškerého textu na každé stránce. Poté vybraný text smažeme.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Krok 4: Uložte upravený PDF

Nakonec upravený PDF dokument uložíme do zadaného výstupního souboru.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Ukázkový zdrojový kód pro Remove All Text using Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Procházejte všechny stránky dokumentu PDF
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Vyberte veškerý text na stránce
	page.Contents.Accept(operatorSelector);
	// Smazat veškerý text
	page.Contents.Delete(operatorSelector.Selected);
}
// Uložte dokument
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Závěr

tomto tutoriálu jste se naučili, jak odstranit veškerý text z dokumentu PDF pomocí knihovny Aspose.PDF pro .NET. Podle podrobného průvodce a provedením poskytnutého kódu C# můžete otevřít PDF, vybrat a odstranit text z každé stránky a uložit upravený PDF.

### FAQ

#### Otázka: Jaký je účel výukového programu "Odebrat veškerý text ze souboru PDF"?

Odpověď: Výukový program "Odstranit veškerý text ze souboru PDF" má za cíl demonstrovat, jak používat knihovnu Aspose.PDF pro .NET k odstranění veškerého textu z dokumentu PDF. Výukový program poskytuje podrobného průvodce a zdrojový kód C#, který vám pomůže otevřít dokument PDF, vybrat a odstranit text z každé stránky a uložit upravený PDF.

#### Otázka: Proč bych měl chtít odstranit veškerý text z dokumentu PDF?

Odpověď: Existují různé scénáře, kdy může být užitečné odstranit veškerý text z dokumentu PDF. Můžete například chtít vytvořit redigovanou verzi dokumentu odstraněním citlivých informací nebo možná budete muset vygenerovat vizuální reprezentaci dokumentu bez jeho textového obsahu.

#### Otázka: Jak nastavím adresář dokumentů?

A: Chcete-li nastavit adresář dokumentů:

1.  Nahradit`"YOUR DOCUMENT DIRECTORY"` v`dataDir` proměnnou s cestou k adresáři, kde jsou umístěny vaše soubory PDF.

#### Otázka: Jak odstraním text z každé stránky dokumentu PDF?

 Odpověď: Výukový program vás provede procesem procházení všemi stránkami dokumentu PDF, výběrem veškerého textu na každé stránce pomocí`OperatorSelector`a poté smazáním vybraného textu.

#### Otázka: Mohu selektivně odstranit text z konkrétních stránek?

Odpověď: Ano, můžete upravit smyčku pro selektivní odstranění textu z konkrétních stránek zadáním čísel stránek, které chcete zpracovat. Příklad uvedený ve výukovém programu ukazuje, jak procházet všemi stránkami, ale můžete jej upravit tak, aby vyhovoval vašim požadavkům.

#### Otázka: Jak uložím upravený dokument PDF?

 Odpověď: Po odstranění textu z každé stránky můžete upravený dokument PDF uložit pomocí`Save` metoda`Document`třída. Zadejte požadovanou cestu k výstupnímu souboru a zadejte požadovaný formát uložení jako argumenty`Save` metoda.

#### Otázka: Jaký je očekávaný výstup tohoto tutoriálu?

Odpověď: Podle návodu a provedení poskytnutého kódu C# vygenerujete upravený dokument PDF, ze kterého byl odstraněn veškerý text na každé stránce.

#### Otázka: Mohu použít různé operátory k odstranění jiných typů obsahu?

Odpověď: Ano, můžete použít různé operátory k cílení a odstranění různých typů obsahu z dokumentu PDF, jako jsou obrázky nebo grafické prvky. Příklad uvedený v tutoriálu se konkrétně zaměřuje na odstranění textu.

#### Otázka: Je pro tento výukový program vyžadována platná licence Aspose?

Odpověď: Ano, pro správné fungování tohoto kurzu je vyžadována platná licence Aspose. Na webu Aspose si můžete zakoupit plnou licenci nebo získat 30denní dočasnou licenci.