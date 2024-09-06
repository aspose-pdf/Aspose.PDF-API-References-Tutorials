---
title: Získejte rozměry stránky PDF
linktitle: Získejte rozměry stránky PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto tutoriálu vysvětlíme, jak získat rozměry stránky PDF a provádět manipulace pomocí Aspose.PDF for .NET. Jsou uvedeny podrobné kroky, které vás provedou celým procesem.
type: docs
weight: 60
url: /cs/net/programming-with-pdf-pages/get-dimensions/
---
tomto tutoriálu vás provedeme krok za krokem procesem získání rozměrů stránky v souboru PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak získat rozměry stránky v souboru PDF pomocí Aspose.PDF pro .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#
- Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kde se nachází váš soubor PDF. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otevřete dokument PDF
 Poté můžete otevřít soubor PDF pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu k souboru PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Krok 3: Přidejte prázdnou stránku (v případě potřeby)
 Pokud dokument PDF již obsahuje stránky, můžete přejít na existující stránku pomocí rejstříku`1` (první stránka má index 1). V opačném případě můžete do dokumentu přidat novou stránku.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Krok 4: Získejte rozměry stránky
 Nyní můžete získat rozměry stránky pomocí`GetPageRect()` metoda`Page` objekt. Tato metoda vrací a`Rectangle` objekt obsahující rozměry stránky. K šířce a výšce můžete přistupovat pomocí`Width` a`Height` vlastnosti.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Krok 5: Otočte stránku
 Pokud chcete stránku otočit, můžete použít`Rotate` majetek z`Page`objekt. V tomto příkladu je stránka otočena o 90 stupňů.

```csharp
page. Rotate = Rotate. on90;
```

## Krok 6: Znovu získejte rozměry stránky
 Po otočení stránky můžete znovu získat rozměry stránky pomocí`GetPageRect()` metoda.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Ukázka zdrojového kódu pro Get Dimensions pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Přidá prázdnou stránku do dokumentu pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Získejte informace o výšce a šířce stránky
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Otočte stránku v úhlu 90 stupňů
page.Rotate = Rotation.on90;
// Získejte informace o výšce a šířce stránky
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Závěr
V tomto tutoriálu jsme se naučili, jak získat rozměry stránky v souboru PDF pomocí Aspose.PDF pro .NET. Podle uvedených kroků můžete snadno extrahovat rozměry stránky a provádět další operace manipulace s PDF. Aspose.PDF for .NET nabízí velkou flexibilitu pro práci se soubory PDF a umožňuje vám vyvíjet výkonná a přizpůsobená řešení.

Neváhejte dále prozkoumat dokumentaci Aspose.PDF, abyste objevili všechny funkce nabízené touto knihovnou.

### Časté dotazy pro získání rozměrů stránky PDF

#### Otázka: Jak mohu získat rozměry konkrétní stránky v souboru PDF?

Odpověď: Chcete-li získat rozměry konkrétní stránky v souboru PDF, můžete použít`GetPageRect()` metoda`Page` objekt v Aspose.PDF pro .NET. Tato metoda vrací a`Rectangle` objekt obsahující rozměry (šířku a výšku) stránky.

####  Q: Co dělá`GetPageRect(true)` method do in the provided C# source code?

 A:`GetPageRect(true)` metoda v poskytnutém zdrojovém kódu C# vrátí rozměry stránky po použití jakýchkoli otočení. Pokud je stránka otočená, metoda vrátí rozměry otočené stránky, které se mohou lišit od původních rozměrů.

#### Otázka: Mohu získat rozměry všech stránek v dokumentu PDF pomocí Aspose.PDF pro .NET?

 Odpověď: Ano, rozměry všech stránek v dokumentu PDF můžete získat iterací přes`Pages` sbírka`Document` objektu a pomocí`GetPageRect(true)` metoda pro každou stránku.

#### Otázka: Jak mohu určit orientaci stránky (na výšku nebo na šířku) na základě jejích rozměrů?

Odpověď: Chcete-li určit orientaci stránky na základě jejích rozměrů, můžete porovnat šířku a výšku stránky. Pokud je šířka větší než výška, je stránka orientována na šířku, a pokud je výška větší než šířka, je stránka orientována na výšku.

#### Otázka: Mohu upravit rozměry stránky pomocí Aspose.PDF pro .NET?

 Odpověď: Ano, rozměry stránky můžete upravit v Aspose.PDF pro .NET. Po získání`Rectangle` objekt představující rozměry stránky, můžete upravit šířku a výšku podle svých požadavků a poté aplikovat změny na stránku.