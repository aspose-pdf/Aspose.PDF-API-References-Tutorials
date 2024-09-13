---
title: Přesunout pole formuláře
linktitle: Přesunout pole formuláře
second_title: Aspose.PDF pro .NET API Reference
description: této příručce se dozvíte, jak přesouvat pole formuláře v dokumentech PDF pomocí Aspose.PDF for .NET. Chcete-li snadno upravit umístění textových polí, postupujte podle tohoto podrobného návodu.
type: docs
weight: 200
url: /cs/net/programming-with-forms/move-form-field/
---
## Zavedení

Úprava polí formuláře v dokumentech PDF se může na první pohled zdát složitá, ale s Aspose.PDF pro .NET je to hračka! Ať už pracujete na přemístění textových polí, dolaďování rozvržení nebo nastavování interaktivních prvků, Aspose.PDF nabízí výkonné řešení pro vaše .NET projekty. V tomto tutoriálu vás provedeme kroky k přesunutí pole formuláře v dokumentu PDF pomocí Aspose.PDF for .NET.

## Předpoklady

Než začneme, zde je několik věcí, které budete potřebovat:

1. Aspose.PDF for .NET nainstalovaný ve vašem vývojovém prostředí.
2. Soubor PDF, který obsahuje pole formuláře (v tomto případě textové pole), které má být upraveno.
3. Základní znalost programování v C#.
4. Visual Studio nebo jiné vývojové prostředí C#.

### Instalace Aspose.PDF pro .NET

 Nejnovější verzi Aspose.PDF pro .NET si můžete stáhnout z webu[Aspose stránku ke stažení](https://releases.aspose.com/pdf/net/)Po stažení jej můžete nainstalovat pomocí NuGet ve Visual Studiu spuštěním následujícího příkazu:

```bash
Install-Package Aspose.PDF
```

 Budete také muset získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) nebo zakoupit licenci od[Aspose obchod](https://purchase.aspose.com/buy).

## Importujte balíčky

Než budete moci používat Aspose.PDF, budete muset do kódu C# importovat požadované jmenné prostory:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
```

Tyto balíčky vám umožní přístup k základním funkcím manipulace s dokumenty PDF a specifickým funkcím formuláře, které potřebujete.

Nyní, když je vše připraveno, pojďme si projít proces přesunutí pole formuláře v dokumentu PDF pomocí Aspose.PDF for .NET.

## Krok 1: Nastavte svůj projekt a načtěte dokument PDF

První věc, kterou musíte udělat, je nastavit projekt a načíst soubor PDF, který obsahuje pole formuláře, které chcete upravit. Jak na to:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

 Tento kód inicializuje dokument jeho načtením ze zadaného adresáře. Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k souboru, kde je váš PDF uložen. Tento soubor PDF by měl obsahovat alespoň jedno pole formuláře, se kterým můžete pracovat.

## Krok 2: Otevřete pole formuláře, které chcete přesunout

Po načtení PDF je dalším krokem přístup k poli formuláře, které chcete přesunout. V tomto případě přesouváme pole formuláře textového pole, ale tuto metodu lze použít i na jiné typy polí formuláře.

```csharp
// Získejte pole formuláře podle názvu (v tomto případě „textbox1“)
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

 Zde přistupujeme k poli formuláře s názvem`"textbox1"`. Ujistěte se, že znáte název pole formuláře, se kterým chcete manipulovat, nebo můžete v případě potřeby použít jiné techniky k výpisu nebo prohledávání polí formuláře.

## Krok 3: Upravte umístění pole

Nyní přichází ta vzrušující část: přesunutí pole formuláře! Toho docílíme úpravou jeho pravoúhlých hranic, které definují polohu a velikost pole formuláře na stránce.

```csharp
// Upravit umístění pole formuláře (nové souřadnice)
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

Ve výše uvedeném řádku kódu nastavíme polohu textového pole definováním souřadnic jeho obdélníku. Čísla představují levý dolní a pravý horní roh obdélníku (`300, 400, 600, 500`). Tyto hodnoty můžete přizpůsobit podle toho, kde se má pole na stránce zobrazovat.

## Krok 4: Uložte upravený dokument

Po přesunutí pole formuláře je posledním krokem uložení upraveného PDF. Můžete jej uložit pod novým názvem, abyste předešli přepsání původního dokumentu.

```csharp
// Uložte aktualizovaný dokument PDF
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

Dokument bude uložen do stejného adresáře s aktualizovaným názvem (`MoveFormField_out.pdf`). Po uložení můžete soubor otevřít a potvrdit, že pole formuláře bylo přesunuto na požadované místo.

## Závěr

 Přesouvání polí formuláře v rámci PDF pomocí Aspose.PDF for .NET je jednoduché, jakmile pochopíte základy práce s`Rectangle` objektová a formulářová pole. Pomocí výše uvedeného kódu můžete snadno upravit polohu libovolného pole formuláře, což vám pomůže přizpůsobit rozvržení PDF a interakce s uživatelem.

## FAQ

### Mohu pomocí této metody přesunout jiné typy polí formuláře?
Ano, můžete přesunout libovolné pole formuláře, včetně zaškrtávacích políček, přepínacích tlačítek a podpisů, pomocí stejné metody přístupem ke konkrétnímu typu pole.

### Jak mohu získat názvy všech polí formuláře v PDF?
 Pomocí polí formuláře můžete iterovat`pdfDocument.Form.Fields` zobrazíte všechna pole formuláře a jejich názvy.

### Co když chci změnit velikost pole formuláře místo jeho přesunutí?
 Můžete upravit umístění i velikost úpravou`Rectangle` šířku a výšku objektu při nastavování nových souřadnic.

### Potřebuji licenci k používání Aspose.PDF pro .NET?
 Ano, Aspose.PDF vyžaduje licenci pro produkční použití, ale můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro účely hodnocení.

### Mohu přesunout více polí formuláře najednou?
 Ano, přístupem ke každému poli formuláře a jeho úpravou`Rect` vlastnost, můžete přesunout více polí současně.