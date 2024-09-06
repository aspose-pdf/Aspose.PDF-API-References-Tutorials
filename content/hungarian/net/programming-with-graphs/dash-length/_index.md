---
title: Dash Length
linktitle: Dash Length
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthatja be a gondolatjelek hosszát az Aspose.PDF for .NET segítségével. Útmutató lépésről lépésre a vonalminták testreszabásához.
type: docs
weight: 70
url: /hu/net/programming-with-graphs/dash-length/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon a kötőjelek hosszának beállításához az Aspose.PDF for .NET használatával.

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
Page page = doc.Pages.Add();
```

## 3. lépés: Grafikonobjektum létrehozása és hozzáadása az oldalhoz

Létrehozunk egy megadott méretű Graph objektumot, és hozzáadjuk az oldal bekezdésgyűjteményéhez.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## 4. lépés: Vonalobjektum létrehozása és konfigurálása

Létrehozunk egy Line objektumot a megadott koordinátákkal, és beállítjuk a kötőjelek színét és hosszát.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 5. lépés: A vonal hozzáadása a grafikon objektumhoz

A vonalat hozzáadjuk a Graph objektum alakgyűjteményéhez.

```csharp
canvas.Shapes.Add(line);
```

## 6. lépés: Mentse el az eredményül kapott PDF-fájlt

Végül elmentjük a kapott PDF fájlt "DashLength_out.pdf" néven a megadott könyvtárba.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Példa a Dash Length forráskódjához az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Példányos dokumentum példány
Document doc = new Document();
// Oldal hozzáadása a Dokumentumobjektum oldalgyűjteményéhez
Page page = doc.Pages.Add();
// Rajzobjektum létrehozása bizonyos méretekkel
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Rajzobjektum hozzáadása az oldalpéldány bekezdésgyűjteményéhez
page.Paragraphs.Add(canvas);
// Vonal objektum létrehozása
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Állítsa be a vonal objektum színét
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Adja meg a vonalobjektum kötőjeltömbjét
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Állítsa be a vonalpéldány kötőjel fázisát
line.GraphInfo.DashPhase = 1;
// Vonal hozzáadása a rajzobjektum alakzatgyűjteményéhez
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// PDF dokumentum mentése
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan állíthatja be a gondolatjelek hosszát az Aspose.PDF for .NET használatával. Mostantól ezt a tudást felhasználhatja arra, hogy egyedi kötőjelmintákkal rendelkező vonalakat hozzon létre PDF-fájljaiban.

## GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezesse a vonalak kötőjeleinek hosszának beállításán az Aspose.PDF for .NET használatával. Megtanulja, hogyan hozhat létre vonalakat egyéni kötőjelmintákkal a PDF-fájlokban.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. A C# programozás alapvető ismerete szintén ajánlott.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: Módosítsa a "dataDir" változót a megadott forráskódban, hogy jelezze azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF-fájlt.

#### K: Hogyan hozhatok létre vonalat egyéni kötőjelmintákkal?

 V: Az oktatóanyag bemutatja a Line objektum létrehozását, valamint színének, kötőjel tömbjének és kötőjel fázisának konfigurálását a`GraphInfo` objektum. Módosítsa ezeket a beállításokat a kívánt vonalminta eléréséhez.

#### K: Testreszabhatom a vonal színét?

 V: Igen, testreszabhatja a vonal színét a`Color` tulajdona a`GraphInfo` a vonalhoz társított objektum.

#### K: Hogyan menthetem el a PDF-dokumentumot a kötőjel hosszának beállítása után?

 V: Miután konfigurálta a Line objektumot a kívánt kötőjelmintával, az eredményül kapott PDF dokumentumot a`doc.Save(dataDir + "DashLength_out.pdf");` sort a megadott forráskódban.