---
title: Vlastní zarážky tabulátoru v souboru PDF
linktitle: Vlastní zarážky tabulátoru v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit vlastní zarážky tabulátoru v PDF pomocí Aspose.PDF pro .NET. Tento tutoriál obsahuje podrobné pokyny pro profesionální zarovnání textu.
type: docs
weight: 120
url: /cs/net/programming-with-text/custom-tab-stops/
---
## Zavedení

Stalo se vám někdy, že jste museli formátovat text v PDF a přáli jste si získat přesnou kontrolu nad tím, jak jsou jednotlivá slova zarovnaná? To je místo, kde se zarážky tabulátoru hodí! Stejně jako v dokumentech aplikace Word můžete použít vlastní zarážky tabulátoru k dokonalému zarovnání textu v konkrétních bodech v PDF. Ať už chcete obsah zarovnat doprava, na střed nebo doleva, Aspose.PDF pro .NET to usnadňuje. V tomto tutoriálu vás provedeme tím, jak nastavit vlastní zarážky tabulátoru v souboru PDF pomocí Aspose.PDF pro .NET. Na konci budete schopni snadno vytvořit krásně zarovnaný dokument.

## Předpoklady

Než začneme, zde je to, co budete muset dodržet:

-  Aspose.PDF for .NET: Budete muset mít nainstalovanou knihovnu Aspose.PDF. Můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).
- Vývojové prostředí .NET: Ujistěte se, že máte Visual Studio nebo jiné IDE nastavené pro spouštění aplikací .NET.
- Základní porozumění C#: Budeme psát kód v C#, takže doporučujeme se s ním trochu seznámit.
-  Dočasná licence: Můžete použít[dočasná licence](https://purchase.aspose.com/temporary-license/)odemknout všechny funkce Aspose.PDF pro .NET.

Jakmile máte vše připraveno, přejděme k importu potřebných balíčků a nastavení prostředí.

## Importujte balíčky

Chcete-li začít, budete muset importovat jmenné prostory Aspose.PDF. Postup:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

 Tyto dva řádky jsou zásadní. The`Aspose.Pdf` jmenný prostor poskytuje strukturu dokumentu, zatímco`Aspose.Pdf.Text` nám poskytuje přístup k funkcím specifickým pro text, jako jsou vlastní zarážky tabulátoru.

Pojďme si rozebrat proces nastavení vlastních zarážek tabulátoru v PDF. Projdeme si každý krok podrobně, abychom se ujistili, že přesně rozumíte tomu, co se děje.

## Krok 1: Vytvořte nový dokument PDF

První věc, kterou musíte udělat, je vytvořit nový dokument PDF. Berte to jako své plátno. Přidáte stránky a poté na ně umístíte svůj formátovaný text.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
```

V tomto úryvku:
-  Vytváříme nový`Document` objekt.
-  Do dokumentu přidáme novou stránku pomocí`Pages.Add()`. Zde vložíme text se zarážkami tabulátoru.

## Krok 2: Nastavení zarážek tabulátoru

Nyní, když máme prázdný dokument, je čas definovat zarážky tabulátoru. Zarážky tabulátoru řídí, jak se text zarovnává na různých pozicích na stránce. Můžete například chtít zarovnat nějaký text doprava a jiný text na střed nebo doleva.

```csharp
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
```

Tady my:
-  Inicializovat a`TabStops` objekt, který bude držet naše vlastní zarážky tabulátoru.
-  Přidejte zarážku tabulátoru na značku 100 pixelů pomocí`ts.Add(100)`. To určuje, kde se karta bude nacházet.
-  Nastavte typ zarovnání na`Right`, což znamená, že text, který narazí na tuto zarážku tabulátoru, bude zarovnán doprava.
- Definujte typ odkazu. Odkazy jsou tečky nebo čárky, které vyplňují prostor před zarážkou tabulátoru. V tomto případě použijeme plnou čáru.

## Krok 3: Přidejte další zarážky tabulátoru

Můžeme přidat tolik zarážek tabulátoru, kolik potřebujeme. V tomto příkladu přidáme kartu zarovnanou na střed a také kartu zarovnanou doleva.

```csharp
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

- Druhá zarážka tabulátoru je nastavena na 200 pixelů se zarovnáním na střed a pomlčkou.
- Třetí zarážka tabulátoru je umístěna na 300 pixelů, zarovnává se doleva a používá tečkovaný odkaz.

## Krok 4: Vytvořte text se zarážkami tabulátoru

Nyní, když jsou zarážky tabulátoru nastaveny, je čas vytvořit nějaký text, který je používá. Tyto zarážky tabulátoru si můžete představit jako neviditelná vodítka, která pomáhají zarovnat váš obsah na různé pozice.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
```

- `TextFragment` představuje kus textu.
- Používáme značky tabulátoru (`#$TAB`), abyste souboru PDF řekli, kde má použít zarážky tabulátoru.
-  Například v`text0`, `#$TABHead1` zarovná se podle první zarážky tabulátoru,`#$TABHead2` zarovná se na druhou a tak dále.

## Krok 5: Přidejte segmenty do textu

 Někdy můžete chtít rozdělit text na více segmentů, z nichž každý má svou vlastní zarážku tabulátoru. Toto je místo`TextSegment` přijde vhod.

```csharp
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
```

V tomto případě:
-  Začínáme s`#$TABdata21`, která se zarovná k první zarážce tabulátoru.
-  Přidáme další segmenty jako`data22` a`data23`, přičemž každá je zarovnána na jiné zarážky tabulátoru.

## Krok 6: Přidejte text na stránku PDF

Nyní, když jsme vytvořili všechny naše textové fragmenty, je čas je přidat na stránku.

```csharp
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

 Tento kód přidá každý`TextFragment`na stránku PDF a ujistěte se, že text je naformátován podle zarážek tabulátoru.

## Krok 7: Uložte dokument PDF

Nakonec musíme dokument uložit do vámi určeného adresáře.

```csharp
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

- Soubor PDF se uloží s použitím vlastních zarážek tabulátoru.
- Zobrazí se zpráva potvrzující úspěšné vytvoření souboru.

## Závěr

A tady to máte! Podle této příručky jste se naučili, jak vytvořit vlastní zarážky tabulátoru v dokumentu PDF pomocí Aspose.PDF for .NET. Zarážky tabulátoru umožňují zarovnat text strukturovaným a vizuálně přitažlivým způsobem, díky čemuž jsou vaše soubory PDF profesionálnější. Ať už zarovnáváte podrobnosti faktury, tabulky nebo jakoukoli jinou formu dat, tato funkce vám dává úplnou kontrolu nad umístěním textu.

## FAQ

### Mohu použít zarážky tabulátoru na existující soubory PDF?  
Ano, existující PDF můžete upravit přidáním vlastních zarážek tabulátoru pro zarovnání textu.

### Jaké typy vedoucích jsou k dispozici?  
Můžete si vybrat z plných, čárkovaných, tečkovaných a dalších typů odkazových čar, které vyplní prostor před zarážkou tabulátoru.

### Mohu přidat více typů zarovnání do jednoho řádku?  
Absolutně! Jak je znázorněno v příkladu, můžete kombinovat zarovnání vpravo, vlevo a na střed ve stejném řádku.

### Existuje omezení počtu zastávek tabulátoru, které mohu přidat?  
Ne, můžete přidat tolik zarážek tabulátoru, kolik potřebujete, aby vyhovovaly vašim požadavkům na design.

### Mohu upravit polohu zarážek tabulátoru?  
Ano, můžete definovat přesnou polohu pixelu pro každou zarážku tabulátoru tak, aby vyhovovala vašemu rozvržení.