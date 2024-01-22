---
title: Hozzon létre kitöltött téglalapot
linktitle: Hozzon létre kitöltött téglalapot
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre kitöltött téglalapot az Aspose.PDF for .NET segítségével. Lépésről lépésre útmutató a kitöltési szín testreszabásához.
type: docs
weight: 50
url: /hu/net/programming-with-graphs/create-filled-rectangle/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon, hogy létrehozzon egy kitöltött téglalapot az Aspose.PDF for .NET használatával.

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

## 4. lépés: Téglalap objektum létrehozása és hozzáadása a diagramhoz

Létrehozunk egy Téglalap objektumot a megadott méretekkel, és hozzáadjuk a diagram alakzatgyűjteményéhez.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 5. lépés: A kitöltés színének beállítása

téglalap kitöltési színét a GraphInfo objektum FillColor tulajdonságával tudjuk megadni.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 6. lépés: Mentse el az eredményül kapott PDF-fájlt

Végül elmentjük a kapott PDF fájlt "CreateFilledRectangle_out.pdf" néven a megadott könyvtárba.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Forráskód minta a Kitöltött téglalap létrehozásához az Aspose.PDF segítségével .NET-hez 

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
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Adja meg a Graph objektum kitöltési színét
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Téglalap objektum hozzáadása a Graph objektum alakzatgyűjteményéhez
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan hozhat létre kitöltött téglalapot az Aspose.PDF for .NET használatával. Ezt a tudást most felhasználhatja geometriai alakzatok létrehozására egyéni kitöltési színekkel a PDF-fájlokban.

## GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezesse a kitöltött téglalap létrehozásának folyamatán az Aspose.PDF for .NET használatával, lehetővé téve, hogy egyéni geometriai alakzatokat és kitöltőszíneket adjon a PDF-fájlokhoz.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. Ezenkívül ajánlott a C# programozás alapismerete.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: A megadott forráskódban módosíthatja a "dataDir" változót, hogy jelezze azt a könyvtárat, ahová menteni kívánja az eredményül kapott PDF-fájlt.

#### K: Mi a Graph objektum célja?

V: A Graph objektum a rajzelemek tárolójaként működik. Megadott méretekkel jön létre, és hozzáadódik az oldal bekezdésgyűjteményéhez.

#### K: Hogyan adhatok kitöltött téglalapot a PDF dokumentumhoz?

V: Kitöltött téglalap hozzáadásához hozzon létre egy példányt a Rectangle osztályból meghatározott méretekkel és kitöltési színnel, és adja hozzá a grafikon alakzatgyűjteményéhez.

#### K: Testreszabhatom a téglalap méreteit és kitöltési színét?

 V: Igen, testreszabhatja a téglalap méreteit és kitöltési színét azáltal, hogy módosítja a`Aspose.Pdf.Drawing.Rectangle` konstruktort és a FillColor tulajdonság beállítását.

#### K: Hogyan menthetem el a kapott PDF-fájlt a kitöltött téglalap létrehozása után?

 V: A kitöltött téglalap létrehozása után elmentheti a kapott PDF-fájlt a`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` sort a megadott forráskódban.