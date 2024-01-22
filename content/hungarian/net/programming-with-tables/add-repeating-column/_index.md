---
title: Ismétlődő oszlop hozzáadása a PDF-dokumentumhoz
linktitle: Ismétlődő oszlop hozzáadása a PDF-dokumentumhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá ismétlődő oszlopot PDF-dokumentumhoz az Aspose.PDF for .NET használatával.
type: docs
weight: 20
url: /hu/net/programming-with-tables/add-repeating-column/
---
Ebben az oktatóanyagban megtudjuk, hogyan lehet ismétlődő oszlopot hozzáadni a PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a forráskódot C# nyelven. Ennek az oktatóanyagnak a végén tudni fogja, hogyan hozhat létre ismétlődő oszlopot tartalmazó táblázatot egy PDF-dokumentumban. Kezdjük!

## 1. lépés: A környezet beállítása
Először is győződjön meg arról, hogy beállította C# fejlesztői környezetét az Aspose.PDF for .NET segítségével. Adja hozzá a hivatkozást a könyvtárhoz, és importálja a szükséges névtereket.

## 2. lépés: A PDF dokumentum létrehozása
Ebben a lépésben létrehozunk egy új PDF dokumentumot.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

Létrehoztunk egy üres PDF dokumentumot, amelybe tartalmat adhatunk hozzá.

## 3. lépés: A táblázatok létrehozása
Ebben a lépésben létrehozunk egy főtáblát (`outerTable`) és egy beágyazott táblázat (`mytable`), amely megismétlődik az oszlopban.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Meghatároztuk a táblázat tulajdonságait, például az oszlopszélességet és a beágyazott táblázattörés módot.

## 4. lépés: Táblázatok hozzáadása a dokumentumhoz
Most hozzáadjuk a létrehozott táblázatokat a PDF dokumentumhoz.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

Először hozzáadjuk a fő táblázatot (`outerTable`) a PDF dokumentumhoz. Ezután hozzáadjuk a beágyazott táblát (`mytable` ) bekezdésként a főtábla cellájában. Megadjuk az ismétlődő oszlopok számát is`mytable` (ebben a példában 5 oszlop).

## 5. lépés: Fejlécek és sorok hozzáadása
Most hozzáadjuk a fejléceket és a sorokat a táblázathoz.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// Adjon hozzá további fejléceket

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // Adja hozzá a többi oszlopot ide
}
```

Először hozzáadjuk a fejléceket a táblázat első sorához (`headerRow`). Ezután egy ciklusból adjuk hozzá az adatsorokat. Ebben a példában 6 adatsort adunk hozzá.

## 6. lépés: A PDF dokumentum mentése
Végül elmentjük a PDF dokumentumot a megadott fájlba.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

Ügyeljen arra, hogy a megfelelő könyvtárat és fájlnevet adja meg a kimeneti PDF-fájl mentéséhez.

### Példa forráskódra ismétlődő oszlop hozzáadásához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// Hozzon létre egy új dokumentumot
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// Példányosítson egy külső táblázatot, amely az egész oldalt elfoglalja
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//Példányosítson egy táblaobjektumot, amely a külső táblázatba lesz beágyazva, és amely ugyanazon az oldalon belül megszakad
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// Adja hozzá a külső táblázatot az oldal bekezdéseihez
// Mytable hozzáadása az outerTable-hoz
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// Fejléc sor hozzáadása
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

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
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
doc.Save(outFile);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet ismétlődő oszlopot hozzáadni egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Ezzel a lépésenkénti útmutatóval ismétlődő oszlopokat tartalmazó táblázatokat hozhat létre saját C#-projektjeiben.

### GYIK ismétlődő oszlopok hozzáadásához a PDF-dokumentumban

#### K: Testreszabhatom az ismétlődő oszlopok számát a beágyazott táblázatban?

 V: Igen, testreszabhatja az ismétlődő oszlopok számát a beágyazott táblázatban. A megadott példában beállítjuk`mytable.RepeatingColumnsCount = 5;`, ami azt jelenti, hogy 5 ismétlődő oszlop lesz. Ezt az értéket tetszőleges számra módosíthatja.

#### K: Lehetséges-e dinamikusan további sorok hozzáadása a beágyazott táblához?

V: Igen, dinamikusan hozzáadhat további sorokat a beágyazott táblához az oktatóanyagban látható módon. Használhat hurkokat vagy bármilyen más logikát sorok hozzáadásához az adatok alapján.

#### K: Alkalmazhatok stílusokat és formázást a táblázatra és celláira?

V: Igen, stílusokat és formázásokat alkalmazhat a táblázatra és celláira az Aspose.PDF for .NET használatával. A könyvtár különféle tulajdonságokat és módszereket kínál a táblázat megjelenésének és tartalmának testreszabásához.

#### K: Az Aspose.PDF for .NET kompatibilis a .NET Core programmal?

V: Igen, az Aspose.PDF for .NET kompatibilis a .NET Core-val. Használhatja a .NET Framework és a .NET Core alkalmazásokban is.

#### K: Használhatom ezt a megközelítést ismétlődő oszlopok hozzáadására egy meglévő PDF-dokumentumhoz?

V: Igen, ezt a megközelítést használhatja ismétlődő oszlopok hozzáadásához egy meglévő PDF-dokumentumhoz. Egyszerűen töltse be a meglévő dokumentumot az Aspose.PDF for .NET segítségével, és kövesse ugyanazokat a lépéseket az ismétlődő oszlop létrehozásához és hozzáadásához.