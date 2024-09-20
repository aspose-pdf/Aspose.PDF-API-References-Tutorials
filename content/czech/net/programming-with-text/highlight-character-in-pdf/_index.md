---
title: Zvýraznit znak v souboru PDF
linktitle: Zvýraznit znak v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se zvýrazňovat znaky v PDF pomocí Aspose.PDF for .NET v tomto podrobném průvodci krok za krokem.
type: docs
weight: 240
url: /cs/net/programming-with-text/highlight-character-in-pdf/
---
## Zavedení

Pokud jde o práci s PDF, často vyvstává potřeba zvýraznit text nebo znaky – ať už pro akademické účely, úpravy nebo jen zlepšení čitelnosti. Představte si, že máte krásný dokument, ale chcete zdůraznit určité části. Zde přichází na scénu zvýraznění! V tomto tutoriálu se ponoříme do toho, jak zvýraznit znaky v souboru PDF pomocí výkonné knihovny Aspose.PDF for .NET. 

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máme vše, co potřebujeme. Zde je to, co budete potřebovat:

1. Vývojové prostředí: Tento kurz předpokládá, že pracujete ve Visual Studiu nebo podobném .NET IDE.
2.  Aspose.PDF for .NET Library: Pokud jste to ještě neudělali, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/) a přidejte jej do svého projektu. 
3. Základní znalost C#: Základní znalost programování v C# vám pomůže snadno pochopit implementaci.
4. Dokument PDF: Měli byste mít připravený vzorový soubor PDF, se kterým budete pracovat. Můžete vytvořit jeden nebo použít existující dokument.

## Import balíčků

Abychom mohli začít, musíme importovat potřebné jmenné prostory. Chcete-li to provést, budete je chtít zahrnout do horní části souboru C#:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Devices;
using Aspose.Pdf.Text;
using System;
using System.Drawing;
```

Tyto balíčky jsou nezbytné pro vytváření, manipulaci a zpracování dokumentů PDF pomocí knihovny Aspose.

Nyní si tento proces rozdělíme na stravitelné kroky pro zvýraznění znaků ve vašem PDF. 

## Krok 1: Inicializujte dokument PDF

Prvním krokem je inicializace dokumentu PDF. To zahrnuje načtení souboru PDF, se kterým budete pracovat. Jak na to:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Ujistěte se, že jste nastavili správnou cestu.
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```
 tomto úryvku nahraďte`YOUR DOCUMENT DIRECTORY` se skutečnou cestou na vašem počítači, kde se nachází váš vstupní soubor PDF. The`Aspose.Pdf.Document` třída je vytvořena pro načtení vašeho PDF.

## Krok 2: Nastavte proces vykreslování

Dále musíme připravit proces vykreslování našeho dokumentu. To je nezbytné pro přesné zvýraznění znaků na stránce.

```csharp
int resolution = 150; // Nastavte rozlišení pro pořizování snímků.
using (MemoryStream ms = new MemoryStream())
{
    PdfConverter conv = new PdfConverter(pdfDocument);
    conv.Resolution = new Resolution(resolution, resolution);
    conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
    Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```
 Definujeme rozlišení pro srozumitelnost, umožňující správné vykreslení textu. The`PdfConverter`změní stránky PDF na obrázky, abychom na ně mohli kreslit.

## Krok 3: Vytvořte grafický objekt pro kreslení

Po nastavení procesu kreslení musíme vytvořit grafický objekt, ve kterém provedeme zvýraznění:

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
    float scale = resolution / 72f; // Faktor měřítka.
    gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
```
Zde vytvoříme grafický objekt z bitmapového obrázku. Transformace pomáhá upravit vykreslování tak, aby správně odpovídalo potřebnému rozlišení.

## Krok 4: Projděte každou stránku a zvýrazněte text

Nyní projdeme každou stránku v PDF a najdeme fragmenty textu, které chceme zvýraznit:

```csharp
for (int i = 0; i < pdfDocument.Pages.Count; i++)
{
    Page page = pdfDocument.Pages[i + 1]; // Stránky jsou indexovány 1 v Aspose.
    TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
    textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
    page.Accept(textFragmentAbsorber);
```
 Přistupujeme ke každé stránce a hledáme veškerý text pomocí`TextFragmentAbsorber` . Vzor regulárního výrazu`@"[\S]+"` zachytí všechny znaky bez mezer.

## Krok 5: Extrahujte textové fragmenty a zvýrazněte

Nyní je čas vyjmout fragmenty textu a zvýraznit je. Tento proces zahrnuje kreslení obdélníků kolem znaků, které chceme zvýraznit:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

foreach (TextFragment textFragment in textFragmentCollection)
{
    // Zde zvýrazněte logiku
    for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
    {
        TextSegment segment = textFragment.Segments[segNum];
        for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
        {
            CharInfo characterInfo = segment.Characters[charNum];
            gr.DrawRectangle(Pens.Black, 
                (float)characterInfo.Rectangle.LLX, 
                (float)characterInfo.Rectangle.LLY, 
                (float)characterInfo.Rectangle.Width, 
                (float)characterInfo.Rectangle.Height);
        }
    }
}
```
Procházíme každý textový fragment, jeho segmenty a jednotlivé znaky a kreslíme kolem nich obdélníky pomocí dříve vytvořeného grafického objektu.

## Krok 6: Uložte upravený obrázek

Po zvýraznění budete muset uložit výsledný obrázek jako nový soubor PNG:

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```
Tento řádek uloží váš upravený bitmapový obrázek jako soubor PNG do určeného adresáře. 

## Krok 7: Zabalte se do zpracování výjimek

Nakonec je dobrým zvykem zabalit kód do bloku try-catch, který zajistí, že všechny neočekávané chyby zvládneme elegantně:

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get a 30-day temporary license from [here](https://purchase.aspose.com/temporary-license/).");
}
```

Tento blok zachycuje všechny výjimky, které mohou nastat během procesu, a poskytuje informativní zpětnou vazbu pro uživatele.

## Závěr

tady to máte! Úspěšně jste zvýraznili znaky v souboru PDF pomocí Aspose.PDF pro .NET. Tato výkonná knihovna otevírá dveře nekonečným možnostem manipulace s PDF – ať už pracujete s anotacemi, vyplňováním formulářů nebo dokonce převodem dokumentů. Jak budete pokračovat na své cestě s Aspose, pamatujte, že praxe je klíčová. Pokračujte v experimentování s různými funkcemi a rychle se z vás stane PDF profesionál!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vytvářet, manipulovat a převádět dokumenty PDF programově v aplikacích .NET.

### Mohu zvýraznit více fragmentů textu najednou?
Ano, poskytnutý kód lze upravit tak, aby zvýraznil více fragmentů procházením celého textu v PDF.

### Existuje bezplatná verze Aspose.PDF?
Ano, Aspose nabízí bezplatnou zkušební verzi, takže si můžete knihovnu před zakoupením vyzkoušet.

### Potřebuji nějaké licence k používání Aspose.PDF?
Ano, pro komerční použití je vyžadována platná licence, ale můžete získat 30denní dočasnou licenci pro testování.

### Kde najdu další dokumentaci?
 Můžete odkazovat na[Dokumentace Aspose.PDF](https://reference.aspose.com/pdf/net/) pro podrobnější informace o implementaci a funkcích.