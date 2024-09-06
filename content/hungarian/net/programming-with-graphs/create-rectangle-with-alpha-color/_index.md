---
title: Hozzon létre téglalapot alfa színnel
linktitle: Hozzon létre téglalapot alfa színnel
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre átlátszó színű téglalapot az Aspose.PDF for .NET használatával. Lépésről lépésre szóló útmutató az átláthatóság testreszabásához.
type: docs
weight: 60
url: /hu/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon, hogy alfaszínű téglalapot hozzon létre az Aspose.PDF for .NET használatával.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretekkel is rendelkezel.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott forráskódban meg kell adnia azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF fájlt. Módosítsa a "dataDir" változót a kívánt könyvtárra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Dokumentumobjektum példányosítása és oldal hozzáadása

Létrehozunk egy példányt a Dokumentum osztályból, és hozzáadunk egy oldalt ehhez a dokumentumhoz.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3. lépés: Grafikonobjektum és téglalap létrehozása

Létrehozunk egy Graph objektumot meghatározott méretekkel és egy téglalapot meghatározott méretekkel.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## 4. lépés: Állítsa be a téglalap alfa színét

A System.Drawing.Color osztály FromArgb metódusával megadhatunk alfa színt a téglalaphoz.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## 5. lépés: A téglalap hozzáadása a grafikon objektumhoz

A téglalapot hozzáadjuk a Graph objektum alakgyűjteményéhez.

```csharp
canvas.Shapes.Add(rect);
```

## 6. lépés: Második téglalap létrehozása eltérő alfa színnel

Létrehozunk egy második téglalapot meghatározott méretekkel és egy másik alfa színnel.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## 7. lépés: Grafikon objektum hozzáadása az oldalhoz

A Graph objektumot hozzáadjuk a Page objektum Paragrafus gyűjteményéhez.

```csharp
page.Paragraphs.Add(canvas);
```

## 8. lépés: Mentse el az eredményül kapott PDF-fájlt

Végül elmentjük a kapott PDF fájlt "CreateRectangleWithAlphaColor_out.pdf" néven a megadott könyvtárba.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Minta forráskód a Create Rectangle With Alpha Color funkcióhoz az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Példányos dokumentum példány
Document doc = new Document();
// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
Aspose.Pdf.Page page = doc.Pages.Add();
// Graph példány létrehozása
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Hozzon létre téglalap objektumot meghatározott méretekkel
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
// Állítsa be a grafikon kitöltési színét a System.Drawing.Color struktúrából 32 bites ARGB értékből
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Téglalap objektum hozzáadása a Graph példány alakzatgyűjteményéhez
canvas.Shapes.Add(rect);
// Második téglalap objektum létrehozása
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Grafikonpéldány hozzáadása az oldalobjektum bekezdésgyűjteményéhez
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan lehet alfa színű téglalapot létrehozni az Aspose.PDF for .NET használatával. Ezt a tudást most felhasználhatja átlátszó színű geometriai alakzatok létrehozására PDF-fájljaiban.

## GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezeti Önt az alfa színű téglalap létrehozásának folyamatán az Aspose.PDF for .NET használatával. Megtanulja, hogyan adhat átlátszó színű geometriai alakzatokat PDF-fájljaihoz.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. Ezenkívül ajánlott a C# programozás alapismerete.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: A megadott forráskódban módosíthatja a "dataDir" változót, hogy jelezze azt a könyvtárat, ahová menteni kívánja az eredményül kapott PDF-fájlt.

#### K: Mi a célja a Graph objektumnak és a téglalapnak?

V: A Graph objektum a rajzelemek tárolójaként működik, míg a téglalap a PDF-hez hozzáadandó geometriai alakzatot képviseli.

#### K: Hogyan állíthatok be alfa színt a téglalaphoz?

 V: A téglalap alfa színét a gombbal adhatja meg`FillColor` tulajdona a`GraphInfo` tárgy és a`Color.FromRgb` módszer ARGB értékkel.

#### K: Létrehozhatok több téglalapot különböző alfa színekkel?

V: Igen, az oktatóanyagban bemutatott hasonló lépéseket követve több téglalapot is létrehozhat különböző alfa színekkel.

#### K: Hogyan menthetem el az eredményül kapott PDF-fájlt alfa színekkel rendelkező téglalapok létrehozása után?

 V: Miután létrehozta a téglalapokat alfa színekkel, elmentheti a kapott PDF-fájlt a`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` sort a megadott forráskódban.