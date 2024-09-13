---
title: Integrálás az adatbázisba PDF fájlba
linktitle: Integrálás az adatbázisba PDF fájlba
second_title: Aspose.PDF for .NET API Reference
description: Adatbázisból származó adatok beágyazása PDF-fájlba az Aspose.PDF for .NET használatával.
type: docs
weight: 120
url: /hu/net/programming-with-tables/integrate-with-database/
---
Ebben az oktatóanyagban megtanuljuk, hogyan ágyazhatunk be adatokat egy adatbázisból PDF-fájlba az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a forráskódot C# nyelven. Ennek az oktatóanyagnak a végén tudni fogja, hogyan importálhat táblázatadatokat egy adatbázisból PDF dokumentumba. Kezdjük!

## 1. lépés: A környezet beállítása
Győződjön meg arról, hogy a C# fejlesztői környezetet az Aspose.PDF for .NET segítségével konfigurálta. Adja hozzá a hivatkozást a könyvtárhoz, és importálja a szükséges névtereket.

## 2. lépés: A DataTable létrehozása
Létrehozzuk a DataTable egy példányát, amely a PDF dokumentumba beágyazni kívánt adatokat képviseli. Ebben a példában egy adattáblát hozunk létre három oszloppal: Alkalmazotti_azonosító, Munkavállaló_neve és Nem. A DataTable-hoz két sort is hozzáadunk áladatokkal.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## 3. lépés: PDF-dokumentum és táblázat létrehozása
Létrehozunk egy példányt a dokumentumból, és hozzáadunk egy oldalt ehhez a dokumentumhoz. Ezután létrehozunk egy táblázatpéldányt, amely a táblázatunkat reprezentálja a PDF dokumentumban. Meghatározzuk a táblázat oszlopainak szélességét és szegélystílusát.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 4. lépés: Adatok importálása a DataTable-ből a táblába
Az ImportDataTable metódus segítségével importálhatjuk az adatokat a DataTable-ból a PDF dokumentum táblázatába.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## 5. lépés: A táblázat hozzáadása a dokumentumhoz
A táblázatot hozzáadjuk a dokumentumoldal bekezdésgyűjteményéhez.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## 6. lépés: Mentse el a dokumentumot
A PDF dokumentumot a beágyazott adatbázis adataival mentjük.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

Gratulálok! Most már tudja, hogyan ágyazhat be adatbázisadatokat egy PDF-dokumentumba az Aspose.PDF for .NET használatával.

### Példa forráskódra az Integrate With Database for Aspose.PDF for .NET használatával programhoz

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//Adjon hozzá 2 sort a DataTable objektumhoz programozottan
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// Dokumentumpéldány létrehozása
Document doc = new Document();
doc.Pages.Add();
// Inicializálja a tábla új példányát
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Állítsa be a táblázat oszlopszélességét
table.ColumnWidths = "40 100 100 100";
// Állítsa be a táblázat szegélyének színét LightGray-re
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Állítsa be a táblázatcellák szegélyét
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// Táblázatobjektum hozzáadása a bemeneti dokumentum első oldalához
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// Mentse el a táblaobjektumot tartalmazó frissített dokumentumot
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan ágyazhatunk be adatokat egy adatbázisból egy PDF dokumentumba az Aspose.PDF for .NET használatával. Ezzel a lépésenkénti útmutatóval importálhatja az adatokat saját adatbázisából, és megjelenítheti őket PDF dokumentumokban. Fedezze fel az Aspose.PDF dokumentációt, és fedezze fel a nagy teljesítményű könyvtár által kínált egyéb funkciókat és lehetőségeket.

### GYIK az adatbázissal való integrációhoz PDF-fájlban

#### K: Használhatom az Aspose.PDF for .NET fájlt különböző típusú adatbázisokkal, mint például a MySQL, SQL Server vagy Oracle?

V: Igen, használhatja az Aspose.PDF for .NET fájlt különböző típusú adatbázisokkal, mint például a MySQL, SQL Server, Oracle és mások. Az Aspose.PDF for .NET olyan funkciókat biztosít, amelyek segítségével különböző adatforrásokból, például adatbázisokból, XML-fájlokból és egyebekből kiolvashatók az adatok. Lekérheti az adatokat a kívánt adatbázistípusból, és feltöltheti egy DataTable-be vagy bármely más adatstruktúrába, amely kompatibilis az Aspose.PDF for .NET fájllal.

#### K: Hogyan szabhatom testre a táblázat megjelenését a PDF-dokumentumban?

V: Testreszabhatja a táblázat megjelenését a PDF-dokumentumban az Aspose.PDF for .NET könyvtár által biztosított különféle tulajdonságokkal. Például beállíthat különböző szegélystílusokat, háttérszíneket, betűstílusokat és igazításokat a táblázathoz és celláihoz. A tábla megjelenésének testreszabásával kapcsolatos további részletekért tekintse meg az Aspose.PDF .NET dokumentációját.

#### K: Lehetséges-e hiperhivatkozásokat vagy interaktív elemeket hozzáadni az adatbázisból importált adatokhoz?

V: Igen, hozzáadhat hiperhivatkozásokat vagy egyéb interaktív elemeket az adatbázisból importált adatokhoz. Az Aspose.PDF for .NET támogatja hiperhivatkozások, könyvjelzők és egyéb interaktív elemek hozzáadását a PDF-dokumentumhoz. A DataTable tartalmát manipulálhatja, mielőtt importálná a táblába, és hiperhivatkozásokat vagy egyéb interaktív szolgáltatásokat is tartalmazhat.

#### K: Lapozhatom a táblázatot, ha túllép egy bizonyos számú sort?

V: Igen, lapozhatja a táblázatot, ha túllép egy bizonyos számú sort. Ennek eléréséhez használhatja a`IsInNewPage` a Row objektum tulajdonsága, amely jelzi, hogy egy új oldalnak egy adott sor után kell kezdődnie. Kiszámolhatja az oldalanként megjelenítendő sorok számát, és beállíthatja a`IsInNewPage` ingatlan ennek megfelelően.

#### K: Hogyan exportálhatom a beágyazott adatbázis-adatokat tartalmazó PDF-dokumentumot különböző fájlformátumokba, mint például DOCX vagy XLSX?

V: Az Aspose.PDF for .NET lehetővé teszi a PDF-dokumentumok különféle más fájlformátumokká való konvertálását, beleértve a DOCX (Microsoft Word) és XLSX (Microsoft Excel) formátumokat. Ennek eléréséhez használhatja az Aspose.PDF for .NET könyvtárat más Aspose könyvtárakkal, például az Aspose.Words-szel és az Aspose.Cells-szel kombinálva. Először mentse el a PDF-dokumentumot a beágyazott adatbázisadatokkal, majd a megfelelő Aspose könyvtár segítségével alakítsa át a kívánt fájlformátumra.