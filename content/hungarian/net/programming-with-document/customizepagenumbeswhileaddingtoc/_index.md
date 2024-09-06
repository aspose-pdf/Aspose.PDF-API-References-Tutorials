---
title: Az oldalszámok testreszabása a tartalomjegyzék hozzáadása közben
linktitle: Az oldalszámok testreszabása a tartalomjegyzék hozzáadása közben
second_title: Aspose.PDF for .NET API Reference
description: Ebben az átfogó oktatóanyagban megtudhatja, hogyan testreszabhatja az oldalszámokat, miközben tartalomjegyzéket ad hozzá PDF-dokumentumaihoz az Aspose.PDF for .NET használatával.
type: docs
weight: 100
url: /hu/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## Bevezetés

dokumentumkezelés világában a PDF-ek uralkodnak. Ezek a legjobb formátumok a dokumentumok megosztásához és megőrzéséhez különböző platformokon. De mi történik akkor, ha PDF-dokumentumait olyan funkciókkal szeretné bővíteni, mint a tartalomjegyzék (TOC)? Itt jön képbe az Aspose.PDF for .NET! Ez a nagy teljesítményű könyvtár lehetővé teszi a fejlesztők számára a PDF-fájlok egyszerű kezelését, lehetővé téve számukra a tartalom könnyű hozzáadását, módosítását és testreszabását. Ebben az oktatóanyagban bemutatjuk, hogyan lehet testreszabni az oldalszámokat, miközben tartalomjegyzéket ad hozzá PDF-dokumentumaihoz az Aspose.PDF for .NET használatával. Szóval, fogd meg a kódoló kalapot, és kezdjük is!

## Előfeltételek

Mielőtt belevágnánk a kódba, néhány dolgot meg kell határoznia:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Ez lesz a fejlesztési környezetünk.
2. Aspose.PDF for .NET: Le kell töltenie és telepítenie kell az Aspose.PDF könyvtárat. Megtalálhatod[itt](https://releases.aspose.com/pdf/net/).
3. Alapvető C# ismerete: A C# programozás ismerete segít jobban megérteni a kódrészleteket.
4. Minta PDF fájl: Készítsen egy minta PDF fájlt, amellyel dolgozni tudunk. Létrehozhat egy egyszerűt, vagy letölthet egy meglévő PDF-et.

## Csomagok importálása

A kezdéshez importálnunk kell a szükséges csomagokat. Nyissa meg a Visual Studio projektet, és adjon hozzá hivatkozást az Aspose.PDF könyvtárhoz. Ezt a NuGet Package Manager használatával teheti meg:

1. Kattintson a jobb gombbal a projektre a Solution Explorerben.
2. Válassza a "NuGet-csomagok kezelése" lehetőséget.
3. Keresse meg az "Aspose.PDF" kifejezést, és telepítse.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Miután telepítette a könyvtárat, elkezdheti a kódolást!

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Először is be kell állítanunk a dokumentumkönyvtárunkat. Itt tároljuk a bemeneti és kimeneti PDF fájljainkat. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

Ebben a részletben cserélje ki`YOUR DOCUMENT DIRECTORY` a PDF-fájlok tényleges elérési útjával. Ez segít a meglévő PDF betöltésében és a módosított verzió mentésében.

## 2. lépés: Töltse be a meglévő PDF-fájlt

Most, hogy beállítottuk a dokumentumkönyvtárunkat, töltsük be a meglévő PDF-fájlt. 

```csharp
Document doc = new Document(inFile);
```

 Itt létrehozunk egy újat`Document` objektumot a bemeneti fájl elérési útjának átadásával. Ez lehetővé teszi számunkra a PDF-tartalom programozott kezelését.

## 3. lépés: Szúrjon be egy új oldalt a tartalomjegyzékhez

Ezután létre kell hoznunk egy új oldalt a PDF-ben, ahol a tartalomjegyzék található.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

Ez a sor egy új oldalt szúr be a dokumentum elejére. A TOC ezen az oldalon jelenik meg.

## 4. lépés: Hozzon létre TOC információkat

Most hozzunk létre egy objektumot a tartalomjegyzék információ megjelenítésére.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

 Ebben a lépésben létrehozzuk a`TocInfo` objektumot, és állítsa a címét "Tartalomjegyzék"-re. A betűméretet és -stílust is személyre szabjuk. A`PageNumbersPrefix` "P"-re van állítva, amely a tartalomjegyzékben az oldalszámok elé kerül.

## 5. lépés: Adjon hozzá címeket a tartalomjegyzékhez

Most jön a szórakoztató rész! Végigpörgetjük a dokumentum oldalait, és fejléceket adunk a TOC-hoz.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

 Ebben a ciklusban újat hozunk létre`Heading` objektumot minden oldalhoz. Minden címsorhoz beállítjuk a céloldalt, és megadjuk a megjelenítendő szöveget, ami az "X oldal", ahol X az oldalszám. Végül hozzáadjuk a címsort a TOC oldalhoz.

## 6. lépés: Mentse el a frissített dokumentumot

Az összes szükséges címsor hozzáadása után ideje elmenteni frissített dokumentumunkat.

```csharp
doc.Save(outFile);
```

Ez a sor menti a módosított PDF fájlt a tartalomjegyzékkel együtt. Most megnyithatja a kimeneti fájlt, és megtekintheti a testreszabott tartalomjegyzékét!

## Következtetés

És megvan! Sikeresen testreszabta az oldalszámokat, miközben tartalomjegyzéket adott a PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Ez a nagy teljesítményű könyvtár megkönnyíti a PDF-fájlok kezelését, és mindössze néhány sornyi kóddal jelentősen javíthatja dokumentumait. Akár jelentéseket, e-könyveket vagy bármilyen más típusú PDF-fájlt készít, a tartalomjegyzék nagymértékben javíthatja olvasói navigációját. Szóval, mire vársz? Merüljön el az Aspose.PDF-ben, és kezdjen el lenyűgöző PDF-fájlok létrehozásával még ma!

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok programozott létrehozását, kezelését és konvertálását.

### Használhatom ingyenesen az Aspose.PDF-et?
 Igen, az Aspose ingyenes próbaverziót kínál, amellyel felfedezheti a könyvtár funkcióit. Letöltheti[itt](https://releases.aspose.com/).

### Hogyan kaphatok támogatást az Aspose.PDF fájlhoz?
 Támogatást kaphat az Aspose fórum meglátogatásával[itt](https://forum.aspose.com/c/pdf/10).

### Van ideiglenes engedély?
 Igen, kérhet ideiglenes licencet az Aspose.PDF fájlhoz[itt](https://purchase.aspose.com/temporary-license/).

### Hol vásárolhatok Aspose.PDF-et .NET-hez?
 Megvásárolhatja az Aspose.PDF-et .NET-hez[itt](https://purchase.aspose.com/buy).