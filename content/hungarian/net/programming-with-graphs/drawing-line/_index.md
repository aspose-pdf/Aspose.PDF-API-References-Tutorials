---
title: Rajz Vonal
linktitle: Rajz Vonal
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan húzhat vonalat egy oldalon az Aspose.PDF for .NET használatával. Útmutató lépésről lépésre egyéni vonalak létrehozásához.
type: docs
weight: 80
url: /hu/net/programming-with-graphs/drawing-line/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon, hogy egy vonalat húzzon az Aspose.PDF for .NET használatával.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretekkel is rendelkezel.

## 1. lépés: Dokumentumkönyvtár beállítása

megadott forráskódban meg kell adnia azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF fájlt. Módosítsa a "dataDir" változót a kívánt könyvtárra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Dokumentumpéldány létrehozása és oldal hozzáadása

Létrehozunk egy példányt a Dokumentum osztályból, és hozzáadunk egy oldalt ehhez a dokumentumhoz.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 3. lépés: Az oldalmargók beállítása

Az oldalmargót minden oldalon 0-ra állítjuk.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## 4. lépés: Grafikonobjektum és az első sor létrehozása

Létrehozunk egy Graph objektumot, amelynek mérete megegyezik az oldal méreteivel, és meghúzzuk az első vonalat a bal alsó saroktól a jobb felső sarkáig.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## 5. lépés: Rajzolja meg a második vonalat

A második vonalat az oldal bal felső sarkától a jobb alsó sarkáig húzzuk.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## 6. lépés: Graph objektum hozzáadása az oldalhoz

Graph objektumot hozzáadjuk az oldal bekezdésgyűjteményéhez.

```csharp
pg.Paragraphs.Add(graph);
```

## 7. lépés: Mentse el az eredményül kapott PDF-fájlt

Végül a kapott PDF-fájlt "DrawingLine_out.pdf" néven mentjük a megadott könyvtárba.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Forráskód minta a Drawing Line számára az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentumpéldány létrehozása
Document pDoc = new Document();
// Oldal hozzáadása a PDF-dokumentum oldalgyűjteményéhez
Page pg = pDoc.Pages.Add();
// Állítsa az oldalmargót minden oldalon 0-ra
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
// Hozzon létre Graph objektumot úgy, hogy a szélesség és a magasság megegyezzen az oldal méreteivel
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Hozzon létre első sor objektumot az oldal bal alsó sarkától a jobb felső sarkáig
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Vonal hozzáadása a Graph objektum alakzatgyűjteményéhez
graph.Shapes.Add(line);
// Rajzoljon vonalat az oldal bal felső sarkától az oldal jobb alsó sarkáig
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Vonal hozzáadása a Graph objektum alakzatgyűjteményéhez
graph.Shapes.Add(line2);
// Graph objektum hozzáadása az oldal bekezdésgyűjteményéhez
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// PDF fájl mentése
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan kell vonalat húzni az Aspose.PDF for .NET használatával. Ezt a tudást most felhasználhatja geometriai alakzatok létrehozására egyéni vonalakkal a PDF-fájlokban.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezesse a vonalak rajzolásán az Aspose.PDF for .NET használatával. Megtanulja, hogyan hozhat létre vonalakat egy PDF-oldalon, és hogyan szabhatja testre a megjelenésüket.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretek is ajánlottak.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: Módosítsa a "dataDir" változót a megadott forráskódban, hogy jelezze azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF-fájlt.

#### K: Hogyan hozhatok létre sorokat egy PDF-oldalon?

V: Az oktatóanyag bemutatja egy Graph objektum létrehozását az oldal méreteivel, majd Line objektumok hozzáadását. Módosítsa a Line objektumok koordinátáit és tulajdonságait a kívánt vonalak létrehozásához.

#### K: Testreszabhatom a vonalak megjelenését?

V: Igen, testreszabhatja a vonalak megjelenését a Vonal objektumok tulajdonságainak módosításával. Ez magában foglalja a koordináták, a szín, a vastagság és más grafikus attribútumok megváltoztatását.

#### K: Hogyan menthetem el a PDF-dokumentumot a vonalak megrajzolása után?

V: Miután hozzáadta a Graph objektumot vonal objektumokkal az oldalhoz, elmentheti az eredményül kapott PDF dokumentumot a`pDoc.Save(dataDir + "DrawingLine_out.pdf");` sort a megadott forráskódban.

#### K: Rajzolhatok különböző szögű és tájolású vonalakat?

V: Igen, a grafikonon belüli vonalobjektumok koordinátáinak és tulajdonságainak módosításával különböző szögű és tájolású vonalakat rajzolhat.