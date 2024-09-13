---
title: Obrázek a číslo stránky v části Zápatí záhlaví
linktitle: Obrázek a číslo stránky v části Zápatí záhlaví
second_title: Aspose.PDF pro .NET API Reference
description: tomto podrobném návodu se dozvíte, jak přidat obrázek a čísla stránek do záhlaví a zápatí PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 110
url: /cs/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Zavedení

Pokud jde o vytváření dokumentů PDF profesionální kvality, je nezbytné mít kontrolu nad drobnými detaily, jako jsou záhlaví a zápatí. Chcete, aby vaše dokumenty vypadaly uhlazeně a dobře uspořádané, že? S Aspose.PDF pro .NET můžete do záhlaví a zápatí vašeho dokumentu bez problémů přidávat obrázky a čísla stránek. V tomto tutoriálu vás provedeme každým krokem, aby bylo snadné ho sledovat.

## Předpoklady

Než se ponoříte do hlubin tohoto tutoriálu, ujistěte se, že máte seřazeno následující:

1. .NET Framework: V počítači musíte mít nainstalovanou jakoukoli verzi .NET Framework. Pokud jej nemáte, můžete si jej snadno stáhnout z webu Microsoftu.
2.  Aspose.PDF pro .NET: Protože budeme používat Aspose.PDF, ujistěte se, že jej máte nainstalovaný ve svém projektu. Můžete si stáhnout zkušební verzi[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Znalost základního programování v C# vám jistě pomůže porozumět kódu bez větších potíží.
4. Soubor obrázku: Budete potřebovat obrázek, který chcete vložit do záhlaví dokumentu PDF, například logo. Uložte jej do přístupného adresáře. 
5. IDE: Pro práci s vaším projektem .NET použijte integrované vývojové prostředí (IDE) dle vašeho výběru, jako je Visual Studio.

Jakmile budete mít připravené předpoklady, budete připraveni vytvořit báječný soubor PDF!

## Importujte balíčky

Chcete-li začít používat Aspose.PDF pro .NET, musíte importovat potřebné jmenné prostory. V horní části souboru C# byste přidali:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Tyto jmenné prostory vám poskytnou přístup ke třídám potřebným pro manipulaci se soubory PDF.

Nyní pojďme k tomu skutečnému! Chcete-li vytvořit dokument PDF, použijte obrázek v záhlaví a čísla stránek v zápatí podle následujících kroků.

## Krok 1: Nastavte adresář dokumentů

Každý dobrý projekt začíná organizací. Definujte adresář dokumentů, kam budete ukládat soubory a kde se nachází váš obrázek. Jak na to:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kam chcete PDF uložit a kde váš obrázek existuje.

## Krok 2: Vytvořte nový dokument PDF

Dále vytvoříme nový dokument PDF, kde se stane všechna kouzla:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

V tomto okamžiku jste vytvořili prázdný dokument PDF. Vzrušující, že?

## Krok 3: Přidejte stránku do dokumentu

PDF je o stránkách. Pojďme do našeho dokumentu přidat novou stránku pomocí:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Nyní máte plátno, na kterém můžete začít navrhovat!

## Krok 4: Vytvořte sekci záhlaví

Vaše záhlaví bude obsahovat obrázek (jako logo), který chcete zobrazit. Vytvořte sekci záhlaví s následujícím kódem:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Nyní máte záhlaví, které si můžete přizpůsobit!

## Krok 5: Přidejte obrázek do záhlaví

Nyní se dostáváme k zábavnější části! Musíte přidat obrázek do záhlaví. Nejprve vytvořte objekt obrázku:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Nastavte cestu k souboru vašeho obrázku:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Nakonec přidejte obrázek do záhlaví:

```csharp
header.Paragraphs.Add(image1);
```

Gratuluji! Právě jste přidali obrázek do záhlaví PDF.

## Krok 6: Vytvořte sekci zápatí

Nyní pojďme pracovat na zápatí. Podobně jako u procesu záhlaví vytvořte objekt zápatí:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Zde umístíte číslo své stránky. 

## Krok 7: Přidejte text do zápatí

Vytvořte fragment textu, který bude obsahovat číslo stránky:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Poté přidejte tento fragment textu do zápatí:

```csharp
footer.Paragraphs.Add(txt);
```

Vidíš, jak to bylo snadné? Číslo stránky jste nastavili dynamicky!

## Krok 8: Uložte dokument PDF

Posledním krokem v našem dobrodružství je uložení dokumentu. Tento příkaz použijte k uložení nově vytvořeného PDF:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

A právě tak je váš PDF připraven a načten s obrázkem záhlaví a čísly stránek v zápatí!

## Závěr

tady to máte! Právě jste vytvořili PDF s obrázkem v záhlaví a dynamickými čísly stránek v zápatí pomocí Aspose.PDF for .NET. Je až neuvěřitelné, jak pár řádků kódu může vést k tak vypilovanému výstupu. Ať už se jedná o podnikovou zprávu nebo personalizovaný dokument, přidání těchto prvků změní tón a profesionalitu vašeho PDF.

## FAQ

### Mohu použít Aspose.PDF na jakékoli platformě .NET?
Ano, Aspose.PDF pro .NET podporuje více platforem .NET včetně .NET Framework, .NET Core a dalších.

### Je k dispozici bezplatná zkušební verze pro Aspose.PDF?
 Absolutně! Můžete si stáhnout bezplatnou zkušební verzi[zde](https://releases.aspose.com/).

### Jaké formáty obrázků jsou podporovány pro záhlaví?
Aspose.PDF podporuje většinu běžných obrazových formátů jako JPG, PNG a BMP pro záhlaví a zápatí.

### Mohu přizpůsobit formát čísel stránek?
Ano, text a formát zápatí si můžete snadno přizpůsobit podle svých potřeb.

### Je k dispozici technická podpora?
 Ano, Aspose poskytuje specializovanou podporu prostřednictvím svého fóra. Můžete se obrátit na pomoc[zde](https://forum.aspose.com/c/pdf/10).