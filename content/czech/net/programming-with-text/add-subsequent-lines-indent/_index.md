---
title: Přidat další odsazení řádků do souboru PDF
linktitle: Přidat další odsazení řádků do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat odsazení následujících řádků do textu v souboru PDF pomocí Aspose.PDF for .NET.
type: docs
weight: 60
url: /cs/net/programming-with-text/add-subsequent-lines-indent/
---
Tento tutoriál vás provede procesem přidávání odsazení následujících řádků do textu v souboru PDF pomocí Aspose.PDF for .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
V souboru kódu, kam chcete přidat odsazení následujících řádků, přidejte následující příkaz using na začátek souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte nový objekt dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## Krok 6: Vytvořte TextFragment s následným odsazením řádků
 Instantovat a`TextFragment` objekt a zadejte požadovaný text. V poskytnutém kódu je text přiřazen k proměnné`text` . Poté inicializujte`TextFormattingOptions` pro`TextFragment` a specifikujte`SubsequentLinesIndent` hodnota.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## Krok 7: Přidejte TextFragment na stránku
 Přidejte`TextFragment` objekt proti kolekci odstavců na stránce.

```csharp
page.Paragraphs.Add(text);
```

## Krok 8: Opakujte kroky 6 a 7 pro další řádky
Chcete-li přidat další řádky se stejným odsazením, opakujte kroky 6 a 7 pro každý řádek. Aktualizujte obsah textu podle potřeby.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## Krok 9: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt. Zadejte cestu k výstupnímu souboru.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Ukázkový zdrojový kód pro Add Subsequent Lines Indent pomocí Aspose.PDF for .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Vytvořte nový objekt dokumentu
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//Inicializujte TextFormattingOptions pro textový fragment a zadejte hodnotu SubsequentLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Závěr
Úspěšně jste přidali odsazení následujících řádků do textu pomocí Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Na co je zaměřen tento tutoriál?

Odpověď: Tento tutoriál poskytuje komplexní návod, jak přidat další odsazení řádků do textu v souboru PDF pomocí knihovny Aspose.PDF for .NET. Obsahuje příklady zdrojového kódu C#, které ilustrují kroky potřebné k dosažení tohoto cíle.

#### Otázka: Které jmenné prostory musím pro tento výukový program importovat?

Odpověď: Do souboru kódu, do kterého chcete přidat odsazení následujících řádků, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Otázka: Jak určím adresář dokumentů?

 Odpověď: V kódu vyhledejte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím objekt dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí následujícího řádku kódu:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Otázka: Jak mohu do textu přidat odsazení následujících řádků?

 Odpověď: V kroku 6 vytvoříte a`TextFragment` objekt a přiřadit k němu požadovaný text. Poté provedete inicializaci`TextFormattingOptions` pro`TextFragment` a specifikujte`SubsequentLinesIndent` hodnota:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Otázka: Jak přidám TextFragment do dokumentu PDF?

 Odpověď: V kroku 7 přidáte`TextFragment` objekt (`text`) do kolekce odstavců na stránce:

```csharp
page.Paragraphs.Add(text);
```

#### Otázka: Mohu proces opakovat pro další řádky?

Odpověď: Ano, v kroku 8 můžete postup zopakovat pro další řádky se stejným odsazením vytvořením nového`TextFragment` objektů a jejich přidání do kolekce odstavců na stránce.

#### Otázka: Jak uložím výsledný dokument PDF?

 A: Po přidání textu s následným odsazením řádků použijte`Save` metoda`Document` objekt pro uložení dokumentu PDF:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Otázka: Jaký je hlavní přínos tohoto tutoriálu?

Odpověď: Sledováním tohoto kurzu jste se úspěšně naučili, jak zlepšit čitelnost textu v dokumentu PDF přidáním odsazení následujících řádků pomocí Aspose.PDF for .NET. Tato technika může být užitečná pro různé typy dokumentů a sestav.