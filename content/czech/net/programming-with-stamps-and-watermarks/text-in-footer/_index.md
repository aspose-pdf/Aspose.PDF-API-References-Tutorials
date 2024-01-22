---
title: Text V Zápatí Souboru PDF
linktitle: Text V Zápatí Souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat text do zápatí souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 180
url: /cs/net/programming-with-stamps-and-watermarks/text-in-footer/
---
V tomto tutoriálu se naučíme, jak přidat text do zápatí souboru PDF pomocí Aspose.PDF pro .NET. Postupujte podle následujících kroků:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 4: Vytvořte text zápatí

Vytvořte nové textové razítko s textem, který chcete přidat do zápatí:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Text můžete přizpůsobit změnou jeho vlastností, jako je spodní okraj, vodorovné zarovnání a svislé zarovnání.

## Krok 5: Přidejte text zápatí na všechny stránky

Projděte všechny stránky dokumentu PDF a přidejte textové razítko do zápatí:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## Krok 6: Uložení dokumentu PDF

Po přidání textu zápatí na všechny stránky uložte aktualizovaný dokument PDF:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Nezapomeňte nahradit "VAŠE ADRESÁŘ DOKUMENTŮ" skutečnou cestou k adresáři, kam chcete uložit dokument PDF.

### Ukázkový zdrojový kód pro Textin Footer pomocí Aspose.PDF pro .NET 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Vytvořit zápatí
TextStamp textStamp = new TextStamp("Footer Text");

// Nastavte vlastnosti razítka
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Přidat zápatí na všechny stránky
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Uložte aktualizovaný soubor PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Závěr

gratuluji! Naučili jste se, jak přidat text do zápatí dokumentu PDF pomocí Aspose.PDF pro .NET. Nyní si můžete upravit zápatí přidáním dalšího textu do dokumentů PDF.

### Časté dotazy pro text v zápatí souboru PDF

#### Otázka: Jaký je účel přidání textu do zápatí dokumentu PDF?

Odpověď: Přidání textu do zápatí dokumentu PDF vám umožní zahrnout důležité informace, jako jsou poznámky o autorských právech, čísla stránek, verze dokumentu nebo jakýkoli jiný text, který chcete konzistentně zobrazovat na konci každé stránky.

#### Otázka: Jak dodaný zdrojový kód C# dosáhne přidání textu do zápatí dokumentu PDF?

Odpověď: Kód demonstruje proces otevření existujícího dokumentu PDF, vytvoření textového razítka s požadovaným textem zápatí, přizpůsobení vlastností textu, přidání textového razítka na všechny stránky a nakonec uložení aktualizovaného dokumentu PDF s přidaným textem zápatí.

#### Otázka: Mohu upravit vzhled textu zápatí, jako je jeho písmo, velikost, barva a zarovnání?

 Odpověď: Ano, vzhled textu zápatí můžete upravit úpravou vlastností souboru`TextStamp` objekt. Příklad kódu zahrnuje nastavení vlastností, jako je spodní okraj, vodorovné zarovnání a svislé zarovnání. Můžete také upravit písmo, velikost, barvu a další vlastnosti související s textem.

#### Otázka: Je možné do zápatí každé stránky přidat jiný text?

 Odpověď: Ano, do zápatí každé stránky můžete přidat jiný text vytvořením samostatného textu`TextStamp` objekty s různým textovým obsahem nebo vlastnostmi a poté je podle potřeby přidávat na konkrétní stránky.

#### Otázka: Jak zajistím, aby se text zápatí zobrazoval konzistentně na každé stránce dokumentu PDF?

Odpověď: Použitím smyčky, která prochází všemi stránkami dokumentu PDF, a přidáním stejného textového razítka na každou stránku zajistíte, že se text zápatí zobrazí konzistentně na každé stránce.

#### Otázka: Mohu přidat více řádků textu nebo formátovat text zápatí pomocí zalomení řádků?

 Odpověď: Ano, do zápatí můžete přidat více řádků textu zahrnutím zalomení řádků do textového řetězce. Můžete například použít sekvenci escape`\n` k označení konce řádku v textu.

#### Otázka: Co se stane, když chci do záhlaví a zápatí stejného dokumentu PDF přidat jiný obsah?

Odpověď: Chcete-li přidat jiný obsah do sekcí záhlaví a zápatí, postupujte podobně pro obě sekce. Kód ukazuje přidání textu do zápatí; můžete použít podobný přístup k přidání textu do záhlaví.

#### Otázka: Je možné pomocí tohoto přístupu přidat obrázky nebo jiné prvky vedle textu zápatí?

Odpověď: I když poskytnutý kód konkrétně demonstruje přidávání textu do zápatí, můžete tento přístup rozšířit o přidání dalších prvků, jako jsou obrázky, čáry, tvary nebo jakýkoli jiný obsah, do sekce zápatí pomocí knihovny Aspose.PDF.