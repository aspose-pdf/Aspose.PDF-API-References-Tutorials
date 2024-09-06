---
title: Extrahujte obrázky ze souboru PDF
linktitle: Extrahujte obrázky ze souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno extrahujte obrázky ze souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 120
url: /cs/net/programming-with-images/extract-images/
---
Tato příručka vás krok za krokem provede extrahováním obrázků ze souboru PDF pomocí Aspose.PDF pro .NET. Ujistěte se, že jste již nastavili své prostředí a postupujte podle následujících kroků:

## Krok 1: Definujte adresář dokumentů

Než začnete, ujistěte se, že jste nastavili správný adresář pro dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s cestou k adresáři, kde se nachází váš dokument PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Otevřete dokument PDF

 V tomto kroku otevřeme dokument PDF pomocí`Document` třída Aspose.PDF. Použijte`Document` konstruktoru a předejte cestu k dokumentu PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## Krok 3: Extrahujte konkrétní obrázek

 tomto kroku budeme extrahovat konkrétní obrázek z konkrétní stránky. Použijte`Images` kolekce stránky`s `Resources` objekt pro přístup k požadovanému obrázku. V níže uvedeném příkladu extrahujeme obrázek s indexem 1 z první stránky.

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## Krok 4: Uložte extrahovaný obrázek

 Uložte extrahovaný obrázek do souboru pomocí`Save` metoda`xImage` objekt. Zadejte výstupní cestu a formát obrázku (v tomto příkladu používáme formát JPEG).

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## Krok 5: Uložte aktualizovaný soubor PDF

 Uložte aktualizovaný soubor PDF pomocí`Save` metoda`pdfDocument` objekt. Zadejte výstupní cestu pro soubor PDF.

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro extrahování obrázků pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
// Extrahujte konkrétní obrázek
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
// Uložit výstupní obrázek
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
// Uložte aktualizovaný soubor PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## Závěr

gratuluji! Úspěšně jste extrahovali obrázky z PDF pomocí Aspose.PDF pro .NET. Extrahovaný obrázek se uloží do určeného adresáře a uloží se také aktualizovaný soubor PDF. Nyní můžete tyto soubory použít pro své specifické potřeby.

### Časté dotazy pro extrahování obrázků ze souboru PDF

#### Otázka: Proč bych chtěl extrahovat obrázky ze souboru PDF pomocí Aspose.PDF pro .NET?

Odpověď: Extrahování obrázků ze souboru PDF může být užitečné pro různé účely, jako je archivace, opětovné použití obrázků v jiných dokumentech, analýza obsahu nebo provádění úloh zpracování obrázků.

#### Otázka: Jak Aspose.PDF for .NET usnadňuje extrakci obrázků z dokumentu PDF?

Odpověď: Aspose.PDF for .NET poskytuje postupný proces otevření dokumentu PDF, přístupu ke konkrétním obrázkům a jejich uložení do souborů obrázků v různých formátech.

####  Otázka: Jakou roli hraje`Document` class in Aspose.PDF for .NET play in image extraction?

 A:`Document` třída se používá k načítání a manipulaci s dokumenty PDF. V této souvislosti pomáhá při otevírání dokumentu PDF, ze kterého budou obrázky extrahovány.

#### Otázka: Jak určím konkrétní obrázek, který chci extrahovat ze stránky PDF?

 A: Můžete použít`Images` kolekce stránek`Resources` objekt pro přístup k požadovanému obrázku podle jeho indexu. Například,`pdfDocument.Pages[1].Resources.Images[1]` přistupuje k prvnímu obrázku na první stránce.

#### Otázka: Mohu extrahovat obrázky z jakékoli stránky v dokumentu PDF?

Odpověď: Ano, můžete extrahovat obrazy z libovolné stránky v dokumentu PDF zadáním požadovaného indexu stránky a indexu obrazu, který se má extrahovat.

#### Otázka: V jakých formátech obrázků mohu extrahované obrázky uložit?

 Odpověď: Extrahované obrázky můžete uložit v různých formátech, které podporuje`ImageFormat` enum, jako jsou JPEG, PNG, BMP a další.

#### Otázka: Jak mohu použít extrahované obrázky po jejich uložení do souborů?

Odpověď: Extrahované obrázky lze použít jako jakékoli jiné soubory obrázků. Můžete je prohlížet, upravovat, sdílet nebo začlenit do jiných dokumentů nebo projektů.

#### Otázka: Ovlivňuje extrahování obrázků z PDF rozvržení nebo obsah původního dokumentu PDF?

Odpověď: Ne, extrahování obrázků z PDF neovlivní rozvržení ani obsah původního dokumentu PDF. Ovlivněny jsou pouze extrahované obrázky.

#### Otázka: Mohu extrahovat více obrázků z různých stránek v jednom procesu?

Odpověď: Ano, stejný proces můžete použít k extrahování obrázků z více stránek iterací přes různé indexy stránek.