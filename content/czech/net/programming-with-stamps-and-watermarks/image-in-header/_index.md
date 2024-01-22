---
title: Obrázek V Záhlaví
linktitle: Obrázek V Záhlaví
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat obrázek do sekce záhlaví dokumentu PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 140
url: /cs/net/programming-with-stamps-and-watermarks/image-in-header/
---
V tomto tutoriálu vás krok za krokem provedeme přidáním obrázku do záhlaví dokumentu PDF pomocí Aspose.PDF pro .NET. Dodaný zdrojový kód C# použijeme k otevření existujícího dokumentu PDF, vytvoření vyrovnávací paměti obrazu, nastavení jeho vlastností a přidání na všechny stránky dokumentu PDF.

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
Document pdfDocument = new Document(dataDir + "ImageinHeader.pdf");
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kde se nachází váš dokument PDF.

## Krok 3: Vytvoření a přidání obrázku do sekce záhlaví

Nyní, když je dokument PDF načten, můžeme vytvořit obrázkovou vyrovnávací paměť a přidat ji na všechny stránky dokumentu jako sekci záhlaví. Zde je postup:

```csharp
// Vytvořte vyrovnávací paměť snímku
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

// Nastavte vlastnosti vyrovnávací paměti obrázku
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Přidejte vyrovnávací paměť obrázků na všechny stránky
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

Výše uvedený kód vytvoří vyrovnávací paměť obrázku ze souboru "aspose-logo.jpg" a nastaví jeho vlastnosti, jako je horní okraj, horizontální a vertikální zarovnání. Poté se obrazové razítko přidá na všechny stránky dokumentu PDF jako sekce záhlaví.

## Krok 4: Uložení upraveného dokumentu PDF

Jakmile je obrázek přidán do sekce záhlaví, můžeme uložit upravený dokument PDF. Zde je postup:

```csharp
// Uložte upravený dokument PDF
pdfDocument.Save(dataDir + "ImageinHeader_out.pdf");
```

Výše uvedený kód uloží upravený dokument PDF do určeného adresáře.

### Ukázkový zdrojový kód pro Imagein Header pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "ImageinHeader.pdf");

// Vytvořit záhlaví
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

// Nastavte vlastnosti razítka
imageStamp.TopMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Top;

// Přidejte záhlaví na všechny stránky
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageinHeader_out.pdf";

// Uložit aktualizovaný dokument
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in header added successfully.\nFile saved at " + dataDir);                        

```

## Závěr

gratuluji! Naučili jste se, jak přidat obrázek do sekce záhlaví dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete upravit záhlaví svých dokumentů PDF přidáním obrázků.

### Časté dotazy k obrázku v záhlaví

#### Otázka: Jaký je účel přidání obrázku do části záhlaví dokumentu PDF?

Odpověď: Přidání obrázku do sekce záhlaví dokumentu PDF vám umožní zahrnout vizuální prvky, jako je logo nebo branding, v horní části každé stránky. To může zlepšit celkový vzhled a dojem z obsahu PDF.

#### Otázka: Jak dodaný zdrojový kód C# dosáhne přidání obrázku do sekce záhlaví dokumentu PDF?

 Odpověď: Poskytnutý kód ukazuje, jak načíst existující dokument PDF, vytvořit soubor`ImageStamp` objekt ze souboru obrázku, nastavte vlastnosti, jako je horní okraj a zarovnání, a poté přidejte razítko obrázku do záhlaví všech stránek.

#### Otázka: Mohu upravit polohu a zarovnání obrázku v sekci záhlaví?

 Odpověď: Ano, můžete upravit polohu a zarovnání obrázku v sekci záhlaví úpravou vlastností souboru`ImageStamp` objekt. Fragment kódu nastavuje vlastnosti jako např`TopMargin`, `HorizontalAlignment` , a`VerticalAlignment`.

#### Otázka: Je možné přidat různé obrázky do sekce záhlaví na různých stránkách dokumentu PDF?

 Odpověď: Ano, můžete přidat různé obrázky do sekce záhlaví na různých stránkách vytvořením samostatných`ImageStamp` objektů s různými obrazovými soubory a vlastnostmi a poté je přidat na konkrétní stránky.

#### Otázka: Jak kód zajistí, aby byl obrázek přidán na všechny stránky záhlaví dokumentu PDF?

Odpověď: Poskytnutý kód používá a`foreach` smyčkou pro iteraci všech stránek dokumentu PDF a přidá to samé`ImageStamp`do sekce záhlaví každé stránky.

#### Otázka: Mohu přidat další prvky, jako je text nebo tvary, do sekce záhlaví pomocí podobného přístupu?

 Odpověď: Ano, do sekce záhlaví můžete přidat další prvky, jako je text nebo tvary, pomocí podobného přístupu vytvořením příslušných objektů razítka (např.`TextStamp`) a podle toho nastavit jejich vlastnosti.

#### Otázka: Jak určím cestu k souboru obrázku, který chci přidat do záhlaví?

 Odpověď: Cesta k souboru obrázku je určena při vytváření souboru`ImageStamp` objekt, jak je uvedeno v kódu. Ujistěte se, že jste zadali správnou cestu k souboru obrázku.

#### Otázka: Mohu upravit velikost obrázku v sekci záhlaví?

 Odpověď: Ano, můžete upravit velikost obrázku v sekci záhlaví úpravou rozměrů`ImageStamp` pomocí vlastností jako`Width` a`Height`.

#### Otázka: Je možné odstranit nebo nahradit obrázek v záhlaví poté, co byl přidán?

 Odpověď: Ano, můžete odstranit nebo nahradit obrázek v sekci záhlaví úpravou obsahu souboru`ImageStamp` objekt nebo odstranění razítka z konkrétních stránek.

#### Otázka: Jak kód zpracovává scénáře, kdy rozměry obrázku přesahují dostupné místo v záhlaví?

 A: Kód nastavuje vlastnosti jako např`TopMargin`, `HorizontalAlignment` , a`VerticalAlignment` pro ovládání umístění a zarovnání obrazu. Ujistěte se, že tyto vlastnosti jsou upraveny tak, aby se předešlo problémům s překrýváním nebo rozvržením.
