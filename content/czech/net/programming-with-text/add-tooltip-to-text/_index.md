---
title: Přidat popisek k textu v souboru PDF
linktitle: Přidat popisek k textu v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat popisky k textu v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 90
url: /cs/net/programming-with-text/add-tooltip-to-text/
---
Tento tutoriál vás provede procesem přidávání popisků k textu v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
V souboru kódu, kam chcete přidat popisky k textu, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte vzorový dokument s textem
 Vytvořte nový`Document` objekt a přidat stránky s textovými fragmenty. V poskytnutém kódu jsou do dokumentu přidány dva textové fragmenty s příslušným textem nápovědy.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## Krok 5: Otevřete dokument a najděte fragmenty textu
 Načtěte vytvořený dokument pomocí`Document` konstruktoru a najděte textové fragmenty, které vyžadují použití popisků`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## Krok 6: Přidejte k fragmentům textu nápovědu
 Procházejte extrahované části textu a na jejich pozicích vytvořte neviditelná tlačítka. Přiřaďte požadovaný text popisku k`AlternateName` majetek z`ButtonField`. Přidejte pole tlačítka do formuláře dokumentu.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## Krok 7: Opakujte pro další fragmenty textu s dlouhými popisky
Opakujte kroky 5 a 6 pro textové fragmenty s dlouhými popisky. Podle toho upravte kritéria vyhledávání a text nápovědy.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## Krok 8: Uložte upravený dokument
 Uložte upravený dokument PDF pomocí`Save` metoda`Document` objekt.

```csharp
document. Save(outputFile);
```

### Ukázkový zdrojový kód pro Add Tooltip To Text pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Vytvořte vzorový dokument s textem
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Otevřete dokument s textem
Document document = new Document(outputFile);
// Vytvořte objekt TextAbsorber a najděte všechny fráze odpovídající regulárnímu výrazu
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Přijměte absorbér pro stránky dokumentu
document.Pages.Accept(absorber);
// Získejte extrahované fragmenty textu
TextFragmentCollection textFragments = absorber.TextFragments;
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
// Uložit dokument
document.Save(outputFile);
```

## Závěr
Úspěšně jste přidali popisky k textu v dokumentu PDF pomocí Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

## Nejčastější dotazy

#### Otázka: Na co je zaměřen tento tutoriál?

Odpověď: Tento tutoriál se zaměřuje na přidávání popisků k textu v souboru PDF pomocí knihovny Aspose.PDF for .NET. Poskytnutý zdrojový kód C# demonstruje kroky potřebné k dosažení tohoto cíle.

#### Otázka: Které jmenné prostory je třeba pro tento výukový program importovat?

Odpověď: Do souboru kódu, kam chcete přidat popisky k textu, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak mohu vytvořit vzorový dokument s textem?

 Odpověď: V kroku 4 vytvoříte nový`Document` objekt a přidat stránky s textovými fragmenty. Poskytnutý kód přidá dva textové fragmenty s příslušným textem popisku.

#### Otázka: Jak mohu otevřít dokument a najít fragmenty textu?

 A: V kroku 5 načtete vytvořený dokument pomocí`Document` konstruktoru a najděte textové fragmenty vyžadující popisky pomocí`TextFragmentAbsorber`.

#### Otázka: Jak přidám popisky k fragmentům textu?

 Odpověď: V kroku 6 budete procházet extrahované části textu a na jejich pozicích vytvoříte neviditelná tlačítka. Text popisku je přiřazen k`AlternateName` majetek z`ButtonField`který je přidán do formuláře dokumentu.

#### Otázka: Jak zopakuji proces pro další fragmenty textu s dlouhými popisky?

Odpověď: U fragmentů textu s dlouhými popisky opakujte kroky 5 a 6. Podle toho upravte kritéria vyhledávání a text popisku.

#### Otázka: Jak uložím upravený dokument?

 Odpověď: V kroku 8 uložíte upravený dokument PDF pomocí`Save` metoda`Document` objekt.

#### Otázka: Jaký je hlavní poznatek z tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se naučili, jak vylepšit dokument PDF přidáním popisků k textu pomocí Aspose.PDF for .NET. To může poskytnout cenné další informace pro čtenáře při interakci s obsahem PDF.