---
title: Přidání různých záhlaví do souboru PDF
linktitle: Přidání různých záhlaví do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak snadno přidat různá záhlaví na každou stránku v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 30
url: /cs/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
V tomto tutoriálu vás krok za krokem provedeme přidáním různých záhlaví do souboru PDF pomocí Aspose.PDF pro .NET. Ukážeme vám, jak použít dodaný zdrojový kód C# k přidání vlastních záhlaví na každou stránku souboru PDF.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že máte následující:

- Nainstalované vývojové prostředí .NET.
- Knihovna Aspose.PDF pro .NET stažená a odkazovaná ve vašem projektu.

## Krok 2: Načtení dokumentu PDF

Prvním krokem je načtení stávajícího dokumentu PDF do vašeho projektu. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Otevřete zdrojový dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

## Krok 3: Vytvoření vyrovnávací paměti záhlaví

Nyní, když jste nahráli dokument PDF, můžete vytvořit razítka záhlaví, která chcete přidat. Zde je postup:

```csharp
// Vytvořte tři vyrovnávací paměti záhlaví
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

Výše uvedený kód vytvoří tři nové vyrovnávací paměti záhlaví obsahující zadaný text.

## Krok 4: Konfigurace vlastností vyrovnávací paměti záhlaví

Před přidáním razítek záhlaví do dokumentu PDF můžete pro každé razítko nakonfigurovat různé vlastnosti, jako je zarovnání, velikost, barva atd. Zde je návod:

```csharp
// Nakonfigurujte první vyrovnávací paměť záhlaví
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

// Konfigurace druhé vyrovnávací paměti záhlaví
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

// Nakonfigurujte třetí vyrovnávací paměť záhlaví
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

Tyto vlastnosti můžete upravit podle potřeby pro každou vyrovnávací paměť záhlaví.

## Krok 5: Přidejte razítka záhlaví do PDF

Nyní, když jsou razítka záhlaví připravena, můžete je přidat na každou konkrétní stránku dokumentu PDF. Zde je postup:

```csharp
// Přidejte vyrovnávací paměti záhlaví na konkrétní stránky
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

Výše uvedený kód přidá každé razítko záhlaví na odpovídající stránku dokumentu PDF.

## Krok 6: Uložte výstupní dokument

Jakmile přidáte razítka záhlaví, můžete upravený dokument PDF uložit. Zde je postup:

```csharp
// Uložte aktualizovaný dokument
doc.Save(dataDir);
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázka zdrojového kódu pro přidávání různých záhlaví pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřený zdrojový dokument
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

// Vytvořte tři razítka
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

// Nastavit zarovnání razítka (umístit razítko na horní stranu stránky, vodorovně na střed)
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Zadejte styl písma jako Tučné
stamp1.TextState.FontStyle = FontStyles.Bold;

// Nastavte informaci o barvě pozadí textu jako červenou
stamp1.TextState.ForegroundColor = Color.Red;

// Zadejte velikost písma 14
stamp1.TextState.FontSize = 14;

// Nyní musíme nastavit vertikální zarovnání 2. objektu razítka jako Top
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Nastavte informace o vodorovném zarovnání pro razítko jako Zarovnáno na střed
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Nastavte faktor přiblížení pro objekt razítka
stamp2.Zoom = 10;

//Nastavte formátování objektu 3. razítka
// Zadejte informace o svislém zarovnání pro objekt razítka jako TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

// Nastavte informace o vodorovném zarovnání pro objekt razítka jako Zarovnáno na střed
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

// Nastavte úhel otočení pro objekt razítka
stamp3.RotateAngle = 35;

// Nastavit růžovou jako barvu pozadí pro razítko
stamp3.TextState.BackgroundColor = Color.Pink;

// Změňte informace o písmu pro razítko na Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

// První razítko je přidáno na první stránku;
doc.Pages[1].AddStamp(stamp1);

// Druhé razítko je přidáno na druhou stránku;
doc.Pages[2].AddStamp(stamp2);

// Třetí razítko je přidáno na třetí stranu.
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

// Uložte aktualizovaný dokument
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## Závěr

gratuluji! Naučili jste se, jak přidat různá záhlaví na každou stránku dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti aplikovat na své vlastní projekty a přizpůsobit záhlaví pro své dokumenty PDF.

### Časté dotazy pro přidávání různých záhlaví do souboru PDF

#### Otázka: Jaký je účel přidávání různých záhlaví do souboru PDF pomocí Aspose.PDF pro .NET?

Odpověď: Přidání různých záhlaví do souboru PDF pomocí Aspose.PDF for .NET vám umožní přizpůsobit obsah zobrazený v horní části každé stránky. Tato funkce je užitečná zejména pro přidávání titulků, názvů oddílů, čísel stránek a dalších informací, které se na různých stránkách dokumentu PDF liší.

#### Otázka: Mohu upravit vzhled každého záhlaví, jako je zarovnání, písmo, velikost, barva a otočení?

 Odpověď: Ano, vzhled každého razítka záhlaví můžete plně přizpůsobit. Poskytnutý zdrojový kód C# ukazuje, jak nastavit různé vlastnosti`TextStamp` objekty pro každé záhlaví, včetně vertikálního a horizontálního zarovnání, stylu písma, velikosti písma, barvy písma, barvy pozadí a úhlu otočení.

#### Otázka: Je možné přidat více razítek záhlaví na stejnou stránku dokumentu PDF?

Odpověď: Zatímco poskytnutý výukový program ukazuje přidávání různých záhlaví na různé stránky dokumentu PDF, můžete kód upravit tak, aby na stejnou stránku přidal více razítek záhlaví. To může být užitečné, pokud chcete zobrazit různá záhlaví ve stejné sekci.

#### Otázka: Jak mohu zajistit, aby se záhlaví nepřekrývala s hlavním obsahem stránek PDF?

 A: Chcete-li zabránit překrývání, můžete upravit`VerticalAlignment`, `HorizontalAlignment` a další vlastnosti`TextStamp` objektů. Tato nastavení budou řídit umístění záhlaví na stránce, což vám umožní umístit je tak, aby nepřekážely hlavnímu obsahu.

#### Otázka: Mohu tuto metodu použít k přidání záhlaví do existujících dokumentů PDF s různým počtem stránek?

Odpověď: Ano, poskytnutý zdrojový kód můžete upravit tak, aby přidával záhlaví do stávajících dokumentů PDF s různým počtem stránek. Jednoduše upravte kód tak, aby odpovídal počtu záhlaví, která chcete přidat, a přiřaďte každé záhlaví k požadované stránce.

#### Otázka: Co když chci přidat záhlaví na konkrétní stránky, nejen na první tři stránky?

 Odpověď: Výukový program demonstruje přidávání záhlaví na první tři stránky pro ilustrativní účely. Chcete-li přidat záhlaví na konkrétní stránky nad rámec prvních tří, upravte kód odkazem na odpovídající indexy stránek a vytvořením`TextStamp` objekty pro každou stránku.

#### Otázka: Mohu použít obrázky jako záhlaví místo textu?

 Odpověď: Poskytovaný výukový program se zaměřuje na přidávání textových záhlaví. Můžete však použít podobný přístup k přidání záhlaví založených na obrázcích pomocí`ImageStamp` předměty místo toho`TextStamp` objektů. To by znamenalo vytvoření a konfiguraci`ImageStamp` objekty s požadovanými vlastnostmi.

#### Otázka: Jak mohu použít tyto znalosti k přidání různých zápatí na každou stránku dokumentu PDF?

 Odpověď: Stejný přístup demonstrovaný v tomto kurzu lze použít k přidání různých zápatí na každou stránku dokumentu PDF. Místo záhlaví byste vytvořili a nakonfigurovali`TextStamp` nebo`ImageStamp` objekty a přidejte je na konec každé stránky pomocí`AddStamp` metoda.

#### Otázka: Mohu automatizovat proces přidávání záhlaví do více dokumentů PDF v dávkové operaci?

Odpověď: Ano, proces přidávání záhlaví do více dokumentů PDF můžete automatizovat pomocí skriptu nebo programu, který prochází seznam dokumentů a aplikuje proces razítkování záhlaví na každý dokument.