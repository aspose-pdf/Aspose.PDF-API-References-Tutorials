---
title: Vytvořte PDF s více sloupci
linktitle: Vytvořte PDF s více sloupci
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet vícesloupcové PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce s příklady kódu a podrobnými vysvětleními. Ideální pro profesionály.
type: docs
weight: 110
url: /cs/net/programming-with-text/create-multi-column-pdf/
---
## Zavedení

Vytváření vícesloupcových souborů PDF je skvělý způsob, jak prezentovat text v organizovanějším a čitelnějším formátu. Ať už vytváříte zprávu, článek nebo rozvržení pro publikaci, vícesloupcové struktury mohou učinit váš obsah poutavějším. V tomto tutoriálu si projdeme, jak vytvořit vícesloupcové PDF pomocí Aspose.PDF pro .NET. Nebojte se, vše rozdělíme do jednoduchých kroků, které vám usnadní sledování, i když jste na platformě noví.

## Předpoklady

Než se pustíme do kódu, je potřeba mít několik věcí, které budete potřebovat, abyste mohli plynule pokračovat:

1.  Aspose.PDF pro .NET: Tuto knihovnu musíte mít nainstalovanou. Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
2. Vývojové prostředí: Nastavte si preferované IDE, jako je Visual Studio, pro psaní a spouštění kódu C#.
3. .NET Framework: Ujistěte se, že máte nainstalovanou kompatibilní verzi .NET.
4. Základní porozumění C#: Znalost syntaxe C# bude užitečná, ale každý krok vysvětlíme podrobně.
5.  Dočasná licence: Aspose.PDF vyžaduje licenci, aby se zabránilo vodoznakům nebo omezením. Můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) v případě potřeby.

## Importujte balíčky

Než začnete kódovat, musíte importovat potřebné jmenné prostory, které vám umožní interakci s Aspose.PDF. Zde je to, co budete potřebovat k importu:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Tyto jmenné prostory poskytují přístup ke třídám potřebným pro vytváření PDF, kreslení tvarů a manipulaci s formátováním textu.

Pojďme si proces vytváření vícesloupcového PDF rozdělit do jednoduchých, zvládnutelných kroků.

## Krok 1: Nastavení dokumentu

Chcete-li začít, musíte vytvořit nový dokument PDF. To zahrnuje definování okrajů a přidání stránky, kam váš obsah půjde.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Vytvořte nový dokument PDF
Document doc = new Document();

// Nastavte okraje pro soubor PDF
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// Přidejte do dokumentu stránku
Page page = doc.Pages.Add();
```

 Zde jsme vytvořili a`Document`objekt a nastavte levý a pravý okraj na 40 jednotek. Poté jsme do tohoto dokumentu přidali novou stránku, která bude obsahovat naše vícesloupcové rozložení.

## Krok 2: Přidání čáry do samostatných sekcí

Dále přidáme na stránku vodorovnou čáru pro vizuální oddělení. To pomáhá vytvořit čistý a profesionální vzhled.

```csharp
// Vytvořte objekt grafu, který bude držet čáru
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// Přidejte řádek do kolekce odstavců na stránce
page.Paragraphs.Add(graph1);

// Definujte souřadnice pro čáru
float[] posArr = new float[] { 1, 2, 500, 2 };

// Vytvořte čáru a přidejte ji do grafu
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

 Zde vytváříme vodorovnou čáru pomocí`Graph` a`Line` třídy. Tento řádek je přidán na stránku`Paragraphs` kolekce, která obsahuje všechny vizuální prvky.

## Krok 3: Přidání HTML textu s formátováním

Dále vložíme text, který obsahuje značky HTML, abychom ukázali, jak lze dynamicky formátovat text v PDF.

```csharp
// Vytvořte řetězec s obsahem HTML
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// Vytvořte nový HtmlFragment s formátovaným textem
HtmlFragment heading_text = new HtmlFragment(s);

// Přidejte na stránku text HTML
page.Paragraphs.Add(heading_text);
```

 Pomocí`HtmlFragment`třídy, můžeme přidat formátovaný text, který obsahuje značky HTML, jako je velikost písma, styl a tučný text. To je užitečné pro vylepšení vzhledu obsahu PDF.

## Krok 4: Vytvoření rozvržení s více sloupci

Nyní vytvoříme rozvržení s více sloupci. Zde se stane kouzlo – můžete určit, kolik sloupců chcete a jak široké by měly být.

```csharp
// Vytvořte plovoucí rámeček pro uložení sloupců
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// Nastavte počet sloupců a mezery mezi nimi
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// Přidejte pole na stránku
page.Paragraphs.Add(box);
```

Zde vytváříme plovoucí rámeček, který bude obsahovat dva sloupce. Nastavíme mezery mezi sloupci a určíme, že každý sloupec by měl být široký 105 jednotek. To nám umožňuje vytvořit požadované rozložení sloupců v PDF.

## Krok 5: Přidání textu do sloupců

 Pojďme nyní naplnit sloupce nějakým textovým obsahem. Můžete přidat různé`TextFragment` objektů do každého sloupce.

```csharp
// Vytvořte a naformátujte první textový fragment
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// Přidejte další řádek pro oddělení
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//Vytvořte a přidejte druhý textový fragment
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

 Přidáme a`TextFragment` do plovoucího rámečku, za nímž následuje další vodorovná čára. Druhý`TextFragment` obsahuje více textu k vyplnění druhého sloupce. Tyto fragmenty nám umožňují přidávat do PDF různé textové prvky s různými možnostmi formátování.

## Krok 6: Uložení PDF

Po přidání veškerého obsahu je posledním krokem uložení dokumentu jako souboru PDF.

```csharp
// Definujte výstupní cestu pro PDF
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// Uložte dokument PDF
doc.Save(dataDir);

// Zpráva o úspěchu výstupu
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

Tento blok uloží soubor PDF do určeného adresáře a zobrazí zprávu o úspěchu v konzole. PDF je nyní připraveno k prohlížení!

## Závěr

Pomocí těchto jednoduchých kroků můžete snadno vytvořit profesionálně vypadající vícesloupcový soubor PDF pomocí Aspose.PDF pro .NET. Ať už jde o zprávu, článek nebo zpravodaj, tato technika pomáhá organizovat obsah do vizuálně přitažlivého formátu. Aspose.PDF nabízí výkonné nástroje pro přizpůsobení vašich PDF, od okrajů a rozvržení až po formátování textu a kreslení tvarů. Nyní je řada na vás, abyste to vyzkoušeli a posunuli své dovednosti při vytváření PDF na další úroveň!

## FAQ

### Mohu vytvořit více než dva sloupce v PDF?
 Ano, můžete vytvořit tolik sloupců, kolik potřebujete. Jednoduše upravte`ColumnCount` vlastnost tak, aby odpovídala požadovanému počtu sloupců.

### Jak změním šířku každého sloupce?
 Můžete upravit`ColumnWidths` vlastnost k určení různé šířky pro každý sloupec. Tato vlastnost přijímá řetězec hodnot oddělený mezerami.

### Je možné přidat obrázky do sloupců?
 Absolutně! Obrázky můžete přidávat pomocí`Image` třídy a zahrňte je do plovoucího rámečku nebo jakéhokoli jiného prvku rozvržení ve vašem PDF.

### Mohu stylovat text pomocí značek HTML ve sloupcích?
 Ano, můžete v něm používat značky HTML`HtmlFragment` objekty pro stylizaci textu. To zahrnuje přidávání písem, velikostí, barev a dalších.

### Jak mohu přidat více stránek se stejným rozložením sloupců?
 Další stránky můžete přidat pomocí`doc.Pages.Add()` a opakujte proces přidávání sloupců a obsahu pro každou stránku.