---
title: Szöveg kibontása az oldalrégióból PDF-fájlban
linktitle: Szöveg kibontása az oldalrégióból PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan lehet szöveget kivonni egy adott régióból a PDF-ben az Aspose.PDF for .NET használatával. Hatékonyan gyűjthet össze és menthet szöveget dokumentumaiból.
type: docs
weight: 190
url: /hu/net/programming-with-text/extract-text-from-page-region/
---
## Bevezetés

A PDF-fájlokkal való munkavégzés gyakran megköveteli bizonyos tartalom kinyerését, legyen az adatgyűjtés űrlapokból, táblázatokból vagy a dokumentum bizonyos részeiből. Ebben az oktatóanyagban végigvezetjük, hogyan lehet szöveget kivonni a PDF egy adott régiójából az Aspose.PDF for .NET használatával. A teljes dokumentum átvizsgálása helyett pontosan meghatározzuk a szöveg helyét, és hatékonyan kibontjuk.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjön meg arról, hogy a következő elemek a helyükön vannak:

1.  Aspose.PDF for .NET: Ha még nem tette meg, töltse le és telepítse az Aspose.PDF for .NET könyvtárat.[Töltse le az Aspose.PDF-et .NET-hez](https://releases.aspose.com/pdf/net/).
2. IDE: Bármilyen .NET fejlesztői környezet, például a Visual Studio.
3. .NET-keretrendszer: Győződjön meg arról, hogy projektje a megfelelő .NET-keretrendszerrel van beállítva.
4. PDF-dokumentum: PDF-minta, amelyből kivonjuk a szöveget.

 Ne felejtsd el, hogy megteheted[kap egy ingyenes próbaverziót](https://releases.aspose.com/) Az Aspose.PDF-ből vagy használja a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) a teljes funkcionalitás érdekében.

## szükséges csomagok importálása

Az Aspose.PDF for .NET használatához importálnia kell a szükséges névtereket a projektbe. Ezek a csomagok biztosítják a PDF dokumentumok kezeléséhez szükséges osztályokat és módszereket.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## 1. lépés: A dokumentumkönyvtár beállítása és a PDF betöltése

Az első lépés az, hogy adja meg, hol található a PDF-fájl, és töltse be a projektbe. Használhatja a dolgozni kívánt PDF-fájl helyi könyvtárának elérési útját.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a PDF dokumentumot
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

 Ez a lépés biztosítja, hogy a PDF-fájl megfelelően betöltődik, és készen áll a munkára. A`Document` osztály az Aspose.PDF könyvtárból lehetővé teszi a PDF fájl kezelését.

## 2. lépés: Inicializálja a szövegabszorbert a kivonathoz

 Ebben a lépésben létrehozzuk a`TextAbsorber` objektum, amely szöveg kinyerésére szolgál egy PDF dokumentumból. A`TextAbsorber` rugalmas, és testreszabható, hogy meghatározott régiókra vagy oldalakra összpontosítson.

```csharp
// Hozzon létre egy TextAbsorber objektumot a szöveg kivonásához
TextAbsorber absorber = new TextAbsorber();
```

 A`TextAbsorber`osztály egy hatékony eszköz, amely minden szöveget rögzít az Ön által megadott határokon belül.

## 3. lépés: Határozza meg azt a régiót, amelyből ki szeretné bontani a szöveget

Itt történik a varázslat. Ahelyett, hogy a teljes oldalról húznánk ki a szöveget, korlátozhatjuk a kibontást az oldal egy meghatározott téglalap alakú területére. Ez akkor tökéletes, ha pontosan tudja, hol található a tartalom.

```csharp
// A szövegkivonás korlátozása egy adott régióra
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

 A`Rectangle` Az objektum lehetővé teszi annak a területnek a koordinátáit (pontokban), ahonnan a szöveg ki lesz bontva. A`TextSearchOptions.LimitToPageBounds` biztosítja, hogy csak a megadott téglalapon belüli szöveg kerüljön kibontásra.

## 4. lépés: Fogadja el az Absorbert a kívánt oldalon

 A régió beállítása után a következő lépés az, hogy elfogadjuk a`TextAbsorber` ahhoz az oldalhoz, amelyről szöveget szeretne kinyerni. Itt a PDF első oldalára koncentrálunk.

```csharp
// Fogadja el az elnyelőt az első oldalhoz
pdfDocument.Pages[1].Accept(absorber);
```

 Felhívva a`Accept` módszert az oldalon, utasítjuk az Aspose.PDF-et, hogy futtassa az abszorbert, és gyűjtse össze a szöveget a meghatározott régióból.

## 5. lépés: Töltse le és tárolja a kivont szöveget

 Ha az abszorber elvégezte a dolgát, ideje összegyűjteni a kivont szöveget és elmenteni. Ez a lépés magában foglalja a szöveg lekérését és a a`.txt` fájlt.

```csharp
// Szerezd meg a kivont szöveget
string extractedText = absorber.Text;

// Hozzon létre egy írót a kivont szöveg mentéséhez
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

// Írja be a szöveget a fájlba
tw.WriteLine(extractedText);

// Zárd be a patakot
tw.Close();
```

 Itt, a`TextWriter` osztályt a kivont szöveg szövegfájlba írására használják. Ez biztosítja, hogy a kivont tartalmat későbbi felhasználás céljából biztonságosan tároljuk.

## Következtetés

 A szöveg kinyerése egy PDF-dokumentum egy adott régiójából hihetetlenül hasznos lehet, különösen akkor, ha strukturált tartalommal, például űrlapokkal vagy táblázatokkal foglalkozik. Az Aspose.PDF for .NET használatával ezt a feladatot néhány sornyi kóddal elvégezheti. Egy régió meghatározásával, inicializálásával a`TextAbsorber`, és a kivont szöveg elmentésével teljes mértékben szabályozhatja, hogy mi kerüljön ki a PDF-ből.

Akár egy kis projekten dolgozik, akár nagy dokumentumokat kezel, ezzel a módszerrel hatékonyan kinyerheti a releváns adatokat PDF-fájljaiból anélkül, hogy a teljes dokumentumot átfésülné.

## GYIK

### Kivonhatok szöveget több oldalról egyszerre?
 Igen, a`Pages` gyűjteménye a`pdfDocument` , alkalmazhatja a`TextAbsorber` több oldalra.

### Mi a teendő, ha a szöveg a PDF egy másik régiójában található?
 Könnyen beállíthatja a`Rectangle` koordinátákat, hogy megfeleljenek annak a régiónak, ahol a szöveg található.

### Működik ez a beolvasott PDF-ekkel?
Nem, a beolvasott PDF-fájlokhoz OCR-re (optikai karakterfelismerésre) van szükség a képek szöveggé alakításához. Az Aspose.PDF OCR funkciókat is kínál.

### Van mód szöveg kivonására meghatározott kulcsszavak alapján?
 Igen, használhatod`TextFragmentAbsorber` kulcsszó alapú szövegkinyeréshez.

### Hogyan bonthatok ki szöveget egy titkosított PDF-ből?
Először dekódolnia kell a PDF-fájlt a helyes jelszó megadásával, majd folytassa a szöveg kibontásával.