---
title: SVG objektum hozzáadása PDF fájlhoz
linktitle: SVG objektum hozzáadása PDF fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Könnyen hozzáadhat SVG-objektumokat PDF-fájlhoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 30
url: /hu/net/programming-with-tables/add-svg-object/
---
Ebben az oktatóanyagban megtanuljuk, hogyan adhat hozzá SVG-objektumot PDF-fájlhoz az Aspose.PDF for .NET könyvtár használatával. Az SVG (Scalable Vector Graphics) a vektorgrafikák népszerű formátuma, amely minőségromlás nélkül egyszerűen méretezhető. Az Aspose.PDF segítségével programozottan SVG-objektumokat adhat hozzá PDF-dokumentumaihoz.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio telepítve
- Aspose.PDF for .NET könyvtár telepítve

## 1. lépés: A környezet beállítása

Először is állítsuk be a környezetet egy új C#-projekt létrehozásával a Visual Studióban. Nyissa meg a Visual Studio-t, és kövesse az alábbi lépéseket:

1. Új projekt létrehozásához kattintson a "Fájl" > "Új" > "Projekt" elemre.
2. Válassza ki a „Konzolalkalmazás (.NET-keretrendszer)” vagy a „Konzolalkalmazás (.NET Core)” sablont a beállítástól függően.
3. Válasszon egy megfelelő nevet és helyet a projektnek, majd kattintson a "Létrehozás" gombra.

## 2. lépés: Hozzon létre dokumentum- és képobjektumokat

Ebben a lépésben elkészítjük a szükséges objektumokat a PDF-dokumentumunkhoz és az SVG-képünkhöz. Nyissa meg a projekt C# fájlját, és adja hozzá a következő kódot:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Azonnali dokumentum objektum
Document doc = new Document();
// Hozzon létre egy képpéldányt
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## 3. lépés: Állítsa be a kép tulajdonságait

Ezután beállítjuk az SVG-képünk tulajdonságait. Megadjuk a fájl típusát SVG-ként, az SVG-fájl elérési útját és a kép méreteit. Adja hozzá a következő kódot az előző lépés után:

```csharp
// Állítsa be a képtípust SVG-re
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// A forrásfájl elérési útja
img.File = dataDir + "SVGToPDF.svg";
// Állítsa be a képpéldány szélességét
img. FixWidth = 50;
// Állítsa be a képpéldány magasságát
img.FixHeight = 50;
```

## 4. lépés: A táblázat létrehozása és konfigurálása

Most hozzunk létre egy táblázatobjektumot, és állítsuk be az oszlopszélességeket. Létrehozunk egy táblázatot két oszlopból, amelyek szélessége 100 egység. Adja hozzá a következő kódot:

```csharp
// Példánytábla létrehozása
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Állítsa be a táblázatcellák szélességét
table. ColumnWidths = "100 100";
```

## 5. lépés: Adjon hozzá cellákat a táblázathoz

Ebben a lépésben egy sort és cellákat adunk a táblázathoz. Minden sor egy vízszintes sort jelent a táblázatban, és a cellák hozzáadódnak a sorokhoz. Adja hozzá a következő kódot:

```csharp
//Hozzon létre sorobjektumot, és adja hozzá a táblapéldányhoz
Aspose.Pdf.Row row = table.Rows.Add();
// Hozzon létre cellaobjektumot, és adja hozzá a sorpéldányhoz
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## 6. lépés: Szöveg és kép hozzáadása a cellákhoz

Ezután adjunk hozzá szöveget és SVG képet a táblázat celláihoz. Az első cellához hozzáadjuk az "Első cella" szöveget, a második cellához pedig az SVG-képet. Adja hozzá a következő kódot:

```csharp
// Szövegtöredék hozzáadása a cellaobjektum bekezdésgyűjteményéhez
cell.Paragraphs.Add(new TextFragment("First cell"));
// Adjon hozzá egy másik cellát a sorobjektumhoz
cell = row. Cells. Add();
// SVG-kép hozzáadása a nemrég hozzáadott cellapéldány bekezdésgyűjteményéhez
cell.Paragraphs.Add(img);
```

## 7. lépés: Hozzon létre és adjon hozzá egy oldalt a dokumentumhoz

Most hozzunk létre egy oldalobjektumot, és adjuk hozzá a dokumentumhoz. A táblázat hozzáadódik az oldal bekezdésgyűjteményéhez. Adja hozzá a következő kódot:

```csharp
// Hozzon létre oldalobjektumot, és adja hozzá a dokumentumpéldány oldalgyűjteményéhez
Page page = doc.Pages.Add();
// Táblázat hozzáadása az oldalobjektum bekezdésgyűjteményéhez
page.Paragraphs.Add(table);
```

## 8. lépés: Mentse el a PDF-fájlt

Végül elmentjük a PDF fájlt a megadott helyre. Adja hozzá a következő kódot:

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Példa forráskódra SVG objektum hozzáadásához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum objektum példányosítása
Document doc = new Document();
// Hozzon létre egy képpéldányt
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Állítsa be a képtípust SVG-re
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// A forrásfájl elérési útja
img.File = dataDir + "SVGToPDF.svg";
// Állítsa be a képpéldány szélességét
img.FixWidth = 50;
// Állítsa be a képpéldány magasságát
img.FixHeight = 50;
// Táblapéldány létrehozása
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Állítsa be a táblázatcellák szélességét
table.ColumnWidths = "100 100";
//Hozzon létre sorobjektumot, és adja hozzá a táblapéldányhoz
Aspose.Pdf.Row row = table.Rows.Add();
// Hozzon létre cellaobjektumot, és adja hozzá a sorpéldányhoz
Aspose.Pdf.Cell cell = row.Cells.Add();
// Szövegtöredék hozzáadása a cellaobjektum bekezdésgyűjteményéhez
cell.Paragraphs.Add(new TextFragment("First cell"));
// Adjon hozzá egy másik cellát a sorobjektumhoz
cell = row.Cells.Add();
// SVG-kép hozzáadása a nemrég hozzáadott cellapéldány bekezdésgyűjteményéhez
cell.Paragraphs.Add(img);
// Hozzon létre oldalobjektumot, és adja hozzá a dokumentumpéldány oldalgyűjteményéhez
Page page = doc.Pages.Add();
// Táblázat hozzáadása az oldalobjektum bekezdésgyűjteményéhez
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá SVG-objektumot egy PDF-fájlhoz az Aspose.PDF for .NET könyvtár használatával. Lépésről lépésre bemutattuk a dokumentum létrehozásának, a környezet beállításának, az SVG-kép táblázatcellához való hozzáadásának és a PDF-fájl mentésének folyamatát. Most már programozottan is beépíthet SVG-objektumokat PDF-dokumentumaiba.

### GYIK az SVG objektum PDF-fájlba való hozzáadásához

#### K: Hozzáadhatok több SVG objektumot a PDF dokumentumhoz?

 V: Igen, több SVG objektumot is hozzáadhat a PDF dokumentumhoz. Egyszerűen hozzon létre és konfiguráljon továbbiakat`Aspose.Pdf.Image` példányokat minden egyes hozzáadni kívánt SVG-képhez, majd adja hozzá azokat a kívánt táblázatcellákhoz vagy bekezdésekhez a PDF-dokumentumban.

#### K: Hogyan állíthatom be az SVG-kép méretét és helyzetét a táblázatcellában?

 V: Az SVG-kép méretének és pozíciójának beállításához a táblázatcellában módosíthatja a`FixWidth` és`FixHeight` tulajdonságai a`Aspose.Pdf.Image`példa. Más tulajdonságokat is használhat, mint pl`HorizontalAlignment` és`VerticalAlignment` a táblázatcellában a pozicionálás vezérléséhez.

#### K: Lehetséges-e szöveget hozzáadni az SVG-kép mellé ugyanabban a táblázatcellában?

 V: Igen, ugyanabban a táblázatcellában lehet szöveget hozzáadni az SVG-kép mellé. Használhatja a`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` módszer, amellyel szöveget adhat a cellához az SVG-képpel együtt.

#### K: Hozzáadhatok hiperhivatkozásokat az SVG-képhez?

 V: Igen, hiperhivatkozásokat adhat hozzá az SVG-képhez a`Hyperlink` tulajdona a`Aspose.Pdf.Image` példa. Állítsa be a hiperhivatkozás URL-jét vagy műveletét, hogy a kép kattintható legyen.

#### K: Az Aspose.PDF for .NET kompatibilis a .NET Core 3.1 vagy újabb verziókkal?

V: Igen, az Aspose.PDF for .NET kompatibilis a .NET Core 3.1-es és újabb verzióival. Használhatja a .NET Framework és a .NET Core alkalmazásokban is.