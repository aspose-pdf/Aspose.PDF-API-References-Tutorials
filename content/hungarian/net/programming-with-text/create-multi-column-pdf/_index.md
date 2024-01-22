---
title: Hozzon létre több oszlopos pdf-et
linktitle: Hozzon létre több oszlopos pdf-et
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre több oszlopos PDF-fájlt az Aspose.PDF for .NET használatával.
type: docs
weight: 110
url: /hu/net/programming-with-text/create-multi-column-pdf/
---
Ez az oktatóanyag végigvezeti a több oszlopos PDF létrehozásának folyamatán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyben több oszlopos PDF-fájlt szeretne létrehozni, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Hozzon létre egy új dokumentumpéldányt
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Document doc = new Document();
```

## 5. lépés: Állítsa be az oldalmargókat
 Adja meg a bal és jobb margó információit a PDF-fájlhoz a gombbal`PageInfo.Margin` tulajdona a`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## 6. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Új oldal hozzáadása a dokumentumhoz a gombbal`Add` módszere a`Pages`Gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`page`.

```csharp
Page page = doc.Pages.Add();
```

## 7. lépés: Hozzon létre egy Graph objektumot, és adjon hozzá egy sort
 Újat csinálni`Graph` adott méretű objektumot, és adjunk hozzá egy sort. Ezután adja hozzá a`Graph` tiltakozik a`Paragraphs` az oldal gyűjteménye.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## 8. lépés: Adjon hozzá címsort HTML-formátummal
 Hozzon létre egy`HtmlFragment` objektumot, és állítsa be a tartalmát a kívánt HTML szövegre. Ezután adja hozzá a töredéket a`Paragraphs` az oldal gyűjteménye.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## 9. lépés: Hozzon létre egy FloatingBoxot több oszloppal
 Hozzon létre egy`FloatingBox` objektumot, és állítsa be az oszlopok számát és az oszlopközöket. Ezután adjon hozzá szövegrészleteket és egy sort a`Paragraphs` gyűjteménye a`FloatingBox`.

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

## 10. lépés: Mentse el a PDF dokumentumot
 Mentse el a PDF dokumentumot a`Save` módszere a`Document` tárgy.

```csharp
doc.Save(dataDir);
```

### Minta forráskód a többoszlopos PDF létrehozásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Adja meg a bal margó információit a PDF-fájlhoz
doc.PageInfo.Margin.Left = 40;
//Adja meg a jobb margó információit a PDF-fájlhoz
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Adja hozzá a sort a szakaszobjektum parafrázi gyűjteményéhez
page.Paragraphs.Add(graph1);
// Adja meg a vonal koordinátáit
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Hozzon létre karakterlánc-változókat html címkéket tartalmazó szöveggel
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Hozzon létre HTML szöveget tartalmazó szöveges bekezdéseket
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Adjon hozzá négy oszlopot a szakaszhoz
box.ColumnInfo.ColumnCount = 2;
// Állítsa be az oszlopok közötti távolságot
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Hozzon létre egy grafikon objektumot egy vonal rajzolásához
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Adja meg a vonal koordinátáit
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Adja hozzá a sort a szakaszobjektum bekezdésgyűjteményéhez
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Következtetés
Sikeresen létrehozott egy több oszlopos PDF-fájlt az Aspose.PDF for .NET használatával. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

### GYIK

#### K: Mi áll ennek az oktatóanyagnak a középpontjában?

Ez az oktatóanyag a többoszlopos PDF létrehozásának folyamatán összpontosít, az Aspose.PDF for .NET könyvtár használatával. A mellékelt C# forráskód bemutatja az ehhez szükséges lépéseket.

#### K: Mely névtereket kell importálnom ehhez az oktatóanyaghoz?

V: Abban a kódfájlban, amelyben több oszlopból álló PDF-et szeretne létrehozni, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre új dokumentumpéldányt?

 V: A 4. lépésben egy új példányt fog létrehozni`Document` objektumot a megadott kód segítségével.

#### K: Hogyan állíthatom be az oldalmargókat?

 V: Az 5. lépésben a`PageInfo.Margin` tulajdona a`Document` a bal és a jobb margó információinak megadásához a PDF-fájlhoz.

#### K: Hogyan adhatok hozzá oldalt a dokumentumhoz?

 V: A 6. lépésben új oldalt ad hozzá a dokumentumhoz a`Add` módszere a`Pages` Gyűjtemény.

#### K: Hogyan hozhatok létre egy Graph objektumot és adhatok hozzá egy sort?

 V: A 7. lépésben újat hoz létre`Graph` objektumot, adjon hozzá egy sort, majd adja hozzá a`Graph` tiltakozik a`Paragraphs` az oldal gyűjteménye.

#### K: Hogyan adhatok hozzá címsort HTML formázással?

 V: A 8. lépésben létrehoz egy`HtmlFragment` objektumot, és állítsa be a tartalmát a kívánt HTML szövegre, majd adja hozzá a töredéket a`Paragraphs` az oldal gyűjteménye.

#### K: Hogyan hozhatok létre több oszlopos FloatingBoxot?

 V: A 9. lépésben létrehoz egy`FloatingBox` objektumot több oszloppal és oszlopközökkel, majd adjon hozzá szövegtöredékeket és egy sort a`Paragraphs` gyűjteménye a`FloatingBox`.

#### K: Hogyan menthetem el a PDF dokumentumot?

 V: A 10. lépésben a PDF-dokumentumot a`Save` módszere a`Document` tárgy.

#### K: Mi a fő kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan hozhat létre többoszlopos PDF-dokumentumot az Aspose.PDF for .NET használatával. Ez hasznos lehet a tartalom strukturált és szervezett elrendezésben történő megjelenítéséhez.