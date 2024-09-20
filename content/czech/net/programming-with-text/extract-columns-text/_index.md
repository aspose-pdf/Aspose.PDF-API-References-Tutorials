---
title: Extrahujte text sloupců v souboru PDF
linktitle: Extrahujte text sloupců v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat sloupce textu ze souborů PDF pomocí Aspose.PDF for .NET. Tato příručka rozebírá každý krok s příklady kódu a vysvětleními.
type: docs
weight: 150
url: /cs/net/programming-with-text/extract-columns-text/
---
## Zavedení

Pracujete se soubory PDF a potřebujete extrahovat text ve specifickém formátu sloupců? Ať už zpracováváte faktury, sestavy nebo jakékoli strukturované dokumenty, přesné extrahování textu z PDF může být ošemetná záležitost. Toto je místo, kde Aspose.PDF for .NET postupuje ke zjednodušení procesu. V tomto tutoriálu vás provedeme tím, jak snadno extrahovat sloupce textu ze souboru PDF. 

## Předpoklady

Než se ponoříme do kódu, pojďme si pokrýt základní věci, které budete potřebovat:

-  Aspose.PDF pro .NET: Ujistěte se, že máte nainstalovanou nejnovější verzi Aspose.PDF pro .NET. Pokud ne, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).
- Vývojové prostředí: Pro práci s kódem budete potřebovat Visual Studio nebo jiné vývojové prostředí .NET.
- Dokument PDF: Mějte po ruce vzorový dokument PDF, nejlépe se sloupci textu, protože z něj budeme extrahovat text.

 Pokud jste ještě nenainstalovali Aspose.PDF pro .NET, můžete si stáhnout a[zkušební verze zdarma](https://releases.aspose.com/) nebo[koupit licenci](https://purchase.aspose.com/buy) pro plné funkce. Můžete také požádat o a[dočasná licence](https://purchase.aspose.com/temporary-license) v případě potřeby.

## Importovat jmenné prostory

Chcete-li ve svém projektu použít Aspose.PDF pro .NET, budete muset importovat následující jmenné prostory:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Podrobný průvodce: Extrahujte sloupce textu z PDF

Nyní si rozeberme jednotlivé části kódu, abychom lépe porozuměli tomu, jak funguje. Postupujte podle toho, jak jdeme krok za krokem, a vysvětlete každý segment procesu.

## Krok 1: Načtěte dokument PDF

 První věc, kterou musíte udělat, je načíst soubor PDF do`Document`objekt. Takto Aspose.PDF spolupracuje s vaším dokumentem.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 V tomto kroku jednoduše definujeme adresář, kde je uložen váš dokument PDF. Nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k místnímu souboru PDF. The`Document` objekt načte PDF do paměti a zpřístupní jej pro další zpracování.

## Krok 2: Nastavte absorbér textových fragmentů

 Dále použijeme a`TextFragmentAbsorber` absorbovat nebo zachytit veškerý text ze souboru PDF. Tato třída absorbéru je navržena tak, aby extrahovala fragmenty textu z konkrétních oblastí ve vašem PDF, takže je ideální pro extrahování sloupců textu.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Zde vytvoříme instanci`TextFragmentAbsorber` a použijte jej na všechny stránky PDF pomocí`Accept()` . The`TextFragmentCollection` ukládá extrahovaný text a z této kolekce můžeme manipulovat nebo extrahovat text podle potřeby.

## Krok 3: Upravte velikost písma extrahovaného textu

Jakmile zachytíte fragmenty textu, možná budete chtít zmenšit jejich velikost písma, zvláště když je původní text příliš velký. V tomto příkladu zmenšujeme velikost písma o 70 %.

```csharp
foreach (TextFragment tf in tfc)
{
    // Zmenšit velikost písma o 70 %
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Tento kód prochází každým`TextFragment` v kolekci a zmenší velikost písma o 70 %. Úprava velikosti písma může usnadnit správu extrahovaného textu, zejména pokud jej formátujete pro různé účely.

## Krok 4: Uložte dokument do Memory Stream

 Po úpravě textu uložíme PDF do a`MemoryStream`. To nám umožňuje ponechat dokument v paměti pro další zpracování, aniž bychom jej museli zapisovat zpět na disk.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Zde uložíme PDF do paměťového toku a poté dokument znovu načteme. Tato metoda je užitečná, když pracujete s velkými soubory a chcete se vyhnout zbytečným operacím s diskem.

## Krok 5: Extrahujte veškerý text pomocí Text Absorber

 Nyní, když jsme připravili PDF, je čas rozbalit text. Využijeme`TextAbsorber` k odebrání veškerého textu z dokumentu.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 V tomto kroku se`TextAbsorber` absorbuje veškerý text z PDF a extrahovaný text se uloží do`extractedText` řetězec. Zde se odehrává kouzlo – vaše sloupce textu jsou nyní ve formátu prostého textu!

## Krok 6: Uložte extrahovaný text do souboru

 Nakonec extrahovaný text uložíme do a`.txt` soubor pro snadný přístup a další použití.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Tento kód zapíše extrahovaný text do nového`.txt` soubor a uloží jej do určeného adresáře. V konzole se zobrazí zpráva potvrzující, že proces byl úspěšný.

## Závěr

Tady to máš! Extrahování sloupců textu ze souboru PDF pomocí Aspose.PDF for .NET je jednodušší, než si možná myslíte. Pomocí několika řádků kódu můžete načíst PDF, extrahovat konkrétní text, upravit formátování a uložit výsledky do textového souboru.

Tato technika je neuvěřitelně užitečná pro zpracování strukturovaných dokumentů, jako jsou tabulky, sestavy nebo jakýkoli obsah uspořádaný do sloupců. Ať už potřebujete automatizovat extrakci dat nebo zpracovávat hromadné dokumenty, Aspose.PDF poskytuje nástroje, jak to udělat efektivně.

## FAQ

### Mohu extrahovat text z konkrétních stránek PDF?  
 Ano! Můžete upravit`TextFragmentAbsorber` k cílení na konkrétní stránky pomocí`pdfDocument.Pages[pageIndex].Accept(tfa);` metoda.

### Je možné extrahovat text pouze z jednoho sloupce ve vícesloupcovém PDF?  
 Ano, ale budete muset pracovat se souřadnicemi použitých textových fragmentů`TextFragment.Rectangle` zacílit na konkrétní oblasti dokumentu.

### Jak mohu zlepšit přesnost extrakce textu?  
 Pro lepší přesnost zajistěte, aby byla struktura PDF dobře definovaná a vyhněte se dokumentům se složitým rozvržením. Můžete také doladit`TextFragmentAbsorber` extrahovat text na základě stylů písma, velikostí nebo oblastí.

### Podporuje Aspose.PDF extrakci textu z naskenovaných dokumentů?  
Ano, ale budete muset použít technologii OCR (Optical Character Recognition). Aspose poskytuje nástroje i pro toto.

### Jak zpracuji velké soubory PDF s tisíci stránkami?  
U velkých souborů PDF zpracujte dokument po částech extrahováním textu z několika stránek najednou, abyste se vyhnuli velkému využití paměti.