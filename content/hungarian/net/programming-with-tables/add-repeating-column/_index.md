---
title: Ismétlődő oszlop hozzáadása a PDF-dokumentumhoz
linktitle: Ismétlődő oszlop hozzáadása a PDF-dokumentumhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá ismétlődő oszlopokat PDF-dokumentumokhoz az Aspose.PDF for .NET használatával. Lépésről lépésre útmutató példákkal és kóddal. Tökéletes fejlesztőknek.
type: docs
weight: 20
url: /hu/net/programming-with-tables/add-repeating-column/
---
## Bevezetés

Ha PDF-dokumentumokkal dolgozik, és ismétlődő oszlopokat kell hozzáadnia, akkor jó helyen jár! Az Aspose.PDF for .NET használatával könnyedén kezelheti a PDF-ben található táblázatokat és tartalmakat. Akár dinamikus jelentéseket, számlákat vagy bármilyen más strukturált dokumentumot készít, az ismétlődő oszlopok megváltoztathatják az adatok rendszerezését. Vessen egy pillantást egy lépésről lépésre szóló útmutatóra, amely bemutatja, hogyan adhatunk ismétlődő oszlopokat egy PDF-dokumentumhoz.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjön meg arról, hogy mindent beállított:

- Aspose.PDF for .NET: telepítenie kell az Aspose.PDF for .NET könyvtárat a projektben.
- [Töltse le az Aspose.PDF-et .NET-hez](https://releases.aspose.com/pdf/net/)
- [Ingyenes próbaverzió](https://releases.aspose.com/)
- Fejlesztői környezet: Győződjön meg arról, hogy telepítve van egy .NET-kompatibilis IDE, például a Visual Studio.
- A C# alapvető ismerete: Noha mindent fel fogunk bontani, a C# alapvető ismerete segít a zökkenőmentes követésben.
  
 Ha még nem rendelkezik Aspose.PDF .NET-hez, beszerezheti a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) hogy elkezdje felfedezni jellemzőit.

## Csomagok importálása

kezdéshez importálnia kell a szükséges névtereket az Aspose.PDF fájlból a .NET-hez. Íme, hogyan kell csinálni:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ezek a csomagok biztosítják a PDF-dokumentumok kezeléséhez és a táblázatok kezeléséhez szükséges alapvető osztályokat és módszereket.

Most bontsuk le a folyamatot több lépésre, hogy ismétlődő oszlopokat adjunk a PDF-dokumentumhoz. Kövessetek!

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

Mielőtt bármilyen fájlt létrehoznánk vagy manipulálnánk, meg kell határoznunk az elérési utat, ahová a generált PDF mentésre kerül. A C# projektben állítsa be a könyvtár elérési útját, ahol a fájlok találhatók:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Ez az útvonal arra a könyvtárra mutat, ahová a kimeneti PDF mentésre kerül. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal a gépen.

## 2. lépés: Hozzon létre egy új PDF-dokumentumot

 Kezdésként példányosítson egy újat`Document` objektum. Ez tárolóként fog szolgálni a PDF-ben található összes oldal és tartalom számára.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Itt létrehoztunk egy új PDF-dokumentumot, és hozzáadtunk egy üres oldalt. A`doc.Pages.Add()` metódus új oldalt szúr be a dokumentumba.

## 3. lépés: Példányosítsa a külső táblázatot

Ezután létrehozunk egy külső táblázatot. Ez a táblázat átfogja az oldal teljes szélességét, és tárolóként szolgál más táblázatok számára, beleértve azt is, amelyik az ismétlődő oszlopokat tartalmazza.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Beállítottuk a`ColumnWidths` tulajdonság "100%-ra", ami azt jelenti, hogy a táblázat az oldal teljes szélességében kiterjed.

## 4. lépés: Hozza létre a belső táblázatot

 Most hozzuk létre a belső táblázatot, amelyben ismétlődő oszlopok lesznek. A legfontosabb tulajdonságok itt vannak`Broken` , amely lehetővé teszi, hogy a táblázat ugyanazon az oldalon folytatódjon, és`ColumnAdjustment`, amely automatikusan a tartalomhoz igazítja az oszlopszélességeket.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Ez a belső táblázat a külső táblán belül lesz beágyazva.

## 5. lépés: Adjon hozzá táblázatokat az oldalhoz

Most, hogy a külső és a belső táblázatok is készen vannak, tegyük fel az oldalra. Ez a lépés biztosítja, hogy a táblázatok szerepeljenek a dokumentum szerkezetében.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Itt hozzáadtuk a`outerTable` oldalra, majd a külső táblán belül beágyaztuk a`mytable` . Ezenkívül beállítottuk`RepeatingColumnsCount`5-ig, megadva, hogy hány oszlopnak kell ismétlődnie az adatok hozzáadásakor.

## 6. lépés: Adja hozzá a fejlécsort

Itt az ideje, hogy hozzáadja a fejléceket a táblázathoz. A fejléc sor kontextust ad az adatokhoz, és segít az oszlopok strukturálásában. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Ez a kódrészlet hozzáadja az első sort (amelyet fejlécként fogunk használni), és olyan cellákkal tölti fel, amelyek szöveget tartalmaznak, például „fejléc 1”, „fejléc 2” stb.

## 7. lépés: Adatsorok hozzáadása

Végül hozzáadhatunk néhány adatot a táblázathoz. Ez a ciklus dinamikusan hoz létre sorokat, és tartalommal tölti meg a cellákat:

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

A ciklus hatszor ismétlődik, sorokat ad hozzá, és minden cellát kitölt a megfelelő oszlopadatokkal (pl. „1. oszlop, 1. oszlop”, „2. oszlop, 2. oszlop” stb.).

## 8. lépés: Mentse el a dokumentumot

Az összes sor és oszlop hozzáadása után az utolsó lépés a dokumentum mentése a megadott fájl elérési útra.

```csharp
doc.Save(outFile);
```

A dokumentum ismétlődő oszlopokkal mentésre kerül!

## Következtetés

Megvan! Ezekkel az egyszerű lépésekkel az Aspose.PDF for .NET használatával PDF-dokumentumot hozhat létre ismétlődő oszlopokkal. A beágyazott táblák rugalmasságának kiaknázásával olyan összetett elrendezéseket érhet el, amelyek professzionális és szervezett PDF-eket eredményeznek. Próbálja ki ezt a következő projektje során, és fedezze fel az Aspose.PDF-ben rejlő lehetőségeket a PDF generálási igényeinek kielégítésére.

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára a PDF-dokumentumok programozott létrehozását, szerkesztését és kezelését.

### Dinamikusan módosíthatom az ismétlődő oszlopok számát?
 Igen, módosíthatja az ismétlődő oszlopok számát a`RepeatingColumnsCount` ingatlan.

### Hogyan kérhetek licencet az Aspose.PDF fájlhoz .NET-hez?
 Fájlból vagy adatfolyamból licencet igényelhet, ha követi a[dokumentáció](https://reference.aspose.com/pdf/net/).

### Lehetséges képeket hozzáadni a táblázat celláihoz?
Igen, az Aspose.PDF for .NET támogatja különféle típusú tartalom hozzáadását a táblázatcellákhoz, beleértve a képeket.

### Testreszabhatom a táblázat elrendezését?
Teljesen! Az Aspose.PDF kiterjedt funkciókat kínál a táblázatstílusok testreszabásához, beleértve a szegélyeket, a kitöltést, az igazítást és egyebeket.