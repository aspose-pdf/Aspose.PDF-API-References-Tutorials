---
title: Přidat popisek k textu v souboru PDF
linktitle: Přidat popisek k textu v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat popisky k textu v souborech PDF pomocí Aspose.PDF for .NET. Bez námahy vylepšete své soubory PDF informativními texty.
type: docs
weight: 90
url: /cs/net/programming-with-text/add-tooltip-to-text/
---
## Zavedení

Pokud jde o vytváření poutavých a interaktivních souborů PDF, mohou být popisy nástrojů neocenitelné. Znáte ty malé vyskakovací rámečky, které vám poskytnou další informace, když na něco najedete? Mohou poskytnout kontext, popisy nebo dokonce rady, aniž by váš dokument zaplnily. V tomto tutoriálu si projdeme, jak přidat popisky k textu v souboru PDF pomocí knihovny Aspose.PDF for .NET. Ať už jste ostřílený vývojář nebo si jen smočíte nohy ve světě PDF, jste na správném místě! Pojďme se tedy ponořit!

## Předpoklady

Než se vrhneme na část kódování, ujistěte se, že máte vše, co potřebujete, abyste mohli hladce sledovat.

### Visual Studio nainstalováno
Je nezbytné mít na svém počítači nainstalované Visual Studio, protože to bude vaše primární vývojové prostředí pro aplikace .NET.

### Aspose.PDF pro knihovnu .NET
 Dále budete potřebovat mít k dispozici knihovnu Aspose.PDF. Můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/). Nezapomeňte jej zahrnout do referencí projektu.

### Základní znalost C#
Pozadí v C# nám hodně pomůže, protože budeme kódovat v tomto jazyce. Ale nezoufejte – provedu vás každým krokem!

### Dokument PDF pro práci
Můžete začít s prázdným dokumentem PDF, jako to děláme v tomto příkladu, nebo použít existující, pokud chcete.

Nyní přejděme k části kódování!

## Importujte balíčky 

 První krok v našem dobrodružství s kódováním zahrnuje import potřebných balíčků. Otevřete projekt sady Visual Studio a v horní části souboru C# budete chtít přidat následující`using` směrnice:

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

Tyto balíčky vám poskytují přístup ke všem třídám a funkcím, které potřebujete pro vytváření a manipulaci s dokumenty PDF.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíme nastavit cestu, kam budete dokumenty ukládat. Berte to jako nalezení útulného místa ve vašem souborovém systému, kde budou umístěny všechny vaše výtvory.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

 Nezapomeňte vyměnit`YOUR DOCUMENT DIRECTORY` se skutečnou cestou na vašem počítači.

## Krok 2: Vytvořte vzorový dokument PDF

Dále je čas vytvořit jednoduché PDF s nějakým textem. Zde zahajujeme náš tvůrčí proces!

```csharp
//Vytvořte vzorový dokument s textem
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

V tomto kroku vytvoříme dokument, přidáme dva textové fragmenty a uložíme jej do naší dříve určené cesty.

## Krok 3: Otevřete dokument ke zpracování

Nyní, když máme vytvořený dokument, pojďme jej otevřít, abychom mohli pracovat na těchto nápovědách!

```csharp
// Otevřete dokument s textem
Document document = new Document(outputFile);
```

Zde jednoduše načteme dokument, který jsme právě vytvořili.

## Krok 4: Vytvořte absorbér textu pro vyhledání fragmentů textu

Musíme najít fragmenty textu, kam chceme přidat popisky. Je to jako používat lupu ke zvýraznění konkrétní části velké mapy! 

```csharp
// Vytvořte objekt TextAbsorber a najděte všechny fráze odpovídající regulárnímu výrazu
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## Krok 5: Extrahujte textové fragmenty

Dále extrahujeme fragmenty textu, které jsme našli v našem předchozím kroku.

```csharp
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragments = absorber.TextFragments;
```

Tento úryvek nám umožňuje uchovat si odkazy na části textu, které nás zajímají.

## Krok 6: Projděte fragmenty a přidejte popisky

Nyní přichází ta zábavná část! Projdeme každý z textových fragmentů a ke každému přidáme nápovědu. Představte si, že kolem konkrétních položek (úryvků textu) zabalíte malé dárky (popisy).

```csharp
// Projděte fragmenty
foreach (TextFragment fragment in textFragments)
{
	// Vytvořit neviditelné tlačítko na pozici fragmentu textu
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Hodnota AlternateName se zobrazí jako nápověda aplikace prohlížeče
	field.AlternateName = "Tooltip for text.";
	// Přidejte do dokumentu pole tlačítka
	document.Form.Add(field);
}
```

V každé iteraci vytvoříme pole tlačítka, které odpovídá poloze textového fragmentu, a přiřadíme k němu text popisku.

## Krok 7: Opakujte pro dlouhé popisky

Stejně jako jsme přidali jednoduchý popis, můžeme totéž udělat pro delší text. Pojďme rozšířit naši kreativitu!

```csharp
// Dále bude ukázka velmi dlouhého popisku
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Nastavit velmi dlouhý text
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

Zde děláme stejný druh práce jako dříve, ale s mnohem rozšířenějším popisem.

## Krok 8: Uložte dokument

Posledním krokem je uložení dokumentu se všemi těmi novými nápovědami. 

```csharp
// Uložit dokument
document.Save(outputFile);
```

právě tak máte hotovo! Do souboru PDF jste přidali nápovědu, takže je uživatelsky přívětivější a interaktivnější.

## Závěr

Tady to máte – snadno srozumitelný návod, jak přidat popisky k textu v souborech PDF pomocí Aspose.PDF pro .NET. Tato technika může výrazně zlepšit uživatelskou zkušenost a učinit vaše dokumenty informativnějšími, aniž by čtenáře zahltily příliš velkým množstvím textu najednou. 

Pouhým najetím kurzoru na slovo nebo frázi získá čtenář relevantní informace, které přidávají hodnotu bez zbytečných zbytečností. Tak si vyhrňte rukávy a vyzkoušejte to! Než se nadějete, můžete vytvářet nejrůznější poutavé dokumenty, které vynikají.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF v aplikacích .NET.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi, abyste mohli prozkoumat jeho funkce! Můžete to najít[zde](https://releases.aspose.com/).

### Jsou pro Aspose.PDF k dispozici nějaké možnosti licencování?
Ano, můžete si zakoupit licenci nebo získat dočasnou licenci. Podívejte se na možnosti[zde](https://purchase.aspose.com/).

### Mohu pomocí Aspose.PDF přidat jiné interaktivní prvky než popisky?
Absolutně! Aspose.PDF umožňuje přidávání různých interaktivních prvků, jako jsou hypertextové odkazy, tlačítka a formuláře.

### Kde najdu další dokumentaci na Aspose.PDF?
 Můžete se podívat na dokumentaci[zde](https://reference.aspose.com/pdf/net/) pro podrobnější návod.