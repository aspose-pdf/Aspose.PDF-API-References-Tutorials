---
title: Text V Záhlaví Souboru PDF
linktitle: Text V Záhlaví Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat text do záhlaví souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 190
url: /cs/net/programming-with-stamps-and-watermarks/text-in-header/
---
V tomto tutoriálu se naučíme, jak přidat text do záhlaví souboru PDF pomocí Aspose.PDF pro .NET. Postupujte podle následujících kroků:

## Krok 1: Příprava projektu

Ujistěte se, že jste nainstalovali Aspose.PDF pro .NET a vytvořili projekt C#.

## Krok 2: Import jmenných prostorů

Přidejte do svého zdrojového souboru C# následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Otevření dokumentu

Otevřete existující dokument PDF pomocí uvedené cesty:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 4: Vytvoření textu záhlaví

Vytvořte nové textové razítko s textem, který chcete přidat do záhlaví:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Text můžete přizpůsobit změnou jeho vlastností, jako je horní okraj, vodorovné zarovnání a svislé zarovnání.

## Krok 5: Přidejte text záhlaví na všechny stránky

Projděte všechny stránky dokumentu PDF a přidejte textové razítko do záhlaví:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Krok 6: Uložení dokumentu PDF

Po přidání textu záhlaví na všechny stránky uložte aktualizovaný dokument PDF:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kam chcete uložit dokument PDF.

### Ukázka zdrojového kódu pro Textin Header pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Vytvořit záhlaví
TextStamp textStamp = new TextStamp("Header Text");

// Nastavte vlastnosti razítka
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Přidejte záhlaví na všechny stránky
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Uložit aktualizovaný dokument
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Závěr

gratuluji! Naučili jste se, jak přidat text do záhlaví dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní můžete upravit záhlaví přidáním dalšího textu do dokumentů PDF.

### Časté dotazy pro text v záhlaví souboru PDF

#### Otázka: Jaký je účel přidání textu do záhlaví dokumentu PDF?

Odpověď: Přidání textu do záhlaví dokumentu PDF vám umožní zahrnout důležité informace, jako jsou názvy, názvy dokumentů, data nebo jakýkoli jiný text, který chcete, aby se konzistentně zobrazoval v horní části každé stránky.

#### Otázka: Jak dodaný zdrojový kód C# dosáhne přidání textu do záhlaví dokumentu PDF?

Odpověď: Kód demonstruje proces otevření existujícího dokumentu PDF, vytvoření textového razítka s požadovaným textem záhlaví, přizpůsobení vlastností textu, přidání textového razítka na všechny stránky a nakonec uložení aktualizovaného dokumentu PDF s přidaným textem záhlaví.

#### Otázka: Mohu upravit vzhled textu záhlaví, jako je jeho písmo, velikost, barva a zarovnání?

Odpověď: Ano, vzhled textu záhlaví můžete upravit úpravou vlastností souboru`TextStamp` objekt. Příklad kódu zahrnuje nastavení vlastností, jako je horní okraj, vodorovné zarovnání a svislé zarovnání. Můžete také upravit písmo, velikost, barvu a další vlastnosti související s textem.

#### Otázka: Je možné do záhlaví každé stránky přidat jiný text?

 Odpověď: Ano, do záhlaví každé stránky můžete přidat jiný text vytvořením samostatného textu`TextStamp` objekty s různým textovým obsahem nebo vlastnostmi a poté je podle potřeby přidávat na konkrétní stránky.

#### Otázka: Jak zajistím, aby se text záhlaví zobrazoval konzistentně na každé stránce dokumentu PDF?

Odpověď: Použitím smyčky, která prochází všemi stránkami dokumentu PDF, a přidáním stejného textového razítka na každou stránku zajistíte, že se text záhlaví zobrazí konzistentně na každé stránce.

#### Otázka: Mohu přidat více řádků textu nebo formátovat text záhlaví se zalomením řádků?

 Odpověď: Ano, do záhlaví můžete přidat více řádků textu tak, že do textového řetězce zadáte zalomení řádků. Můžete například použít sekvenci escape`\n` k označení konce řádku v textu.

#### Otázka: Co se stane, když chci do záhlaví a zápatí stejného dokumentu PDF přidat jiný obsah?

Odpověď: Chcete-li přidat jiný obsah do sekcí záhlaví a zápatí, postupujte podobně pro obě sekce. Kód ukazuje přidání textu do záhlaví; můžete použít podobný přístup k přidání textu do zápatí.

#### Otázka: Je možné pomocí tohoto přístupu přidat obrázky nebo jiné prvky vedle textu záhlaví?

Odpověď: I když poskytnutý kód konkrétně demonstruje přidávání textu do záhlaví, můžete tento přístup rozšířit o přidání dalších prvků, jako jsou obrázky, čáry, tvary nebo jakýkoli jiný obsah, do sekce záhlaví pomocí knihovny Aspose.PDF.
