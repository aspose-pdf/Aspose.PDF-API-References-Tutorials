---
title: Frissítse a PDF oldal méreteit
linktitle: Frissítse a PDF oldal méreteit
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a PDF oldalméretek frissítéséhez az Aspose.PDF for .NET használatával. Ellenőrizze a méreteket igényei szerint.
type: docs
weight: 150
url: /hu/net/programming-with-pdf-pages/update-dimensions/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a PDF-dokumentum oldalméreteinek frissítéséhez az Aspose.PDF for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén megtudhatja, hogyan módosíthatja az oldalméreteket egy PDF-dokumentumban az Aspose.PDF for .NET használatával.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Alapszintű C# programozási nyelv ismerete
- Aspose.PDF for .NET telepítve a fejlesztői környezetbe

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahová menteni szeretné a szerkesztett PDF-dokumentumot. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF dokumentumot
 Ezután megnyithatja a meglévő PDF dokumentumot a`Document` osztályú Aspose.PDF. Ügyeljen arra, hogy a megfelelő dokumentum elérési utat adja meg.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. lépés: Szerezze be az oldalgyűjteményt
 Mostantól elérheti a PDF-dokumentum oldalgyűjteményét a`Pages` tulajdona a`Document` osztály.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4. lépés: Szerezzen be egy adott oldalt
Ezután kiválaszthatja a dokumentum egy adott oldalát a gyűjtemény oldalának indexével. Ebben a példában a második oldalt használjuk (1. index).

```csharp
Page pdfPage = pageCollection[1];
```

## 5. lépés: Határozza meg az új oldalméreteket
 Most a gombbal állíthatja be az új oldalméretet`SetPageSize()` módszere a`Page`tárgy. Ebben a példában az oldalméreteket A4-re (11,7 x 8,3 hüvelyk) állítjuk, pontokra konvertálva (1 hüvelyk = 72 pont).

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 6. lépés: Mentse el a frissített dokumentumot
 Végül a frissített PDF-dokumentumot fájlba mentheti a`Save()` módszere a`Document`osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### Minta forráskód a dimenziók frissítéséhez az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Oldalgyűjtemény letöltése
PageCollection pageCollection = pdfDocument.Pages;
// Szerezzen be egy adott oldalt
Page pdfPage = pageCollection[1];
// Állítsa be az oldalméretet A4-re (11,7 x 8,3 hüvelyk), Aspose.Pdf-ben pedig 1 hüvelyk = 72 pont
// Tehát az A4-es méretek pontokban a következők lesznek: (842,4, 597,6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
// Mentse el a frissített dokumentumot
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet frissíteni egy oldal méreteit egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ennek a lépésről-lépésre szóló útmutatónak a követésével szükség szerint egyszerűen módosíthatja egy PDF-dokumentum oldalának méretét. Az Aspose.PDF hatékony és rugalmas API-t kínál a PDF-fájlokkal való munkavégzéshez és különféle manipulációk végrehajtásához, beleértve az oldalméretek módosítását. Ezzel a tudással szabályozhatja és testreszabhatja PDF-oldalainak méreteit, hogy megfeleljenek az Ön egyedi igényeinek.

### GYIK a PDF oldalméretek frissítéséhez

#### K: Hogyan frissíthetem egy adott oldal méreteit egy PDF-dokumentumban az Aspose.PDF for .NET használatával?

V: A PDF-dokumentum egy adott oldalának méreteinek frissítéséhez az Aspose.PDF for .NET használatával, kövesse az alábbi lépéseket:

1. Állítsa be a dokumentumkönyvtárat az eredeti PDF-fájl elérési útjának és a frissített PDF-fájl mentési helyének megadásával. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.
2.  Nyissa meg a meglévő PDF-dokumentumot a frissítéshez a`Document` osztályú Aspose.PDF. Ügyeljen arra, hogy megadja az eredeti PDF-dokumentum megfelelő elérési útját.
3.  Nyissa meg a PDF dokumentum oldalgyűjteményét a`Pages` tulajdona a`Document` osztály.
4. Válassza ki a frissíteni kívánt oldalt az oldalgyűjteményből az oldal indexe segítségével. A megadott C# forráskódban a második oldalt használjuk (1. index).
5.  Határozza meg az új oldalméretet a gombbal`SetPageSize()` módszere a`Page` tárgy. A példában az oldalméreteket A4-es méretre (11,7 x 8,3 hüvelyk) állítottuk be, pontokra konvertálva (1 hüvelyk = 72 pont).
6.  Mentse el a frissített PDF-dokumentumot fájlba a`Save()` módszere a`Document`osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

#### K: Frissíthetem a PDF-dokumentum több oldalának méreteit egyidejűleg?

V: Igen, módosíthatja a megadott forráskódot, hogy egyszerre frissítse a PDF-dokumentum több oldalának méretét. Ahelyett, hogy egy adott oldalt választana ki (ahogyan a 4. lépésben látható), végignézheti az oldalgyűjtemény összes oldalát, és minden oldalhoz beállíthatja a kívánt oldalméretet.

#### K: Hogyan konvertálhatom át az oldalméreteket hüvelykből pontokká az Aspose.PDF for .NET használatakor?

 V: Az Aspose.PDF for .NET fájlban az oldalméretekhez használt mértékegység a pont, ahol 1 hüvelyk 72 pontnak felel meg. A hüvelyk pontokká alakításához használhatja a következő képletet:`points = inches * 72`. Például egy 11,7 x 8,3 hüvelykes oldalméret beállításához a megfelelő méreteket a (11,7 * 72) és (8,3 * 72) pontokban számíthatja ki.

#### K: Az oldal méreteinek frissítése hatással lesz a PDF-dokumentum tartalmi elrendezésére?

V: Igen, az oldal méreteinek frissítése hatással lesz a PDF-dokumentum tartalmi elrendezésére az adott oldalon. Amikor módosítja az oldal méreteit, az oldal tartalma ennek megfelelően módosul, hogy illeszkedjen az új méretekhez.

#### K: Lehetséges a módosítások visszaállítása és az eredeti oldalméretek visszaállítása azok frissítése után?

V: Igen, ha vissza szeretné állítani a módosításokat és vissza szeretné állítani az eredeti oldalméreteket, akkor vagy megtarthatja az eredeti PDF-dokumentum másolatát a módosítások elvégzése előtt, vagy újra megnyithatja az eredeti PDF-dokumentumot a változtatások mentése nélkül. Így az eredeti méretek megmaradnak.