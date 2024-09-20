---
title: Určete řádkování v souboru PDF
linktitle: Určete řádkování v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto podrobném průvodci se dozvíte, jak určit řádkování v PDF pomocí Aspose.PDF for .NET. Ideální pro vývojáře, kteří hledají přesné formátování textu.
type: docs
weight: 510
url: /cs/net/programming-with-text/specify-line-spacing/
---
## Zavedení

Už jste někdy bojovali s ovládáním řádkování v souboru PDF? Možná jste měli text, který vypadá příliš nacpaný nebo prostě nevypadá tak uhlazeně, jak byste chtěli. V tomto tutoriálu si projdeme, jak můžete snadno určit řádkování v PDF pomocí Aspose.PDF pro .NET. Použijeme jednoduchého průvodce krok za krokem, který vás provede od prázdného PDF k dokumentu, který obsahuje vlastní řádkování. To je perfektní, pokud potřebujete přesnost v rozložení textu pro dokumenty, jako jsou zprávy, faktury nebo certifikáty.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte vše, co potřebujete:

1.  Aspose.PDF pro .NET nainstalován. Pokud ji nemáte, vezměte si ji z[Stránka ke stažení Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí .NET (jako Visual Studio).
3. Soubor písma TrueType (`.ttf` ), který použijeme v příkladu. Můžete použít jakékoli písmo, ale pro tuto příručku použijeme písmo`HPSimplified.TTF` písmo.
4. Základní znalost práce s C# a PDF.

Pokud jste připraveni, přejděme k importu potřebných balíčků.

## Importujte balíčky

Ve svém projektu C# budete muset importovat jmenné prostory Aspose.PDF, abyste mohli pracovat s funkcemi PDF. Postupujte takto:

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Tyto jmenné prostory vám umožňují vytvářet a manipulovat s dokumenty PDF a také pracovat s formátováním textu a možnostmi písma.

Rozdělíme si to na malé kroky, abyste je mohli snadno sledovat. Každý krok se zaměří na klíčovou část procesu, od nastavení PDF po specifikaci řádkování.

## Krok 1: Nastavte svůj projekt a definujte adresář dokumentů

První věc, kterou musíme udělat, je definovat, kde jsou umístěny naše soubory. To pomáhá programu vědět, kde najít písmo a kam uložit výsledné PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 V tomto kroku vyměníte`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k umístění souborů. Zde umístíte soubor s písmem (`HPSimplified.TTF`) a kam bude PDF uložen.

## Krok 2: Načtěte dokument PDF

Nyní musíme vytvořit nový dokument PDF. V této příručce začneme s prázdným dokumentem, ale v případě potřeby můžete také načíst existující PDF.

```csharp
Document doc = new Document();
```

Tím se vytvoří nový prázdný dokument PDF. Snadné, že?

## Krok 3: Nastavte možnosti formátování textu

 Tady se děje kouzlo. Určíme režim řádkování pro text, který chceme přidat do PDF. Aspose.PDF nám nabízí několik možností, ale v této příručce je použijeme`LineSpacingMode.FullSize`, což zajišťuje plné dodržení řádkování.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Tento kód nastaví režim řádkování na`FullSize` , zajistíte, že text bude zobrazen se správnými mezerami. Existují další možnosti jako`Proportional` pokud chcete jiné chování mezer, ale prozatím zůstaňme u toho`FullSize`.

## Krok 4: Vytvořte textový fragment

Nyní vytvoříme skutečný text, který bude umístěn do PDF. Tento text bude respektovat námi definované řádkování.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Vytvořili jsme textový fragment s řetězcem`"Hello world"`. Tento text si samozřejmě můžete upravit, jak chcete.

## Krok 5: Načtěte a použijte vlastní písmo

Aby text vynikl, načteme ze souboru vlastní písmo TrueType. Tento krok je volitelný, ale může vašim souborům PDF dodat profesionální vzhled.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Zde načteme soubor písma a aplikujeme jej na textový fragment. Pokud je cesta k souboru platná, použije se písmo. Jinak se použije výchozí písmo.

## Krok 6: Nastavte polohu a formátování textu

Dále musíme umístit text do PDF. Použijeme také možnosti formátování, které jsme vytvořili dříve.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 The`Position` metoda nastavuje souřadnice, kde se text na stránce objeví (v tomto případě 100 jednotek zleva a 600 jednotek zdola). Zde se použijí možnosti formátování, včetně režimu řádkování.

## Krok 7: Přidejte text na stránku PDF

Nyní, když je náš text naformátován a umístěn, je čas jej přidat do dokumentu PDF.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Tento kód vytvoří v dokumentu PDF novou stránku a přidá k ní fragment textu.

## Krok 8: Uložte soubor PDF

Dosáhli jsme posledního kroku! Nyní, když je vše nastaveno, uložíme PDF.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Tím se uloží PDF se zadaným řádkováním a váš soubor je připraven!

## Závěr

A je to! Právě jste vytvořili dokument PDF s vlastním řádkováním pomocí Aspose.PDF pro .NET. Je to mocný nástroj, který vám umožňuje ovládat každý aspekt vašich souborů PDF, a toto je jen jeden příklad toho, čeho můžete dosáhnout. Od umístění textu po formátování, možnosti jsou nekonečné.

Pokud se chcete ponořit hlouběji do manipulace s PDF, Aspose.PDF nabízí množství funkcí k prozkoumání. Neváhejte experimentovat a posouvat hranice toho, co můžete se svými dokumenty dělat!

## FAQ

### Mohu upravit řádkování na jiné režimy?  
 Ano, můžete použít i jiné režimy, např`Proportional` nebo`Fixed` v závislosti na vašich potřebách.

### Je možné načíst fonty ze systému místo souboru?  
 Ano, písma nainstalovaná systémem můžete načíst pomocí`FontRepository`.

### Mohu použít Aspose.PDF pro .NET s jinými formáty souborů?  
Absolutně! Aspose.PDF for .NET podporuje různé formáty jako XML, HTML a další.

### Potřebuji licenci k používání Aspose.PDF pro .NET?  
Ano, pro plnou funkčnost budete potřebovat licenci, kterou můžete získat[zde](https://purchase.aspose.com/buy).

### Jak nastavím řádkování pro více odstavců?  
 Můžete se přihlásit`TextFormattingOptions` každému`TextFragment` nebo`TextParagraph` pro ovládání mezer pro více řádků nebo odstavců.