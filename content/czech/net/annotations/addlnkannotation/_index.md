---
title: Přidat anotaci lnk
linktitle: Přidat anotaci lnk
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat inkoustové anotace do souborů PDF pomocí Aspose.PDF for .NET v tomto poutavém podrobném průvodci.
type: docs
weight: 20
url: /cs/net/annotations/addlnkannotation/
---
## Zavedení

Vítejte ve světě manipulace s PDF pomocí Aspose.PDF pro .NET! Pokud chcete vylepšit své dokumenty PDF, ať už pro profesionální použití, osobní projekty nebo cokoli mezi tím, jste na správném místě. Dnes se ponoříme do specifické, ale praktické funkce Aspose.PDF: přidání inkoustové anotace do vašich souborů PDF. Tato funkce může být neuvěřitelně užitečná, když chcete do svých dokumentů přidat ručně psané poznámky nebo podpisy, aby byly interaktivnější a poutavější.

## Předpoklady

Než se ponoříme do kouzelného kódování, ujistěte se, že máte vše, co potřebujete, abyste mohli začít:

1. .NET Framework: Ujistěte se, že máte na svém počítači nainstalováno rozhraní .NET. Tato knihovna bezproblémově funguje s různými verzemi .NET, včetně .NET Core.
2.  Knihovna Aspose.PDF: Budete muset mít staženou knihovnu Aspose.PDF pro .NET a odkazovat na ni ve svém projektu. Pokud jste to ještě neudělali, můžete si stáhnout nejnovější verzi z[odkaz ke stažení](https://releases.aspose.com/pdf/net/).
3. Editor kódu: Můžete použít libovolný editor kódu podle svého výběru, ale Visual Studio je vysoce doporučeno pro snadné použití s aplikacemi .NET.
4. Základní porozumění C#: Pracovní znalost C# vám pomůže hladce procházet příklady kódování.
5. Nastavení vývojového prostředí: Ujistěte se, že je vaše IDE nastaveno tak, aby zpracovávalo projekty .NET a že jste ve svém projektu správně odkazovali na knihovnu Aspose.PDF. 

Když jsou tyto předpoklady splněny, jste připraveni začít přidávat inkoustové anotace do vašich PDF!

## Importujte balíčky

Než se pustíme do kódování, naimportujme potřebné balíčky. V horní části souboru C# přidejte pomocí příkazů následující:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

To vám umožní přístup ke všem třídám a metodám, které potřebujete pro práci s anotacemi PDF.

Nyní, když jsme připravili půdu, je čas vyhrnout si rukávy a pustit se do toho šmrncovního! Rozebereme každý krok, abychom se ujistili, že přesně rozumíte tomu, jak vytvořit a přidat inkoustovou anotaci do vašeho dokumentu PDF.

## Krok 1: Nastavte dokument a adresář

První věc, kterou chcete udělat, je nastavit dokument a cestu, kam chcete výstupní soubor uložit. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 Definujeme proměnnou`dataDir` , který ukazuje na adresář, kam se uloží výsledné PDF. The`Document` objekt se pak vytvoří a vytvoří nový dokument PDF pro úpravy.

## Krok 2: Přidejte do dokumentu stránku

Dále budete chtít přidat stránku do nově vytvořeného dokumentu.

```csharp
Page pdfPage = doc.Pages.Add();
```
Zde přidáváme do našeho dokumentu novou stránku. Každý PDF potřebuje alespoň jednu stránku, takže tento krok je nezbytný.

## Krok 3: Definujte obdélník kreslení

Než budete moci cokoli kreslit, musíte definovat, kam na stránce umístíte svou inkoustovou anotaci.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 Zde vytvoříme a`Rectangle` objekt, který určuje oblast na stránce, kam přidáme naši poznámku inkoustem. Nastavujeme jeho rozměry tak, aby se vešly na celou stránku, počínaje (0,0).

## Krok 4: Připravte inkoustové body

Nyní přichází ta zábavná část – definování bodů, které tvoří vaši inkoustovou anotaci. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
Tento blok kódu vytváří seznam polí bodů, kde každé pole představuje sadu bodů pro váš tah inkoustem. Zde definujeme tři body tvořící trojúhelník; můžete upravit souřadnice tak, aby odpovídaly vašemu návrhu.

## Krok 5: Vytvořte poznámku inkoustem

Když máte definované body, je čas vytvořit skutečnou poznámku inkoustem.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 Vytvoříme instanci`InkAnnotation`objekt, předávání ve stránce, obdélník a inkoustové body. Kromě toho nastavujeme některé vlastnosti jako`Title`, `Color` a`CapStyle`. Přizpůsobte si je tak, aby vyhovovaly vašim potřebám!

## Krok 6: Nastavte okraje a krytí

Chcete, aby vaše anotace vynikla? Dejme tomu styl.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
Zde přidáváme k anotaci ohraničení s konkrétní šířkou a nastavujeme její neprůhlednost, aby byla poloprůhledná.

## Krok 7: Přidejte anotaci na stránku

Nyní, když je vaše anotace připravena, je čas ji přidat na stránku PDF.

```csharp
pdfPage.Annotations.Add(ia);
```
Tento řádek přidá inkoustovou anotaci, kterou jsme vytvořili dříve, do kolekce anotací stránky. 

## Krok 8: Uložte dokument

Nakonec náš upravený dokument uložíme.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 Upravujeme naše`dataDir` zahrnout název výstupního souboru a uložit dokument. Na konzoli se vytiskne potvrzovací zpráva, která vás informuje, že vše proběhlo hladce.

## Závěr

tady to máte! Úspěšně jste přidali inkoustovou anotaci do svého dokumentu PDF pomocí Aspose.PDF pro .NET. Tato jednoduchá, ale účinná funkce může vylepšit vaše dokumenty a učinit je interaktivními. Ať už přidáváte podpisy, poznámky nebo čmáranice, inkoustové anotace poskytují jedinečný způsob, jak obohatit obsah.

## FAQ

### Co je Aspose.PDF?
Aspose.PDF je knihovna pro vytváření, manipulaci a konverzi dokumentů PDF v aplikacích .NET.

### Mohu používat Aspose.PDF zdarma?
 Ano! Aspose nabízí bezplatnou zkušební verzi pro hodnocení svých produktů. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Je možné přidat více inkoustových anotací?
 Absolutně! Můžete vytvořit více`InkAnnotation` objekty a přidejte je na stránku dokumentu.

### Kde najdu další příklady?
 Můžete se podívat na[dokumentace](https://reference.aspose.com/pdf/net/) pro podrobné návody a ukázky.

### Co dělat, když potřebuji podporu?
 Pokud narazíte na nějaké problémy, můžete vyhledat pomoc na[fórum podpory](https://forum.aspose.com/c/pdf/10).