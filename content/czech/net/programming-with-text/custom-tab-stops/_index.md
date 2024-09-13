---
title: Vlastní zarážky tabulátoru v souboru PDF
linktitle: Vlastní zarážky tabulátoru v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak vytvořit vlastní zarážky tabulátoru v souboru PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 120
url: /cs/net/programming-with-text/custom-tab-stops/
---

Tento tutoriál vás provede procesem vytváření vlastních zarážek tabulátoru v souboru PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kde chcete vytvořit vlastní zarážky tabulátoru, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte novou instanci dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document _pdfdocument = new Document();
```

## Krok 5: Přidejte do dokumentu stránku
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## Krok 6: Vytvořte vlastní zarážky tabulátoru
 Vytvořte a`TabStops` objekt a přidejte k němu vlastní zarážky tabulátoru. Nastavte typ zarovnání a typ odkazu pro každou zarážku tabulátoru.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## Krok 7: Vytvořte fragmenty textu se zarážkami tabulátoru
 Vytvořit`TextFragment` objektů a předat jim vlastní zarážky tabulátoru. Použijte speciální znaky`#$TAB` k označení zarážek tabulátoru v textu.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## Krok 8: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Ukázkový zdrojový kód pro Custom Tab Stops pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Závěr
Úspěšně jste vytvořili dokument PDF s vlastními zarážkami tabulátoru pomocí Aspose.PDF for .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Na co je zaměřen tento tutoriál?

Odpověď: Tento tutoriál je zaměřen na to, aby vás provedl procesem vytváření vlastních zarážek tabulátoru v souboru PDF pomocí knihovny Aspose.PDF for .NET. Poskytnutý zdrojový kód C# demonstruje nezbytné kroky k dosažení tohoto cíle.

#### Otázka: Které jmenné prostory bych měl importovat pro tento výukový program?

Odpověď: V souboru kódu, kde chcete vytvořit vlastní zarážky tabulátoru, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím novou instanci dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí poskytnutého kódu.

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 5 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka.

#### Otázka: Jak vytvořím vlastní zarážky tabulátoru?

 Odpověď: V kroku 6 vytvoříte a`TabStops` objekt a přidejte k němu vlastní zarážky tabulátoru. Pro každou zarážku tabulátoru také nastavíte typy zarovnání a odkazové čáry.

#### Otázka: Jak vytvořím fragmenty textu se zarážkami?

 Odpověď: V kroku 7 vytvoříte`TextFragment` objektů a předat jim vlastní zarážky tabulátoru. Budete používat speciální znaky`#$TAB` k označení zarážek tabulátoru v textu.

#### Otázka: Jak uložím dokument PDF?

 Odpověď: V kroku 8 uložíte dokument PDF pomocí`Save` metoda`Document` objekt.

#### Otázka: Jaký je hlavní poznatek z tohoto tutoriálu?

Odpověď: Podle tohoto kurzu jste se naučili, jak vytvořit dokument PDF s vlastními zarážkami tabulátoru pomocí Aspose.PDF for .NET. To může být užitečné pro uspořádání a zarovnání textu strukturovaným způsobem.