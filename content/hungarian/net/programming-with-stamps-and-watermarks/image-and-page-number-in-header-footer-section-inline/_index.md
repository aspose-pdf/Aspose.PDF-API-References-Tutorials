---
title: Kép és oldalszám a Fejléc lábléc szakaszában soron belül
linktitle: Kép és oldalszám a Fejléc lábléc szakaszában soron belül
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről-lépésre szóló útmutatóból megtudhatja, hogyan adhat hozzá közvetlenül egy képet és oldalszámot a PDF fejlécrészéhez az Aspose.PDF for .NET használatával.
type: docs
weight: 120
url: /hu/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Bevezetés

Az Aspose.PDF for .NET egy hatékony eszköz, amely kiterjedt lehetőségeket biztosít PDF-fájlok kezeléséhez és létrehozásához. Akár képeket kell hozzáadnia, akár testre kell szabnia a fejlécet és láblécet, akár szöveget kell kezelnie, az Aspose.PDF mindent megtesz. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet képet és oldalszámot közvetlenül hozzáadni egy PDF-dokumentum fejlécéhez vagy láblécéhez. Merüljünk el, és bontsuk le a folyamatot lépésről lépésre.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjünk meg arról, hogy minden a helyén van a követéshez:

-  Aspose.PDF for .NET: Töltse le a legújabb verziót a[Aspose PDF letöltési oldal](https://releases.aspose.com/pdf/net/).
- Fejlesztési környezet: Szüksége lesz egy C# IDE-re, például a Visual Studiora.
-  Licenc: Ha még nincs jogosítványa, akkor a[ideiglenes engedély itt](https://purchase.aspose.com/temporary-license/) vagy vásároljon egy teljeset a[Aspose üzlet](https://purchase.aspose.com/buy).

Most, hogy készen vannak az előfeltételek, kezdjük.

## Csomagok importálása

A kódolás megkezdése előtt feltétlenül importálja a szükséges névtereket:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ezek a csomagok lehetővé teszik a PDF fájlokkal való munkát és a szövegkezelést.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Az első dolog, amit meg kell tennünk, hogy meghatározzuk annak a könyvtárnak az elérési útját, ahová a PDF-fájlunk mentésre kerül. Ez az elérési út testreszabható a projekt mappájához vagy a számítógép bármely helyéhez.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ez a változó tartalmazza azt a helyet, ahol a dokumentumot tárolni fogják. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges úttal.

## 2. lépés: Példányosítsa a PDF-dokumentumot

 Ebben a lépésben létrehozzuk a`Aspose.Pdf.Document` objektum. Ez az objektum szolgál majd a PDF-fájl gerinceként.

```csharp
// Példányosítson egy dokumentum objektumot az üres konstruktor meghívásával
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Itt egy üres PDF-fájlt hozunk létre, amelyet később feltölthetünk tartalommal.

## 3. lépés: Adjon hozzá egy oldalt a PDF-hez

A PDF-nek legalább egy oldalra van szüksége, ahol fejléceket, láblécet és tartalmat adhat hozzá. Adjunk hozzá egy üres oldalt a dokumentumunkhoz.

```csharp
// Hozzon létre egy oldalt a PDF objektumban
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 Hívással`pdf1.Pages.Add()`egy új oldal kerül a dokumentumba, amely készen áll a fejléc és lábléc testreszabására.

## 4. lépés: Hozza létre és állítsa be a fejlécet

Itt az ideje, hogy létrehozza a dokumentum fejlécét. Itt adjuk hozzá a szöveget, a képet és az oldalszámot.

```csharp
// Hozzon létre fejléc szakaszt a dokumentumban
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Állítsa be a PDF-fájl fejlécét
page.Header = header;
```

 Létrehozunk a`HeaderFooter` objektumot, és rendelje hozzá a`Header` az oldal tulajdonsága, biztosítva, hogy bármi, amit a fejléchez adunk, az oldal tetején jelenjen meg.

## 5. lépés: Adjon hozzá szöveget a fejléchez

 Szöveg hozzáadása olyan egyszerű, mint a`TextFragment` és tulajdonságainak megadása. Adjunk hozzá színes szöveget a fejlécünkhöz.

```csharp
// Hozzon létre egy szöveg objektumot
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Adja meg a színt
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 Ebben a lépésben létrehozzuk a`TextFragment` az "Aspose.Pdf is a Robust komponent by" tartalommal, és állítsa be a színét kékre. A`IsInLineParagraph` A tulajdonság biztosítja, hogy a szöveg soron belüli legyen, vagyis ugyanabban a sorban fog megjelenni, mint a többi elem (például a kép és a kiegészítő szöveg).

## 6. lépés: Szúrjon be egy soron belüli képet a fejlécbe

Annak érdekében, hogy a fejléc vizuálisan tetszetős legyen, hozzáadhat egy képet a szöveghez. Ez lehet a cég logója vagy bármilyen más grafika.

```csharp
// Hozzon létre egy képobjektumot a szakaszban
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Állítsa be a képfájl elérési útját
image1.File = dataDir + "aspose-logo.jpg";
// Állítsa be a képszélesség információit
image1.FixWidth = 50;
image1.FixHeight = 20;
// Jelezze, hogy a seg1 InlineParagraphja egy kép.
image1.IsInLineParagraph = true;
```

 Itt egy képet adunk a fejléchez úgy, hogy létrehozunk egy`Image` objektumot, útvonalát, valamint a szélességet és magasságot. A`IsInLineParagraph` biztosítja, hogy a kép igazodjon a szöveghez.

## 7. lépés: Adjon hozzá további soron belüli szöveget a fejléc kitöltéséhez

Adjunk hozzá további szöveget a soron belüli fejléc kiegészítéséhez.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 Ebben a részben létrehozunk egy másikat`TextFragment` "Pty Ltd." tartalommal. és állítsa a színét gesztenyebarnara. Mind a szövegtöredékek, mind a kép hozzáadásra kerül a fejléchez.

## 8. lépés: Mentse el a PDF-fájlt

Miután beállította a fejlécet, ideje elmenteni a PDF-fájlt.

```csharp
// Mentse el a PDF-et
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 A`Save` módszer a végső PDF-fájlt a megadott helyre írja.

## Következtetés

Gratulálok! Sikeresen hozzáadott egy képet és szöveget egy PDF-dokumentum fejlécéhez az Aspose.PDF for .NET használatával. Ez az oktatóanyag végigvezeti Önt az alapvető lépéseken, beleértve a dokumentum létrehozását, az oldalak hozzáadását, a fejlécek beszúrását és a beágyazott tartalom, például szöveg és képek elhelyezését. Az Aspose.PDF hihetetlen rugalmasságot biztosít a PDF-fájlok kezelésében, legyen szó fejlécek, láblécek vagy összetett tartalom kezeléséről. 

## GYIK

### Hozzáadhatok oldalszámot a fejléchez is?
 Igen! Könnyen hozzáadhat oldalszámot a gombbal`TextFragment` osztályt, és szükség szerint formázzuk. Csak illessze be a fejléc részbe soron belüli tartalomként.

### Hogyan állíthatok be háttérképet a fejlécben?
 Használhatja a`BackgroundImage` tulajdona a`HeaderFooter` osztályban háttérkép beállításához. Ez azonban nem inline tartalom, hanem a teljes fejlécterületet lefedi.

### Lehetséges a JPEG-en kívül más képformátumokat is használni?
Teljesen! Az Aspose.PDF különféle képformátumokat támogat, például PNG, BMP és GIF.

### Testreszabhatom a fejlécben lévő szöveg betűtípusát?
 Igen, használhatod a`TextState`objektumot a szöveg betűtípusának, méretének és stílusának módosításához.

### Szükségem van licencre az Aspose.PDF for .NET használatához?
 Igen, az Aspose.PDF éles felhasználáshoz licenc szükséges, de kezdheti a[ingyenes próbaverzió itt](https://releases.aspose.com/).