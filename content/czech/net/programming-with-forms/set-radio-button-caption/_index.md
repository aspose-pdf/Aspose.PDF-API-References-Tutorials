---
title: Nastavte titulek přepínače
linktitle: Nastavte titulek přepínače
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se používat Aspose.PDF pro .NET k nastavení titulku pro přepínač ve formátu PDF.
type: docs
weight: 280
url: /cs/net/programming-with-forms/set-radio-button-caption/
---
této příručce si krok za krokem vysvětlíme, jak používat knihovnu Aspose.PDF pro .NET k definování titulku přepínače ve formátu PDF. Ukážeme vám, jak získat přístup k poli přepínače, vytvořit novou možnost přepínače a upravit popis tlačítka.

## Krok 1: Konfigurace adresáře dokumentů

 Prvním krokem je konfigurace adresáře dokumentu, kde se nachází formulář PDF, se kterým chcete pracovat. Můžete použít`dataDir` proměnnou k určení cesty k adresáři.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Nezapomeňte vyměnit`"YOUR DOCUMENTS DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Načtení zdrojového formuláře PDF

 V tomto kroku načteme zdrojový PDF formulář pomocí`Aspose.Pdf.Facades.Form` třída Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Ujistěte se, že soubor PDF obsahující formulář je přítomen v zadaném adresáři dokumentů.

## Krok 3: Úprava titulku přepínače

Projdeme názvy polí formuláře a vyhledáme pole s přepínači. Pokud je nalezeno odpovídající pole, vytvoříme nový přepínač s vlastním popiskem a přidáme jej do stávajícího pole.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Vytvořte objekt TextParagraph
TextParagraph par = new TextParagraph();
// Nastavit pozici odstavce
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Určete režim zalamování slov
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Přidejte nový TextFragment do odstavce
par.AppendLine(updatedFragment);
// Přidejte TextParagraph pomocí TextBuilder
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Podle potřeby upravte přepínač titulků a další nastavení.

## Krok 4: Uložení výsledného PDF

 Nyní, když jsme dokončili úpravu popisku přepínače, můžeme uložit výsledné PDF pomocí`Save` metoda`Document` třída.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Nezapomeňte zadat úplnou cestu a název souboru pro výsledný soubor PDF.

### Ukázkový zdrojový kód pro Set Radio Button Caption pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Načíst zdrojový formulář PDF
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		// Vytvořte objekt TextParagraph
		TextParagraph par = new TextParagraph();
		// Nastavit pozici odstavce
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		// Určete režim zalamování slov
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		// Přidejte nový TextFragment do odstavce
		par.AppendLine(updatedFragment);
		// Přidejte TextParagraph pomocí TextBuilder
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Závěr

V této příručce jsme se naučili, jak používat knihovnu Aspose.PDF pro .NET k nastavení titulku pro přepínač ve formátu PDF. Podle popsaných kroků můžete přizpůsobit možnosti přepínače a změnit titulek podle potřeby. Neváhejte dále prozkoumat funkce Aspose.PDF pro .NET, abyste rozšířili možnosti manipulace se soubory PDF.

### FAQ

#### Otázka: Mohu použít Aspose.PDF pro .NET k nastavení titulků pro přepínače ve formátu PDF?

Odpověď: Ano, můžete použít Aspose.PDF pro .NET k nastavení titulků pro přepínače ve formě PDF. Poskytnutý ukázkový zdrojový kód ukazuje, jak získat přístup k poli přepínacího tlačítka, vytvořit novou možnost přepínacího tlačítka s vlastním titulkem a aktualizovat stávající pole.

#### Otázka: Jak mohu přizpůsobit vzhled titulku přepínače, jako je velikost a barva písma?

 Odpověď: Vzhled titulku přepínače si můžete přizpůsobit úpravou vlastností`TextFragment` použito pro titulek. Můžete například nastavit písmo, velikost písma, barvu, řádkování a další možnosti formátování textu.

#### Otázka: Je možné přidat více možností přepínačů s různými titulky do jedné skupiny přepínačů?

Odpověď: Ano, do jedné skupiny přepínačů můžete přidat více možností přepínačů s různými titulky. Každá možnost bude představovat jinou možnost a uživatelé mohou vybrat pouze jednu možnost ze skupiny.

#### Otázka: Mohu použít Aspose.PDF pro .NET k úpravě jiných polí formuláře v dokumentu PDF?

Odpověď: Ano, Aspose.PDF for .NET poskytuje komplexní sadu funkcí pro manipulaci s různými poli formuláře v dokumentu PDF, jako jsou textová pole, zaškrtávací políčka, rozevírací seznamy a další. Knihovnu můžete použít k nastavení hodnot, úpravě vzhledů a přidání interaktivity do polí formuláře.

#### Otázka: Podporuje Aspose.PDF for .NET práci s PDF generovanými z jiných zdrojů, jako jsou naskenované dokumenty?

Odpověď: Ano, Aspose.PDF for .NET podporuje práci s PDF generovanými z různých zdrojů, včetně naskenovaných dokumentů. Knihovna poskytuje funkce OCR (Optical Character Recognition) pro extrahování textu z naskenovaných PDF a programovou manipulaci s obsahem.