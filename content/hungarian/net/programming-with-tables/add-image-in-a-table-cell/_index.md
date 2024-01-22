---
title: Kép hozzáadása a táblázat cellájához
linktitle: Kép hozzáadása a táblázat cellájához
second_title: Aspose.PDF for .NET API Reference
description: Adjon hozzá egy képet a táblázat cellájához az Aspose.PDF for .NET segítségével, amely lépésről lépésre nyújt útmutatót a PDF-dokumentumok képeinek precíz kezeléséhez.
type: docs
weight: 10
url: /hu/net/programming-with-tables/add-image-in-a-table-cell/
---
Ebben az oktatóanyagban végigvezetjük a kép táblázatcellához való hozzáadásának folyamatán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja, hogyan érhető el ez a funkció. Az alábbiakban vázolt lépések követésével hatékonyan illesztheti be a képeket a táblázat celláiba.

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy az Aspose.PDF for .NET könyvtár telepítve van, és hivatkozik rá a projektben.

## 1. lépés: A dokumentum beállítása

 A kezdéshez létre kell hoznunk egy új példányt a`Document` osztályt az Aspose.Pdf névtérből. Ez az osztály egy PDF dokumentumot képvisel.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányosítson egy dokumentum objektumot
Document pdfDocument = new Document();
```

## 2. lépés: Oldal létrehozása

Ezután hozzá kell adnunk egy oldalt a PDF dokumentumhoz. Az oldal a táblázat és más elemek tárolójaként szolgál.

```csharp
// Hozzon létre egy oldalt a pdf dokumentumban
Page sec1 = pdfDocument.Pages.Add();
```

## 3. lépés: Táblázat hozzáadása

 Ebben a lépésben létrehozunk egy táblázatot a példányosítással`Table` osztályt az Aspose.Pdf névtérből.

```csharp
// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 4. lépés: Az alapértelmezett cellaszegély beállítása

 A következetesség érdekében beállíthatunk egy alapértelmezett cellaszegélyt a`DefaultCellBorder`az asztal tulajdonsága`BorderInfo` tárgy.

```csharp
// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 5. lépés: Oszlopszélesség beállítása

 A táblázat egyes oszlopai szélességének meghatározásához beállíthatjuk a`ColumnWidths` ingatlan. Adja meg a szélességet karakterláncként szóközzel elválasztott értékekkel.

```csharp
// Állítsa be a táblázat oszlopszélességeivel
tab1.ColumnWidths = "100 100 120";
```

## 6. lépés: Kép hozzáadása egy táblázatcellához

Most jön az izgalmas rész, egy kép hozzáadása a táblázat cellájához. Ehhez az alábbi allépéseket fogjuk követni:

## 6.1. lépés: Képobjektum létrehozása

 Hozzon létre egy példányt a`Image` osztályt az Aspose.Pdf névtérből. Állítsa be a`File` tulajdonságot a hozzáadni kívánt képfájl elérési útjára.

```csharp
// Hozzon létre egy Image objektumot
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## 6.2. lépés: Sor és cellák létrehozása

A kép táblázathoz való hozzáadásához először létre kell hoznunk egy sort és a szükséges cellákat.

```csharp
// Hozzon létre egy sort a táblázatban
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Szöveges cella hozzáadása a sorhoz
row1.Cells.Add("Sample text in cell");

// Adja hozzá a képet tartalmazó cellát
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## 6.3. lépés: A kép hozzáadása a táblázat cellájához

Végül hozzáadhatjuk a képet a táblázat cellájához úgy, hogy a cellán belül bekezdésként adjuk hozzá.

```csharp
// Adja hozzá a képet a táblázat cellájához
cell2.Paragraphs.Add(img);
```

## 6.4. lépés: További cellák hozzáadása

A képcella hozzáadása után szükség esetén további cellákat is hozzáadhatunk a sorhoz.

```csharp
//Adjon hozzá egy másik cellát a sorhoz
row1.Cells.Add("Previous cell with image");

// Állítsa be a harmadik cella függőleges igazítását
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## 7. lépés: A dokumentum mentése

 Végül a módosított dokumentumot a megadott helyre menthetjük a`Save` módszer.

```csharp
// Mentse el a dokumentumot
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Gratulálunk! Sikeresen megtanulta, hogyan adhat hozzá képet egy táblázatcellához az Aspose.PDF for .NET használatával. Nyugodtan fedezze fel a további testreszabási lehetőségeket, és integrálja ezt a funkciót projektjeibe.

### Példa forráskódra kép hozzáadásához egy táblázatcellában az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányosítson egy dokumentum objektumot
Document pdfDocument = new Document();
// Hozzon létre egy oldalt a pdf dokumentumban
Page sec1 = pdfDocument.Pages.Add();
// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adja hozzá a táblázatot a kívánt oldal bekezdésgyűjteményéhez
sec1.Paragraphs.Add(tab1);
// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Állítsa be a táblázat oszlopszélességeivel
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Adja hozzá a képet tartalmazó cellát
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Adja hozzá a képet a táblázat cellájához
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Mentse el a dokumentumot
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Következtetés

Ebben az oktatóanyagban egy lépésről lépésre bemutatjuk, hogyan adhatunk hozzá képet egy táblázatcellához az Aspose.PDF for .NET használatával. Kezdtük a dokumentum beállításával, egy oldal létrehozásával és egy táblázat hozzáadásával. Ezután beállítjuk az alapértelmezett cellaszegélyt és oszlopszélességet. Bemutattuk, hogyan lehet képet hozzáadni egy táblázatcellához, és hogyan lehet beállítani a cella függőleges igazítását. Végül elmentettük a módosított dokumentumot. Ha követi ezeket a lépéseket, hatékonyan javíthatja PDF-dokumentumait táblázatcellákban lévő képekkel.

### GYIK

#### K: Hozzáadhatok több képet egyazon táblázat különböző celláihoz az Aspose.PDF for .NET használatával?

V: Igen, az Aspose.PDF for .NET használatával több képet is hozzáadhat ugyanazon a táblázat különböző celláihoz. Egyszerűen kövesse az oktatóanyagban bemutatott eljárást minden egyes, a táblázathoz hozzáadni kívánt képhez.

#### K: Testreszabhatom a kép méretét és pozícióját a táblázatcellán belül?

 V: Igen, testreszabhatja a kép méretét és pozícióját a táblázatcellán belül a tulajdonságok beállításával`Image`tárgy. Beállíthatja a kép szélességét és magasságát, valamint a cellán belüli igazítást.

#### K: Hozzáadhatok képeket egy dinamikus számú sorral és oszloppal rendelkező táblázathoz?

V: Igen, dinamikus számú sorral és oszloppal rendelkező táblázathoz is hozzáadhat képeket. Az Aspose.PDF for .NET rugalmasságot biztosít a változó méretű táblázatok létrehozásában. Szükség szerint hozzáadhat sorokat és cellákat, majd ennek megfelelően képeket adhat hozzá adott cellákhoz.

#### K: Milyen képformátumokat támogat az Aspose.PDF for .NET a képek táblázatcellákhoz való hozzáadásához?

V: Az Aspose.PDF for .NET a képformátumok széles skáláját támogatja, beleértve a JPEG-et, PNG-t, GIF-et, BMP-t és TIFF-et. Ezen formátumok bármelyikének képeivel hozzáadhatja azokat a táblázat celláihoz.

#### K: Hozzáadhatok képeket egy meglévő PDF-dokumentum táblázataihoz?

V: Igen, képeket adhat hozzá egy meglévő PDF-dokumentum táblázataihoz az Aspose.PDF for .NET használatával. Egyszerűen töltse be a meglévő dokumentumot, és kövesse ugyanazokat a lépéseket, hogy képeket adjon a táblázathoz, az oktatóanyagban bemutatott módon.