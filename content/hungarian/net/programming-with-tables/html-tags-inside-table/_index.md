---
title: HTML-címkék a táblázatban PDF-fájlban
linktitle: HTML-címkék a táblázatban PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan használhatja a HTML-címkéket egy táblázatban PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 100
url: /hu/net/programming-with-tables/html-tags-inside-table/
---
Ebben az oktatóanyagban megtanuljuk, hogyan használhatunk HTML-címkéket egy táblázatban egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a forráskódot C# nyelven. Ennek az oktatóanyagnak a végén tudni fogja, hogyan illeszthet be HTML-tartalmat egy PDF-dokumentum táblázatába. Kezdjük!

## 1. lépés: A környezet beállítása
Győződjön meg arról, hogy a C# fejlesztői környezetet az Aspose.PDF for .NET segítségével konfigurálta. Adja hozzá a hivatkozást a könyvtárhoz, és importálja a szükséges névtereket.

## 2. lépés: Táblaadatok létrehozása
Létrehozunk egy DataTable-t, amely egy String típusú "adat" oszlopot tartalmaz. Ezután sorokat adunk hozzá ehhez a DataTable-hoz HTML-tartalom használatával.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## 3. lépés: A dokumentum és a táblázat létrehozása
Létrehozunk egy új PDF dokumentumot, és hozzáadunk egy oldalt ehhez a dokumentumhoz. Ezután inicializáljuk a Table osztály egy példányát, és beállítjuk a tábla tulajdonságait.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## 4. lépés: Adatok importálása a táblázatba
Az adatokat a DataTable-ból importáljuk a táblába az "ImportDataTable" metódussal. Metódusparamétereket adunk meg annak jelzésére, hogy a DataTable melyik sor- és oszloptartományát kell importálni.

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## 5. lépés: A táblázat hozzáadása a dokumentumhoz
A táblázatot hozzáadjuk a dokumentum oldalához.

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## 6. lépés: A dokumentum mentése
A PDF dokumentumot a HTML tartalmat tartalmazó táblázattal mentjük.

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### Példa a HTML-címkék Inside Table forráskódjához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
// Inicializálja a tábla új példányát
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//Állítsa be a táblázat oszlopszélességét
tableProvider.ColumnWidths = "400 50 ";
// Állítsa be a táblázat szegélyének színét LightGray-re
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// Állítsa be a táblázatcellák szegélyét
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan használhatunk HTML-címkéket egy táblázatban egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ezzel a lépésenkénti útmutatóval HTML-tartalmat szúrhat be egy PDF-dokumentum táblázatcelláiba C# használatával.

### GYIK a PDF-fájl táblázatában található HTML-címkékkel kapcsolatban

#### K: Használhatok más HTML címkéket és attribútumokat a táblázat celláiban?

 V: Igen, a táblázatcellákon belül különféle HTML címkéket és attribútumokat használhat, mint pl`<b>`, `<i>`, `<a>`és még sok más. Az Aspose.PDF for .NET a HTML-elemek és -stílusok széles skáláját támogatja, amelyek segítségével formázhatja a táblázatcellákon belüli tartalmat.

#### K: Alkalmazhatok CSS-stílusokat a táblázatcellákon belüli HTML-tartalomra?

V: Igen, alkalmazhat CSS-stílusokat a táblázatcellákon belüli HTML-tartalomra. Az Aspose.PDF for .NET támogatja az alapvető CSS-stílusokat, amelyek alkalmazhatók a HTML-elemekre.

#### K: Lehetséges képeket HTML-tartalommal együtt hozzáadni a táblázat celláihoz?

 V: Igen, képeket és HTML-tartalmat is hozzáadhat a táblázat celláihoz. Használhat HTML-t`<img>` címkék, amelyek különféle forrásokból, például helyi fájlokból vagy URL-ekből származó képeket tartalmazhatnak.

#### K: Hogyan adhatok meg különböző oszlopszélességeket a táblázathoz?

 V: Különböző oszlopszélességeket adhat meg a táblázathoz a`ColumnWidths` az asztal tulajdonsága. A tulajdonság szóközzel elválasztott értékeket tartalmazó karakterláncot vesz fel, ahol minden érték egy oszlop szélességét jelenti pontokban.

#### K: Használhatok beágyazott táblázatokat egy HTML-tartalmú cellán belül?

V: Igen, használhat beágyazott táblázatokat egy HTML-tartalommal rendelkező cellán belül. Létrehozhat különálló táblázatpéldányokat, és hozzáadhatja őket a cellán belüli HTML-tartalom részeként a beágyazási hatás eléréséhez.