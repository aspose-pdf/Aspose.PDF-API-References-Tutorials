---
title: Dash Length
linktitle: Dash Length
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre szóló útmutatónk segítségével megtudhatja, hogyan szabhatja testre a vonalak szaggatott mintáit PDF-fájlokban az Aspose.PDF for .NET használatával. Tökéletes, hogy stílust adjon dokumentumaihoz.
type: docs
weight: 70
url: /hu/net/programming-with-graphs/dash-length/
---
## Bevezetés

Egy kis kreativitást szeretne adni PDF-dokumentumainak a vonalak testreszabásával különféle szaggatott mintákkal? Az Aspose.PDF for .NET segítségével könnyedén módosíthatja a sorstílusokat a dokumentum igényeinek megfelelően. Ebben az oktatóanyagban megvizsgáljuk, hogyan állíthatja be a vonalak kötőjelének hosszát egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Akár szaggatott vonalat, akár pontozott mintát szeretne elérni, ez az útmutató biztosítja a kívánt eredmény eléréséhez szükséges eszközöket és lépéseket.

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, néhány dologra lesz szüksége:

1. Aspose.PDF .NET-hez: Győződjön meg arról, hogy az Aspose.PDF for .NET telepítve van. Ha még nem telepítette, letöltheti innen[Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/).
2. Alapvető C# ismeretek: Ez az oktatóanyag feltételezi, hogy rendelkezik alapvető ismeretekkel a C# programozásról. Ha még nem ismeri a C#-t, érdemes először az alapokat felfrissíteni.
3. Visual Studio: Bár bármilyen IDE-t használhat, ez az útmutató feltételezi, hogy a Visual Studio-t használja a C#-kód írásához és futtatásához.
4.  Aspose-fiók: További forrásokért és támogatásért győződjön meg arról, hogy rendelkezik Aspose-fiókkal. Jelentkezni lehet a[ingyenes próbaverzió](https://releases.aspose.com/) vagy vásároljon licencet[itt](https://purchase.aspose.com/buy).

## Csomagok importálása

Az Aspose.PDF for .NET használatához importálnia kell a megfelelő névtereket. A következőképpen teheti meg:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ezek a névterek a PDF dokumentumok, rajzok és vonalak kezeléséhez szükséges osztályokat és módszereket tartalmazzák.

## 1. lépés: Állítsa be a projektet

kódolás megkezdése előtt állítson be egy új C#-projektet a Visual Studióban. Adja hozzá az Aspose.PDF for .NET könyvtárat a projekthez a NuGet segítségével vagy a DLL manuális hivatkozásával. 

## 2. lépés: Inicializálja a dokumentumot

Kezdje új PDF-dokumentum létrehozásával, és adjon hozzá egy oldalt. Ez az a vászon, amelyre megrajzolja a vonalait.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányos dokumentum példány
Document doc = new Document();

// Oldal hozzáadása a Dokumentumobjektum oldalgyűjteményéhez
Page page = doc.Pages.Add();
```

 Itt létrehozunk a`Document` objektumot, és adjunk hozzá egy újat`Page` hozzá. Ez megteremti az alapot a vonal megrajzolásához.

## 3. lépés: Hozd létre a rajzobjektumot

 Ezután hozzon létre a`Graph` objektum, amely azt a területet képviseli, ahol rajzolni fog. Határozza meg a méreteit igényei szerint.

```csharp
// Rajzobjektum létrehozása bizonyos méretekkel
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100.0, 400.0);

// Rajzobjektum hozzáadása az oldalpéldány bekezdésgyűjteményéhez
page.Paragraphs.Add(canvas);
```

 A`Graph` Az objektum a rajzelemek tárolójaként működik. Itt 100 egység szélességre és 400 egység magasságra van beállítva.

## 4. lépés: Határozza meg a vonalat

 Most itt az ideje létrehozni a`Line`objektum. Adja meg a vonal kezdő- és végpontját, és szabja testre a stílusát.

```csharp
// Vonal objektum létrehozása
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
```

Ez a vonal a (100, 100) koordinátákkal kezdődik és (200, 100) pontban ér véget. Ezeket a koordinátákat saját igényei szerint állíthatja be.

## 5. lépés: A vonalstílus testreszabása

Állítsa be a vonal színét és szaggatott mintáját. Itt kiemelheti vonalát.

```csharp
// Állítsa be a vonal objektum színét
line.GraphInfo.Color = Aspose.Pdf.Color.Red;

// Adja meg a vonalobjektum kötőjeltömbjét
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };

// Állítsa be a vonalpéldány kötőjel fázisát
line.GraphInfo.DashPhase = 1;
```

- `line.GraphInfo.Color`: Beállítja a vonal színét. Ebben az esetben piros.
- `line.GraphInfo.DashArray` : Meghatározza a szaggatott mintát. Itt,`{ 0, 1, 0 }` szaggatott mintát jelent.
- `line.GraphInfo.DashPhase`: Beállítja a kötőjelminta kezdőpontját.

## 6. lépés: Adja hozzá a vonalat a rajzhoz

 A vonal stílusával adja hozzá a`Graph` objektum.

```csharp
// Vonal hozzáadása a rajzobjektum alakzatgyűjteményéhez
canvas.Shapes.Add(line);
```

Ez integrálja a vonalat a rajzvászonba.

## 7. lépés: Mentse el a dokumentumot

Végül mentse a dokumentumot egy megadott elérési útra. Itt jön létre a PDF fájl.

```csharp
dataDir = dataDir + "DashLength_out.pdf";

// PDF dokumentum mentése
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);
```

Ez a kódsor menti a PDF-dokumentumot, és egy megerősítő üzenetet ad, amely jelzi, hogy a fájl hova lett elmentve.

## Következtetés

A PDF-dokumentumok vonalstílusainak testreszabása professzionális megjelenést adhat jelentéseinek, prezentációinak és egyéb dokumentumainak. Az oktatóanyag követésével megtanulta, hogyan állíthatja be a vonalak kötőjelének hosszát az Aspose.PDF for .NET használatával. Akár egyszerű szaggatott vonalakat, akár összetettebb mintákat hoz létre, az Aspose.PDF biztosítja azt a rugalmasságot, amelyre szüksége van ahhoz, hogy dokumentumai kiemelkedjenek. Kísérletezzen különböző vonalmintákkal és színekkel, hogy megtalálja az igényeinek leginkább megfelelő stílust.

## GYIK

### Hogyan telepíthetem az Aspose.PDF-et .NET-hez?
 Telepítheti a NuGet segítségével a Visual Studio alkalmazásban, vagy letöltheti a webhelyről[Aspose honlapja](https://releases.aspose.com/pdf/net/).

### Használhatom ingyenesen az Aspose.PDF-et .NET-hez?
 Igen, az Aspose kínál a[ingyenes próbaverzió](https://releases.aspose.com/) így a licenc megvásárlása előtt tesztelheti a funkcióit.

### Milyen egyéb testreszabásokat végezhetek a PDF sorain?
 Beállíthatja a vonalvastagságot, a színt és a szaggatott mintákat. Lásd a[dokumentáció](https://reference.aspose.com/pdf/net/) további részletekért.

### Hogyan kaphatok támogatást, ha problémákba ütközöm?
 A támogatást a következőn keresztül érheti el[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Hol vásárolhatok licencet az Aspose.PDF for .NET számára?
Vásárolhat licencet[itt](https://purchase.aspose.com/buy).