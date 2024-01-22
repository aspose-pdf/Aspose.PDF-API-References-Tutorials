---
title: Převést tok obrázků na soubor PDF
linktitle: Převést tok obrázků na soubor PDF
second_title: Aspose.PDF pro .NET API Reference
description: Snadno převádějte proud obrázků do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 70
url: /cs/net/programming-with-images/convert-image-stream-to-pdf/
---
Tato příručka vás krok za krokem provede převodem proudu obrázků do souboru PDF pomocí Aspose.PDF pro .NET. Ujistěte se, že jste již nastavili své prostředí a postupujte podle následujících kroků:

## Krok 1: Definujte adresář dokumentů

 Než začnete, ujistěte se, že jste nastavili správný adresář pro dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s cestou k adresáři, kde se nachází váš obrázek.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte instanci objektu dokumentu

 V tomto kroku vytvoříme instanci a`Document` objekt pomocí prázdného konstruktoru`Aspose.Pdf.Document` třída.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Krok 3: Přidejte stránku do dokumentu PDF

 Přidejte stránku do dokumentu PDF pomocí`Add` metoda`Pages` předmět`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Krok 4: Přečtěte si tok obrázků

 V tomto kroku vytvoříme a`FileStream` objekt pro čtení souboru obrázku ze streamu.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Krok 5: Přečtěte si obrázek do bajtového pole

 Přečtěte si obrázek ze streamu a uložte jej do bajtového pole pomocí`Read` metoda`fs` objekt.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Krok 6: Vytvořte objekt MemoryStream z bajtového pole

 Vytvořit`MemoryStream` objekt z bajtového pole obsahujícího obrázek.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Krok 7: Vytvořte objekt obrázku

 V tomto kroku vytvoříme`Image` objekt pomocí`Aspose.Pdf.Image` třída. Určete proud obrazu pomocí`ImageStream` majetek a předat`ms` objekt, který jsme vytvořili dříve.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Krok 8: Přidejte objekt Image do kolekce Odstavce

 Přidat`imageht` namítat proti`Paragraphs` sbírka`sec` sekce.

```csharp
sec.Paragraphs.Add(imageht);
```

## Krok 9: Uložte dokument PDF

 Uložte dokument PDF pomocí`Save` metoda`pdf1` objekt. Zadejte výstupní cestu souboru PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Krok 10: Zavřete objekt MemoryStream

 Zavři`ms` objekt pomocí`Close` způsob uvolnění zdrojů.

```csharp
ms. Close();
```

### Ukázkový zdrojový kód pro Convert Image Stream to PDF pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Vytvořte instanci instance dokumentu voláním jejího prázdného konstruktoru
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Přidejte stránku do dokumentu pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Vytvořte objekt FileStream pro čtení souboru imag
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Načtěte obrázek do pole Byte
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Vytvořte objekt MemoryStream z obrazového pole Byte
MemoryStream ms = new MemoryStream(data);
// Vytvořte objekt obrázku
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Určete zdroj obrázku jako MemoryStream
imageht.ImageStream = ms;
// Přidejte objekt obrázku do kolekce Odstavce sekce
sec.Paragraphs.Add(imageht);
// Uložte Pdf
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Zavřete objekt MemoryStream
ms.Close();
```

## Závěr

gratuluji! Úspěšně jste převedli proud obrázků na soubor PDF pomocí Aspose.PDF for .NET. Vygenerovaný soubor PDF se uloží do zadaného adresáře. Nyní můžete tento soubor PDF používat ve svých projektech nebo aplikacích.

### FAQ

#### Otázka: Jaký je účel převodu proudu obrázků na soubor PDF pomocí Aspose.PDF pro .NET?

Odpověď: Převod obrazového proudu na soubor PDF může být užitečný pro začlenění obrazů do dokumentů PDF, vytváření souborů PDF založených na obrazech nebo vkládání obrazů do textového obsahu.

#### Otázka: Jak Aspose.PDF for .NET pomáhá při převodu proudu obrázků na soubor PDF?

Odpověď: Aspose.PDF for .NET poskytuje pohodlný a krok za krokem proces vytváření dokumentu PDF, čtení proudu obrázků a vkládání obrázku do souboru PDF.

#### Otázka: Proč je definování adresáře dokumentů důležité v procesu převodu obrazového proudu do PDF?

Odpověď: Určení adresáře dokumentu zajišťuje, že obrazový proud a výsledný soubor PDF jsou správně umístěny v požadované výstupní cestě.

#### Otázka: Jak vytvořím dokument PDF pomocí Aspose.PDF for .NET v procesu převodu obrazového proudu do PDF?

 A: Instantovat a`Document` objekt pomocí`Aspose.Pdf.Document` prázdný konstruktor třídy k vytvoření dokumentu PDF.

####  Otázka: Jaká je role`Pages` object in the image stream to PDF conversion process?

 A:`Pages` objekt umožňuje přidávat stránky do dokumentu PDF a spravovat jeho obsah.

#### Otázka: Jak se obrazový proud čte a zpracovává v procesu převodu obrazového proudu do PDF?

 A: Obrazový proud se čte pomocí a`FileStream` objekt a jeho obsah je uložen v bajtovém poli. Bytové pole se pak použije k vytvoření a`MemoryStream` objekt, který je následně použit k vytvoření`Image` objekt.

#### Otázka: Jak je obrázek vložený do dokumentu PDF během procesu převodu?

 A: An`Image` objekt je vytvořen pomocí`Aspose.Pdf.Image` třída a proud obrazu je přiřazen k`ImageStream` vlastnictví. The`Image` objekt je pak přidán do`Paragraphs` sbírka PDF dokumentu.

#### Otázka: Mohu upravit polohu, velikost nebo jiné atributy obrázku ve výsledném souboru PDF?

 Odpověď: Ano, můžete upravit polohu, velikost a další atributy obrázku úpravou vlastností`Image` objekt před jeho přidáním do`Paragraphs` sbírka.

#### Otázka: Jaký je poslední krok v procesu převodu obrazového streamu do PDF?

 Odpověď: Dokument PDF se uloží pomocí`Save` metoda`Document` objekt a`MemoryStream` objekt se uzavírá pomocí`Close` způsob uvolňování zdrojů.