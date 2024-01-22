---
title: Vytvořte PDF s více sloupci
linktitle: Vytvořte PDF s více sloupci
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet vícesloupcové PDF pomocí Aspose.PDF pro .NET.
type: docs
weight: 110
url: /cs/net/programming-with-text/create-multi-column-pdf/
---
Tento tutoriál vás provede procesem vytváření vícesloupcového PDF pomocí Aspose.PDF pro .NET. Poskytnutý zdrojový kód C# ukazuje potřebné kroky.

## Požadavky
Než začnete, ujistěte se, že máte následující:

- Visual Studio nebo jakýkoli jiný kompilátor C# nainstalovaný na vašem počítači.
- Aspose.PDF pro knihovnu .NET. Můžete si jej stáhnout z oficiálního webu Aspose nebo jej nainstalovat pomocí správce balíčků, jako je NuGet.

## Krok 1: Nastavte projekt
1. Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí.
2. Přidejte odkaz na knihovnu Aspose.PDF for .NET.

## Krok 2: Importujte požadované jmenné prostory
Do souboru kódu, kde chcete vytvořit vícesloupcové PDF, přidejte následující pomocí direktiv v horní části souboru:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Krok 3: Nastavte adresář dokumentů
 V kódu vyhledejte řádek, který říká`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` s cestou k adresáři, kde jsou uloženy vaše dokumenty.

## Krok 4: Vytvořte novou instanci dokumentu
 Vytvořte nový`Document` objekt přidáním následujícího řádku kódu:

```csharp
Document doc = new Document();
```

## Krok 5: Nastavte okraje stránky
 Zadejte informace o levém a pravém okraji pro soubor PDF pomocí`PageInfo.Margin` vlastnictvím`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Krok 6: Přidejte stránku do dokumentu
 Přidejte do dokumentu novou stránku pomocí`Add` metoda`Pages`sbírka. V poskytnutém kódu je nová stránka přiřazena k proměnné`page`.

```csharp
Page page = doc.Pages.Add();
```

## Krok 7: Vytvořte objekt Graph a přidejte čáru
 Vytvoř nový`Graph` objekt s konkrétními rozměry a přidejte k němu čáru. Poté přidejte`Graph` namítat proti`Paragraphs` kolekce stránky.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Krok 8: Přidejte text nadpisu s formátováním HTML
 Vytvořit`HtmlFragment` objekt a nastavte jeho obsah na požadovaný HTML text. Poté přidejte fragment do`Paragraphs` kolekce stránky.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Krok 9: Vytvořte FloatingBox s více sloupci
 Vytvořit`FloatingBox` objekt a nastavte počet sloupců a mezery mezi sloupci. Poté přidejte fragmenty textu a řádek`Paragraphs` sbírka`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Krok 10: Uložte dokument PDF
 Uložte dokument PDF pomocí`Save` metoda`Document` objekt.

```csharp
doc.Save(dataDir);
```

### Ukázka zdrojového kódu pro Create Multi Column Pdf pomocí Aspose.PDF pro .NET 
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Zadejte informace o levém okraji souboru PDF
doc.PageInfo.Margin.Left = 40;
//Zadejte informace o pravém okraji pro soubor PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Přidejte řádek do kolekce parafráze objektu sekce
page.Paragraphs.Add(graph1);
// Zadejte souřadnice čáry
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Vytvořte řetězcové proměnné s textem obsahujícím html značky
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Vytvářejte textové odstavce obsahující text HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Přidejte čtyři sloupce v sekci
box.ColumnInfo.ColumnCount = 2;
// Nastavte rozestupy mezi sloupci
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Vytvořte objekt graphs pro nakreslení čáry
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Zadejte souřadnice čáry
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Přidejte řádek do kolekce odstavců objektu sekce
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Uložit soubor PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Závěr
Úspěšně jste vytvořili vícesloupcové PDF pomocí Aspose.PDF pro .NET. Výsledný soubor PDF lze nyní nalézt na zadané cestě k výstupnímu souboru.

### FAQ

#### Otázka: Na co je zaměřen tento tutoriál?

Tento tutoriál je zaměřen na to, aby vás provedl procesem vytváření vícesloupcového PDF pomocí knihovny Aspose.PDF for .NET. Poskytnutý zdrojový kód C# demonstruje nezbytné kroky k dosažení tohoto cíle.

#### Otázka: Které jmenné prostory bych měl importovat pro tento výukový program?

Odpověď: Do souboru kódu, ve kterém chcete vytvořit vícesloupcové PDF, importujte na začátek souboru následující jmenné prostory:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Otázka: Jak určím adresář dokumentů?

 A: V kódu najděte řádek`string dataDir = "YOUR DOCUMENT DIRECTORY";` a nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k vašemu adresáři dokumentů.

#### Otázka: Jak vytvořím novou instanci dokumentu?

 Odpověď: V kroku 4 vytvoříte instanci nového`Document` objekt pomocí poskytnutého kódu.

#### Otázka: Jak nastavím okraje stránky?

 Odpověď: V kroku 5 použijete`PageInfo.Margin` vlastnictvím`Document` zadejte informace o levém a pravém okraji souboru PDF.

#### Otázka: Jak přidám stránku do dokumentu?

 Odpověď: V kroku 6 přidáte do dokumentu novou stránku pomocí`Add` metoda`Pages` sbírka.

#### Otázka: Jak vytvořím objekt Graph a přidám čáru?

 Odpověď: V kroku 7 vytvoříte nový`Graph` objekt, přidejte k němu řádek a poté přidejte`Graph` namítat proti`Paragraphs` kolekce stránky.

#### Otázka: Jak přidám text nadpisu s formátováním HTML?

 Odpověď: V kroku 8 vytvoříte soubor`HtmlFragment` objekt a nastavte jeho obsah na požadovaný text HTML, poté přidejte fragment do`Paragraphs` kolekce stránky.

#### Otázka: Jak vytvořím FloatingBox s více sloupci?

 Odpověď: V kroku 9 vytvoříte a`FloatingBox` objekt s více sloupci a mezerami mezi sloupci, pak do něj přidejte fragmenty textu a řádek`Paragraphs` sbírka`FloatingBox`.

#### Otázka: Jak uložím dokument PDF?

 Odpověď: V kroku 10 uložíte dokument PDF pomocí`Save` metoda`Document` objekt.

#### Otázka: Jaký je hlavní poznatek z tohoto tutoriálu?

Odpověď: Podle tohoto návodu jste se naučili, jak vytvořit vícesloupcový dokument PDF pomocí Aspose.PDF pro .NET. To může být užitečné pro zobrazení obsahu ve strukturovaném a organizovaném rozložení.