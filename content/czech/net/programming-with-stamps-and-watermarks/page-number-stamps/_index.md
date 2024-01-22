---
title: Číslo stránky Razítka V Souboru PDF
linktitle: Číslo stránky Razítka V Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat razítka s čísly stránek do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 160
url: /cs/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
V tomto tutoriálu vás krok za krokem provedeme, jak přidat razítka s čísly stránek do souboru PDF pomocí Aspose.PDF pro .NET. Dodaný zdrojový kód C# použijeme k otevření existujícího dokumentu PDF, vytvoření razítka s číslem stránky, nastavení jeho vlastností a přidání na konkrétní stránku v souboru PDF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Načtení existujícího dokumentu PDF

Prvním krokem je načtení stávajícího dokumentu PDF do vašeho projektu. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otevřete existující dokument PDF
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

## Krok 3: Vytvoření a konfigurace číslovacího razítka stránek

Nyní, když je dokument PDF načten, můžeme vytvořit vyrovnávací paměť pro číslování stránek a nakonfigurovat ji podle našich potřeb. Zde je postup:

```csharp
// Vytvořte vyrovnávací paměť pro čísla stránek
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Definujte, zda je vyrovnávací paměť na pozadí nebo ne
pageNumberStamp.Background = false;

// Formát vyrovnávací paměti pro číslování stránek
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Dolní okraj vyrovnávací paměti pro číslování stránek
pageNumberStamp.BottomMargin = 10;

// Vodorovné zarovnání vyrovnávací paměti pro číslování stránek
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Počáteční číslo číslování stránek
pageNumberStamp.StartingNumber = 1;

// Nastavte vlastnosti textu vyrovnávací paměti čísel stránek
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Výše uvedený kód vytvoří razítko s číslem stránky s vlastnostmi, jako je formát čísla stránky, spodní okraj, vodorovné zarovnání, počáteční číslo a vlastnosti textu.

## Krok 4: Přidání razítka s číslem stránky na konkrétní stránku

Jakmile je razítko s číslem stránky nakonfigurováno, můžeme jej přidat na konkrétní stránku dokumentu PDF. Zde je postup:

```csharp
// Přidejte vyrovnávací paměť pro čísla stránek na konkrétní stránku
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

Výše uvedený kód přidá razítko s číslem stránky na první stránku dokumentu PDF. Číslo stránky můžete podle potřeby změnit.

## Krok 5: Uložení upraveného dokumentu PDF

Jakmile je do dokumentu PDF přidáno razítko s číslem stránky, můžeme upravený dokument PDF uložit. Zde je postup:

```csharp
// Uložte upravený dokument PDF
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kam chcete uložit upravený dokument PDF.

### Ukázkový zdrojový kód pro razítka čísel stránek pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Vytvořte razítko s číslem stránky
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Zda je razítko pozadí
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Nastavte vlastnosti textu
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Přidejte razítko na konkrétní stránku
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Uložit výstupní dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Závěr

gratuluji! Naučili jste se, jak přidat razítka s čísly stránek do dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete své dokumenty PDF personalizovat přidáním jasných a informativních čísel stránek.

### Časté dotazy k razítkům s čísly stránek v souboru PDF

#### Otázka: Co je to razítko s číslem stránky a jak se používá k přidávání čísel stránek do souboru PDF?

A: Číslo stránky je funkce v Aspose.PDF, která vám umožňuje přidávat dynamická čísla stránek na konkrétní stránky dokumentu PDF. V tomto kurzu je toho dosaženo vytvořením objektu PageNumberStamp, konfigurací jeho vlastností a přidáním na určenou stránku.

#### Otázka: Jak poskytnutý zdrojový kód C# provádí přidávání razítek s čísly stránek do souboru PDF?

Odpověď: Kód ukazuje, jak načíst existující dokument PDF, vytvořit PageNumberStamp, nastavit různé vlastnosti (jako je formát, písmo, zarovnání atd.) a poté přidat razítko na konkrétní stránku. Razítko automaticky vypočítá celkový počet stránek a vloží správná čísla stránek.

#### Otázka: Mohu upravit vzhled čísla stránky, jako je styl písma, barva a velikost?

Odpověď: Vzhled razítka s číslem stránky můžete upravit úpravou vlastností, jako je písmo, velikost písma, styl písma (tučné, kurzíva atd.) a barva textu.

#### Otázka: Je možné přidat razítka s čísly stránek na více stránek v rámci dokumentu PDF?

Odpověď: Ano, můžete přidat razítka s čísly stránek na více stránek vytvořením více objektů PageNumberStamp a přidáním každého z nich na požadované stránky.

#### Otázka: Mohu si vybrat, zda se razítko s číslem stránky zobrazí jako součást obsahu stránky nebo jako prvek pozadí?

 Odpověď: Ano, můžete nastavit, zda se razítko s číslem stránky objeví jako součást obsahu stránky nebo jako prvek pozadí, nastavením`Background` vlastnost PageNumberStamp.

#### Otázka: Jak určím formát čísla stránky, včetně celkového počtu stránek?

 A: Kód používá`Format`vlastnost PageNumberStamp k určení formátu čísla stránky. Makro "# z" se používá k vyjádření celkového počtu stránek.

#### Otázka: Co se stane, když přidám stejné číslo stránky na více stránek?

Odpověď: Přidání stejné instance PageNumberStamp na více stránek zobrazí správná čísla stránek pro každou stránku. Razítko automaticky upraví číslo stránky a celkový počet stránek.

#### Otázka: Mohu přidat razítka s čísly stránek do částí záhlaví nebo zápatí dokumentu PDF?

Odpověď: I když se PageNumberStamps obvykle přidávají přímo do obsahu stránky, můžete je umístit do sekce záhlaví nebo zápatí pomocí FloatingBox nebo jiných technik.

#### Otázka: Jak určím polohu razítka s číslem stránky na stránce?

 A:`BottomMargin` a`HorizontalAlignment` vlastnosti PageNumberStamp umožňují řídit pozici razítka na stránce.

#### Otázka: Co když chci začít číslování stránek od jiného čísla než od 1?

 A: Můžete nastavit`StartingNumber`vlastnost PageNumberStamp k určení počátečního čísla stránky.