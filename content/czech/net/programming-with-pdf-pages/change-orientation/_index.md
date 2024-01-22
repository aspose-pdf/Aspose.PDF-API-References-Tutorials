---
title: Změnit orientaci
linktitle: Změnit orientaci
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce změnou orientace stránky PDF pomocí Aspose.PDF pro .NET. Snadné sledování a implementace do vašich projektů.
type: docs
weight: 10
url: /cs/net/programming-with-pdf-pages/change-orientation/
---
V tomto tutoriálu vás provedeme krok za krokem procesem změny orientace stránky dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak změnit orientaci stránky vašich dokumentů PDF pomocí Aspose.PDF for .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#
- Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kde se nachází váš vstupní soubor PDF a kam chcete uložit upravený výstupní soubor PDF. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Načtěte dokument PDF
 Poté můžete načíst dokument PDF ze vstupního souboru pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu k souboru PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Krok 3: Změňte orientaci stránky
Nyní projdeme každou stránku dokumentu a změníme její orientaci. Pro každou stránku upravujeme rozměry mediálního boxu (`MediaBox`) prohozením šířky a výšky pak upravíme souřadnice pole médií tak, aby byla zachována poloha stránky. Nakonec nastavíme otočení stránky na 90 stupňů.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Krok 4: Uložte upravený dokument PDF
 Nakonec můžete upravený dokument PDF uložit do výstupního souboru pomocí`Save()` metoda`Document`třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Ukázka zdrojového kódu pro změnu orientace pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Musíme posunout stránku nahoru, abychom kompenzovali měnící se velikost stránky
	// (spodní okraj stránky je 0,0 a informace jsou obvykle umístěny z
	// Začátek stránky. To je důvod, proč posouváme milenecký okraj nahoru na rozdíl mezi
	// Stará a nová výška.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Někdy také potřebujeme nastavit CropBox (pokud byl nastaven v původním souboru)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Nastavení úhlu otočení stránky
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Uložit výstupní soubor
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Závěr
V tomto tutoriálu jsme se naučili, jak změnit orientaci stránky dokumentu PDF pomocí Aspose.PDF pro .NET. Podle výše uvedených kroků můžete tuto funkci snadno implementovat do svých vlastních projektů. Neváhejte a prozkoumejte dále dokumentaci Aspose.PDF, abyste objevili další užitečné funkce pro práci se soubory PDF.

### FAQ

#### Otázka: Jaký je účel změny orientace stránky v dokumentu PDF?

Odpověď: Změna orientace stránky v dokumentu PDF umožňuje otočit obsah stránky o 90 stupňů. To může být užitečné ve scénářích, kdy je třeba původní obsah zobrazit nebo vytisknout v jiné orientaci, jako je přepnutí z režimu na výšku do režimu na šířku nebo naopak.

#### Otázka: Mohu změnit orientaci konkrétních stránek v dokumentu PDF?

 Odpověď: Ano, můžete změnit orientaci konkrétních stránek v dokumentu PDF. V poskytnutém zdrojovém kódu C# je`foreach` smyčka slouží k procházení každé stránky dokumentu a změně její orientace. Pokud chcete změnit pouze orientaci konkrétních stránek, můžete upravit smyčku tak, aby cílila na tyto stránky na základě jejich čísel stránek nebo jiných kritérií.

#### Otázka: Má změna orientace stránky vliv na rozložení obsahu na stránce?

Odpověď: Ano, změna orientace stránky ovlivní rozložení obsahu na stránce. Obsah se otočí o 90 stupňů a šířka a výška stránky se zamění. V důsledku toho se může změnit umístění a zarovnání obsahu na stránce.

#### Otázka: Mohu stránku otočit o jiný úhel než 90 stupňů?

 Odpověď: V poskytnutém zdrojovém kódu C# je otočení stránky nastaveno na 90 stupňů pomocí`page.Rotate = Rotate.on90;` . V případě potřeby však můžete změnit úhel natočení na jiné hodnoty. Můžete například použít`Rotate.on180` pro otočení stránky o 180 stupňů nebo`Rotate.on270` pro otočení o 270 stupňů.

#### Otázka: Jak naložím s obsahem stránky, který přeteče po změně orientace?

Odpověď: Při změně orientace stránky se mohou změnit rozměry stránky, což může mít za následek přetečení obsahu. Abyste to zvládli, možná budete muset upravit rozvržení a formátování obsahu na stránce. Můžete použít funkce poskytované Aspose.PDF pro .NET, jako je změna velikosti prvků, úprava okrajů nebo reorganizace obsahu, abyste zajistili, že se obsah stránky po změně orientace vejde správně.