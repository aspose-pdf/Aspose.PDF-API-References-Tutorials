---
title: Nastavit vlastnost popisku v souboru PDF
linktitle: Nastavit vlastnost popisku v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit vlastnost popisku v souboru PDF pomocí Aspose.PDF pro .NET. Přizpůsobte si anotace pomocí řádků popisků, barvy textu a stylů zakončení.
type: docs
weight: 130
url: /cs/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET je výkonná knihovna pro vytváření, manipulaci a konverzi PDF dokumentů v C#. Jednou z funkcí poskytovaných touto knihovnou je možnost nastavit vlastnosti popisků pro volné textové poznámky v dokumentech PDF. To lze provést pomocí`FreeTextAnnotation` třídy, která umožňuje vytvářet poznámky s popisky.

V tomto tutoriálu vás provedeme procesem nastavení vlastností popisku pro anotaci volného textu pomocí Aspose.PDF pro .NET v C#. Začněte podle následujících kroků.

## Nainstalujte Aspose.PDF pro .NET

 Pokud jste tak ještě neučinili, budete muset[stažení](https://releases.aspose.com/pdf/net/) a nainstalujte Aspose.PDF for .NET z Aspose Releases nebo přes správce balíčků NuGet.

## Krok 1: Vytvořte nový dokument PDF

 Vytvořte nový dokument PDF pomocí`Document`třídy poskytované Aspose.PDF pro .NET.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Krok 2: Přidejte do dokumentu novou stránku

 Přidejte do dokumentu novou stránku pomocí`Pages` sbírka`Document` třída.

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Nastavte výchozí vzhled

 Nastavte výchozí vzhled poznámky s volným textem vytvořením nové`DefaultAppearance` objektu a nastavení jeho vlastností jako např`TextColor` a`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## Krok 4: Vytvořte volnou textovou anotaci s popiskem

 Vytvořte novou anotaci volného textu s popiskem pomocí`FreeTextAnnotation` třída. Nastav`Intent` majetek do`FreeTextIntent.FreeTextCallout` k určení, že se jedná o popisku. Nastav`EndingStyle` majetek do`LineEnding.OpenArrow` k určení stylu šipky na konci popisku. Nastav`Callout` vlastnost do pole`Point` objekty, které představují body na stránce, kde má být nakreslena čára popisku.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## Krok 5: Přidejte na stránku anotaci volného textu

 Přidejte na stránku anotaci volného textu pomocí`Annotations` sbírka`Page` třída.

```csharp
page.Annotations.Add(fta);
```

## Krok 6: Přidejte text do anotace

 Přidejte text do anotace nastavením`RichText`vlastnost na řetězec formátovaného XML. V tomto tutoriálu nastavujeme barvu textu na červenou a velikost písma na 9.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## Krok 7: Uložte dokument

Nyní uložte dokument pomocí následujícího kódu:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Příklad zdrojového kódu pro Set Callout Property pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Toto je ukázka</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Závěr

tomto tutoriálu jsme prozkoumali, jak nastavit vlastnosti popisků pro anotaci volného textu v dokumentu PDF pomocí Aspose.PDF pro .NET. Popisky jsou užitečné pro poskytování dalších informací nebo vysvětlení týkajících se konkrétních oblastí v dokumentu. Aspose.PDF for .NET poskytuje širokou škálu funkcí a možností pro práci se soubory PDF, včetně vytváření a přizpůsobení anotací, jako jsou popisky. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu C# mohou vývojáři snadno implementovat popisky do svých dokumentů PDF, čímž se zlepší použitelnost a srozumitelnost jejich dokumentů. Aspose.PDF for .NET je všestranná a spolehlivá knihovna pro operace PDF v aplikacích .NET, která nabízí výkonné nástroje pro efektivní zpracování různých úloh souvisejících s PDF.

### Časté dotazy pro nastavení vlastnosti popisku v souboru PDF

#### Otázka: Co je popisná anotace v dokumentu PDF?

Odpověď: Popisová anotace v dokumentu PDF je typ anotace, která vám umožňuje vytvořit textové pole s odkazovou čarou směřující do určité oblasti v dokumentu. Běžně se používá k poskytování dalších informací nebo komentářů souvisejících s konkrétní částí nebo prvkem v dokumentu.

#### Otázka: Mohu upravit vzhled popisné poznámky pomocí Aspose.PDF pro .NET?

Odpověď: Ano, můžete přizpůsobit různé vlastnosti popisku, jako je barva, velikost písma, zarovnání textu, styl čáry, styl šipky a další.

#### Otázka: Jak přidám text do popisku?

 A: Chcete-li přidat text k anotaci popisku, můžete nastavit`RichText` vlastnictvím`FreeTextAnnotation` objekt. The`RichText` Vlastnost přebírá řetězec formátovaného XML, který představuje text, který se má zobrazit v anotaci popisku.

#### Otázka: Mohu do dokumentu PDF pomocí Aspose.PDF pro .NET přidat více popisků?

 Odpověď: Ano, můžete vytvořit více popisků v dokumentu PDF vytvořením více instancí souboru`FreeTextAnnotation`objekt a přidat je na různé stránky nebo umístění v dokumentu.