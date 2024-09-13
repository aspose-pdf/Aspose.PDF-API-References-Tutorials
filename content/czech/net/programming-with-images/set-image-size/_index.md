---
title: Nastavte velikost obrázku v souboru PDF
linktitle: Nastavte velikost obrázku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit velikost obrázku v PDF pomocí Aspose.PDF pro .NET. Tento podrobný průvodce vám pomůže změnit velikost obrázků, upravit vlastnosti stránky a uložit soubory PDF.
type: docs
weight: 270
url: /cs/net/programming-with-images/set-image-size/
---
## Zavedení

Práce s PDF je běžným požadavkem mnoha aplikací a schopnost manipulovat s prvky v souboru PDF může být zásadní. Ať už vytváříte generátor sestav nebo přidáváte dynamický obsah do PDF, kontrola velikosti obrázků v dokumentu je základní funkcí. V tomto tutoriálu vás provedeme nastavením velikosti obrázku v souboru PDF pomocí Aspose.PDF pro .NET. Tato výkonná knihovna nabízí rozsáhlou kontrolu nad obsahem PDF a my ji krok za krokem rozebereme, abychom vám ukázali, jak snadné to může být. Na konci budete s jistotou měnit velikost obrázků a pochopíte, jak tato funkce může zlepšit vaše pracovní postupy PDF.


## Předpoklady

Než se ponoříme do kódu, je zde několik věcí, které musíte mít na svém místě, abyste je mohli sledovat spolu s tímto tutoriálem.

1.  Aspose.PDF for .NET: Ujistěte se, že máte nainstalovanou nejnovější verzi knihovny Aspose.PDF. Můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).
2. .NET Framework nebo .NET Core: Ujistěte se, že máte pracovní prostředí s nastaveným rozhraním .NET Framework nebo .NET Core.
3. Základní znalost C#: Jako náš programovací jazyk budeme používat C#, takže znalost je nezbytná.
4. Ukázkový obrázek: K vložení do PDF budete potřebovat ukázkový obrázek. Můžete použít libovolný obrázek, ale ujistěte se, že je přístupný v adresáři vašeho projektu.

## Importujte balíčky

Chcete-li použít Aspose.PDF pro .NET, musíte nejprve importovat potřebné jmenné prostory. Zde je jednoduché nastavení:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Nyní, když jsme probrali základy, přejděme k vytváření a úpravám dokumentu PDF.

## Krok 1: Inicializujte svůj dokument PDF

 První věc, kterou musíme udělat, je vytvořit nový dokument PDF. Použijeme`Document` třídy z Aspose.PDF, abyste toho dosáhli.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Objekt okamžitého dokumentu
Document doc = new Document();
```
 
 Zde vytvoříme instanci a`Document` objekt, který bude představovat náš soubor PDF. Také určíme adresář, kde jsou naše soubory umístěny pomocí`dataDir` variabilní. Toto je výchozí bod pro vytváření jakéhokoli PDF pomocí Aspose.PDF.

## Krok 2: Přidejte do svého PDF novou stránku

Jakmile máme náš dokument hotový, musíme do něj přidat stránku. Každý PDF musí mít alespoň jednu stránku, tak si jednu přidejte.

```csharp
// Přidat stránku do kolekce stránek souboru PDF
Aspose.Pdf.Page page = doc.Pages.Add();
```
 
 Do dokumentu přidáme novou stránku pomocí`Pages.Add()` metoda. Tato stránka bude fungovat jako plátno, na které umístíme náš obrázek. Každá stránka v PDF je v podstatě prázdný list, kam můžete přidat text, obrázky nebo jiný obsah.

## Krok 3: Vytvořte instanci obrázku

 Nyní je čas připravit obrázek, který chceme vložit do PDF. Aspose.PDF poskytuje soubor`Image` třídy pro práci s obrázky.

```csharp
// Vytvořte instanci obrázku
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```
 
 Vytvoříme novou instanci`Image` třída. Tento objekt bude obsahovat vlastnosti obrázku, který chceme přidat do PDF. V dalších krocích nakonfigurujeme velikost a typ obrázku.

## Krok 4: Nastavte velikost obrázku (šířku a výšku)

Zde se dostáváme k jádru našeho tutoriálu: nastavení velikosti obrázku. Aspose.PDF umožňuje zadat šířku a výšku obrázku v bodech.

```csharp
// Nastavte šířku a výšku obrázku v bodech
img.FixWidth = 100;
img.FixHeight = 100;
```
 
 The`FixWidth` a`FixHeight`vlastnosti umožňují nastavit přesné rozměry obrázku v bodech. V tomto příkladu měníme velikost obrázku na 100x100 bodů. Tyto hodnoty můžete upravit tak, aby vyhovovaly vašim potřebám.

## Krok 5: Zadejte typ obrázku

V závislosti na formátu obrázku, se kterým pracujete, možná budete muset nastavit typ obrázku. Aspose.PDF podporuje různé formáty obrázků a zde definujeme typ souboru.

```csharp
// Nastavte typ obrázku jako SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
```
 
 V tomto případě ponecháme typ souboru jako`Unknown` , což umožňuje knihovně automaticky detekovat typ obrázku. Pokud znáte konkrétní typ souboru, můžete jej nastavit (např.`ImageFileType.Jpeg` pro obrázky JPEG). Tento krok zajišťuje, že Aspose ví, jak správně zacházet s obrázkem.

## Krok 6: Nastavte cestu k souboru obrázku

Nyní musíme Aspose říct, kde najde soubor obrázku. Ujistěte se, že je váš obrázek přístupný v určeném adresáři.

```csharp
// Cesta ke zdrojovému souboru
img.File = dataDir + "aspose-logo.jpg";
```
 
 Zde nastavíme cestu souboru k obrázku. Obrázek se v tomto případě nachází v`dataDir` složka a je pojmenována`aspose-logo.jpg`Ujistěte se, že jste jej nahradili skutečným názvem a umístěním souboru obrázku.

## Krok 7: Přidejte obrázek na stránku

S nakonfigurovaným obrazem a nastavenou cestou k souboru můžeme nyní přidat obrázek na naši stránku.

```csharp
// Přidejte obrázek do kolekce odstavců
page.Paragraphs.Add(img);
```
 
 The`Paragraphs.Add()` metoda nám umožňuje přidat obrázek na stránku. Myslete na`Paragraphs` kolekce jako seznam položek, které budou vykresleny na stránce PDF. Do této kolekce můžeme přidat více prvků, jako jsou obrázky, text a tvary.

## Krok 8: Upravte vlastnosti stránky

Aby nám obrázek dobře seděl, upravíme velikost stránky. Tím zajistíte, že rozměry stránky budou odpovídat obsahu, který přidáváme.

```csharp
// Nastavte vlastnosti stránky
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```
 
Zde nastavujeme šířku a výšku stránky na 800 bodů. Tento krok je volitelný, ale zajišťuje, že se stránka přizpůsobí obrázku se změněnou velikostí. Tyto hodnoty můžete upravit na základě vašich konkrétních požadavků.

## Krok 9: Uložte soubor PDF

Nakonec, po konfiguraci vlastností obrázku a stránky, můžeme PDF uložit.

```csharp
//Uložte výsledný soubor PDF
dataDir = dataDir + "SetImageSize_out.pdf";
doc.Save(dataDir);
```
 
 Upravený dokument uložíme jako`SetImageSize_out.pdf` ve stejném adresáři. Tento soubor bude nyní obsahovat obrázek se změněnou velikostí, který jste přidali.

## Závěr

V tomto tutoriálu jsme probrali, jak nastavit velikost obrázku v PDF pomocí Aspose.PDF pro .NET. Prošli jsme vytvořením dokumentu, přidáním stránky, konfigurací obrázku a uložením výsledku. Tento průvodce krok za krokem je jen začátek toho, co můžete dělat s Aspose.PDF pro .NET. Nyní, když jste se naučili měnit velikost obrázků, můžete bez obav prozkoumat další funkce, jako je formátování textu, vytváření tabulek a dokonce přidávání anotací do PDF.

## FAQ

### Mohu s Aspose.PDF pro .NET používat různé formáty obrázků?  
Ano, Aspose.PDF podporuje různé formáty obrázků, jako jsou JPEG, PNG, BMP a SVG.

### Jak zachovám poměr stran obrazu?  
 Poměr stran můžete zachovat nastavením buď`FixWidth` nebo`FixHeight` při ponechání druhé dimenze nenastavené.

### Mohu přidat více obrázků na jednu stránku PDF?  
Absolutně! Stačí zopakovat proces přidávání instance obrázku a každou přidat do`Paragraphs` sbírka.

### Je možné nastavit velikost obrázku v jiných jednotkách než v bodech?  
Aspose.PDF pracuje primárně s body, ale můžete převést další jednotky, jako jsou palce nebo milimetry, na body (1 palec = 72 bodů).

### Jak umístím obrázek na konkrétní místo na stránce?  
 Můžete nastavit`Image.LowerLeftX` a`Image.LowerLeftY` vlastnosti pro umístění obrázku na stránku.