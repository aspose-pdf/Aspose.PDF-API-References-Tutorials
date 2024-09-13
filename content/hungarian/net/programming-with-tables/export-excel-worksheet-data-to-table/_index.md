---
title: Exportálja az Excel munkalap adatait táblázatba
linktitle: Exportálja az Excel munkalap adatait táblázatba
second_title: Aspose.PDF for .NET API Reference
description: Exportáljon adatokat egy Excel-lapról PDF-táblázatba az Aspose.PDF for .NET használatával.
type: docs
weight: 70
url: /hu/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
Ebben az oktatóanyagban megtanuljuk, hogyan exportálhatunk adatokat Excel-munkalapról, és hogyan hozhatunk létre táblázatot PDF-dokumentumban az Aspose.PDF for .NET könyvtár használatával. Lépésről lépésre végigjárjuk a forráskódot, és részletesen elmagyarázzuk az egyes részeket. Ennek az oktatóanyagnak a végére képes lesz PDF-fájlok létrehozására Excel-munkalapok adatait tartalmazó táblázatokkal. Kezdjük is!

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- C# programozási nyelv alapismerete
- A Visual Studio telepítve van a gépedre
- Aspose.PDF for .NET könyvtár hozzáadva a projekthez

## 1. lépés: A környezet beállítása
Kezdésként hozzon létre egy új C#-projektet a Visual Studióban. Adja hozzá a hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ehhez kattintson a jobb gombbal a projektjére a Solution Explorerben, válassza ki a „NuGet-csomagok kezelése” lehetőséget, és keressen az „Aspose.PDF” kifejezésre. Telepítse a csomagot, és már indulhat is.

## 2. lépés: Az Excel munkalap betöltése
Kódunk első lépésében meghatározzuk az Excel dokumentumot tartalmazó könyvtár elérési útját. Cserélje le a „DOKUMENTUMKÖNYVTÁR” elemet a tényleges könyvtár elérési útjával, ahol az Excel-fájl található.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

Itt az Aspose.Cells könyvtárat használjuk az Excel-munkafüzet betöltésére. Ügyeljen arra, hogy a „newBook1.xlsx” szöveget az Excel-fájl nevére cserélje.

## 3. lépés: A munkalap elérése
 Ezután el kell érnünk az Excel fájl első munkalapját. Ezt a`Worksheets` gyűjteménye a`Workbook` objektum.

```csharp
// Az Excel fájl első munkalapjának elérése
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Ha az Excel-fájl több munkalapot is tartalmaz, módosíthatja az indexértéket`[0]` egy másik munkalap eléréséhez.

## 4. lépés: Adatok exportálása a DataTable-ba
 Most exportáljuk az Excel munkalap tartalmát a`DataTable` objektum. A segítségével megadjuk az exportálandó cellák tartományát`ExportDataTable` módszer.

```csharp
// 7 sor és 2 oszlop tartalmának exportálása az 1. cellától kezdve a DataTable-ba
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

Ebben a példában minden sort és oszlopot exportálunk az első cellától (0, 0) a munkalap utolsó cellájáig. Állítsa be a megfelelő tartományt igényei szerint.

## 5. lépés: PDF-dokumentum létrehozása
Most létrehozunk egy új PDF dokumentumot az Aspose.PDF könyvtár használatával.

```csharp
// Példányosítson egy dokumentumpéldányt
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Ez létrehoz egy üres PDF dokumentumot, amelyhez tartalmat adhatunk hozzá.

## 6. lépés: Oldal és táblázat hozzáadása
Az adatok táblázatos formátumban történő megjelenítéséhez egy oldalt és egy táblázatot kell hozzáadnunk a PDF dokumentumhoz.

```csharp
// Hozzon létre egy oldalt a dokumentumpéldányban
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Hozzon létre egy táblázat objektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adja hozzá a Table objektumot a szakasz bekezdésgyűjteményéhez
sec1.Paragraphs.Add(tab1);
```

Itt létrehozunk egy új oldalt és egy táblázatobjektumot. Ezután hozzáadjuk a táblázatot az oldal bekezdésgyűjteményéhez.

## 7. lépés: A táblázat tulajdonságainak beállítása
Az adatok importálása előtt be kell állítanunk a táblázat néhány tulajdonságát, például az oszlopszélességeket és az alapértelmezett cellaszegélyeket.

```csharp
// Állítsa be a táblázat oszlopszélességét
tab1.ColumnWidths = "40 100 100";

// Állítsa be a táblázat alapértelmezett cellaszegélyét a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

Ebben a példában az oszlopszélességeket 40, 100 és 100 egységre állítjuk be. Állítsa be az értékeket az adatok alapján. Az alapértelmezett cellaszegélyt úgy is beállítottuk, hogy az egyes cellák minden oldalán szegélyek jelenjenek meg.

## 8. lépés: Adatok importálása a táblázatba
 Most importáljuk az adatokat a`DataTable` objektumot a táblázatba a`ImportDataTable` módszer.

```csharp
// Importáljon adatokat a Table objektumba a fent létrehozott DataTable-ból
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Itt megadjuk az importálandó sorok és oszlopok tartományát. Ebben a példában az összes sort és oszlopot importáljuk a`dataTable` objektum.

## 9. lépés: A táblázat formázása
táblázat megjelenésének javítása érdekében formázást alkalmazhatunk adott cellákon vagy sorokon. Ebben a lépésben megformázzuk a táblázat első és alternatív sorait.

```csharp
// Vegye ki az 1. sort a táblázatból
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Formázza az első sort
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // Állítsa be az első sor celláinak háttérszínét
     curCell.BackgroundColor = Color.Blue;// Állítsa be az első sor celláinak arcát
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // Állítsa be az első sor celláinak betűszínét
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // Állítsa be az első sor celláinak szövegigazítását
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// Alternatív sorformátum
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // Állítsa be a cellák háttérszínét az alternatív sorokban
         curCell.BackgroundColor = Color.Gray;
        
         // Állítsa be a cellák szövegszínét az alternatív sorokban
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

Itt végigmegyünk az első sor celláin, és beállítjuk a háttérszínt, a betűtípust, a betűszínt és a szöveg igazítását. Ezután végigfutjuk az alternatív sorok összes celláját, és beállítjuk a háttér és a szöveg színét.

## 10. lépés: Mentse el a PDF-dokumentumot
Végül elmentjük a PDF dokumentumot a megadott helyre.

```csharp
// Mentse el a PDF-et
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

Ügyeljen arra, hogy a „DOKUMENTUMKÖNYVTÁR” szöveget a kívánt könyvtár elérési útjával és fájlnevével cserélje ki a kimeneti PDF-fájlhoz.

### Példa forráskódra az Excel-munkalapadatok táblába exportálásához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Az Excel fájl első munkalapjának elérése
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 7 sor és 2 oszlop tartalmának exportálása az 1. cellától kezdve a DataTable-ba
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// Példányosítson egy dokumentum példányt
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Hozzon létre egy oldalt a dokumentumpéldányban
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// Hozzon létre egy táblázat objektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adja hozzá a Table objektumot a szakasz bekezdésgyűjteményéhez
sec1.Paragraphs.Add(tab1);

// Állítsa be a táblázat oszlopszélességét. A ColumnCount-ot manuálisan kell megadnunk.
// Mivel a jelenlegi excel munkalapnak három oszlopa van, ezért ugyanazt a számot adjuk meg
tab1.ColumnWidths = "40 100 100";

// Állítsa be a táblázat alapértelmezett cellaszegélyét a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Importáljon adatokat a Table objektumba a fent létrehozott DataTable-ból
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// Vegye ki az 1. sort a táblázatból
Aspose.Pdf.Row row1 = tab1.Rows[0];

// Ismételje meg az 1. sor összes celláját, és állítsa a háttérszínüket kékre
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// Állítsa be a táblázat 1. sorában található összes cella hátterét.
	curCell.BackgroundColor = Color.Blue;
	// Állítsa be a betűtípust a táblázat 1. sorának celláihoz.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// Állítsa be a táblázat 1. sorában található összes cella betűtípusának színét.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// Állítsa be az 1. sor celláinak szövegigazítását Középre.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// Ismételje meg az 1. sor összes celláját, és állítsa a háttérszínüket kékre
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// Állítsa be az összes cella háttérszínét, kivéve az 1. sort.
		curCell.BackgroundColor = Color.Gray;
		// Állítsa be az összes cella szöveg színét, kivéve az 1. sort.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// Mentse el a PDF-et
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan exportálhatunk adatokat Excel-munkalapról PDF-táblázatba az Aspose.PDF for .NET könyvtár használatával. Lépésről lépésre bemutattuk az Excel munkalap betöltésének, a PDF dokumentum létrehozásának, a táblázat hozzáadásának, az adatok importálásának és a táblázat formázásának lépéseit. Most már programozottan is létrehozhat PDF-fájlokat Excel-adatokat tartalmazó táblázatokkal.

### GYIK

#### K: Mi a célja az Excel-munkalapadatok PDF-táblába történő exportálásának?

V: Az Excel munkalap adatainak PDF-táblázatba történő exportálása lehetővé teszi az adatok strukturált és szervezett formátumban történő megjelenítését. Lehetővé teszi PDF-fájlok létrehozását Excel-munkalapok adatait tartalmazó táblázatokkal, megkönnyítve ezzel az információk hordozható dokumentumformátumban történő megosztását és megőrzését.

#### K: Testreszabhatom a PDF-tábla megjelenését?

V: Igen, testreszabhatja a PDF-tábla megjelenését az Aspose.PDF for .NET által biztosított különféle tulajdonságaival. A mellékelt C# forráskódban módosíthatja az oszlopszélességeket, a cellaszegélyeket, a szövegigazítást, a betűstílust és egyebeket, hogy megfeleljen az Ön egyedi igényeinek.

#### K: Hogyan kezelhetem a több munkalappal rendelkező Excel-fájlokat?

 V: A megadott C# kódban az index segítségével elértük az Excel fájl első munkalapját`[0]` . Ha az Excel-fájl több munkalapot is tartalmaz, akkor az index értékének megfelelő módosításával érheti el őket, például`[1]` a második munkalaphoz ill`[2]` a harmadik munkalaphoz.

#### K: Alkalmazhatok eltérő formázást a PDF-tábla adott soraihoz vagy celláihoz?

V: Igen, eltérő formázást alkalmazhat a PDF-tábla adott soraihoz vagy celláihoz. A mellékelt C# forráskódban bemutattuk, hogyan lehet az első sort és az alternatív sorokat eltérő módon formázni a háttérszínük, a betűstílusuk és a betűszínük megváltoztatásával. Szükség szerint alkalmazhat hasonló formázási technikákat bármely konkrét sorra vagy cellára.

#### K: Az Aspose.PDF for .NET az egyetlen olyan könyvtár, amely lehetővé teszi az Excel adatok PDF táblába történő exportálását?

V: Az Aspose.PDF for .NET egy hatékony könyvtár a PDF-dokumentumokkal való munkavégzéshez .NET-alkalmazásokban. Bár más könyvtárak is elérhetők, az Aspose.PDF for .NET a szolgáltatások és lehetőségek széles skáláját kínálja az Excel-adatokból származó táblázatokat tartalmazó PDF-fájlok előállításához, kezeléséhez és exportálásához, így népszerű választás az ilyen feladatokhoz.