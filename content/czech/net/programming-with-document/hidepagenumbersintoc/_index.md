---
title: Skrýt čísla stránek v obsahu
linktitle: Skrýt čísla stránek v obsahu
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se skrýt čísla stránek v obsahu pomocí Aspose.PDF for .NET. Chcete-li vytvářet profesionální soubory PDF, postupujte podle tohoto podrobného průvodce s příklady kódu.
type: docs
weight: 220
url: /cs/net/programming-with-document/hidepagenumbersintoc/
---
## Zavedení

Když pracujete s PDF, někdy možná budete chtít vygenerovat obsah (TOC), ale zachovat úhlednost tím, že skryjete čísla stránek. Možná, že dokument plyne lépe bez nich, nebo je to možná estetická volba. Ať už je váš důvod jakýkoli, pokud pracujete s Aspose.PDF pro .NET, tento tutoriál vám přesně ukáže, jak skrýt čísla stránek v obsahu.

## Předpoklady

Než začneme, je několik věcí, které budete potřebovat. Zde je rychlý kontrolní seznam:

- Nainstalované Visual Studio: K kódování budete potřebovat funkční verzi Visual Studia.
- Knihovna Aspose.PDF pro .NET: Ujistěte se, že jste nainstalovali knihovnu Aspose.PDF pro .NET.
  -  Odkaz ke stažení:[Aspose.PDF pro .NET](https://releases.aspose.com/pdf/net/)
- Dočasná licence: Pokud funkce testujete, je užitečné mít dočasnou licenci.
  -  Dočasná licence:[Získejte to zde](https://purchase.aspose.com/temporary-license/)

## Importujte balíčky

Před skokem do kódu se ujistěte, že jste do svého projektu C# importovali následující jmenné prostory. Ty poskytnou nezbytné třídy a metody pro práci s dokumenty PDF a vytváření obsahu (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Nyní, když je vaše prostředí připraveno a balíčky jsou importovány, pojďme si rozebrat jednotlivé kroky procesu. Abychom zajistili srozumitelnost, pokryjeme každou část kódu, abyste jej mohli snadno sledovat.

## Krok 1: Inicializujte svůj dokument PDF

První věc, kterou musíme udělat, je vytvořit nový dokument PDF a přidat stránku pro obsah (TOC).


```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Toto je adresář, kam bude uložen váš výstupní soubor.
- Document(): Inicializuje nový dokument PDF.
- Pages.Add(): Přidá do dokumentu novou prázdnou stránku, která bude později obsahovat váš obsah.

## Krok 2: Nastavte informace o obsahu a název

Dále definujeme informace o obsahu, včetně nastavení názvu, který se zobrazí v horní části obsahu.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Tento objekt obsahuje všechny informace o obsahu.
- TextFragment: Představuje text názvu TOC, zde jej nastavíme jako "Table Of Contents."
- FontStyle: Název obsahu upravíme tak, že nastavíme jeho velikost na 20 a zvýrazníme ho tučným písmem.
- tocPage.TocInfo: Informace o obsahu přiřadíme stránce, která bude zobrazovat obsah.

## Krok 3: Skryjte čísla stránek v obsahu

Nyní k té zábavnější části! Zde nakonfigurujeme obsah tak, aby skryl čísla stránek.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Toto je magický přepínač, který skryje čísla stránek. Nastavte na`false`a čísla stránek se v obsahu nezobrazí.
- FormatArrayLength: Toto jsme nastavili na 4, což znamená, že chceme definovat formátování pro čtyři úrovně nadpisů TOC.

## Krok 4: Přizpůsobte formátování obsahu

Chcete-li přidat více stylu do obsahu, budeme nyní definovat formátování pro různé úrovně nadpisů.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Toto pole řídí formátování položek obsahu. Každý index představuje jinou úroveň nadpisu.
- Margin a TextStyle: Pro každou úroveň nadpisu nastavíme okraje a použijeme styly písma, jako je tučné písmo, kurzíva a podtržení.

## Krok 5: Přidejte nadpisy do dokumentu

Na závěr dodejme skutečné nadpisy, které budou součástí TOC.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Nadpis a textový segment: Představují nadpisy, které se objeví ve vašem obsahu. Každá úroveň má svůj vlastní nadpis.
- IsAutoSequence: Automaticky čísluje nadpisy.
- IsInList: Zajistí, aby se každý nadpis objevil v obsahu.

## Krok 6: Uložte dokument

Jakmile je vše nastaveno, uložte dokument PDF do zadaného výstupního souboru.

```csharp
doc.Save(outFile);
```

A je to! Úspěšně jste vytvořili PDF s obsahem a čísla stránek jsou skrytá!

## Závěr

Vytvoření obsahu v PDF a skrytí čísel stránek se může zdát složité, ale s Aspose.PDF pro .NET je to hračka. Podle tohoto podrobného průvodce jste se naučili, jak přizpůsobit formát obsahu, skrýt čísla stránek a použít různé styly na nadpisy. Nyní můžete vytvářet profesionální soubory PDF přesně na míru vašim potřebám.

## FAQ

### Mohu zobrazit čísla stránek pro konkrétní nadpisy v obsahu?
Ne, Aspose.PDF skryje nebo zobrazí čísla stránek pro celý obsah. Nemůžete je selektivně skrýt pro konkrétní položky.

### Je možné přidat další úrovně do TOC?
 Ano, můžete zvýšit`FormatArrayLength` definovat více úrovní nadpisů TOC.

### Jak mohu změnit písmo pro všechny položky obsahu?
 Písmo můžete změnit úpravou`TextState.Font` vlastnost pro každou úroveň v`FormatArray`.

### Mohu vložit hypertextové odkazy do obsahu?
 Ano, každou položku TOC můžete propojit s konkrétní sekcí v dokumentu pomocí`Heading.TocPage` vlastnictví.

### Potřebuji licenci pro Aspose.PDF?
Ano, pro produkční použití je vyžadována platná licence. Můžete získat dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/) k testování funkcí.