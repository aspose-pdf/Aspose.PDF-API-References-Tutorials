---
title: Získejte vlastnosti PDF
linktitle: Získejte vlastnosti PDF
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce pro získání vlastností PDF, jako jsou rozměry a rotace krabice pomocí Aspose.PDF pro .NET.
type: docs
weight: 100
url: /cs/net/programming-with-pdf-pages/get-properties/
---
tomto tutoriálu vás provedeme krok za krokem procesem získání vlastností PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak přistupovat k různým vlastnostem stránky PDF, jako je rámeček umění, rámeček oříznutí, rámeček oříznutí atd., pomocí Aspose.PDF pro .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#
- Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí

## Krok 1: Nastavte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění souboru PDF, jehož vlastnosti chcete získat. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otevřete dokument PDF
 Dále musíte otevřít dokument PDF pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu k souboru PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Krok 3: Přístup ke kolekci stránek
 Nyní můžete přistupovat ke kolekci stránek dokumentu pomocí`Pages` majetek z`pdfDocument` objekt.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Krok 4: Přejděte na konkrétní stránku
Poté můžete přejít na konkrétní stránku pomocí indexu stránky v kolekci. V níže uvedeném příkladu přistupujeme na druhou stránku (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Krok 5: Získejte vlastnosti stránky
 Nyní můžete získat různé vlastnosti stránky PDF, jako je umělecký rámeček, rámeček oříznutí, rámeček oříznutí atd., pomocí odpovídajících vlastností`pdfPage` objekt.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Ukázkový zdrojový kód pro Get Properties pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Získejte kolekci stránek
PageCollection pageCollection = pdfDocument.Pages;
// Získejte konkrétní stránku
Page pdfPage = pageCollection[1];
// Získejte vlastnosti stránky
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Závěr
gratuluji! Úspěšně jste získali vlastnosti PDF pomocí Aspose.PDF pro .NET. Naučili jste se, jak otevřít dokument PDF, přejít na konkrétní stránku a získat různé vlastnosti stránky, jako jsou kótovací rámečky a otočení. Tyto informace nyní můžete použít k přizpůsobení zacházení se soubory PDF na základě jejich vlastností.

Nezapomeňte se podívat na oficiální dokumentaci Aspose.PDF pro .NET, kde najdete další informace o pokročilých funkcích a možnostech přizpůsobení.

### FAQ

#### Otázka: Jak mohu získat vlastnosti PDF pomocí Aspose.PDF pro .NET?

A: Chcete-li získat vlastnosti PDF pomocí Aspose.PDF pro .NET, můžete postupovat takto:

1. Nastavte adresář dokumentu zadáním cesty k souboru PDF, jehož vlastnosti chcete načíst.
2.  Otevřete dokument PDF pomocí`Document` třídy Aspose.PDF poskytující správnou cestu k souboru PDF.
3.  Přístup ke kolekci stránek dokumentu pomocí`Pages` majetek z`pdfDocument` objekt.
4. Přejít na konkrétní stránku pomocí indexu stránky v kolekci (indexování začíná od 1).
5.  Získejte různé vlastnosti stránky PDF, jako je ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Číslo stránky a Rotace, pomocí odpovídajících vlastností`pdfPage` objekt.

#### Otázka: Jaké jsou různé vlastnosti stránky PDF, které mohu načíst pomocí Aspose.PDF pro .NET?

Odpověď: Pomocí Aspose.PDF pro .NET můžete načíst různé vlastnosti stránky PDF, například:

- ArtBox: Představuje rozměry kresby stránky.
- BleedBox: Představuje rozměry spadávky stránky.
- CropBox: Představuje rozměry viditelného obsahu stránky po oříznutí.
- MediaBox: Představuje rozměry fyzického média stránky.
- TrimBox: Představuje rozměry oříznutého obsahu stránky.
- Obdélník: Představuje rozměry ohraničovacího rámečku stránky.
- Číslo stránky: Představuje číslo stránky v dokumentu.
- Otočit: Představuje úhel otočení stránky.

#### Otázka: Jak získám přístup ke konkrétní stránce v dokumentu PDF, abych získal její vlastnosti?

 Odpověď: Pro přístup ke konkrétní stránce v dokumentu PDF a načtení jejích vlastností můžete použít`Pages` majetek z`pdfDocument` objekt pro přístup ke kolekci stránek dokumentu. Poté můžete pomocí indexu stránky v kolekci přejít na požadovanou stránku. Například pro přístup na druhou stránku můžete použít`pdfDocument.Pages[1]` (indexování začíná od 1).

#### Otázka: Mohu provádět operace s načtenými vlastnostmi, jako je úprava nebo změna velikosti rámečků stránky?

Odpověď: Ano, jakmile načtete vlastnosti stránky PDF pomocí Aspose.PDF pro .NET, můžete s nimi provádět různé operace. Můžete například upravit rozměry rámečků stránky, otočit stránku nebo použít načtené informace pro vlastní zpracování a manipulaci s dokumentem PDF.

#### Otázka: Podporuje Aspose.PDF for .NET extrahování vlastností ze zašifrovaných nebo heslem chráněných souborů PDF?

Odpověď: Ano, Aspose.PDF for .NET podporuje extrahování vlastností ze zašifrovaných nebo heslem chráněných souborů PDF. Pokud zadáte správné heslo pro otevření dokumentu PDF, můžete přistupovat k jeho vlastnostem a získávat je pomocí stejného přístupu, který je ukázán ve výukovém programu.