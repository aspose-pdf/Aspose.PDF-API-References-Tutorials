---
title: Vonalobjektum hozzáadása PDF-fájlhoz
linktitle: Vonalobjektum hozzáadása PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá egyéni vonalobjektumot PDF-fájlhoz az Aspose.PDF for .NET használatával.
type: docs
weight: 30
url: /hu/net/programming-with-graphs/add-line-object/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon, hogy hozzáadhasson egy vonalobjektumot az Aspose.PDF for .NET használatával.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretekkel is rendelkezel.

## 1. lépés: Dokumentumkönyvtár beállítása

megadott forráskódban meg kell adnia azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF fájlt. Módosítsa a "dataDir" változót a kívánt könyvtárra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Dokumentumpéldány létrehozása és oldal hozzáadása

Létrehozunk egy példányt a Dokumentum osztályból, és hozzáadunk egy oldalt ehhez a dokumentumhoz.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3. lépés: Grafikonobjektum létrehozása és hozzáadása az oldalhoz

Létrehozunk egy megadott méretű Graph objektumot, és hozzáadjuk az oldal bekezdésgyűjteményéhez.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## 4. lépés: Hozzon létre vonalobjektumot és Hozzáadás a diagramhoz

Létrehozunk egy Line objektumot a megadott koordinátákkal, és hozzáadjuk a diagram alakzatgyűjteményéhez.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## 5. lépés: Vonal beállítása

Megadhatunk a vonal tulajdonságait, például a kötőjel típusát és a kötőjel fázisát.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 6. lépés: A PDF-fájl mentése

Végül a kapott PDF-fájlt "AddLineObject_out.pdf" néven mentjük a megadott könyvtárba.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Minta forráskód az Add Line Object-hez az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentumpéldány létrehozása
Document doc = new Document();
// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
Page page = doc.Pages.Add();
// Graph példány létrehozása
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Grafikon objektum hozzáadása az oldalpéldány bekezdésgyűjteményéhez
page.Paragraphs.Add(graph);
// Téglalap példány létrehozása
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Adja meg a Graph objektum kitöltési színét
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Téglalap objektum hozzáadása a Graph objektum alakzatgyűjteményéhez
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Következtetés

Ebben az oktatóanyagban lépésről lépésre elmagyaráztuk, hogyan adhat hozzá vonalobjektumot az Aspose.PDF for .NET használatával. Mostantól ezt a tudást használhatja egyedi sorokat tartalmazó PDF-dokumentumok létrehozására az alkalmazásokban.

### GYIK a sorobjektum PDF-fájlhoz történő hozzáadásához

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ez az oktatóanyag végigvezeti Önt egy vonalobjektum hozzáadásának folyamatán az Aspose.PDF for .NET használatával PDF-dokumentumok javítása érdekében.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. Ezenkívül ajánlott a C# programozás alapismerete.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: A megadott forráskódban módosíthatja a "dataDir" változót, hogy jelezze azt a könyvtárat, ahová menteni kívánja az eredményül kapott PDF-fájlt.

#### K: Mi a Graph objektum célja?

V: A Graph objektum a rajzelemek tárolójaként szolgál. Megadott méretekkel jön létre, és hozzáadódik az oldal bekezdésgyűjteményéhez.

#### K: Hogyan adhatok hozzá vonalobjektumot a PDF dokumentumhoz?

V: Vonalobjektum hozzáadásához hozzon létre egy példányt a Vonal osztályból meghatározott koordinátákkal, és adja hozzá a gráf alakzatgyűjteményéhez.

#### K: Testreszabhatom a vonal megjelenését?

V: Igen, testreszabhatja a vonal megjelenését azáltal, hogy olyan tulajdonságokat állít be, mint a kötőjel típusa és a kötőjel fázisa a Vonal objektum GraphInfo tulajdonságával.

#### K: Mi a célja a kötőjel tömb és a kötőjel fázis megadásának?

V: A kötőjel tömb és a szaggatott fázis tulajdonságai lehetővé teszik szaggatott vagy pontozott vonalak létrehozását meghatározott mintákkal.

#### K: Hogyan menthetem el a PDF-fájlt a vonalobjektum hozzáadása után?

 V: A vonalobjektum hozzáadása után az eredményül kapott PDF-fájlt a`doc.Save(dataDir + "AddLineObject_out.pdf");` sort a megadott forráskódban.

#### K: Rendelkezésre áll minta forráskód?

V: Igen, az oktatóanyag tartalmaz egy minta forráskódot, amelyre hivatkozhat a leírt lépések végrehajtásához.