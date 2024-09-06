---
title: Nastavit výchozí písmo v souboru PDF
linktitle: Nastavit výchozí písmo v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit výchozí písmo v souboru PDF pomocí Aspose.PDF for .NET, pomocí tohoto podrobného průvodce.
type: docs
weight: 280
url: /cs/net/programming-with-document/setdefaultfont/
---
Pokud pracujete s dokumenty PDF v .NET, můžete narazit na problémy, kdy písmo použité v PDF není dostupné v systému, kde je prohlíženo nebo tištěno. To může způsobit, že se text zobrazí nesprávně nebo se nezobrazí vůbec. Aspose.PDF for .NET poskytuje řešení tohoto problému tím, že vám umožňuje nastavit výchozí písmo pro dokument. V tomto příkladu, jak nastavit výchozí písmo pomocí Aspose.PDF pro .NET.

## Krok 1: Nastavte cestu k adresáři dokumentů

musíme nastavit cestu k adresáři, kde se nachází náš PDF dokument. Tuto cestu uložíme do proměnné s názvem „dataDir“.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument PDF

 Začneme načtením existujícího dokumentu PDF, který má chybějící písma. V tomto příkladu budeme předpokládat, že dokument PDF je umístěn v adresáři určeném`dataDir` variabilní.

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    // kód jde sem
}
```

## Krok 3: Nastavte výchozí písmo

 Dále nastavíme výchozí písmo pro dokument PDF pomocí`PdfSaveOptions`třída. V tomto příkladu nastavíme výchozí písmo na "Arial".

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## Krok 4: Uložte aktualizovaný dokument

Nakonec aktualizovaný dokument uložíme do nového souboru. V tomto příkladu uložíme aktualizovaný dokument do souboru s názvem "output_out.pdf" ve stejném adresáři jako vstupní soubor.

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### Příklad zdrojového kódu pro nastavení výchozího písma pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načtěte existující dokument PDF s chybějícím písmem
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	// Zadejte výchozí název písma
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## Závěr

Nastavení výchozího písma v dokumentech PDF pomocí Aspose.PDF for .NET je jednoduchý a efektivní způsob, jak zajistit, aby se text zobrazoval správně, i když původní písma nejsou k dispozici. Podle podrobného průvodce a pomocí dodaného zdrojového kódu C# mohou vývojáři snadno nastavit výchozí písmo a vytvářet soubory PDF, které nabízejí konzistentní a spolehlivý zážitek ze zobrazení v různých prostředích. Tato funkce je užitečná zejména ve scénářích, kde budou soubory PDF zobrazeny nebo vytištěny na různých systémech, které mohou mít nainstalované různé sady písem.

### Časté dotazy pro nastavení výchozího písma v souboru PDF

#### Otázka: Proč je v dokumentech PDF důležité nastavení výchozího písma?

Odpověď: Nastavení výchozího písma v dokumentech PDF je důležité, protože zajišťuje, že se text zobrazí správně, i když původní písma nejsou k dispozici v systému, kde se PDF prohlíží nebo tiskne. Pomáhá předcházet problémům, jako je chybějící nebo zkomolený text, a zajišťuje konzistentní a spolehlivý zážitek ze sledování.

#### Otázka: Mohu si pomocí Aspose.PDF pro .NET vybrat jakékoli písmo jako výchozí?

 Odpověď: Ano, pomocí Aspose.PDF pro .NET si můžete vybrat jakékoli písmo, které je v systému dostupné jako výchozí písmo. Jednoduše zadejte název písma v`DefaultFontName` majetek z`PdfSaveOptions` třída.

#### Otázka: Co se stane, když zadané výchozí písmo není v systému dostupné?

Odpověď: Pokud zadané výchozí písmo není v systému dostupné, prohlížeč PDF použije k zobrazení textu záložní písmo. Je vhodné zvolit běžně dostupný font jako Arial nebo Times New Roman, aby byla zajištěna kompatibilita napříč různými systémy.