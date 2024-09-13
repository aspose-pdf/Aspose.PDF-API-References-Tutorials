---
title: Informace o obrázku v souboru PDF
linktitle: Informace o obrázku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se extrahovat obrazové informace z PDF pomocí Aspose.PDF for .NET s naším komplexním průvodcem krok za krokem.
type: docs
weight: 160
url: /cs/net/programming-with-images/image-information/
---
## Zavedení

Soubory PDF jsou v dnešní době všude – prakticky každý profesionální a osobní dokument si v určitém okamžiku najde cestu do tohoto formátu. Ať už se jedná o zprávu, brožuru nebo e-knihu, pochopení toho, jak s těmito soubory programově pracovat, nabízí nespočet možností. Jedním z běžných požadavků je extrahovat obrazové informace ze souborů PDF. V této příručce se ponoříme do toho, jak používat knihovnu Aspose.PDF pro .NET k extrahování důležitých podrobností o obrázcích vložených do dokumentu PDF.

## Předpoklady

Než se pustíme do hrubky kódování, musíte mít splněno několik předpokladů:

1. Vývojové prostředí: Budete potřebovat nastavit vývojové prostředí .NET. Může to být Visual Studio nebo jakékoli jiné IDE kompatibilní s .NET.
2.  Knihovna Aspose.PDF: Ujistěte se, že máte přístup ke knihovně Aspose.PDF. Můžete si jej stáhnout z[Aspose webové stránky](https://releases.aspose.com/pdf/net/). 
3. Základní znalost C#: Znalost jazyka C# a objektově orientovaného programování vám pomůže bez námahy sledovat výukový program.
4. Dokument PDF: Mějte po ruce vzorový dokument PDF, který obsahuje obrázky pro testování kódu. 

## Import balíčků

Abyste mohli začít používat knihovnu Aspose.PDF, budete muset do souboru C# importovat potřebné jmenné prostory. Zde je rychlý přehled:

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Tyto jmenné prostory vám poskytnou přístup k požadovaným třídám a metodám pro manipulaci se soubory PDF a extrahování obrazových dat.

Nyní, když máte vše nastaveno, je čas to rozdělit do zvládnutelných kroků. Napíšeme C# program, který načte PDF dokument, projde každou stránku a extrahuje rozměry a rozlišení každého obrázku v dokumentu.

## Krok 1: Inicializujte dokument

 V tomto kroku inicializujeme dokument PDF pomocí cesty k vašemu souboru PDF. Měli byste vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kde se nachází váš soubor PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načtěte zdrojový soubor PDF
Document doc = new Document(dataDir + "ImageInformation.pdf");
```
 Vytváříme a`Document` objekt, který načte PDF ze zadaného adresáře. To nám umožní pracovat s obsahem souboru.

## Krok 2: Nastavte výchozí rozlišení a inicializujte datové struktury

Dále nastavíme výchozí rozlišení obrázků, což je užitečné pro výpočty. Připravíme také pole pro názvy obrázků a zásobník pro správu grafických stavů.

```csharp
// Definujte výchozí rozlišení obrázku
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Definujte objekt seznamu polí, který bude obsahovat názvy obrázků
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```
 The`defaultResolution` proměnná nám pomáhá správně vypočítat rozlišení obrázků. The`graphicsState`zásobník slouží jako prostředek k uložení aktuálního grafického stavu dokumentu, když narazíme na transformační operátory.

## Krok 3: Zpracujte každého operátora na stránce

Nyní projdeme všechny operátory na první stránce dokumentu. Zde dochází k těžkému zvedání. 

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Operátoři procesu...
}
```
Každý operátor v souboru PDF je příkaz, který říká rendereru, jak spravovat grafické prvky, včetně obrázků.

## Krok 4: Obsluha operátorů GSave/GRestore

Uvnitř smyčky budeme zpracovávat příkazy pro ukládání a obnovu grafiky, abychom mohli sledovat změny provedené v grafickém stavu.

```csharp
if (opSaveState != null) 
{
    // Uložit předchozí stav
    graphicsState.Push(((Matrix)graphicsState.Peek()).Clone());
} 
else if (opRestoreState != null) 
{
    // Obnovit předchozí stav
    graphicsState.Pop();
}
```
`GSave` uloží aktuální grafický stav, zatímco`GRestore` obnovuje poslední uložený stav, což nám umožňuje vrátit jakékoli transformace při zpracování obrázků.

## Krok 5: Správa transformačních matic

Dále se zabýváme zřetězením transformačních matic při aplikaci transformací na obrázky.

```csharp
else if (opCtm != null) 
{
    Matrix cm = new Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);
    
    ((Matrix)graphicsState.Peek()).Multiply(cm);
    continue;
}
```
Když je použita transformační matice, vynásobíme ji aktuální maticí uloženou v grafickém stavu, abychom mohli sledovat jakékoli změny měřítka nebo translace aplikované na obrázek.

## Krok 6: Extrahujte informace o obrázku

Nakonec zpracujeme operátora výkresu pro obrázky a extrahujeme potřebné informace, jako jsou rozměry a rozlišení.

```csharp
else if (opDo != null) 
{
    // Operátor Handle Do, který kreslí objekty
    if (imageNames.Contains(opDo.Name)) 
    {
        Matrix lastCTM = (Matrix)graphicsState.Peek();
        XImage image = doc.Pages[1].Resources.Images[opDo.Name];
        double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
        double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
        double originalWidth = image.Width;
        double originalHeight = image.Height;
        
        double resHorizontal = originalWidth * defaultResolution / scaledWidth;
        double resVertical = originalHeight * defaultResolution / scaledHeight;
        
        // Vypište informace
        Console.Out.WriteLine(string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
                         opDo.Name, scaledWidth, scaledHeight, resHorizontal, resVertical));
    }
}
```
Zde zkontrolujeme, zda je za kreslení obrázku odpovědný operátor. Pokud ano, získáme odpovídající objekt XImage, vypočítáme jeho zmenšené rozměry a rozlišení a vytiskneme potřebné informace.

## Závěr

Gratuluji! Právě jste vytvořili funkční příklad, jak extrahovat informace o obrázku ze souboru PDF pomocí Aspose.PDF for .NET. Tato schopnost může být neuvěřitelně užitečná pro vývojáře, kteří potřebují analyzovat nebo manipulovat s dokumenty PDF pro různé aplikace, jako je vytváření sestav, extrakce dat nebo dokonce vlastní prohlížeče PDF. 


## FAQ

### Co je to knihovna Aspose.PDF?
Knihovna Aspose.PDF je výkonný nástroj pro vytváření, manipulaci a konverzi souborů PDF v aplikacích .NET.

### Mohu používat knihovnu zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Jaké typy obrazových formátů lze extrahovat?
Knihovna podporuje různé formáty obrázků, včetně JPEG, PNG a TIFF, pokud jsou vložené do PDF.

### Používá se Aspose pro komerční účely?
 Ano, produkty Aspose můžete používat komerčně. Pro licencování navštivte[nákupní stránku](https://purchase.aspose.com/buy).

### Jak získám podporu pro Aspose?
 Můžete vstoupit do fóra podpory[zde](https://forum.aspose.com/c/pdf/10).