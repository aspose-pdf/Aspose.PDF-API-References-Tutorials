---
title: Umístění obrázků
linktitle: Umístění obrázků
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat a manipulovat s umístěním obrázků v dokumentech PDF pomocí Aspose.PDF for .NET. Podrobný průvodce s příklady a úryvky kódu.
type: docs
weight: 170
url: /cs/net/programming-with-images/image-placements/
---
## Zavedení

Práce s obrázky v souborech PDF může být složitá, ale s Aspose.PDF pro .NET můžete snadno manipulovat a extrahovat vlastnosti obrázku, aniž byste se museli zapotit. Ať už chcete získat rozměry obrázku, extrahovat je nebo načíst další vlastnosti, jako je rozlišení, Aspose.PDF má nástroje, které potřebujete. Tento tutoriál vás provede podrobným průvodcem, jak extrahovat umístění obrázků v dokumentu PDF pomocí Aspose.PDF for .NET. Pokryjeme vše od importu balíčků až po načtení vlastností obrázku, jako je šířka, výška a rozlišení.

## Předpoklady

Než se pustíme do výukového programu, je zde několik věcí, které musíte mít na svém místě. Zde je rychlý kontrolní seznam:

1.  Aspose.PDF for .NET: Ujistěte se, že jste nainstalovali knihovnu Aspose.PDF for .NET. Můžete si jej stáhnout[zde](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Budete potřebovat Visual Studio nebo jakékoli jiné IDE podporované .NET na vašem počítači.
3. Dokument PDF: Připravte si vzorový dokument PDF, který obsahuje obrázky. V tomto příkladu použijeme soubor s názvem`ImagePlacement.pdf`.
4. Základní znalost C#: I když je tato příručka vhodná pro začátečníky, základní znalost C# vám pomůže lépe porozumět úryvkům kódu.

## Importujte balíčky

Než se pustíme do hrubky kódu, první věc, kterou musíte udělat, je importovat potřebné jmenné prostory. Tyto balíčky jsou klíčové pro práci s dokumenty PDF a manipulaci s obrázky v Aspose.PDF pro .NET.

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Drawing;
```

Tyto balíčky vám umožňují pracovat s PDF (`Aspose.Pdf`), manipulovat s umístěním obrázků (`Aspose.Pdf.ImagePlacement`) a zpracovávat proudy obrázků a grafiku (`System.Drawing` a`System.IO`).

Nyní, když máme předpoklady a balíčky připravené, pojďme si jednotlivé části výukového programu rozebrat v jednoduchém a srozumitelném průvodci.

## Krok 1: Načtěte dokument PDF

Prvním krokem je načtení dokumentu PDF do vašeho projektu. To bude základem pro práci s obrázky uvnitř souboru PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "ImagePlacement.pdf");
```

 V tomto kroku definujeme cestu k souboru dokumentu PDF pomocí`dataDir` poté vytvoření nové instance souboru`Aspose.Pdf.Document` třída. To nám umožňuje načíst soubor PDF do našeho programu. Jednoduché, že? Stejně jako když otevřete knihu a začnete číst, jsme nyní připraveni prozkoumat obsah uvnitř.

## Krok 2: Inicializujte absorbér umístění obrazu

K extrahování obrázků potřebujeme něco, co se nazývá "Image Placement Absorber". Představte si to jako nástroj, který absorbuje všechny obrazové informace na konkrétní stránce.

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
```

 Zde vytváříme instanci`ImagePlacementAbsorber`. Tento objekt bude shromažďovat a ukládat informace o všech umístěních obrázků na konkrétní stránce PDF. Představte si to jako skenování stránky pomocí lupy a identifikaci všech obrázků na ní!

## Krok 3: Přijměte absorbér na první stránce

Dále musíme sdělit absorbérovi, kterou stránku PDF má naskenovat. V tomto příkladu se zaměříme na první stránku.

```csharp
doc.Pages[1].Accept(abs);
```

 The`Accept` metoda naskenuje první stránku dokumentu PDF, zda neobsahuje žádné obrázky a uloží výsledky dovnitř`ImagePlacementAbsorber`Je to jako říkat lupě, kde má obrázky hledat.

## Krok 4: Projděte každé umístění obrázku

Nyní, když jsme stránku naskenovali, musíme projít každý obrázek nalezený na stránce a načíst jeho vlastnosti.

```csharp
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
    Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
    Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
    Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
    Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
    Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
    Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

Tato smyčka prochází každým obrázkem nalezeným na stránce. Vytiskneme šířku, výšku, x vlevo dole (LLX), y vlevo dole (LLY) a rozlišení obrázku (horizontální i vertikální). Tyto podrobnosti vám pomohou porozumět velikosti a umístění každého obrázku v PDF.

## Krok 5: Extrahujte obrázek s viditelnými rozměry

Po shromáždění informací o obrázcích možná budete chtít extrahovat skutečný obrázek s jeho rozměry. Zde je návod, jak to udělat.

```csharp
Bitmap scaledImage;
using (MemoryStream imageStream = new MemoryStream())
{
    imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
    scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
}
```

 Tento úryvek kódu načte obrázek z PDF a změní jeho měřítko na jeho skutečné rozměry, jak je definováno v`ImagePlacement` objekt. Uložením obrázku do paměťového toku a jeho změnou zajistíte, že si extrahovaný obrázek zachová přesnou velikost, ve které byl zobrazen v PDF.

## Závěr

Extrahování umístění obrázků z dokumentu PDF pomocí Aspose.PDF for .NET je docela jednoduché, jakmile to rozeberete krok za krokem. Pokryli jsme vše od načítání PDF po načtení vlastností obrázku a extrahování obrázků s jejich skutečnými rozměry. Aspose.PDF neuvěřitelně zjednodušuje práci s PDF a manipulaci s obsahem a umožňuje vám efektivně pracovat s obrázky, textem a mnoha dalšími.

## FAQ

### Mohu extrahovat obrázky z konkrétní stránky PDF?  
 Ano, zadáním čísla stránky při použití`Accept` můžete zaměřit na kteroukoli konkrétní stránku.

### Jaké formáty obrázků jsou podporovány pro extrakci?  
Aspose.PDF podporuje různé formáty, včetně PNG, JPEG, BMP a dalších.

### Je možné s extrahovaným obrázkem manipulovat?  
 Absolutně! Po extrahování můžete použít`System.Drawing` jmenný prostor pro manipulaci s obrázkem.

### Mohu extrahovat obrázky ze souborů PDF chráněných heslem?  
Ano, můžete, ale před extrahováním obrázků budete muset PDF odemknout pomocí příslušných přihlašovacích údajů.

### Funguje Aspose.PDF pro .NET na všech .NET frameworkech?  
Ano, podporuje .NET Framework, .NET Core a .NET 5 a vyšší.