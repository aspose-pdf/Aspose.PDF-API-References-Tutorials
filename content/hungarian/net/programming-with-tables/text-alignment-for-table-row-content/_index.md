---
title: Szöveg igazítása a táblázat sor tartalmához
linktitle: Szöveg igazítása a táblázat sor tartalmához
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan igazíthatja a sor tartalmát egy PDF-táblázatban az Aspose.PDF for .NET használatával.
type: docs
weight: 210
url: /hu/net/programming-with-tables/text-alignment-for-table-row-content/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan igazítsa el egy sor tartalmát egy PDF-dokumentum táblázatában az Aspose.PDF for .NET használatával. Elmagyarázzuk a megadott C# forráskódot, és megmutatjuk, hogyan kell megvalósítani.

## 1. lépés: A PDF dokumentum létrehozása
Először elkészítjük a PDF dokumentumot:

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 2. lépés: Táblázat inicializálása
Ezután inicializáljuk a táblázatot:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 3. lépés: A táblázat szegélyének színének beállítása
Beállítjuk a táblázat szegélyének színét:

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 4. lépés: A táblázat cellaszegélyének konfigurálása
Beállítjuk a táblázat cellaszegélyét:

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 5. lépés: Ismételje meg a hurkot 10 sor hozzáadásához a táblázathoz
Most egy hurok segítségével 10 sort adunk a táblázathoz:

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## 6. lépés: A függőleges vonaligazítás konfigurálása
Beállítjuk a táblázat sorainak függőleges igazítását:

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## 7. lépés: Tartalom hozzáadása a sorcellákhoz
Tartalmat fogunk hozzáadni a sorcellákhoz:

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## 8. lépés: A táblázat hozzáadása a dokumentum oldalához
Most adjuk hozzá a táblázatot a dokumentum oldalához:

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## 9. lépés: Mentse el a PDF dokumentumot
Végül elmentjük a PDF dokumentumot:

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### Példa forráskódra a táblázat sortartalmának szövegigazítására az Aspose.PDF for .NET használatával

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF dokumentum létrehozása
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Inicializálja a tábla új példányát
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Állítsa be a táblázat szegélyének színét LightGray-re
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// állítsa be a táblázatcellák szegélyét
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// hozzon létre egy hurkot 10 sor hozzáadásához
for (int row_count = 0; row_count < 10; row_count++)
{
	// sor hozzáadása a táblázathoz
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// Táblázatobjektum hozzáadása a bemeneti dokumentum első oldalához
tocPage.Paragraphs.Add(table);
// Mentse el a táblaobjektumot tartalmazó frissített dokumentumot
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## Következtetés
Gratulálok ! Most megtanulta, hogyan igazíthatja egy sor tartalmát egy táblázatban egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ez a lépésenkénti útmutató bemutatja, hogyan hozhat létre dokumentumot, inicializálhat egy táblázatot, hogyan konfigurálhatja a szegélyt és az igazítást, hogyan adhat hozzá tartalmat, és hogyan mentheti el a PDF-dokumentumot. Most már alkalmazhatja ezt a tudást saját projektjeihez.

### GYIK

#### K: Hogyan igazíthatom vízszintesen a táblázatcellák tartalmát?

 V: A táblázatcellák tartalmát vízszintesen igazíthatja a`HorizontalAlign` a sejt tulajdonsága`TextState` objektum. Például a szöveg középre igazításához használja a`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . Azt is beállíthatja`HorizontalAlignment.Left` vagy`HorizontalAlignment.Right` balra és jobbra igazításhoz.

#### K: Alkalmazhatok különböző szegélystílusokat és színeket a táblázat egyes celláira?

 V: Igen, különböző szegélystílusokat és színeket alkalmazhat a táblázat egyes celláira. Egy adott cella szegélyének testreszabásához állítsa be a`cell.Border` ingatlan egy új`BorderInfo`objektum a kívánt beállításokkal, például szegélyoldalak, szélesség és szín.

#### K: Hogyan állíthatom be a táblázat tartalmának függőleges igazítását a cellákon belül?

 V: Beállíthatja a táblázat tartalmának függőleges igazítását a cellákon belül a`VerticalAlignment` a sor tulajdonsága, hogy`VerticalAlignment.Center`, `VerticalAlignment.Top` , vagy`VerticalAlignment.Bottom`. Ez a tulajdonság szabályozza az adott sorban lévő összes cella függőleges igazítását.

#### K: Lehetséges-e dinamikusan további oszlopok vagy sorok hozzáadása a táblázathoz?

 V: Igen, további oszlopokat és sorokat adhat hozzá dinamikusan a táblázathoz a`table.Rows.Add()` módszer új sorok hozzáadásához és a`row.Cells.Add()` módszer új cellák hozzáadásához a sorokhoz. Ezt megteheti hurkon belül, vagy egyedi igényei alapján.

#### K: Hogyan állíthatok be háttérszínt bizonyos cellákhoz vagy az egész táblázathoz?

 V: Adott cellák vagy a teljes táblázat háttérszínének beállításához használja a`BackgroundColor` tulajdona a`Cell` vagy`Table` objektum. Például egy cella háttérszínének beállításához használja a`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.