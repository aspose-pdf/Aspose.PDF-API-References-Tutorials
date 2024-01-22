---
title: Orientace stránky podle rozměrů obrázku
linktitle: Orientace stránky podle rozměrů obrázku
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce nastavením orientace stránky na základě rozměrů obrázku pomocí Aspose.PDF pro .NET.
type: docs
weight: 80
url: /cs/net/document-conversion/page-orientation-according-image-dimensions/
---
V tomto tutoriálu vás provedeme procesem nastavení orientace stránky na základě rozměrů obrázku pomocí Aspose.PDF for .NET. Projdeme seznam obrázků JPG v daném adresáři a automaticky upravíme orientaci stránky podle šířky každého obrázku. Chcete-li toho dosáhnout, postupujte podle níže uvedených kroků.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Procházejte obrázky JPG
V tomto kroku projdeme všechny obrázky JPG v daném adresáři. Postupujte podle níže uvedeného kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte nový dokument PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Načíst názvy všech souborů JPG v konkrétním adresáři
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde jsou umístěny vaše obrázky JPG.

## Krok 2: Vytvoření stránky a obrázku
Po procházení JPG souborů vytvoříme pro každý soubor stránku a obrázek. Použijte následující kód:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Vytvořte objekt stránky
Aspose.Pdf.Page page = doc.Pages.Add();

// Vytvořte objekt Image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Krok 3: Kontrola rozměrů obrázku
Nyní zkontrolujeme rozměry každého obrázku, abychom určili orientaci stránky. Použijte následující kód:

```csharp
// Chcete-li získat informace ze souboru obrázku, vytvořte objekt BitMap
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Zkontrolujte, zda je šířka obrázku větší než šířka stránky nebo ne
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Pokud je šířka obrázku menší než šířka stránky, nastavte orientaci stránky na výšku
page.PageInfo.IsLandscape = false;
```

## Krok 4: Přidání obrázku do dokumentu PDF
Po kontrole rozměrů obrázku přidáme obrázek do kolekce odstavců PDF dokumentu. Použijte následující kód:

```csharp
// Přidejte obrázek do kolekce odstavců dokumentu PDF
page.Paragraphs.Add(image1);
```

## Krok 5: Uložení souboru PDF
Jakmile přidáme všechny obrázky do dokumentu PDF, můžeme nyní uložit výsledný soubor PDF. Zde je poslední krok:

```csharp
// Uložte soubor PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Nahradit`"YOUR DOCUMENTS DIRECTORY"` s požadovaným adresářem, kam chcete uložit výstupní soubor PDF.

### Příklad zdrojového kódu pro Orientaci stránky podle rozměrů obrázku pomocí Aspose.PDF pro .NET

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Načíst názvy všech souborů JPG v konkrétním adresáři
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Vytvořte objekt stránky
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Vytvořte objekt obrázku
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Vytvořte objekt BitMap, abyste získali informace o souboru obrázku
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Zkontrolujte, zda je šířka souboru obrázku větší než šířka stránky nebo ne
	if (myimage.Width > page.PageInfo.Width)
		// Pokud je šířka obrázku větší než šířka stránky, nastavte orientaci stránky na šířku
		page.PageInfo.IsLandscape = true;
	else
		// Pokud je šířka obrázku menší než šířka stránky, nastavte orientaci stránky na výšku
		page.PageInfo.IsLandscape = false;
	// Přidejte obrázek do kolekce odstavců dokumentu PDF
	page.Paragraphs.Add(image1);
}
// Uložte soubor Pdf
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Závěr
tomto tutoriálu jsme probrali krok za krokem proces nastavení orientace stránky na základě rozměrů obrázku pomocí Aspose.PDF for .NET. Podle výše uvedených pokynů byste nyní měli být schopni vytvořit dokument PDF se správnou orientací stránky pro každý obrázek. Tato funkce je užitečná, když máte obrázky různých velikostí a chcete je vložit do dokumentu PDF.

### FAQ

#### Otázka: Mohu použít jiné formáty obrázků místo JPG pro nastavení orientace stránky na základě rozměrů obrázku?

Odpověď: Ano, pro nastavení orientace stránky na základě rozměrů obrázku můžete kromě JPG použít i další obrazové formáty, jako je PNG, BMP nebo GIF. Poskytnutý kód prochází všechny soubory obrázků s příponou „.JPG“, ale můžete jej upravit tak, aby zahrnoval i jiné formáty obrázků.

#### Otázka: Co se stane, když se rozměry obrázku přesně rovnají šířce stránky?

Odpověď: Pokud je šířka obrázku přesně stejná jako šířka stránky, bude orientace stránky nastavena na výšku. V poskytnutém kódu je orientace stránky nastavena na šířku, pouze pokud je šířka obrázku větší než šířka stránky.

#### Otázka: Mohu přizpůsobit logiku orientace stránky na základě konkrétních požadavků?

Odpověď: Ano, logiku orientace stránky můžete přizpůsobit na základě konkrétních požadavků. Můžete například nastavit prahovou hodnotu pro určení, kdy má být orientace stránky nastavena na šířku nebo na výšku. Kromě toho můžete při určování orientace stránky zvážit faktory, jako je výška obrázku nebo poměr stran.

#### Otázka: Mohu do dokumentu PDF přidat spolu s obrázky další obsah, například text nebo tabulky?

Odpověď: Ano, do dokumentu PDF můžete spolu s obrázky přidat další obsah, například text nebo tabulky. Aspose.PDF for .NET poskytuje bohatou sadu funkcí pro manipulaci s dokumenty PDF, včetně přidávání textu, obrázků, tabulek a dalších prvků na stránky.