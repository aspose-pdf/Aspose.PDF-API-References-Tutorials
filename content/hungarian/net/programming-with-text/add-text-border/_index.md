---
title: Szövegszegély hozzáadása PDF-fájlhoz
linktitle: Szövegszegély hozzáadása PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá szövegszegélyt PDF-fájlhoz az Aspose.PDF for .NET használatával.
type: docs
weight: 70
url: /hu/net/programming-with-text/add-text-border/
---
Ez az oktatóanyag végigvezeti Önt a PDF-fájl szövegszegélyének hozzáadásának folyamatán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyhez hozzá szeretné adni a szövegszegélyt, adja hozzá a következőket a fájl tetején található direktíva használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Hozzon létre egy új dokumentum objektumot
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Document pdfDocument = new Document();
```

## 5. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Új oldal hozzáadása a dokumentumhoz a gombbal`Add` módszere a`Pages` gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 6. lépés: Hozzon létre egy szövegrészletet
 Hozzon létre a`TextFragment`objektumot, és adja meg a kívánt szöveget. Állítsa be a szövegrészlet pozícióját a gombbal`Position` ingatlan. A megadott kódban a szöveg „főszöveg”-re van állítva, és az oldalon (100, 600) található.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 7. lépés: Állítsa be a szöveg tulajdonságait
Testreszabhatja a szövegtulajdonságokat, például a betűméretet, a betűtípust, a háttérszínt, az előtérszínt stb. A megadott kódban olyan tulajdonságok vannak beállítva a szövegrészlethez, mint a betűméret, a betűtípus, a háttérszín, az előtér színe és a körvonalszín.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 8. lépés: Engedélyezze a szövegszegélyt
 A szövegszegély engedélyezéséhez állítsa be a`DrawTextRectangleBorder` a szövegrészlet tulajdonsága`TextState` hogy`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 9. lépés: Adja hozzá a TextFragmentet az oldalhoz
 Használja a`TextBuilder` osztály hozzáadásához a`TextFragment` tiltakozik az oldalra.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## 10. lépés: Mentse el a PDF dokumentumot
 Mentse el a PDF dokumentumot a`Save` módszere a`Document` objektum. Adja meg a kimeneti fájl elérési útját, amelyet a 3. lépésben állított be.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Forráskód minta a Szövegszegély hozzáadása az Aspose.PDF for .NET használatával fájlhoz 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Új dokumentum objektum létrehozása
Document pdfDocument = new Document();
// Szerezzen be egy adott oldalt
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Szövegrészlet létrehozása
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Állítsa be a szöveg tulajdonságait
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Állítsa be a StrokingColor tulajdonságot a szöveges téglalap körüli szegély (vonás) rajzolásához
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Állítsa a DrawTextRectangleBorder tulajdonság értékét igazra
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Mentse el a dokumentumot
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Következtetés
Sikeresen hozzáadott egy szövegszegélyt a PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

### GYIK

#### K: Mi a fő hangsúly ebben az oktatóanyagban?

V: Ez az oktatóanyag végigvezeti Önt a PDF-fájl szövegszegélyének hozzáadásának folyamatán az Aspose.PDF for .NET könyvtár használatával. A mellékelt C# forráskód bemutatja az ehhez szükséges lépéseket.

#### K: Milyen névtereket kell importálnom ehhez az oktatóanyaghoz?

V: Abban a kódfájlban, amelyhez a szövegszegélyt hozzá szeretné adni, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre egy dokumentum objektumot?

 V: A 4. lépésben egy új példányt fog létrehozni`Document` objektum a következő kódsor használatával:

```csharp
Document pdfDocument = new Document();
```

#### K: Hogyan adhatok hozzá oldalt a dokumentumhoz?

 V: Az 5. lépésben új oldalt ad hozzá a dokumentumhoz a`Add` módszere a`Pages` gyűjtemény:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### K: Hogyan hozhatok létre szövegtöredéket és állíthatom be a pozícióját?

 V: A 6. lépésben létrehoz egy`TextFragment` objektumot, és állítsa be a pozícióját az oldalon a gombbal`Position` ingatlan:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### K: Hogyan szabhatom testre a szöveg tulajdonságait, beleértve a szövegszegélyt is?

V: A 7. lépésben testreszabhatja a különböző szövegtulajdonságokat, például a betűméretet, a betűtípust, a háttérszínt, az előtér színét és a szövegszegélyt:

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### K: Hogyan adhatom hozzá a szövegtöredéket a PDF dokumentumhoz?

 V: A 9. lépésben a`TextBuilder` osztály hozzáadásához a`TextFragment` objektum az oldalra:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### K: Hogyan menthetem el az eredményül kapott PDF-dokumentumot?

V: Miután hozzáadta a szöveget szegéllyel, használja a`Save` módszere a`Document` objektum a PDF dokumentum mentéséhez:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### K: Mi a fő kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével sikeresen megtanulta, hogyan javíthatja PDF-dokumentumát szövegszegély hozzáadásával az Aspose.PDF for .NET használatával. Ez különösen hasznos lehet a PDF-fájlok bizonyos szöveges tartalmának kiemeléséhez.