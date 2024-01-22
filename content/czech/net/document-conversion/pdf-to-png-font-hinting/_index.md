---
title: Hinting písem PDF do PNG
linktitle: Hinting písem PDF do PNG
second_title: Aspose.PDF pro .NET API Reference
description: Krok za krokem průvodce převodem PDF do PNG s nápovědou písem pomocí Aspose.PDF pro .NET.
type: docs
weight: 160
url: /cs/net/document-conversion/pdf-to-png-font-hinting/
---
V tomto tutoriálu vás provedeme procesem převodu obrázků PDF na obrázky PNG pomocí Aspose.PDF for .NET, přičemž povolíme napovídání písem. Hinting písma je technika, která zlepšuje čitelnost malých písem. Podle níže uvedených kroků budete moci převést každou stránku PDF na obrázek PNG s náznakem písma.

## Předpoklady
Než začnete, ujistěte se, že splňujete následující předpoklady:

- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.PDF pro .NET nainstalovaná ve vašem systému.
- Vývojové prostředí, jako je Visual Studio.

## Krok 1: Otevření zdrojového dokumentu PDF
V tomto kroku otevřeme zdrojový soubor PDF pomocí Aspose.PDF for .NET. Postupujte podle níže uvedeného kódu:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Otevřete dokument
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečným adresářem, kde se nachází váš soubor PDF.

## Krok 2: Povolte nápovědu k písmu
Po otevření souboru PDF povolíme hintování písem pomocí možností vykreslování. Použijte následující kód:

```csharp
// Vytvořte možnosti vykreslování, abyste povolili nápovědu k písmu
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Krok 3: Převeďte obrázky na PNG
Nyní převedeme každou stránku PDF na obrázek PNG s náznakem písma. Použijte následující kód:

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Vytvořte objekt PNGDevice se zadanými atributy
         // Šířka, výška, rozlišení, kvalita
         // Kvalita [0-100], 100 je maximum
         // Vytvořte objekt rozlišení
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Nastavte předdefinované možnosti vykreslování
         pngDevice.RenderingOptions = opts;

         // Převeďte konkrétní stránku a uložte obrázek do streamu
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Zavřete stream
         imageStream.Close();
     }
}
```

Výše uvedený kód převede každou stránku PDF na obrázek PNG s nápovědou k písmu a uloží každý obrázek jako samostatný soubor PNG.

### Příklad zdrojového kódu pro PDF to PNGFont Hinting pomocí Aspose.PDF pro .NET

```csharp
try
{
	
	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Otevřete dokument
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Vytvořte Aspose.Pdf.RenderingOptions, abyste povolili napovídání písem
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Vytvořte zařízení PNG se zadanými atributy
			// Šířka, výška, rozlišení, kvalita
			// Kvalita [0-100], 100 je maximum
			// Vytvořit objekt rozlišení
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Nastavte předdefinované možnosti vykreslování
			pngDevice.RenderingOptions = opts;

			//Převeďte konkrétní stránku a uložte obrázek do streamu
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Zavřít stream
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Závěr
V tomto tutoriálu jsme se zabývali podrobným procesem převodu obrázků PDF na obrázky PNG pomocí tipování písem pomocí Aspose.PDF for .NET. Podle výše uvedených pokynů byste nyní měli být schopni převést každou stránku PDF na obrázek PNG s nápovědou pro písmo. Tato funkce je užitečná, když chcete zachovat čitelnost malých písem při převodu na obrázky PNG.

### FAQ

#### Otázka: Co je napovídání písem a proč je důležité při převodu PDF do PNG?

Odpověď: Hinting písma je technika používaná ke zlepšení čitelnosti malých písem úpravou jejich tvarů a umístění. Při převodu obrázků PDF na obrázky PNG povolení nápověd k písmu zajistí, že text ve výsledných obrázcích PNG zůstane čitelný a jasný, zejména u malých velikostí písem. To je důležité pro zachování kvality a čitelnosti textu při převodu dokumentů PDF na obrázky.

#### Otázka: Jak nápověda písem ovlivňuje proces převodu PNG?

Odpověď: Nápověda písma ovlivňuje způsob, jakým je text vykreslen ve výsledných obrázcích PNG během procesu převodu PDF do PNG. Povolením napovídání písem upravuje knihovna Aspose.PDF vykreslování písem tak, aby zajistila, že si malá písma zachovají svou jasnost a čitelnost, díky čemuž jsou obrázky PNG vizuálně přitažlivější a čitelnější.

#### Otázka: Mohu upravit nastavení nápověd pro písmo a přizpůsobit převod PNG?

 Odpověď: Ano, knihovna Aspose.PDF for .NET poskytuje možnosti přizpůsobení procesu převodu PNG, včetně nastavení tipování písem. V uvedeném příkladu kódu je`UseFontHinting` vlastnictvím`RenderingOptions` objekt je nastaven na`true` pro aktivaci tipování písem. Proces převodu můžete dále doladit úpravou dalších vlastností v`RenderingOptions` třídy dle vašich požadavků.

#### Otázka: Jak se ukládají obrázky PNG v procesu převodu PNG?

Odpověď: V uvedeném příkladu kódu je každá stránka dokumentu PDF převedena na samostatný obrázek PNG. Obrázky PNG se ukládají jako jednotlivé soubory s názvy souborů podle vzoru "image{pageCount}_ out.png", kde`{pageCount}` je číslo stránky, která se převádí. Každý obrázek PNG představuje jednu stránku původního dokumentu PDF.