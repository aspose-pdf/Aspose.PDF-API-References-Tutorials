---
title: Következő sorok behúzása hozzáadása a PDF-fájlhoz
linktitle: Következő sorok behúzása hozzáadása a PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá sorok behúzását a PDF-fájl szövegéhez az Aspose.PDF for .NET segítségével.
type: docs
weight: 60
url: /hu/net/programming-with-text/add-subsequent-lines-indent/
---
Ez az oktatóanyag végigvezeti Önt a következő sorok behúzásának a PDF-fájl szövegéhez való hozzáadásának folyamatán az Aspose.PDF for .NET segítségével. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelybe a következő sorok behúzását kívánja hozzáadni, adja hozzá a következőt a fájl tetején található direktíva használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Hozzon létre egy új dokumentum objektumot
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## 5. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Új oldal hozzáadása a dokumentumhoz a gombbal`Add` módszere a`Pages`gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## 6. lépés: Hozzon létre egy szövegtöredéket következő sorok behúzásával
 Példányosítás a`TextFragment` objektumot, és adja meg a kívánt szöveget. A megadott kódban a szöveg hozzá van rendelve a változóhoz`text` . Ezután inicializálja`TextFormattingOptions` a`TextFragment`és adja meg a`SubsequentLinesIndent` érték.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## 7. lépés: Adja hozzá a TextFragmentet az oldalhoz
 Add hozzá a`TextFragment` tiltakozik az oldal bekezdésgyűjteményével szemben.

```csharp
page.Paragraphs.Add(text);
```

## 8. lépés: Ismételje meg a 6. és 7. lépést további sorokhoz
Ha további sorokat szeretne hozzáadni ugyanazzal a behúzással, ismételje meg a 6. és 7. lépést minden sornál. Szükség szerint frissítse a szöveges tartalmat.

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

## 9. lépés: Mentse el a PDF dokumentumot
 Mentse el a PDF dokumentumot a`Save` módszere a`Document` objektum. Adja meg a kimeneti fájl elérési útját.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Forráskód minta a következő sorok behúzásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Új dokumentum objektum létrehozása
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
// Inicializálja a TextFormattingOptions parancsot a szövegrészlethez, és adja meg a SubsequentLinesIndent értéket
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

## Következtetés
Sikeresen hozzáadta a következő sorok behúzását a szöveghez az Aspose.PDF for .NET segítségével. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

### GYIK

#### K: Mi áll ennek az oktatóanyagnak a középpontjában?

V: Ez az oktatóanyag átfogó útmutatást nyújt arról, hogyan lehet a következő sorok behúzását hozzáadni egy PDF-fájl szövegéhez az Aspose.PDF for .NET könyvtár használatával. C# forráskód példákat tartalmaz, amelyek bemutatják az ehhez szükséges lépéseket.

#### K: Milyen névtereket kell importálnom ehhez az oktatóanyaghoz?

V: Abba a kódfájlba, amelybe a következő sorok behúzását kívánja hozzáadni, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre egy dokumentum objektumot?

 V: A 4. lépésben egy új példányt fog létrehozni`Document` objektum a következő kódsor használatával:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### K: Hogyan adhatok hozzá oldalt a dokumentumhoz?

 V: Az 5. lépésben új oldalt ad hozzá a dokumentumhoz a`Add` módszere a`Pages` gyűjtemény:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### K: Hogyan adhatok hozzá következő sorok behúzását a szöveghez?

 V: A 6. lépésben létrehoz egy`TextFragment` objektumot, és rendelje hozzá a kívánt szöveget. Ezután inicializálja`TextFormattingOptions` a`TextFragment`és adja meg a`SubsequentLinesIndent` érték:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### K: Hogyan adhatom hozzá a szövegtöredéket a PDF dokumentumhoz?

 V: A 7. lépésben hozzáadja a`TextFragment` tárgy (`text`) az oldal bekezdésgyűjteményéhez:

```csharp
page.Paragraphs.Add(text);
```

#### K: Megismételhetem a folyamatot további soroknál?

 V: Igen, a 8. lépésben megismételheti a folyamatot további sorok esetében is, ugyanazzal a behúzással új létrehozásával`TextFragment` objektumokat, és hozzáadjuk őket az oldal bekezdésgyűjteményéhez.

#### K: Hogyan menthetem el az eredményül kapott PDF-dokumentumot?

 V: Miután hozzáadta a szöveget a következő sorok behúzásával, használja a`Save` módszere a`Document` objektum a PDF dokumentum mentéséhez:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével sikeresen megtanulta, hogyan javíthatja a PDF-dokumentum szövegének olvashatóságát az Aspose.PDF for .NET segítségével sorok behúzásával. Ez a technika különféle típusú dokumentumok és jelentések esetén hasznos lehet.