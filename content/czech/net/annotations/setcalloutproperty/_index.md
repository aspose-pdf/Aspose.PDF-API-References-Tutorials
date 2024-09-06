---
title: Nastavit vlastnost popisku v souboru PDF
linktitle: Nastavit vlastnost popisku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit vlastnost callout v souboru PDF pomocí Aspose.PDF for .NET v tomto podrobném, podrobném tutoriálu.
type: docs
weight: 130
url: /cs/net/annotations/setcalloutproperty/
---
## Zavedení

Vytváření profesionálních a vizuálně přitažlivých dokumentů PDF často vyžaduje přidání anotací, které upozorňují na konkrétní obsah. Jednou z takových poznámek je popisek, který je jako ty bubliny, které vidíte v komiksech. Pomáhají objasnit nebo zdůraznit text ve vašem PDF. Aspose.PDF for .NET neuvěřitelně usnadňuje přidávání takových anotací do vašich dokumentů a v tomto tutoriálu si projdeme, jak nastavit vlastnost callout v souboru PDF pomocí této výkonné knihovny. Ať už jste zkušený vývojář nebo teprve začínáte, na konci této příručky budete mít jasno v tom, jak pracovat s popisky v souborech PDF.

## Předpoklady

Než se ponoříme do kódu, pojďme si pokrýt to podstatné, co potřebujete, abyste mohli začít.

1.  Aspose.PDF for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF for .NET. Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
2. IDE: Vývojové prostředí, jako je Visual Studio.
3. .NET Framework: Ujistěte se, že máte na svém počítači nainstalováno rozhraní .NET.
4. Dočasná licence: Pokud chcete vyzkoušet všechny funkce Aspose.PDF bez omezení, získejte a[dočasná licence](https://purchase.aspose.com/temporary-license/).

## Importujte balíčky

Než začnete psát kód, musíte importovat potřebné balíčky, které vám umožní pracovat se soubory PDF a anotacemi.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Tyto importy vám poskytnou všechny potřebné třídy a metody pro manipulaci s dokumenty PDF a vytváření anotací, jako je popis.

## Krok 1: Inicializujte dokument PDF

Prvním krokem na naší cestě je inicializace nového dokumentu PDF, do kterého přidáme naši popisku. Berte to jako nastavení prázdného plátna, kde můžete začít přidávat prvky.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializujte nový dokument PDF
Document doc = new Document();
```
 Tady vytváříme nový`Document` objekt, který bude sloužit jako náš soubor PDF. The`dataDir` proměnná je nastavena na adresář, kam chcete uložit soubor PDF poté, co skončíme.

## Krok 2: Přidejte do dokumentu novou stránku

Dokument PDF může mít více stránek a v tomto kroku do našeho dokumentu přidáme novou stránku. Na této stránce bude umístěna naše popisková anotace.

```csharp
//Přidejte do dokumentu novou stránku
Page page = doc.Pages.Add();
```
 The`Pages.Add()`metoda se používá k přidání nové stránky do`doc` objekt. Nová stránka je uložena v`page` proměnnou, kterou později použijeme při přidávání anotace.

## Krok 3: Definujte výchozí vzhled

Poznámky, stejně jako popisky, mají vizuální vzhled, který si můžete přizpůsobit. V tomto kroku definujeme, jak má text v popisku vypadat.

```csharp
// Definujte výchozí vzhled pro anotaci
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Vytváříme a`DefaultAppearance` objekt, který definuje barvu textu a velikost písma. Zde bude text červený a velikost písma je nastavena na 10. Tento vzhled bude aplikován na anotaci popisku.

## Krok 4: Vytvořte anotaci volného textu

Nyní je čas vytvořit skutečnou anotaci. Anotace volného textu nám umožňuje přidat popisek s konkrétním textem a stylem.

```csharp
// Vytvořte FreeTextAnnotation s popiskem
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Vytváříme a`FreeTextAnnotation` objekt s konkrétními souřadnicemi, definujícími jeho polohu na stránce. The`Intent` je nastaveno na`FreeTextCallout` , což znamená, že se jedná o popisku. The`EndingStyle` je nastaveno na`OpenArrow`což znamená, že řádek popisu bude končit otevřenou šipkou.

## Krok 5: Definujte body čáry popisku

Popisek má čáru, která ukazuje na oblast zájmu. Zde definujeme body, které tvoří tuto čáru.

```csharp
// Definujte body pro čáru popisku
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 The`Callout` vlastnost je pole`Point` objekty, z nichž každý představuje souřadnice na stránce. Tyto body definují cestu čáry popisku a dodávají jí klasický vzhled bubliny.

## Krok 6: Přidejte anotaci na stránku

Po vytvoření a konfiguraci naší anotace je dalším krokem její přidání na stránku.

```csharp
// Přidejte na stránku anotaci
page.Annotations.Add(fta);
```
 The`Annotations.Add()` metoda se používá k umístění anotace na stránku, kterou jsme vytvořili dříve. Tento krok efektivně „vykreslí“ popisek na stránku PDF.

## Krok 7: Nastavte obsah RTF

Popisky mohou obsahovat formátovaný text, což umožňuje formátovaný obsah v bublině. Přidejme nějaký ukázkový text.

```csharp
// Nastavte formátovaný text pro anotaci
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;hmotnost písma:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Toto je ukázka</span></p></body>";
```
 The`RichText` vlastnost je nastavena s obsahem HTML. To umožňuje podrobné formátování v popisku, jako je určení velikosti písma, barvy a stylu.

## Krok 8: Uložte dokument PDF

Nakonec po nastavení všeho musíme dokument uložit. Tento krok dokončuje vytvoření PDF s popiskem.

```csharp
// Uložte dokument
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 The`Save()` metoda uloží dokument do zadaného adresáře s názvem "SetCalloutProperty.pdf". Tímto krokem končí náš proces vytváření PDF.

## Závěr

tady to máte! Právě jste vytvořili dokument PDF s popisem pomocí Aspose.PDF pro .NET. Tato anotace může být neuvěřitelně užitečná pro zvýraznění nebo vysvětlení konkrétních částí vašeho dokumentu. Aspose.PDF nabízí výkonné API, díky kterému je manipulace s PDF přímočará a flexibilní. Ať už přidáváte anotace, převádíte dokumenty nebo zpracováváte složité úlohy PDF, Aspose.PDF vám pomůže.

## FAQ

### Mohu si vzhled popisku dále přizpůsobit?

Absolutně! Můžete přizpůsobit různé aspekty, jako je barva čáry, tloušťka a rodina a styl písem textu.

### Je možné přidat více popisků na jednu stránku?

Ano, můžete přidat tolik popisků, kolik potřebujete, opakováním kroků pro každou anotaci.

### Jak změním pozici popisku?

 Jednoduše upravte souřadnice v`Rectangle` a`Callout` vlastnosti pro přemístění anotace.

### Mohu přidat další typy anotací pomocí Aspose.PDF?

Ano, Aspose.PDF podporuje různé typy anotací, včetně zvýraznění, razítek a příloh souborů.

### Je obsah formátovaného textu omezen na HTML?

 The`RichText` vlastnost podporuje podmnožinu HTML, což vám umožňuje zahrnout stylizovaný text a základní formátování.