---
title: lnk Annotation Line Width
linktitle: lnk Annotation Line Width
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthatja be a tinta megjegyzés vonalszélességét egy PDF-fájlban az Aspose.PDF for .NET használatával. Ez a részletes oktatóanyag végigvezeti Önt az egyes lépéseken, biztosítva a kiváló minőségű kimenetet.
type: docs
weight: 110
url: /hu/net/annotations/lnkannotationlinewidth/
---
## Bevezetés

Amikor PDF-dokumentumokkal dolgozik, a megjegyzések hozzáadása hatékony módja lehet az információk kiemelésének vagy interaktív elemek hozzáadásának a fájlokhoz. Az egyik ilyen megjegyzés az Ink Annotation, amely lehetővé teszi, hogy szabad formájú vonalakat rajzoljon a PDF-fájlba. De mi van akkor, ha testre kell szabnia e vonalak megjelenését, különösen a vonalszélességet? Ebben az oktatóanyagban végigvezetjük a tinta megjegyzés vonalszélességének beállításán az Aspose.PDF for .NET használatával.

## Előfeltételek

Mielőtt belemerülne a kódba, győződjön meg arról, hogy minden be van állítva az oktatóanyag zökkenőmentes követéséhez:

1.  Aspose.PDF for .NET: Győződjön meg arról, hogy telepítve van az Aspose.PDF for .NET könyvtár. Letöltheti a[letöltési oldal](https://releases.aspose.com/pdf/net/) vagy telepítse a NuGet Package Manager segítségével a Visual Studio alkalmazásban.
2. Fejlesztési környezet: Ez az oktatóanyag feltételezi, hogy .NET fejlesztői környezetben, például a Visual Studioban dolgozik.
3. Alapvető C# ismerete: A C# alapvető ismerete segít a kódolási lépések követésében.
4. PDF-dokumentum: Használjon egy meglévő PDF-dokumentumot, vagy hozzon létre egy újat ehhez az oktatóanyaghoz.

## A szükséges névterek importálása

A kódolás megkezdése előtt feltétlenül importálja a szükséges névtereket a projektbe:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Ezek a névterek biztosítják a PDF-dokumentumok kezeléséhez, a megjegyzésekkel való munkához és a grafikus elemek kezeléséhez szükséges osztályokat és módszereket.

Most, hogy megvannak az előfeltételeink, bontsuk le a tinta annotáció vonalszélességének beállítását egyértelmű, kezelhető lépésekre.

## 1. lépés: Inicializálja a PDF-dokumentumot

Először is létre kell hoznunk vagy meg kell nyitnunk egy PDF dokumentumot. Ehhez az oktatóanyaghoz egy új PDF-dokumentumot készítünk a semmiből.

```csharp
// Inicializálja a PDF-dokumentumot
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Adja meg a dokumentumkönyvtárat
Document doc = new Document();
doc.Pages.Add(); // Adjon hozzá egy üres oldalt a dokumentumhoz
```

 Itt inicializálunk egy újat`Document` objektum, amely a mi PDF fájlunkat képviseli. Ezután hozzáadunk egy üres oldalt ehhez a dokumentumhoz.

## 2. lépés: Hozza létre a tintajegyzetet

Ezután létrehozzuk magát a tinta-annotációt. Ez magában foglalja a tintavonásokat alkotó pontok meghatározását.

```csharp
// Hozzon létre tintajegyzetet
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 Ebben a lépésben meghatározzuk a`LineInfo` objektum, amely tartalmazza a tintavonások koordinátáit, láthatóságát, színét és kezdeti vonalszélességét. A`VerticeCoordinate` A tömb a körvonal minden pontjának X és Y koordinátáit tartalmazza.

## 3. lépés: Konvertálja a koordinátákat pontokká

Most ezeket a koordinátákat olyan pontokká kell konvertálnunk, amelyeket az Ink Annotation használhat.

```csharp
// Konvertálja a koordinátákat pontokká
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Ez a ciklus feldolgozza a koordinátatömböt, és minden koordinátapárt a-vá alakít`Point` objektum, amely azután hozzáadódik a mi`inkList`.

## 4. lépés: Adja hozzá a tinta megjegyzést a PDF-oldalhoz

Ha készen vannak a pontok, most elkészíthetjük a tinta annotációt, és hozzáadhatjuk a PDF oldalhoz.

```csharp
// Adja hozzá a tinta megjegyzést a PDF-oldalhoz
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 Ebben a lépésben inicializálunk egy`InkAnnotation`objektumot, megadva az oldalt, egy határoló téglalapot és a pontlistánkat. Beállítjuk a kommentár tárgyát, címét és színét is.

## 5. lépés: A kommentár szegélyének testreszabása

A kommentár megjelenésének további testreszabása érdekében módosítjuk a szegély tulajdonságait.

```csharp
// Testreszabhatja a kommentár szegélyét
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Itt létrehozunk a`Border` objektumot a megjegyzésünkhöz, beállítva annak szélességét, hatását, szaggatott mintáját és stílusát. Ez a lépés biztosítja, hogy a megjegyzés vizuálisan kiemelkedjen a PDF-oldalon.

## 6. lépés: Mentse el a PDF-dokumentumot

Végül az összes szükséges módosítás elvégzése után eljött az ideje a dokumentum mentésének.

```csharp
// Mentse el a PDF dokumentumot
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Ez a kód elmenti a módosított PDF dokumentumot a tinta megjegyzéssel a megadott könyvtárba. A`Console.WriteLine` utasítás megerősíti a kód sikeres végrehajtását.

## Következtetés

Gratulálok! Sikeresen létrehozott és testreszabott egy tintajegyzetet egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ez az oktatóanyag a teljes folyamatot lefedte, a dokumentum inicializálásától a végső fájl mentéséig. Ezzel a tudással tovább fedezheti az Aspose.PDF for .NET hatalmas képességeit, és hasonló technikákat alkalmazhat más típusú megjegyzéseknél vagy PDF-manipulációknál.

## GYIK

### Használhatok különböző színeket a tintajegyzet különböző részeihez?  
 Igen, létrehozhat többször is`InkAnnotation` különböző színű objektumokat, és adja hozzá őket a PDF-fájl azonos vagy különböző oldalaihoz.

### Hogyan változtathatom meg dinamikusan a vonal szélességét?  
 Beállíthatja a`LineWidth` tulajdona a`LineInfo` objektumot a koordináták pontokká alakítása előtt.

### Lehetséges-e átlátszóvá tenni a tinta annotációt?  
 Igen, módosíthatja a`Opacity` tulajdona a`InkAnnotation` tárgyat, hogy átlátszó legyen.

### Hozzáadhatok több tintajelölést ugyanarra az oldalra?  
Teljesen! A folyamat megismétlésével tetszőleges számú tintajegyzetet adhat hozzá egyetlen oldalhoz.

### Hogyan távolíthatok el egy tintajelölést a PDF-ből?  
 A kommentárt a következővel távolíthatja el`doc.Pages[1].Annotations.Delete(a1)` módszer, hol`a1` a megjegyzés objektuma.