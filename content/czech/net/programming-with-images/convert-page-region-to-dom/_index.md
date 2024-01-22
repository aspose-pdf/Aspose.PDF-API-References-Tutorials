---
title: Převést oblast stránky na DOM
linktitle: Převést oblast stránky na DOM
second_title: Aspose.PDF pro .NET API Reference
description: Pomocí Aspose.PDF for .NET můžete snadno převést určitou oblast stránky PDF na objektový model dokumentu (DOM).
type: docs
weight: 80
url: /cs/net/programming-with-images/convert-page-region-to-dom/
---
Tato příručka vás krok za krokem provede převodem konkrétní oblasti stránky na objektový model dokumentu (DOM) pomocí Aspose.PDF for .NET. Ujistěte se, že jste již nastavili své prostředí a postupujte podle následujících kroků:

## Krok 1: Definujte adresář dokumentů

 Než začnete, ujistěte se, že jste nastavili správný adresář pro dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s cestou k adresáři, kde se nachází váš dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument

 tomto kroku otevřeme dokument PDF pomocí`Document` třída Aspose.PDF. Použijte`Document` konstruktoru a předejte cestu k dokumentu PDF.

```csharp
Document document = new Document(dataDir + "AddImage.pdf");
```

## Krok 3: Získejte obdélník oblasti stránky

 V tomto kroku definujeme obdélník představující konkrétní oblast stránky, kterou chceme převést na DOM. Použijte`Aspose.Pdf.Rectangle` třídy k definování souřadnic obdélníku.

```csharp
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
```

## Krok 4: Definujte oblast oříznutí stránky

 Použijte`CropBox` vlastnictvím`Page` objekt pro nastavení ořezového pole stránky na požadovaný obdélník oblasti.

```csharp
document.Pages[1].CropBox = pageRect;
```

## Krok 5: Uložte oříznutý dokument PDF do streamu

 V tomto kroku uložíme oříznutý dokument PDF do streamu pomocí`MemoryStream` třída.

```csharp
MemoryStream ms = new MemoryStream();
document.Save(ms);
```

## Krok 6: Otevřete oříznutý dokument PDF a převeďte jej na obrázek

 Otevřete oříznutý dokument PDF pomocí`Document` třídy a převést ji na obrázek. Použijeme rozlišení 300 dpi.

```csharp
document = newDocument(ms);
Resolution resolution = new Resolution(300);
PngDevice pngDevice = new PngDevice(resolution);
```

## Krok 7: Převeďte konkrétní stránku na obrázek

 Převeďte konkrétní stránku na obrázek pomocí`Process` metoda`pngDevice`objekt. Zadejte cestu výstupu obrazu.

```csharp
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
pngDevice.Process(document.Pages[1], dataDir);
```

### Ukázkový zdrojový kód pro Převést oblast stránky na DOM pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document document = new Document( dataDir + "AddImage.pdf");
// Získejte obdélník konkrétní oblasti stránky
Aspose.Pdf.Rectangle pageRect = new Aspose.Pdf.Rectangle(20, 671, 693, 1125);
// Nastavte hodnotu CropBox podle obdélníku požadované oblasti stránky
document.Pages[1].CropBox = pageRect;
// Uložte oříznutý dokument do streamu
MemoryStream ms = new MemoryStream();
document.Save(ms);
// Otevřete oříznutý dokument PDF a převeďte jej na obrázek
document = new Document(ms);
// Vytvořit objekt rozlišení
Resolution resolution = new Resolution(300);
// Vytvořte zařízení PNG se zadanými atributy
PngDevice pngDevice = new PngDevice(resolution);
dataDir = dataDir + "ConvertPageRegionToDOM_out.png";
//Převeďte konkrétní stránku a uložte obrázek do streamu
pngDevice.Process(document.Pages[1], dataDir);
ms.Close();
Console.WriteLine("\nPage region converted to DOM successfully.\nFile saved at " + dataDir); 
```

## Závěr

gratuluji! Úspěšně jste převedli určitou oblast stránky na Document Object Model (DOM) pomocí Aspose.PDF for .NET. Výsledný obrázek se uloží do určeného adresáře. Nyní můžete tento obrázek použít ve svých projektech nebo aplikacích.

## FAQ

#### Otázka: Jaký je účel převodu konkrétní oblasti stránky na objektový model dokumentu (DOM) pomocí Aspose.PDF pro .NET?

Odpověď: Převedení určité oblasti stránky PDF na objektový model dokumentu (DOM) může být užitečné pro extrahování a manipulaci s určitou částí obsahu v dokumentu PDF.

#### Otázka: Jak Aspose.PDF for .NET usnadňuje převod konkrétní oblasti stránky na DOM?

Odpověď: Aspose.PDF for .NET poskytuje proces krok za krokem k definování požadované oblasti stránky, nastavení oblasti oříznutí, uložení oříznutého dokumentu PDF do proudu a převedení určené oblasti stránky na obrázek.

#### Otázka: Proč je důležité definovat adresář dokumentů před zahájením procesu převodu?

Odpověď: Určení adresáře dokumentu zajistí, že dokument PDF a výsledný obrázek budou správně umístěny v požadované výstupní cestě.

####  Otázka: Jak to`Document` class in Aspose.PDF for .NET help in the conversion process?

 A:`Document` třída umožňuje otevírat, manipulovat a ukládat dokumenty PDF. V tomto případě se používá k načtení dokumentu PDF a vytvoření jeho oříznuté verze.

####  Otázka: Jaký je účel`Rectangle` class in the page region conversion process?

 A:`Rectangle` class definuje souřadnice konkrétní oblasti na stránce PDF, kterou chcete převést na DOM. Pomáhá přesně specifikovat oblast plodiny.

#### Otázka: Jak je oblast oříznutí stránky nastavena na požadovanou oblast v procesu převodu?

 A:`CropBox` vlastnictvím`Page` objekt se používá k nastavení oblasti oříznutí stránky na definovaný obdélník představující konkrétní oblast.

#### Otázka: Jak se oříznutý dokument PDF uloží do proudu během procesu převodu?

 A: Oříznutý dokument PDF se uloží do a`MemoryStream` objekt, který umožňuje efektivní manipulaci s obsahem PDF.

####  Otázka: Jakou roli hraje`PngDevice` class play in the page region to DOM conversion process?

 A:`PngDevice` class pomáhá převést oříznutý dokument PDF do obrazového formátu, jako je PNG, což vám umožní vizualizovat konkrétní oblast stránky.

#### Otázka: Mohu během procesu převodu upravit rozlišení nebo jiné atributy výsledného obrázku?

 Odpověď: Ano, můžete upravit rozlišení a další atributy výsledného obrázku konfigurací`PngDevice` objekt před převodem stránky.