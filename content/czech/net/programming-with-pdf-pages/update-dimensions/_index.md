---
title: Aktualizujte rozměry stránky PDF
linktitle: Aktualizujte rozměry stránky PDF
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce aktualizací rozměrů stránky PDF pomocí Aspose.PDF pro .NET. Zkontrolujte rozměry podle vašich potřeb.
type: docs
weight: 150
url: /cs/net/programming-with-pdf-pages/update-dimensions/
---
V tomto tutoriálu vás provedeme krok za krokem procesem aktualizace rozměrů stránky v dokumentu PDF pomocí Aspose.PDF for .NET. Vysvětlíme vám přibalený zdrojový kód C# a poskytneme vám komplexního průvodce, který vám pomůže pochopit a implementovat tuto funkci ve vašich vlastních projektech. Na konci tohoto tutoriálu budete vědět, jak změnit rozměry stránky v dokumentu PDF pomocí Aspose.PDF for .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující:

- Základní znalost programovacího jazyka C#
- Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí

## Krok 1: Definujte adresář dokumentů
Nejprve musíte nastavit cestu k adresáři dokumentů. Toto je umístění, kam chcete uložit upravený dokument PDF. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Otevřete dokument PDF
 Poté můžete otevřít existující dokument PDF pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu dokumentu.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Krok 3: Získejte kolekci stránek
 Nyní můžete přistupovat ke kolekci stránek dokumentu PDF pomocí`Pages` majetek z`Document` třída.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Krok 4: Získejte konkrétní stránku
Poté můžete vybrat konkrétní stránku dokumentu pomocí indexu stránky v kolekci. V tomto příkladu používáme druhou stránku (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Krok 5: Definujte nové rozměry stránky
 Nyní můžete nastavit novou velikost stránky pomocí`SetPageSize()` metoda`Page`objekt. V tomto příkladu nastavujeme rozměry stránky na A4 (11,7 x 8,3 palce), převedené na body (1 palec = 72 bodů).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## Krok 6: Uložte aktualizovaný dokument
 Nakonec můžete aktualizovaný dokument PDF uložit do souboru pomocí`Save()` metoda`Document`třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Ukázkový zdrojový kód pro Update Dimensions pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Získejte kolekci stránek
PageCollection pageCollection = pdfDocument.Pages;
// Získejte konkrétní stránku
Page pdfPage = pageCollection[1];
// Nastavte velikost stránky jako A4 (11,7 x 8,3 palce) a v Aspose.Pdf, 1 palec = 72 bodů
// Rozměry A4 v bodech tedy budou (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Uložte aktualizovaný dokument
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Závěr
V tomto tutoriálu jsme se naučili, jak aktualizovat rozměry stránky v dokumentu PDF pomocí Aspose.PDF for .NET. Podle tohoto podrobného průvodce můžete snadno změnit rozměry stránky v dokumentu PDF podle potřeby. Aspose.PDF nabízí výkonné a flexibilní API pro práci se soubory PDF a provádění různých manipulací, včetně změny rozměrů stránky. S těmito znalostmi můžete řídit a přizpůsobovat rozměry svých stránek PDF tak, aby vyhovovaly vašim specifickým potřebám.

### Časté dotazy pro aktualizaci rozměrů stránky PDF

#### Otázka: Jak mohu aktualizovat rozměry konkrétní stránky v dokumentu PDF pomocí Aspose.PDF pro .NET?

Odpověď: Chcete-li aktualizovat rozměry konkrétní stránky v dokumentu PDF pomocí Aspose.PDF pro .NET, můžete postupovat takto:

1. Nastavte adresář dokumentu zadáním cesty, kde se nachází váš původní soubor PDF a kam chcete uložit aktualizovaný soubor PDF. Nahraďte "VAŠE ADRESÁŘ DOKUMENTŮ" příslušnou cestou.
2.  Otevřete existující dokument PDF a aktualizujte jej pomocí`Document` třída Aspose.PDF. Ujistěte se, že jste zadali správnou cestu k původnímu dokumentu PDF.
3.  Přístup ke kolekci stránek dokumentu PDF pomocí`Pages` majetek z`Document` třída.
4. Vyberte konkrétní stránku, kterou chcete aktualizovat, z kolekce stránek pomocí indexu stránky. V poskytnutém zdrojovém kódu C# používáme druhou stránku (index 1).
5.  Definujte novou velikost stránky pomocí`SetPageSize()` metoda`Page` objekt. V příkladu nastavíme rozměry stránky na velikost A4 (11,7 x 8,3 palce), převedené na body (1 palec = 72 bodů).
6.  Uložte aktualizovaný dokument PDF do souboru pomocí`Save()` metoda`Document`třída. Ujistěte se, že jste zadali správnou cestu a název souboru.

#### Otázka: Mohu aktualizovat rozměry více stránek v dokumentu PDF současně?

Odpověď: Ano, poskytnutý zdrojový kód můžete upravit tak, aby se současně aktualizovaly rozměry více stránek v dokumentu PDF. Namísto výběru konkrétní stránky (jak je znázorněno v kroku 4) můžete procházet všechny stránky v kolekci stránek a nastavit požadovanou velikost stránky pro každou stránku.

#### Otázka: Jak převedu rozměry stránky z palců na body při použití Aspose.PDF pro .NET?

 Odpověď: V Aspose.PDF pro .NET jsou měrnou jednotkou používanou pro rozměry stránky body, kde 1 palec odpovídá 72 bodům. Chcete-li převést palce na body, můžete použít vzorec:`points = inches * 72`. Chcete-li například nastavit velikost stránky 11,7 x 8,3 palce, můžete vypočítat odpovídající rozměry v bodech jako (11,7 * 72) a (8,3 * 72).

#### Otázka: Ovlivní aktualizace rozměrů stránky rozložení obsahu dokumentu PDF?

Odpověď: Ano, aktualizace rozměrů stránky ovlivní rozložení obsahu dokumentu PDF na této konkrétní stránce. Když změníte rozměry stránky, obsah stránky se odpovídajícím způsobem upraví tak, aby odpovídal novým rozměrům.

#### Otázka: Je možné vrátit změny a obnovit původní rozměry stránky po jejich aktualizaci?

Odpověď: Ano, pokud chcete vrátit změny a obnovit původní rozměry stránky, můžete si před provedením změn buď ponechat kopii původního dokumentu PDF, nebo znovu otevřít původní dokument PDF bez uložení změn. Tímto způsobem zůstanou zachovány původní rozměry.