---
title: Szavak kihúzása
linktitle: Szavak kihúzása
second_title: Aspose.PDF for .NET API Reference
description: Ebből az átfogó, lépésenkénti útmutatóból megtudhatja, hogyan lehet szavakat kihúzni egy PDF-ből az Aspose.PDF for .NET használatával. Fejlessze dokumentumszerkesztési készségeit.
type: docs
weight: 150
url: /hu/net/annotations/strikeoutwords/
---
## Bevezetés

Előfordult már, hogy egy PDF-fájlban egy adott szöveget ki kell hangsúlyoznia úgy, hogy áthúzza? Akár dokumentumokat tekint át, akár szöveget jelöl meg, akár egyszerűen csak bizonyos részeket szeretne kiemelni, a szavak áthúzása értékes eszköz lehet. Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet ezt megtenni az Aspose.PDF for .NET használatával. Ez az átfogó útmutató végigvezeti Önt az egyes lépéseken, biztosítva, hogy minden információ birtokában legyen ennek a funkciónak a .NET-alkalmazásaiban való hatékony megvalósításához. 

## Előfeltételek

Mielőtt belevágnánk a kódba, van néhány előfeltétel, amelyeket teljesítenie kell, hogy kövesse ezt az oktatóanyagot:

1.  Aspose.PDF for .NET Library: Győződjön meg arról, hogy az Aspose.PDF for .NET könyvtár telepítve van. Tudod[töltse le itt](https://releases.aspose.com/pdf/net/).

2. .NET-keretrendszer: Győződjön meg arról, hogy a .NET-keretrendszer telepítve van a számítógépen. Ez az oktatóanyag .NET-alkalmazásokhoz készült.

3. Fejlesztési környezet: A kód írásához és futtatásához olyan IDE-re lesz szüksége, mint a Visual Studio.

4. PDF-dokumentum: Készítsen egy PDF-mintafájlt, amellyel dolgozni szeretne. Ez lesz az a dokumentum, ahol áthúzzuk a szöveget.

5. Alapvető C# ismeretek: A C# programozás ismerete szükséges az oktatóanyag lépéseinek megértéséhez és végrehajtásához.

## Csomagok importálása

Mielőtt elkezdhetnénk a kódolást, importálnunk kell a szükséges névtereket a .NET projektünkbe. Ez hozzáférést biztosít számunkra a PDF-fájlok Aspose.PDF használatával történő kezeléséhez szükséges osztályokhoz és módszerekhez.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Ezek a névterek elengedhetetlenek a PDF-dokumentumokkal való munkavégzéshez, a szövegek kezeléséhez és a megjegyzések, például az áthúzások hozzáadásához.

Ebben a részben a szavak kihúzásának folyamatát egy PDF-dokumentumban egyszerű, kezelhető lépésekre bontjuk. Minden lépést részletes magyarázat kísér, hogy megértse, hogyan működik minden.

## 1. lépés: Töltse be a PDF-dokumentumot

Az első lépés a szerkeszteni kívánt PDF dokumentum betöltése. Ez a dokumentum lesz az, ahol konkrét szavakat vagy kifejezéseket fog kihúzni.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a PDF dokumentumot
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Ez a változó tartalmazza a dokumentumkönyvtár elérési útját. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a PDF-fájl tényleges elérési útjával.
- `Document` : A`Document` osztály egy PDF dokumentumot jelent. A fájl elérési útját a konstruktorának átadva megnyitjuk a PDF fájlt feldolgozásra.

## 2. lépés: Hozzon létre egy szövegtöredék-elnyelőt az adott szöveg megkereséséhez

 Ezután létrehozunk egy példányt`TextFragmentAbsorber` adott szövegrészlet megkereséséhez a PDF dokumentumban. Ez lehetővé teszi, hogy megtaláljuk a kihúzni kívánt szöveget.

```csharp
// Hozzon létre TextFragment Absorber példányt egy adott szövegrészlet kereséséhez
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Ez az osztály meghatározott szövegrészletek megkeresésére és kezelésére szolgál a PDF-dokumentumban. Ebben a példában az "Estoque" szóra keresünk. Cserélje le az „Estoque” szót vagy kifejezést, amelyet a dokumentumban keresni szeretne.

## 3. lépés: Ismételje meg a PDF-dokumentum oldalait

 Most, hogy megvan a miénk`TextFragmentAbsorber`, végig kell ismételnünk a PDF-dokumentum minden oldalát, hogy megtaláljuk a megadott szöveget.

```csharp
// Iteráljon a PDF-dokumentum oldalain
for (int i = 1; i <= document.Pages.Count; i++)
{
    // A PDF-dokumentum aktuális oldalának lekérése
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: Ez a ciklus a PDF-dokumentum minden oldalán áthalad.
- `document.Pages[i]`: Az aktuális feldolgozás alatt álló oldal lekérése.
- `page.Accept(textFragmentAbsorber)` : Ez a módszer a`TextFragmentAbsorber` az aktuális oldalra, a megadott szövegre keresve.

## 4. lépés: Gyűjtse össze és dolgozza fel a szövegtöredékeket

Az oldalak iterációja után összegyűjtjük a talált szövegrészleteket, és előkészítjük a további feldolgozásra.

```csharp
// Hozzon létre egy gyűjteményt elnyelt szövegrészletekből
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Ez a gyűjtemény a dokumentumban található összes szövegrészletet tárolja. A következő lépésben ezt a gyűjteményt használjuk a szöveg áthúzására.

## 5. lépés: Ismételje meg a szövegrészleteket, és húzza ki őket

Ebben a lépésben végigfutjuk gyűjteményünk minden egyes szövegrészletét, és áthúzunk rájuk.

```csharp
// Iteráljon a szövegrészletek gyűjteményén
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Szerezze meg a TextFragment objektum téglalap alakú méreteit
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // A StrikeOut Annotation példány példányosítása
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Állítsa be az áthúzott megjegyzés tulajdonságait
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Adja hozzá a megjegyzést a szövegrészlet oldalának megjegyzésgyűjteményéhez
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: Ez a sor az aktuális szövegrészletet kéri le.
- `Aspose.Pdf.Rectangle`: Kiszámoljuk a szövegrészlet téglalap alakú méreteit, hogy meghatározzuk, hol alkalmazzuk az áthúzást.
- `StrikeOutAnnotation`: Ez az osztály az áthúzott megjegyzést jelöli. Példányosítjuk a számított téglalappal és az aktuális oldallal.
- `strikeOut.Opacity`: Ez a tulajdonság beállítja a kihúzás átlátszatlanságát, így 80%-ban láthatóvá válik.
- `strikeOut.Color`Az áthúzás színét pirosra állítottuk. Ezt bármilyen kívánt színre módosíthatja.
- `textFragment.Page.Annotations.Add(strikeOut)`: Ezzel hozzáadja az áthúzott megjegyzést az oldalhoz.

## 6. lépés: Mentse el a módosított PDF-dokumentumot

Az utolsó lépés a módosított PDF-dokumentum mentése az alkalmazott áthúzással.

```csharp
// Mentse el a frissített PDF dokumentumot
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: Ez új fájlnevet hoz létre a módosított dokumentumhoz. Az eredeti fájl változatlan marad.
- `document.Save(dataDir)`: Az áthúzott PDF-dokumentumot a megadott helyre menti.

## Következtetés

Gratulálok! Sikeresen kihúzott bizonyos szavakat egy PDF-dokumentumból az Aspose.PDF for .NET használatával. Ennek a lépésről lépésre szóló útmutatónak a követésével most személyre szabhatja a PDF-dokumentumokat a szöveg kiemelésével vagy kihúzásával, így dinamikusabbá és az Ön igényeihez szabottabbá teheti azokat. Akár jogi dokumentumokat ír, akár jelentéseket készít, akár csak szöveget jelöl meg áttekintésre, ez az oktatóanyag felvértezi Önt a hatékony munkavégzéshez szükséges készségekkel.

## GYIK

### Megváltoztathatom az áthúzás színét?

 Igen, módosíthatja a színt a`strikeOut.Color`ingatlan. Például beállíthatja`Aspose.Pdf.Color.Blue` kék áthúzásra.

### Lehetséges egyszerre több szót kihúzni?

 Teljesen! A`TextFragmentAbsorber` használható bármely szó vagy kifejezés keresésére a dokumentumban. Az áthúzást több példányra is alkalmazhatja a következőn keresztül történő iterációval`TextFragmentCollection`.

### Mi a teendő, ha csak bizonyos oldalakon szeretném áthúzni a szöveget?

 Módosíthatja az oldalakon iteráló ciklust úgy, hogy csak a módosítani kívánt oldalakat tartalmazza. Például,`for (int i = 1; i <= 3; i++)` csak az első három oldalon alkalmazná az áthúzást.

### Hogyan állíthatom be az áthúzó vonal vastagságát?

 Az áthúzott vonal vastagságát módosíthatja a`Border` tulajdona a`StrikeOutAnnotation`. Ez lehetővé teszi az áthúzás megjelenésének testreszabását.

### Van mód a kihúzás visszavonására a dokumentum mentése után?

dokumentum mentése után az áthúzás végleges. Ha meg kell tartania az eredeti szöveget az áthúzás nélkül, fontolja meg az eredeti dokumentum biztonsági másolatának mentését, mielőtt bármilyen módosítást alkalmazna.