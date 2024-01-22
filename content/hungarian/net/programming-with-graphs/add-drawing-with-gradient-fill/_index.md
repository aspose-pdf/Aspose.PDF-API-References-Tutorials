---
title: Rajz hozzáadása színátmenetes kitöltéssel
linktitle: Rajz hozzáadása színátmenetes kitöltéssel
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá rajzot színátmenetes kitöltéssel az Aspose.PDF for .NET segítségével. Lépésről lépésre bemutató útmutató vonzó PDF dokumentumok létrehozásához.
type: docs
weight: 20
url: /hu/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon, hogy egy színátmenetes kitöltésű rajzot adjon hozzá a grafikával történő programozáshoz az Aspose.PDF for .NET használatával.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretekkel is rendelkezel.

## 1. lépés: Dokumentumkönyvtár beállítása

megadott forráskódban meg kell adnia azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF fájlt. Módosítsa a "dataDir" változót a kívánt könyvtárra.

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
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## 4. lépés: Téglalap objektum létrehozása és hozzáadása a diagramhoz

Létrehozunk egy téglalap objektumot meghatározott méretekkel, és hozzáadjuk a diagram alakzatgyűjteményéhez.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## 5. lépés: A színátmenetes kitöltés konfigurálása

A téglalap színátmenetes kitöltését a GradientAxialShading osztály segítségével konfiguráljuk.

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

Ezzel egy színátmenetes kitöltést hoz létre a pirostól a kékig, a (0, 0) ponttól a (300, 300) pontig.

## 6. lépés: A PDF-fájl mentése

Végül elmentjük a kapott PDF-fájlt "AddDrawingWithGradientFill_out.pdf" néven a megadott könyvtárba.

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### Minta forráskód a rajz hozzáadása színátmenetes kitöltéssel az Aspose.PDF for .NET használatával programhoz 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## Következtetés

Ebben az oktatóanyagban lépésről lépésre elmagyaráztuk, hogyan adhatunk hozzá színátmenetes kitöltésű rajzot a grafikus programozáshoz az Aspose.PDF for .NET használatával. Mostantól ezt a tudást felhasználhatja vonzó PDF-dokumentumok létrehozásához egyedi tervezésű és színátmenetes kitöltéssel.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ez az oktatóanyag végigvezeti Önt a színátmenetes kitöltésű rajz hozzáadásának folyamatán a grafikával történő programozáshoz az Aspose.PDF for .NET használatával.

#### K: Milyen előfeltételek szükségesek a kezdéshez?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. Ezenkívül ajánlott a C# programozás alapismerete.

#### K: Hogyan adhatom meg a PDF-fájl mentési könyvtárát?

V: A megadott forráskódban megváltoztathatja a "dataDir" változó értékét, hogy jelezze azt a könyvtárat, ahová menteni szeretné az eredményül kapott PDF fájlt.

#### K: Mi a Graph objektum célja?

V: A Graph objektum a rajzelemek tárolójaként szolgál. Megadott méretekkel jön létre, és hozzáadódik az oldal bekezdésgyűjteményéhez.

#### K: Hogyan konfigurálhatom egy alakzat színátmenetes kitöltését?

V: A színátmenet-kitöltés konfigurálásához beállíthatja egy alakzat GraphInfo-jának FillColor tulajdonságát a GradientAxialShading osztály segítségével. Ez lehetővé teszi a színátmenet kezdő- és végpontjának, valamint a színek közötti átmenet meghatározását.

#### K: Testreszabhatom a színátmenet kitöltés színeit és irányát?

V: Igen, testreszabhatja a színátmenet-kitöltés színeit és irányát a Color objektumok beállításával és a GradientAxialShading kezdő- és végpontjának megadásával.

#### K: Mi az oktatóanyag utolsó lépése?

V: Az utolsó lépés az eredményül kapott PDF-fájl mentése „AddDrawingWithGradientFill_out.pdf” néven a megadott könyvtárba.

#### K: Rendelkezésre áll minta forráskód?

V: Igen, az oktatóanyag tartalmaz egy minta forráskódot, amelyet referenciaként használhat a leírt lépések végrehajtásához.

#### K: Alkalmazhatok színátmenetes kitöltést a téglalapokon kívül más alakzatokra is?

V: Igen, más alakzatokra is alkalmazhat színátmenetes kitöltést. A folyamat magában foglalja az alakzat GraphInfo FillColor tulajdonságának konfigurálását a GradientAxialShading osztály használatával.