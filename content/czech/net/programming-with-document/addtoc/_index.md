---
title: Přidat TOC do souboru PDF
linktitle: Přidat TOC do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat obsah do PDF pomocí Aspose.PDF for .NET. Tento průvodce krok za krokem zjednodušuje proces a zajišťuje snadnou navigaci ve vašich dokumentech.
type: docs
weight: 40
url: /cs/net/programming-with-document/addtoc/
---
## Zavedení

Už jste někdy donekonečna listovali dlouhým PDF a přáli si, aby měl dobře uspořádaný obsah? No, dnes je váš šťastný den! V tomto tutoriálu se naučíte, jak přidat TOC do souboru PDF pomocí Aspose.PDF pro .NET. Ať už pracujete na komplexní zprávě, elektronické knize nebo obchodním návrhu, TOC může přeměnit váš dokument na profesionální mistrovské dílo, které lze snadno ovládat.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše, co potřebujete:

1. Aspose.PDF for .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu Aspose.PDF. Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
   
2. Vývojové prostředí: Ujistěte se, že máte na svém počítači nastavené vývojové prostředí .NET, jako je Visual Studio.

3.  Licence: Pokud nemáte licenci, můžete získat bezplatnou zkušební verzi nebo požádat o dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/).

## Importujte balíčky

Chcete-li začít, nezapomeňte importovat potřebné jmenné prostory na začátku souboru kódu. Zde je postup:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Tyto jmenné prostory umožňují přístup k funkcím specifickým pro PDF a manipulaci s textovými prvky v dokumentu.

Pojďme si tento úkol rozdělit na malé kroky. Každý krok vás provede procesem vytváření a vkládání obsahu do vašeho dokumentu PDF.

## Krok 1: Načtěte dokument PDF

První věc, kterou musíme udělat, je načíst existující soubor PDF, kam chceme přidat obsah.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 V tomto kroku určíme cestu k adresáři dokumentu a načteme PDF pomocí`Document` objekt. Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu souboru.

## Krok 2: Vložte novou stránku pro TOC

Dále vložíme novou stránku na začátek dokumentu PDF. Tato stránka bude hostit obsah.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

Vložením stránky obsahu na začátek zajistíme, že se zobrazí jako úplně první věc, kterou čtenáři v PDF uvidí.

## Krok 3: Vytvořte objekt TOC Information Object

Nyní vytvoříme objekt, který bude reprezentovat informace TOC. Do obsahu také přidáme název, aby vynikl.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Zde jsme nastavili název obsahu jako „Table Of Contents“, zvětšili jsme velikost písma a zdůraznili ho tučným písmem.

## Krok 4: Definujte prvky TOC

V tomto kroku definujeme prvky (nebo nadpisy), které se budou zobrazovat v TOC. Tyto prvky pomohou čtenářům přejít do konkrétních částí dokumentu.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Vytvořili jsme pole řetězců, které budou sloužit jako naše položky obsahu odpovídající různým stránkám v PDF.

## Krok 5: Vytvořte nadpisy obsahu

Nyní přichází klíčová část – přidání nadpisů do obsahu a jejich propojení s příslušnými stránkami.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Zde je to, co se děje:
- Nadpis: Vytváříme a`Heading` objekt a přidejte a`TextSegment` k tomu.
- Cílová stránka: Nastavíme stránku, na kterou bude odkazovat každý nadpis.
- Horní pozice: Určujeme pozici na stránce, kam bude nadpis ukazovat.
- Text: Každý nadpis získá svůj příslušný název z pole, které jsme vytvořili dříve.

Tato smyčka vytváří nadpisy pro první dva prvky v obsahu a spojuje je s odpovídajícími stránkami.

## Krok 6: Uložte soubor PDF s obsahem

Nakonec, když jsme přidali všechny prvky TOC, je čas uložit aktualizované PDF.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Soubor je nyní uložen s obsahem přidaným do PDF. Gratulujeme – úspěšně jste přidali obsah!

## Krok 7: Potvrzující zpráva

Aby uživatel věděl, že proces je dokončen, zobrazíme v konzole jednoduchou zprávu.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Závěr

tady to máte! S Aspose.PDF pro .NET je přidání obsahu do PDF nejen snadné, ale také přizpůsobitelné. Ať už potřebujete vytvořit jednoduché navigační odkazy nebo složité struktury, tento nástroj vás pokryje. Takže až budete příště pracovat na zdlouhavém PDF, nezapomeňte přidat TOC pro profesionální dotek!

## FAQ

### Mohu upravit vzhled obsahu v Aspose.PDF?  
Ano, můžete si plně přizpůsobit vzhled obsahu, včetně stylu písma, velikosti a zarovnání.

### Jak přidám podnadpisy do obsahu?  
 Podnadpisy můžete přidat úpravou`Heading` úroveň (např.`Heading(2)`) vytvořit hierarchický TOC.

### Je možné automaticky aktualizovat TOC, pokud se dokument změní?  
Ne, obsah se neaktualizuje automaticky. Pokud se změní struktura dokumentu, budete jej muset znovu vytvořit.

### Mohu propojit položky TOC s externími dokumenty?  
Ano, můžete použít hypertextové odkazy k propojení položek obsahu s externími soubory PDF nebo URL.

### Podporuje Aspose.PDF víceúrovňové TOC?  
Ano, Aspose.PDF podporuje víceúrovňové TOC pro složité dokumenty s podsekcemi.