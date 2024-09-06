---
title: Kontrolní obdélník Z pořadí v souboru PDF
linktitle: Kontrolní obdélník Z pořadí v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se ovládat Z-pořadí obdélníků v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 40
url: /cs/net/programming-with-graphs/control-rectangle-z-order/
---
tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, abyste mohli ovládat pořadí Z obdélníků pomocí Aspose.PDF pro .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit výsledný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření instance objektu dokumentu a přidání stránky

Vytvoříme instanci třídy Document a do tohoto dokumentu přidáme stránku.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Krok 3: Nastavení velikosti stránky

Velikost stránky PDF nastavíme pomocí metody SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Krok 4: Nastavení okrajů stránky

Okraje stránky můžeme nakonfigurovat pomocí vlastností objektu PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Krok 5: Přidejte obdélníky se zadaným pořadím Z

Vytváříme a přidáváme na stránku obdélníky s různými barvami a zadanými Z řády.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Krok 6: Uložení výsledného souboru PDF

Nakonec výsledný soubor PDF s názvem „ControlRectangleZOrder_out.pdf“ uložíme do zadaného adresáře.

```csharp
doc1.Save(dataDir);
```
### Ukázka zdrojového kódu pro Control Rectangle Z Order pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Objekt třídy Instantiate Document
Document doc1 = new Document();
/// Přidat stránku do kolekce stránek souboru PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Nastavit velikost stránky PDF
page1.SetPageSize(375, 300);
// Nastavte levý okraj pro objekt stránky na 0
page1.PageInfo.Margin.Left = 0;
// Nastavit horní okraj objektu stránky na 0
page1.PageInfo.Margin.Top = 0;
//Vytvořte nový obdélník s Color as Red, Z-Order jako 0 a určitými rozměry
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Vytvořte nový obdélník s Color as Blue, Z-Order jako 0 a určitými rozměry
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Vytvořte nový obdélník s Color as Green, Z-Order jako 0 a určitými rozměry
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Uložte výsledný soubor PDF
doc1.Save(dataDir);

```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak ovládat Z-pořadí obdélníků pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k přesnému uspořádání a vrstvení obdélníků v souborech PDF.

### Kontrolní obdélník z FAQ v pořadí v souboru PDF

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Tento výukový program vás provede procesem ovládání Z-pořadí obdélníků pomocí Aspose.PDF pro .NET, což vám umožní uspořádat a vrstvit obdélníky v souborech PDF.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

A: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili vaše vývojové prostředí. Kromě toho se doporučuje základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: V poskytnutém zdrojovém kódu můžete upravit proměnnou "dataDir" tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jaký je účel nastavení velikosti stránky a okrajů?

Odpověď: Nastavení velikosti stránky a okrajů pomáhá konfigurovat rozvržení stránky PDF a poskytuje plátno, na kterém můžete uspořádat obdélníky.

#### Otázka: Jak přidám obdélníky se zadaným pořadím Z?

Odpověď: Obdélníky můžete vytvořit a přidat na stránku pomocí`AddRectangle` určující polohu, rozměry, barvu a pořadí Z pro každý obdélník.

#### Otázka: Co je Z-pořadí a proč je důležité?

Odpověď: Z-order určuje pořadí překrývání objektů na stránce. Objekty s vyššími hodnotami pořadí Z jsou umístěny nad objekty s nižšími hodnotami pořadí Z, což ovlivňuje jejich viditelnost a vrstvení.

#### Otázka: Mohu přizpůsobit barvy a rozměry obdélníků?

 Odpověď: Ano, můžete upravit barvy, pozice a rozměry obdélníků úpravou parametrů předávaných do`AddRectangle` metoda.

#### Otázka: Jak uložím výsledný soubor PDF po uspořádání obdélníků?

 Odpověď: Po uspořádání obdélníků můžete výsledný soubor PDF uložit pomocí`doc1.Save(dataDir);` řádek v poskytnutém zdrojovém kódu.