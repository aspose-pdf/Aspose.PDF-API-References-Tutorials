---
title: Nastavit výchozí název písma
linktitle: Nastavit výchozí název písma
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce nastavením výchozího názvu písma v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 270
url: /cs/net/document-conversion/set-default-font-name/
---
tomto tutoriálu vám ukážeme, jak nastavit výchozí název písma v souboru PDF pomocí Aspose.PDF pro .NET. Někdy při extrahování obrázků ze souboru PDF můžete narazit na problémy s chybějícím písmem. Zadáním výchozího názvu písma můžete zajistit, že se extrahovaný text zobrazí správně. Chcete-li nastavit výchozí název písma v souboru PDF, postupujte podle následujících kroků.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Načtení dokumentu PDF
 Prvním krokem je načtení dokumentu PDF do souboru a`Document` objekt. Použijte následující kód:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     // Kód pro přidání
}
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Nastavte výchozí název písma
 Dále nastavíme výchozí název písma pomocí`DefaultFontName` možnost z`RenderingOptions` objekt. Použijte následující kód:

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         // Kód pro přidání
     }
}
```

 Nezapomeňte vyměnit`"Arial"` s požadovaným názvem písma.

## Krok 3: Extrakce obrazu
Dále vyjmeme obrázek ze zadané stránky dokumentu PDF. Použijte následující kód:

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

 Nezapomeňte zadat správné číslo stránky`pdfDocument.Pages[1]`.

### Příklad zdrojového kódu pro Set Default Font Name pomocí Aspose.PDF for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## Závěr
tomto tutoriálu jsme se naučili, jak nastavit výchozí název písma v souboru PDF pomocí Aspose.PDF pro .NET. Zadáním výchozího názvu písma můžete zajistit, že se extrahovaný text zobrazí správně. Tuto metodu použijte k vyřešení problémů s chybějícím písmem při extrahování obrázků ze souborů PDF.

### FAQ

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s dokumenty PDF v aplikacích C#. Nabízí různé funkce, včetně nastavení výchozího názvu písma v souboru PDF.

#### Otázka: Proč bych měl v souboru PDF nastavit výchozí název písma?

Odpověď: Nastavení výchozího názvu písma je užitečné při extrahování textu z dokumentu PDF. Pokud PDF obsahuje text s písmy, která nejsou k dispozici na extrakčním stroji, zadání výchozího názvu písma zajistí správné zobrazení textu.

#### Otázka: Jak mohu načíst dokument PDF a nastavit výchozí název písma pomocí Aspose.PDF pro .NET?

 Odpověď: Chcete-li načíst dokument PDF a nastavit výchozí název písma, můžete použít`Document`třídy k načtení souboru PDF a`RenderingOptions.DefaultFontName` vlastnost k určení požadovaného výchozího názvu písma.

#### Otázka: Mohu si jako výchozí název písma vybrat libovolné písmo?

Odpověď: Ano, jako výchozí název písma si můžete vybrat libovolné písmo, které je dostupné na extrakčním stroji. Použijte písmo, které se co nejvíce shoduje s chybějícími písmy v původním PDF, abyste zajistili přesné vykreslení textu.

#### Otázka: Je nastavení výchozího názvu písma trvalou změnou souboru PDF?

Odpověď: Ne, nastavení výchozího názvu písma pomocí Aspose.PDF pro .NET je dočasná změna provedená během extrakce textu. Nemění původní soubor PDF.