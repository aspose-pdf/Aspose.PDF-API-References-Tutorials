---
title: Přidat textové razítko do souboru PDF
linktitle: Přidat textové razítko do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak snadno přidat textové razítko do souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 50
url: /cs/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
V tomto tutoriálu vás krok za krokem provedeme, jak přidat textové razítko do souboru PDF pomocí Aspose.PDF pro .NET. Ukážeme vám, jak použít dodaný zdrojový kód C# k přidání vlastního textového razítka na konkrétní stránku souboru PDF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Načtení dokumentu PDF

Prvním krokem je načtení stávajícího dokumentu PDF do vašeho projektu. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

## Krok 3: Vytvoření textové vyrovnávací paměti

Nyní, když jste nahráli dokument PDF, můžete vytvořit textové razítko, které chcete přidat. Jak na to:

```csharp
// Vytvořte textovou vyrovnávací paměť
TextStamp textStamp = new TextStamp("Example Stamp");
```

Výše uvedený kód vytvoří nový textový buffer obsahující zadaný text.

## Krok 4: Konfigurace vlastností textového razítka

Před přidáním textového razítka do dokumentu PDF můžete nakonfigurovat různé vlastnosti razítka, jako je pozadí, poloha, otočení, písmo, velikost atd. Zde je návod:

```csharp
// Nakonfigurujte vlastnosti textové vyrovnávací paměti
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Tyto vlastnosti si můžete upravit podle svých potřeb.

## Krok 5: Přidejte textové razítko do PDF

Nyní, když je textové razítko připraveno, můžete jej přidat na konkrétní stránku dokumentu PDF. Zde je postup:

```csharp
//Přidejte textovou vyrovnávací paměť na konkrétní stránku
pdfDocument.Pages[1].AddStamp(textStamp);
```

Výše uvedený kód přidá textové razítko na první stránku dokumentu PDF. V případě potřeby můžete zadat jinou stránku.

## Krok 6: Uložte výstupní dokument

Jakmile přidáte textové razítko, můžete upravený dokument PDF uložit. Zde je postup:

```csharp
// Uložte výstupní dokument
pdfDocument.Save(dataDir);
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro Přidat textové razítko pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Vytvořte textové razítko
TextStamp textStamp = new TextStamp("Sample Stamp");

// Nastavte, zda je razítko pozadí
textStamp.Background = true;

// Nastavit původ
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Otočit razítko
textStamp.Rotate = Rotation.on90;

// Nastavte vlastnosti textu
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Přidejte razítko na konkrétní stránku
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Uložit výstupní dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Závěr

gratuluji! Naučili jste se přidat textové razítko pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti aplikovat na své vlastní projekty a přidávat do dokumentů PDF vlastní textová razítka.

### Časté dotazy pro přidání textového razítka do souboru PDF

#### Otázka: Jaký je účel přidání textového razítka do souboru PDF pomocí Aspose.PDF pro .NET?

Odpověď: Přidání textového razítka vám umožní umístit vlastní text na konkrétní stránku dokumentu PDF. Tato funkce je užitečná pro přidávání štítků, komentářů, vodoznaků nebo jakýchkoli jiných textových informací pro vylepšení obsahu dokumentu a poskytnutí dalšího kontextu.

#### Otázka: Mohu upravit vzhled textového razítka, jako je písmo, velikost, barva a otočení?

 Odpověď: Ano, vzhled textového razítka si můžete plně přizpůsobit. Poskytnutý zdrojový kód C# ukazuje, jak nastavit různé vlastnosti`TextStamp` objekt, včetně písma, velikosti písma, stylu písma, barvy textu, barvy pozadí a otočení.

#### Otázka: Je možné přidat více textových razítek na různé stránky stejného dokumentu PDF?

Odpověď: Rozhodně můžete přidat více textových razítek na různé stránky stejného dokumentu PDF. Kód poskytnutý výukovým programem vám umožňuje určit cílovou stránku pro přidání textového razítka, takže je univerzální pro různé stránky v dokumentu.

#### Otázka: Jak určím polohu textového razítka v dokumentu PDF?

 Odpověď: Pozici textového razítka můžete upravit úpravou`XIndent` a`YIndent` vlastnosti`TextStamp` objekt. Tyto vlastnosti definují souřadnice levého horního rohu razítka vzhledem k počátku stránky.

#### Otázka: Mohu použít tuto metodu na existující dokumenty PDF a přidat textová razítka?

Odpověď: Ano, tuto metodu můžete použít na existující dokumenty PDF a přidat textová razítka. Kód poskytnutý výukovým programem ukazuje, jak načíst existující dokument PDF a přidat textové razítko na konkrétní stránku.

#### Otázka: Mohu k textovému razítku přidat barvy pozadí i popředí?

 Odpověď: Ano, k textovému razítku můžete přidat barvu pozadí i popředí. Nastavením`Background` majetek do`true` , můžete poskytnout barevné pozadí pro textové razítko. Navíc můžete nastavit`TextState.ForegroundColor` vlastnost k určení barvy samotného textu.

#### Otázka: Jak mohu zajistit, aby textové razítko nezakrývalo základní obsah dokumentu PDF?

 Odpověď: Při přidávání textového razítka dbejte na jeho umístění, abyste zajistili, že nebude bránit kritickým informacím nebo negativně neovlivňovat čitelnost dokumentu. Můžete upravit`XIndent` a`YIndent` vlastnosti pro správné umístění textového razítka.

#### Otázka: Mohu tuto metodu použít k přidání jiných razítek než textu, jako jsou obrázky nebo loga?

Odpověď: Tento konkrétní výukový program se zaměřuje na přidávání textových razítek, ale podobně můžete přidat další typy razítek, jako jsou obrázky nebo loga, pomocí Aspose.PDF pro .NET. Proces zahrnuje vytvoření vhodného objektu razítka a konfiguraci jeho vlastností.

#### Otázka: Jak mohu automatizovat proces přidávání textových razítek do více dokumentů PDF?

Odpověď: Proces přidávání textových razítek do více dokumentů PDF můžete automatizovat vytvořením skriptu nebo programu, který prochází seznam dokumentů a na každý z nich aplikuje stejný proces razítkování textu.