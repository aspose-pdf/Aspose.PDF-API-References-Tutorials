---
title: Nagyítási faktor letöltése PDF-fájlban
linktitle: Nagyítási faktor letöltése PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan használja az Aspose.PDF for .NET fájlt a PDF-fájl nagyítási tényezőjének megjelenítéséhez.
type: docs
weight: 210
url: /hu/net/programming-with-document/getzoomfactor/
---
Az Aspose.PDF for .NET egy PDF-manipulációs könyvtár, amely számos funkciót biztosít a PDF-dokumentumok különféle műveleteinek végrehajtásához. Az egyik ilyen funkció a nagyítási tényező beolvasása PDF-fájlba. Ebben az oktatóanyagban elmagyarázzuk, hogyan használható az Aspose.PDF for .NET a PDF-fájl nagyítási tényezőjének C# forráskóddal történő lekéréséhez.


## 1. lépés: Új dokumentum objektum példányosítása

 Az Aspose.PDF for .NET használatával PDF-fájlok nagyítási tényezőjének eléréséhez az első lépés egy új példány létrehozása.`Document` tárgy. A`Document` Az objektum egy fájlból vagy adatfolyamból betölthető PDF dokumentumot jelent.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Új dokumentum objektum példányosítása
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 A fenti kódban létrehoztuk a`Document` objektumot úgy, hogy átadja a PDF fájl elérési útját a konstruktornak`Document` osztály. A "DOKUMENTUMKÖNYVTÁR"-t le kell cserélnie annak a könyvtárnak az elérési útjára, ahol a PDF-fájl található.

## 2. lépés: Hozzon létre GoToAction objektumot

 A következő lépés az a`GoToAction` tárgy. A`GoToAction`Az objektum egy olyan műveletet jelöl, amely egy adott célhelyre megy a PDF-dokumentumban. Esetünkben a PDF fájl nagyítási tényezőjét szeretnénk megkapni, ezért a`OpenAction` tulajdona a`Document` kifogást szerezni a`GoToAction` tárgy.

```csharp
// Hozzon létre GoToAction objektumot
GoToAction action = doc.OpenAction as GoToAction;
```

 A fenti kódban létrehoztuk a`GoToAction` tárgy öntésével a`OpenAction` tulajdona a`Document` tiltakozni`GoToAction`.

## 3. lépés: Szerezze be a PDF-fájl nagyítási tényezőjét

 A harmadik lépés a PDF-fájl nagyítási tényezőjének beszerzése. A PDF fájl nagyítási tényezőjét a`Destination` tulajdona a`GoToAction` objektumra, majd ráöntjük`XYZExplicitDestination` . A`XYZExplicitDestination` osztály egy olyan célhelyet jelent egy PDF-dokumentumban, amely meghatározza a koordinátákat és a nagyítási tényezőt, ahová továbbítani kell.

```csharp
// Szerezze be a PDF-fájl nagyítási tényezőjét
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokumentum nagyítási értéke;
```

 A fenti kódban elértük a`Destination` tulajdona a`GoToAction` tárgyat, majd rádobja`XYZExplicitDestination` . Ezt követően elértük a`Zoom` tulajdona a`XYZExplicitDestination` objektumot a PDF-fájl nagyítási tényezőjének lekéréséhez.

## 4. lépés: Adja meg a Zoom tényezőt

 Az utolsó lépés a PDF-fájl nagyítási tényezőjének kiadása. Használhatjuk a`System.Console.WriteLine`

```csharp
// Szerezze be a PDF-fájl nagyítási tényezőjét
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokumentum nagyítási értéke;
```        

### Példa forráskódra a Get Zoom Factorhoz az Aspose.PDF for .NET használatával

Íme a Get Zoom Factor teljes forráskódja az Aspose.PDF for .NET használatával:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Új dokumentum objektum példányosítása
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Hozzon létre GoToAction objektumot
GoToAction action = doc.OpenAction as GoToAction;

// Szerezze be a PDF-fájl nagyítási tényezőjét
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Dokumentum nagyítási értéke;
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan használhatjuk az Aspose.PDF-et .NET-hez a PDF-fájlok nagyítási tényezőjének megállapításához. A nagyítási tényező kulcsfontosságú szempont a PDF-dokumentumban, mivel ez határozza meg a kezdeti megjelenítési méretet a megjelenítőben való megnyitáskor. A nagyítási tényező elérésével és használatával a fejlesztők testreszabhatják a megtekintési élményt a végfelhasználók számára. Az Aspose.PDF for .NET egy egyszerű és hatékony API-t biztosít a nagyítási tényező és egyéb navigációval kapcsolatos információk lekéréséhez egy PDF-dokumentumból, lehetővé téve a fejlesztők számára, hogy funkciókban gazdag és interaktív PDF-alkalmazásokat készítsenek.

### GYIK a nagyítási tényező letöltéséhez PDF-fájlban

#### K: Mi a nagyítási tényező egy PDF-fájlban?

V: A PDF-fájl nagyítási tényezője a dokumentum megtekintésekor alkalmazott nagyítási szintre vonatkozik. Meghatározza a PDF-fájl kezdeti megjelenítési méretét a képernyőn. Az 1,0-s zoomtényező a tényleges méretet (100%-os zoom), míg az 1,0-nál nagyobb zoomtényező a nagyítást, az 1,0-nál kisebb zoomtényező pedig a csökkentést jelenti.

#### K: Hogyan használhatom a nagyítási tényezőt az alkalmazásomban?

V: A nagyítási tényező információival testreszabhatja a PDF-dokumentum kezdeti megjelenítési méretét, amikor a megjelenítőben megnyitják. Például beállíthat egy adott nagyítási tényezőt annak biztosítására, hogy a PDF egy adott méretben jelenjen meg, vagy a teljes oldalt a megtekintő ablakához illessze.

#### K: Módosíthatom egy PDF-dokumentum nagyítási tényezőjét programozottan az Aspose.PDF for .NET használatával?

 V: Igen, a PDF-dokumentum nagyítási tényezője programozottan módosítható az Aspose.PDF for .NET használatával. Beállíthatja a nagyítási tényezőt bizonyos műveletekhez, mint pl`GoToAction` vagy`GoToRemoteAction`annak szabályozására, hogy a dokumentum hogyan jelenjen meg, amikor a felhasználó hivatkozásokkal vagy könyvjelzőkkel lép kapcsolatba.

#### K: Vannak más módok a PDF-dokumentumok meghatározott helyeire történő navigálásra az Aspose.PDF for .NET használatával?

 V: Igen, az Aspose.PDF for .NET különféle funkciókat kínál a PDF-dokumentumok meghatározott helyeire történő navigáláshoz. A használat mellett`GoToAction` , használhat más műveleteket is, mint pl`GoToURIAction` URL megnyitásához,`GoToEmbeddedAction` a beágyazott fájlok eléréséhez, és`GoToNamedAction` hogy a PDF-dokumentumban megnevezett célhelyekre lépjen.