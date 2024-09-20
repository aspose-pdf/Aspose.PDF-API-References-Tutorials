---
title: Exportálja az Excel munkalap adatait táblázatba
linktitle: Exportálja az Excel munkalap adatait táblázatba
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan exportálhatja az Excel-munkalap adatait PDF-táblázatba az Aspose.PDF for .NET segítségével. Lépésről lépésre bemutató oktatóprogram kódpéldákkal, előfeltételekkel és hasznos tippekkel.
type: docs
weight: 70
url: /hu/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
## Bevezetés

Szüksége volt már arra, hogy adatokat exportáljon Excel-munkalapról PDF-fájlba, szépen táblázatformátumba rendezve? Képzelje el, hogy egy csomó adat van az Excelben, de professzionális megjelenésű PDF-fájlként kell megosztania. Ez bonyolultan hangozhat, igaz? Az Aspose.PDF for .NET segítségével azonban ezt a feladatot gyerekjátékká változtathatja. Ebben az oktatóanyagban végigvezetjük az Excel-munkalapok adatainak PDF-dokumentumban lévő táblázatba való exportálásán az Aspose.PDF for .NET használatával. Lépésről lépésre végigvezetjük, mindent lebontva, hogy még ha még új vagy ebben, a végére profinak érezd magad.

## Előfeltételek

Mielőtt belemerülnénk a kódolásba, állítsunk be néhány dolgot:

1.  Aspose.PDF for .NET Library – Győződjön meg arról, hogy a legújabb verzió van telepítve. Megteheti[töltse le itt](https://releases.aspose.com/pdf/net/).
2.  Aspose.Cells for .NET Library – Erre az Excel műveletek kezeléséhez lesz szüksége. Töltse le innen[itt](https://releases.aspose.com/cells/net/).
3. .NET fejlesztői környezet – Egy olyan eszköz, mint a Visual Studio, tökéletesen működik a kódoláshoz.
4. Excel-fájl – Készítsen Excel-fájlt az exportálni kívánt adatokkal.

 Ha nem rendelkezik Aspose.PDF és Aspose.Cells könyvtárral, kezdheti egy[ingyenes próbaverzió](https://releases.aspose.com/).

## Csomagok importálása

Először is győződjön meg arról, hogy az Aspose.PDF és az Aspose.Cells könyvtárakat is telepítette a projektben. Telepítheti őket a Visual Studio NuGet Package Manager használatával.

Így importálhatja a szükséges csomagokat a C# kódba:

```csharp
using System.Data;
using System.IO;
using System.Linq;
```

Most, hogy az előfeltételek be vannak állítva, menjünk végig az adatok exportálásán egy Excel-lapból egy PDF-dokumentum táblázatába.

## 1. lépés: Töltse be az Excel-munkafüzetet

A kezdéshez be kell töltenie az Excel-munkafüzetet a programba. Ebben a lépésben az Aspose.Cells fájlt használjuk az Excel fájl megnyitásához.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Töltse be az Excel munkafüzetet
Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

 Magyarázat: Itt megadjuk az Excel fájl elérési útját, és ezzel töltjük be a munkafüzetet`Aspose.Cells.Workbook` . Ügyeljen a beállításra`"YOUR DOCUMENT DIRECTORY"` hogy a fájl helyére mutasson.

## 2. lépés: Nyissa meg az első munkalapot

munkafüzet betöltése után el kell érnünk az első munkalapot, ahol az adataink tárolódnak.

```csharp
// Az Excel fájl első munkalapjának elérése
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

Magyarázat: Ez a lépés egyszerű – megragadjuk a munkafüzet első munkalapját, amely az exportálandó adatokat tartalmazza.

## 3. lépés: Exportálja az adatokat a DataTable-ba

Most exportáljuk az adatokat az Excel-lapról egy DataTable objektumba, amely közvetítőként fog működni az adatok PDF-be történő átvitelében.

```csharp
// 7 sor és 2 oszlop tartalmának exportálása az 1. cellától kezdve a DataTable-ba
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

 Magyarázat: A`ExportDataTable` metódus kivonja az adatokat a munkalap első cellájától kezdve, és átfogja az összes sort és oszlopot. Ezek az adatok ezután a`DataTable` további felhasználásra.

## 4. lépés: Hozzon létre egy új PDF-dokumentumot

Ezután létre kell hoznunk egy új PDF dokumentumot az Aspose.PDF használatával.

```csharp
// Példányosítson egy dokumentumpéldányt
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a dokumentumpéldányban
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

 Magyarázat: Itt inicializálunk egy újat`Aspose.Pdf.Document`és adjunk hozzá egy oldalt. Ez az oldal később azt a táblázatot fogja tartalmazni, amelyet az Excel-adatokból készítünk.

## 5. lépés: Hozzon létre egy táblázatobjektumot PDF-ben

Térjünk át egy táblázat létrehozására a PDF dokumentumon belül.

```csharp
// Hozzon létre egy táblázat objektumot
Aspose.Pdf.Table table = new Aspose.Pdf.Table();

// Adja hozzá a Table objektumot az oldal bekezdésgyűjteményéhez
page.Paragraphs.Add(table);
```

 Magyarázat: Létrehozunk egy`Aspose.Pdf.Table` objektumot, és adja hozzá az oldal bekezdésgyűjteményéhez, ami biztosítja, hogy a táblázat megjelenjen az oldalon.

## 6. lépés: Állítsa be az oszlopszélességeket és a szegélyeket

A PDF-ben lévő táblázatoknak meghatározott oszlopszélességre van szükségük. Szegélyeket is hozzáadunk a táblázat olvashatóbbá tételéhez.

```csharp
// Állítsa be a táblázat oszlopszélességét
table.ColumnWidths = "40 100 100";

// Állítsa be az alapértelmezett cellaszegélyt
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

 Magyarázat: Beállítjuk a három oszlop szélességét, és minden cellának alapértelmezett szegélyt adunk, amelynek vastagsága:`0.1F`.

## 7. lépés: Importáljon adatokat a DataTable-ből PDF-táblázatba

Most itt az ideje importálni az adatokat a DataTable-ból a PDF-táblázatunkba.

```csharp
// Importáljon adatokat a Table objektumba a DataTable-ból
table.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 Magyarázat: A`ImportDataTable`módszer az összes adatot átviszi a`DataTable` a PDF táblázathoz. Ez feltölti a táblázatot az Excel-lap adataival.

## 8. lépés: alakítsa ki a fejlécesor stílusát

A háttérszín, a betűtípus és az igazítás módosításával alakítsuk ki a táblázat fejlécsorának stílusát.

```csharp
// Vegye ki az első sort a táblázatból
Aspose.Pdf.Row headerRow = table.Rows[0];

// Állítsa be a fejlécsor stílusát
foreach (Aspose.Pdf.Cell cell in headerRow.Cells)
{
    cell.BackgroundColor = Color.Blue;
    cell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    cell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    cell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}
```

Magyarázat: Az első sor (fejléc) összes celláját végigpörgetjük, háttérszínüket kékre, a szöveg színét sárgára állítjuk, és a szöveget középre igazítjuk.

## 9. lépés: alakítsa ki a fennmaradó sorok stílusát

A fejléc és a többi sor közötti különbségtétel érdekében adjunk hozzá más stílust a fennmaradó sorokhoz.

```csharp
for (int i = 1; i <= dataTable.Rows.Count; i++)
{
    foreach (Aspose.Pdf.Cell cell in table.Rows[i].Cells)
    {
        cell.BackgroundColor = Color.Gray;
        cell.DefaultCellTextState.ForegroundColor = Color.White;
    }
}
```

Magyarázat: A fejléc kivételével minden sorhoz szürke hátteret és fehér szövegszínt állítottunk be.

## 10. lépés: Mentse el a PDF-dokumentumot

Végül mentse el a PDF dokumentumot a táblázattal együtt.

```csharp
// Mentse el a PDF-et
pdfDocument.Save(dataDir + "Exceldata_toPdf_table.pdf");
```

Magyarázat: A PDF-fájlt a megadott könyvtárba mentjük. Voilà! Az Excel-adatok most egy gyönyörűen formázott PDF-táblázatban vannak.

## Következtetés

És megvan! Néhány lépésben exportálta az adatokat egy Excel-munkalapról egy PDF-ben található táblázatba az Aspose.PDF for .NET használatával. A folyamat lebontásával és menet közbeni stílusával testreszabhatja a kimenetet, és gondoskodhat arról, hogy az adatok tisztán és professzionálisan nézzenek ki. Így amikor legközelebb valaki átad Önnek egy Excel-fájlt, és PDF-jelentést kér, pontosan tudja, mit kell tennie.

## GYIK

### Testreszabhatom a táblázatot jobban?
Teljesen! Módosíthatja a színeket, a betűtípusokat, az igazítást, sőt szegélyeket is hozzáadhat bizonyos cellákhoz.

### Ingyenes az Aspose.PDF for .NET?
 Ingyenes próbaverziót kínál, de hosszabb használathoz licencre lesz szüksége. Megteheti[vásárold meg itt](https://purchase.aspose.com/buy).

### Csak meghatározott sorokat és oszlopokat exportálhatok?
 Igen, módosíthatja a paramétereket a`ExportDataTable` módszer adott tartományok exportálására.

### Ez működik nagy Excel fájlokkal?
Igen, az Aspose.Cells a nagy Excel-fájlok hatékony kezelésére készült.

### Hogyan tudok több oldalt hozzáadni a PDF-hez?
 Használhatod`pdfDocument.Pages.Add()` hogy annyi oldalt adjon hozzá, amennyire szüksége van.