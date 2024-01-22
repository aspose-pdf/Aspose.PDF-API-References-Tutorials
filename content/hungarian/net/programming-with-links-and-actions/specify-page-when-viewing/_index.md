---
title: Megtekintéskor adja meg az oldalt
linktitle: Megtekintéskor adja meg az oldalt
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat meg oldalt PDF-fájl megtekintésekor az Aspose.PDF for .NET használatával.
type: docs
weight: 110
url: /hu/net/programming-with-links-and-actions/specify-page-when-viewing/
---
Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan adhat meg egy oldalt PDF-fájl megtekintésekor az Aspose.PDF for .NET használatával.

## 1. lépés: A környezet beállítása

Győződjön meg arról, hogy a fejlesztői környezetet egy C# projekttel és a megfelelő Aspose.PDF hivatkozásokkal állította be.

## 2. lépés: A PDF fájl betöltése

Állítsa be a dokumentumok könyvtárának elérési útját, és töltse fel a PDF-fájlt a következő kóddal:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Töltse be a PDF fájlt
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## 3. lépés: A céloldal megadása

Szerezze meg a céloldal példányát a következő kóddal:

```csharp
Page page2 = doc.Pages[2];
```

 Beállíthatja az indexet`[2]` a kívánt oldal kiválasztásához.

## 4. lépés: A zoom beállítás konfigurálása

Hozzon létre egy változót a céloldal nagyítási tényezőjének beállításához:

```csharp
double zoom = 1;
```

A zoom értékét igényeinek megfelelően állíthatja be.

## 5. lépés: Hozza létre a navigációs műveletet

Hozzon létre egy példányt a navigációs művelethez a megadott céloldal használatával:

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## 6. lépés: A cél beállítása

Állítsa be a céloldalra lépést a koordináták és a nagyítás segítségével:

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## 7. lépés: A dokumentummegnyitási művelet konfigurálása

Állítsa be a dokumentum megnyitási műveletét a létrehozott navigációs művelettel:

```csharp
doc. OpenAction = action;
```

## 8. lépés: Mentse el a frissített dokumentumot

 Mentse el a frissített dokumentumot a`Save` módszer:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Minta forráskód az Oldal megadása megtekintéskor Aspose.PDF for .NET használatával fájlhoz 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Töltse be a PDF fájlt
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Szerezze be a dokumentum második oldalának példányát
Page page2 = doc.Pages[2];
// Hozza létre a változót a céloldal nagyítási tényezőjének beállításához
double zoom = 1;
// Hozzon létre GoToAction példányt
GoToAction action = new GoToAction(doc.Pages[2]);
// Ugrás a 2 oldalra
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Állítsa be a dokumentum megnyitási műveletét
doc.OpenAction = action;
// Mentse el a frissített dokumentumot
doc.Save(dataDir + "goto2page_out.pdf");
```

## Következtetés

Gratulálok ! Most már tudja, hogyan adjon meg egy oldalt PDF megtekintésekor az Aspose.PDF for .NET használatával. Használja ezt a tudást a felhasználói élmény testreszabásához a PDF-dokumentumokban.

Most, hogy befejezte ezt az útmutatót, alkalmazhatja ezeket a koncepciókat saját projektjeire, és tovább fedezheti az Aspose.PDF for .NET szolgáltatásait.

### GYIK 

#### K: Mi a célja a céloldal megadásának PDF-fájl megtekintésekor?

V: A céloldal megadásával szabályozhatja, hogy a PDF-dokumentum melyik oldala jelenjen meg a fájl megnyitásakor. Ez javíthatja a felhasználói élményt azáltal, hogy egy adott oldalra irányítja őket.

#### K: Hogyan lehet hasznos egy céloldal megadása PDF dokumentumokban?

V: A céloldal megadása akkor hasznos, ha egy PDF-dokumentum egy adott szakaszához vagy tartalmához szeretné elvezetni a felhasználókat anélkül, hogy manuálisan kellene navigálnia az oldalakon.

#### K: Hogyan segíti elő az Aspose.PDF for .NET egy céloldal megadását a megtekintéshez?

V: Az Aspose.PDF for .NET API-kat biztosít, amelyek lehetővé teszik a PDF-dokumentum kezdeti nézetének beállítását, beleértve a céloldalt, a nagyítási szintet és egyéb megjelenítési tulajdonságokat.

#### K: Megadhatok bármely oldalt céloldalként?

V: Igen, a PDF-dokumentum bármely oldalát megadhatja a megtekintés céloldalaként. Egyszerűen használja a megfelelő indexet a kívánt oldal kiválasztásához.

#### K: Mi a nagyítási tényező jelentősége a céloldal megadásakor?

V: A nagyítási tényező határozza meg a céloldalon alkalmazott nagyítás mértékét a PDF-dokumentum megnyitásakor. Azt szabályozza, hogy mennyi tartalom jelenjen meg a nézetablakban.

#### K: Beállíthatok különböző nagyítási tényezőket a különböző céloldalakhoz?

V: Igen, különböző nagyítási tényezőket állíthat be a különböző céloldalakhoz, külön létrehozva`GoToAction` példányokat, és ennek megfelelően konfigurálja a célokat.

#### K: Vannak korlátozások a céloldal megadására?

V: A céloldal megadása a PDF megnyitásakor megjelenő kezdeti nézet vezérlésére korlátozódik. A PDF megjelenítése után nincs hatással a felhasználói interakciókra vagy a navigációra.

#### K: Használhatom ezt a funkciót prezentációk létrehozására PDF-dokumentumban?

V: Igen, ezzel a funkcióval prezentációszerű élményeket hozhat létre egy PDF-dokumentumban, amely a felhasználókat a különböző szakaszokon vagy témákon keresztül vezeti végig.

#### K: Testreszabhatom a kezdeti nézet egyéb szempontjait, például az oldalelrendezést?

V: Igen, az Aspose.PDF for .NET tulajdonságokat biztosít a kezdeti nézet egyéb szempontjainak testreszabásához, beleértve az oldalelrendezést, az oldalmódot és egyebeket.

#### K: Hogyan tesztelhetem, hogy a megadott céloldal és a nagyítási tényező megfelelően működik-e?

V: Miután a megadott kódot alkalmazta a céloldal és a nagyítási tényező megadásához, nyissa meg a módosított PDF-fájlt, és ellenőrizze, hogy a megfelelő oldallal és nagyítási szinttel nyílik-e meg.