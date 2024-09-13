---
title: Render táblázat PDF dokumentumban
linktitle: Render táblázat PDF dokumentumban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan jeleníthet meg táblázatot PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 170
url: /hu/net/programming-with-tables/render-table/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk a táblázatot PDF-dokumentumban az Aspose.PDF for .NET használatával. Elmagyarázzuk a megadott C# forráskódot, és megmutatjuk, hogyan kell megvalósítani.

## 1. lépés: A dokumentum létrehozása
Először létrehozunk egy új PDF dokumentumot:

```csharp
// A dokumentumok könyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy új dokumentumot
Document doc = new Document();
```

## 2. lépés: Az oldalmargók és a tájolás beállítása
Ezután konfiguráljuk az oldalmargókat, és a tájolást fekvő módba állítjuk:

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## 3. lépés: A táblázat és az oszlopok létrehozása
Most hozzunk létre egy táblázatot, és állítsuk be az oszlopszélességeket:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## 4. lépés: Adjon hozzá sorokat és cellákat a táblázathoz
Ezután sorokat és cellákat adunk a táblázathoz egy hurok segítségével:

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## 5. lépés: A táblázat hozzáadása az oldalhoz
Most adjuk hozzá a táblázatot a dokumentum oldalához:

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## 6. lépés: A táblázat megjelenítése új oldalon
Ezután létrehozunk egy új táblázatot, és az "IsInNewPage" tulajdonságot "true"-ra állítjuk, hogy a táblázat egy új oldalon jelenjen meg:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## 7. lépés: Mentse el a PDF-fájlt
Végül elmentjük a PDF dokumentumot:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### Példa a Render Table forráskódjához Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// Hozzáadott oldal.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// Az 1. táblázatot a következő oldalra szeretném hagyni...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## Következtetés
Gratulálok ! Megtanulta, hogyan jeleníthet meg táblázatot PDF-dokumentumban az Aspose.PDF for .NET használatával. Ez a részletes útmutató bemutatja, hogyan hozhat létre dokumentumot, hogyan konfigurálhatja az oldalmargókat és tájolást, hogyan adhat hozzá táblázatot, és hogyan jeleníthet meg egy táblázatot egy új oldalon. Most már alkalmazhatja ezt a tudást saját projektjeihez.

### GYIK a renderelési táblázathoz PDF-dokumentumban

#### K: Hogyan módosíthatom a táblázat megjelenését, például módosíthatom a cellák színét vagy szegélyeket adhatok hozzá?

 V: A táblázat megjelenésének módosításához beállíthatja a táblázat különböző tulajdonságait`Aspose.Pdf.Table` és sejtjei. Például beállíthatja a`BackgroundColor` a cellák azon tulajdonsága, hogy megváltoztatják a háttérszínüket. Azt is beállíthatja a`Border` a táblázat vagy az egyes cellák tulajdonsága szegélyek hozzáadásához. Ezenkívül személyre szabhatja a betűtípust, a szöveg színét és a táblázat tartalmának igazítását a módosításával`TextState` a`TextFragment` a cellákhoz hozzáadott objektumok.

#### K: Hozzáadhatok fejlécet vagy láblécet a táblázathoz?

V: Igen, fejlécet vagy láblécet adhat hozzá a táblázathoz, ha további sorokat hoz létre a táblázat elején vagy végén, és beállítja a megfelelő tartalmat a cellákban. A fejléceket vagy lábléceket a táblázat többi részétől függetlenül testreszabhatja, ha különböző stílusokat vagy tartalmat ad hozzá ezekhez a konkrét sorokhoz.

#### K: Hogyan szabályozhatom a táblázat pozícióját az oldalon?

V: A táblázat pozíciójának szabályozásához az oldalon beállíthatja a`MarginInfo` a`PageInfo` objektum. A`MarginInfo` lehetővé teszi az oldal bal, jobb, felső és alsó margójának beállítását, ami befolyásolja a táblázat számára rendelkezésre álló helyet. Használhatja a`PositioningType` tulajdona a`Aspose.Pdf.Table` az oldal tartalmi területén belüli vízszintes és függőleges igazításának szabályozására.

#### K: Exportálhatom a táblázatot különböző fájlformátumokba, például Excel vagy CSV formátumba?

V: Az Aspose.PDF for .NET elsősorban PDF-dokumentumokkal való munkavégzéshez készült. Bár képes a PDF-dokumentumot képként vagy XPS-ként exportálni, közvetlenül nem támogatja a táblázatok exportálását olyan formátumokba, mint az Excel vagy a CSV. Ha a táblázat adatait különböző fájlformátumokba szeretné exportálni, előfordulhat, hogy további könyvtárakat vagy módszereket kell használnia a PDF-tartalom kívánt formátumba konvertálásához.

#### K: Hogyan adhatok hiperhivatkozásokat a táblázat celláihoz?

 V: Ha hiperhivatkozásokat szeretne hozzáadni a táblázat celláihoz, használja a`Aspose.Pdf.WebHyperlink` osztályban hozzon létre egy hiperhivatkozást, majd adja hozzá horgonyként a`TextFragment` sejt belsejében. Ez lehetővé teszi, hogy egy URL-címet vagy hivatkozási célt egy adott szöveghez vagy tartalomhoz társítson a cellán belül, és kattintható hiperhivatkozásokat hozzon létre.