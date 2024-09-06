---
title: Nastavit výchozí název písma
linktitle: Nastavit výchozí název písma
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit výchozí název písma při vykreslování PDF do obrázků pomocí Aspose.PDF for .NET. Tato příručka obsahuje předpoklady, podrobné pokyny a často kladené otázky.
type: docs
weight: 270
url: /cs/net/document-conversion/set-default-font-name/
---
## Zavedení

Zkoušeli jste někdy vykreslit dokument PDF na obrázek, ale zjistili jste, že písma prostě nevypadají správně? Možná se text zdá zkreslený nebo možná není podporováno původní písmo. To je místo, kde nastavení výchozího písma může zachránit den! Pomocí Aspose.PDF for .NET můžete snadno nastavit výchozí písmo pro vykreslování PDF, čímž zajistíte, že váš dokument bude vypadat ostrý a profesionální. V tomto tutoriálu vás provedeme tím, jak nastavit výchozí název písma při vykreslování PDF do obrázku. Na konci této příručky budete mít dovednosti, abyste se vypořádali s jakýmikoli problémy při vykreslování PDF, které vám přijdou do cesty. Připraveni? Pojďme se ponořit!

## Předpoklady

Než se pustíme do kódu, je třeba mít připraveno několik věcí:

- Aspose.PDF for .NET: Tato výkonná knihovna je to, co budeme používat k manipulaci s naším dokumentem PDF. Můžete si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/pdf/net/).
- Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio. Toto bude naše vývojové prostředí.
- .NET Framework: Ujistěte se, že máte nainstalované rozhraní .NET Framework. Aspose.PDF for .NET podporuje různé verze, takže si zkontrolujte dokumentaci, aby odpovídala vašim potřebám.
- Dokument PDF: Budete potřebovat vzorový dokument PDF, se kterým budete pracovat. Pokud jej nemáte, vytvořte si jednoduché PDF nebo si stáhněte ukázku online.

Jakmile máte vše nastaveno, jsme připraveni začít kódovat!

## Importujte balíčky

Než se ponoříme do kódu, je nezbytné naimportovat potřebné balíčky. To zajišťuje, že máme přístup ke všem třídám a metodám, které pro náš projekt potřebujeme.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Tyto importy jsou životně důležité, protože přinášejí požadované jmenné prostory pro manipulaci s PDF, vykreslování obrázků a operace toku souborů.

## Krok 1: Nastavte svůj projekt a cestu k dokumentu

Nejprve nastavíme cestu k adresáři, kde se nachází váš dokument PDF. Toto bude váš výchozí bod pro manipulaci se souborem PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Zde,`dataDir` je adresář, kde se nachází váš dokument PDF. Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu dokumentu. To je nezbytné, protože kód potřebuje vědět, odkud soubor PDF načíst.

## Krok 2: Načtěte dokument PDF

Nyní, když máme cestu k dokumentu, je dalším krokem načtení dokumentu PDF do paměti, abychom na něm mohli začít pracovat.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Používáme`Document` třídy z knihovny Aspose.PDF k načtení našeho souboru PDF. Tato třída poskytuje různé metody a vlastnosti pro práci s dokumentem PDF. The`"input.pdf"` by měl být nahrazen skutečným názvem souboru vašeho PDF. Tento soubor bude použit jako vstup pro renderování.

## Krok 3: Vytvořte obrazový tok pro výstup

Jakmile je dokument načten, musíme nastavit stream pro uložení vykresleného obrázku. Zde bude uložen výstupní obrázek.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 The`FileStream`class se používá k vytvoření nového souboru, do kterého bude uložen vykreslený obrázek. V tomto příkladu ukládáme obrázek jako`"SetDefaultFontName.png"` . The`FileMode.Create` zajišťuje vytvoření nového souboru nebo přepsání existujícího souboru.

## Krok 4: Nastavte rozlišení pro obrázek

Před vykreslením PDF do obrázku je důležité nastavit rozlišení. To určuje kvalitu a čistotu výstupního obrazu.

```csharp
Resolution resolution = new Resolution(300);
```
 The`Resolution` class nastavuje rozlišení výstupního obrazu. Zde jsme zvolili rozlišení 300 DPI (bodů na palec), což je standard pro vysoce kvalitní snímky. To zajistí, že se text a grafika ve vašem PDF vykreslí jasně bez ztráty detailů.

## Krok 5: Nakonfigurujte zařízení PNG

Dále musíme nakonfigurovat zařízení, které bude zpracovávat vykreslování PDF do obrázku PNG.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 The`PngDevice` třída je zodpovědná za vykreslení dokumentu PDF do obrázku PNG. Předáním`resolution` objekt k němu, zajistíme, aby byl obrázek vytvořen se zadaným DPI.

## Krok 6: Nastavte výchozí název písma

Zde je kritická část – nastavení výchozího názvu písma. Toto bude záložní písmo v případě, že původní písmo v PDF není k dispozici.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Vytvoříme instanci`RenderingOptions` a nastavte jej`DefaultFontName` majetek do`"Arial"`. To znamená, že pokud nelze najít původní písmo v PDF, použije se místo něj Arial. Tento krok je zásadní pro zachování čitelnosti a vzhledu textu v renderovaném obrázku.

## Krok 7: Vykreslete stránku PDF na obrázek

Konečně, když je vše nastaveno, můžeme nyní vykreslit první stránku dokumentu PDF do obrázku a uložit jej pomocí streamu souborů, který jsme vytvořili dříve.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 The`Process` metoda`PngDevice` třída se používá k vykreslení zadané stránky PDF (v tomto případě první stránky) do obrázku. Výstup je poté uložen do`imageStream`. Tento krok převede stránku PDF na obrázek PNG se zadaným rozlišením a výchozím písmem.

## Krok 8: Zavřete tok souborů a dokument PDF

Po vykreslení obrázku je nezbytné zavřít proud souboru a dokument PDF, aby se uvolnily zdroje.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Zavírání`imageStream` zajišťuje správné uložení souboru a nedochází ke ztrátě dat. Likvidace`pdfDocument` uvolňuje paměť a zdroje a zabraňuje potenciálním únikům paměti.

## Závěr

A tady to máte! Pomocí několika řádků kódu jste se naučili, jak nastavit výchozí název písma při vykreslování PDF do obrázku pomocí Aspose.PDF for .NET. Tato dovednost je neuvěřitelně užitečná, zejména při práci s PDF, které mohou obsahovat nepodporovaná písma. Nastavením výchozího písma zajistíte, že si vykreslené obrázky zachovají čitelnost a profesionální vzhled.

## FAQ

### Co se stane, když zadané výchozí písmo není v systému nainstalováno?
 Pokud výchozí písmo zadané v`RenderingOptions` není v systému nainstalován, Aspose.PDF použije systémově definovaný záložní font.

### Mohu jako výchozí písmo použít jiná písma než Arial?
Absolutně! Jako výchozí písmo můžete nastavit libovolné písmo nainstalované ve vašem systému.

### Je možné vykreslit více stránek PDF na obrázky najednou?
Ano, můžete procházet stránky vašeho PDF a vykreslovat každou stránku jednotlivě pomocí stejného procesu.

### Ovlivňuje nastavení vysokého rozlišení výkon vykreslování PDF?
Ano, vyšší rozlišení bude mít za následek větší soubory obrázků a může prodloužit dobu vykreslování, ale také vytvoří jasnější obrázky.

### Mohu vykreslit PDF do jiných obrazových formátů kromě PNG?
Ano, Aspose.PDF podporuje vykreslování do různých obrazových formátů, jako jsou JPEG, BMP a TIFF.