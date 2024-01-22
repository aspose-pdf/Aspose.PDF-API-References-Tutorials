---
title: Vezérlő Téglalap Z Rendezés PDF fájlban
linktitle: Vezérlő Téglalap Z Rendezés PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan szabályozhatja a téglalapok Z-rendjét egy PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 40
url: /hu/net/programming-with-graphs/control-rectangle-z-order/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon a téglalapok Z-rendjének szabályozásához az Aspose.PDF for .NET segítségével.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretekkel is rendelkezel.

## 1. lépés: Dokumentumkönyvtár beállítása

megadott forráskódban meg kell adnia azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF fájlt. Módosítsa a "dataDir" változót a kívánt könyvtárra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Dokumentumobjektum példányosítása és oldal hozzáadása

Létrehozunk egy példányt a Dokumentum osztályból, és hozzáadunk egy oldalt ehhez a dokumentumhoz.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## 3. lépés: Az oldalméret beállítása

PDF oldalméretét a SetPageSize metódussal állítjuk be.

```csharp
page1.SetPageSize(375, 300);
```

## 4. lépés: Az oldalmargók beállítása

Az oldalmargókat a PageInfo objektum tulajdonságaival konfigurálhatjuk.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## 5. lépés: Adjon hozzá téglalapokat meghatározott Z sorrenddel

Különböző színekkel és megadott Z rendelésekkel téglalapokat készítünk és adunk az oldalhoz.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## 6. lépés: Mentse el az eredményül kapott PDF-fájlt

Végül a kapott PDF fájlt "ControlRectangleZOrder_out.pdf" néven mentjük a megadott könyvtárba.

```csharp
doc1.Save(dataDir);
```
### Minta forráskód a Control Rectangle Z Orderhez az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentum osztály objektum példányosítása
Document doc1 = new Document();
/// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Állítsa be a PDF oldal méretét
page1.SetPageSize(375, 300);
// Az oldalobjektum bal margójának beállítása 0-ra
page1.PageInfo.Margin.Left = 0;
// Állítsa be az oldalobjektum felső margóját 0-ra
page1.PageInfo.Margin.Top = 0;
// Hozzon létre egy új téglalapot, amelyben a szín piros, a Z-sorrend pedig 0 és bizonyos méretek
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Hozzon létre egy új téglalapot a színnel kék, a Z-sorrenddel 0 és bizonyos méretekkel
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//Hozzon létre egy új téglalapot, ahol a szín zöld, a Z-sorrend 0 és bizonyos méretek
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Az eredményül kapott PDF fájl mentése
doc1.Save(dataDir);

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan szabályozható a téglalapok Z-rendje az Aspose.PDF for .NET használatával. Ezt a tudást most felhasználhatja a PDF-fájlok téglalapjainak pontos elrendezésére és rétegezésére.

### GYIK vezérlő téglalap z sorrendje PDF fájlban

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak a célja, hogy végigvezesse a téglalapok Z-rendjének szabályozásán az Aspose.PDF for .NET használatával, lehetővé téve a téglalapok elrendezését és rétegezését a PDF-fájlokban.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. Ezenkívül ajánlott a C# programozás alapismerete.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: A megadott forráskódban módosíthatja a "dataDir" változót, hogy jelezze azt a könyvtárat, ahová menteni kívánja az eredményül kapott PDF-fájlt.

#### K: Mi a célja az oldalméret és a margók beállításának?

V: Az oldalméret és a margók beállítása segít a PDF-oldal elrendezésének konfigurálásában, és egy vásznat biztosít, amelyen elrendezheti a téglalapokat.

#### K: Hogyan adhatok hozzá téglalapokat meghatározott Z sorrendben?

 V: A gombbal téglalapokat hozhat létre és adhat hozzá az oldalhoz`AddRectangle` módszerrel, megadva az egyes téglalapok helyzetét, méreteit, színét és Z sorrendjét.

#### K: Mi az a Z-sorrend, és miért fontos?

V: A Z-sorrend határozza meg az objektumok halmozási sorrendjét az oldalon. A magasabb Z-rendű objektumok az alacsonyabb Z-rendű objektumok tetejére kerülnek, ami befolyásolja láthatóságukat és rétegzettségüket.

#### K: Testreszabhatom a téglalapok színét és méreteit?

 V: Igen, személyre szabhatja a téglalapok színét, helyzetét és méreteit azáltal, hogy módosítja a`AddRectangle` módszer.

#### K: Hogyan menthetem el a kapott PDF-fájlt a téglalapok elrendezése után?

 V: A téglalapok elrendezése után a kapott PDF-fájlt a`doc1.Save(dataDir);` sort a megadott forráskódban.