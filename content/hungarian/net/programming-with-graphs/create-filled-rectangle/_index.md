---
title: Hozzon létre kitöltött téglalapot
linktitle: Hozzon létre kitöltött téglalapot
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre mutató oktatóanyagból megtudhatja, hogyan hozhat létre kitöltött téglalapot PDF-fájlban az Aspose.PDF for .NET használatával. Tökéletes minden szintű fejlesztő számára.
type: docs
weight: 50
url: /hu/net/programming-with-graphs/create-filled-rectangle/
---
## Bevezetés

Szeretett volna programozottan látványos PDF-eket készíteni? Ha igen, akkor jó helyen jársz! Ebben az oktatóanyagban belemerülünk az Aspose.PDF for .NET világába, amely egy hatékony könyvtár, amely lehetővé teszi a PDF dokumentumok egyszerű kezelését. Ma egy kitöltött téglalap létrehozására fogunk összpontosítani egy PDF-fájlban. Akár tapasztalt fejlesztő, akár csak most kezdő, ez az útmutató barátságos és vonzó módon végigvezeti Önt minden lépésen. Szóval, fogd meg a kódoló kalapot, és kezdjük is!

## Előfeltételek

Mielőtt belevágnánk a kódba, néhány dolgot meg kell határoznia:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Ez egy fantasztikus IDE a .NET fejlesztéshez.
2.  Aspose.PDF .NET-hez: Le kell töltenie és telepítenie kell az Aspose.PDF könyvtárat. Megtalálhatod[itt](https://releases.aspose.com/pdf/net/).
3. Alapvető C# ismerete: A C# programozás egy kis ismerete segít jobban megérteni a kódrészleteket.

## Csomagok importálása

A kezdéshez importálnia kell a szükséges csomagokat a C# projektbe. A következőképpen teheti meg:

### Hozzon létre egy új projektet

Nyissa meg a Visual Studio-t, és hozzon létre egy új C#-projektet. Az egyszerűség kedvéért választhat egy konzolalkalmazást.

### Adja hozzá az Aspose.PDF hivatkozást

1. Kattintson a jobb gombbal a projektre a Solution Explorerben.
2. Válassza a "NuGet-csomagok kezelése" lehetőséget.
3. Keresse meg az "Aspose.PDF" kifejezést, és telepítse a legújabb verziót.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Most, hogy mindent beállítottunk, merüljünk el a kódban!

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Először is meg kell adnia a PDF mentési útvonalat. Ez döntő fontosságú, mert megmondja a programnak, hogy hol kell létrehozni a fájlt.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal a gépén, ahová menteni szeretné a PDF-fájlt.

## 2. lépés: Hozzon létre egy dokumentumpéldányt

 Ezután létrehozzuk a`Document`osztály. Ez az osztály azt a PDF-dokumentumot képviseli, amellyel dolgozni fog.

```csharp
// Dokumentumpéldány létrehozása
Document doc = new Document();
```

Ez a sor inicializál egy új PDF-dokumentumot, amelyet kezelhetünk.

## 3. lépés: Adjon hozzá egy oldalt a dokumentumhoz

Most adjunk hozzá egy oldalt a dokumentumunkhoz. Minden PDF-nek legalább egy oldalra van szüksége, igaz?

```csharp
// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
Page page = doc.Pages.Add();
```

Ez a kód egy új oldalt ad a dokumentumhoz, lehetővé téve, hogy alakzatokat rajzoljunk rá.

## 4. lépés: Hozzon létre egy grafikonpéldányt

 Alakzatok rajzolásához létre kell hoznunk a`Graph` példa. Gondoljon a grafikonra úgy, mint egy vászonra, ahol különféle alakzatokat rajzolhat.

```csharp
// Graph példány létrehozása
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);
```

Itt egy 100 szélességű és 400 magasságú grafikont hozunk létre.

## 5. lépés: Adja hozzá a grafikont az oldalhoz

Most, hogy megvan a grafikonunk, adjuk hozzá a korábban létrehozott oldalhoz.

```csharp
// Grafikon objektum hozzáadása az oldalpéldány bekezdésgyűjteményéhez
page.Paragraphs.Add(graph);
```

Ez a vonal rögzíti a grafikont az oldalhoz, így készen áll a rajzolásra.

## 6. lépés: Hozzon létre egy téglalappéldányt

Ezután létrehozunk egy téglalapot, amelyet ki szeretnénk tölteni színnel.

```csharp
// Téglalap példány létrehozása
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
```

Ebben a kódban meghatározzuk a téglalap helyzetét és méretét. A paraméterek az x és y koordinátákat, szélességet és magasságot jelentik.

## 7. lépés: Adja meg a kitöltés színét

Most válasszunk színt a téglalapunkhoz. Ebben a példában pirossal töltjük ki.

```csharp
// Adja meg a Graph objektum kitöltési színét
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

Ez a vonal a téglalap kitöltési színét pirosra állítja. Bármilyen színt választhatsz!

## 8. lépés: Adja hozzá a téglalapot a diagramhoz

Ha készen van a téglalapunk, ideje hozzáadni a grafikonhoz.

```csharp
// Téglalap objektum hozzáadása a Graph objektum alakzatgyűjteményéhez
graph.Shapes.Add(rect);
```

Ez a kód hozzáadja a téglalapot a grafikonhoz, így a rajzunk részévé válik.

## 9. lépés: Mentse el a PDF-dokumentumot

Végül el kell mentenünk a dokumentumunkat a megadott könyvtárba.

```csharp
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
```

 Ez a kód elmenti a PDF fájlt a névvel`CreateFilledRectangle_out.pdf` a korábban megadott könyvtárban.

## 10. lépés: Megerősítő üzenet

Hogy tudassuk velünk, hogy minden zökkenőmentesen ment, kinyomtathatunk egy megerősítő üzenetet.

```csharp
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);
```

Ez a sor egy üzenetet ad ki a konzolon, megerősítve, hogy a kitöltött téglalap sikeresen létrejött.

## Következtetés

És megvan! Sikeresen létrehozott egy kitöltött téglalapot egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ez a nagy teljesítményű könyvtár a lehetőségek világát nyitja meg a PDF-kezeléshez, lehetővé téve, hogy lenyűgöző dokumentumokat készítsen programozottan. Függetlenül attól, hogy jelentéseket, számlákat vagy bármilyen más típusú PDF-et készít, az Aspose.PDF gondoskodik róla.

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok programozott létrehozását, kezelését és konvertálását.

### Használhatom ingyenesen az Aspose.PDF-et?
 Igen, az Aspose ingyenes próbaverziót kínál, amellyel felfedezheti a könyvtár funkcióit. Letöltheti[itt](https://releases.aspose.com/).

### Van mód az Aspose.PDF támogatására?
 Teljesen! Az Aspose fórumon keresztül kaphat támogatást[itt](https://forum.aspose.com/c/pdf/10).

### Hogyan vásárolhatom meg az Aspose.PDF-et?
 Az Aspose.PDF-et a vásárlási oldalon vásárolhatja meg[itt](https://purchase.aspose.com/buy).

### Milyen típusú alakzatokat hozhatok létre az Aspose.PDF segítségével?
Az Aspose.PDF könyvtár használatával különféle alakzatokat hozhat létre, például téglalapokat, köröket, vonalakat és egyebeket.