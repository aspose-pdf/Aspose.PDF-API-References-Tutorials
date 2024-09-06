---
title: Táblázat a fejléc lábléc szakaszában
linktitle: Táblázat a fejléc lábléc szakaszában
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá táblázatot egy PDF-dokumentum fejléc/lábléc részéhez az Aspose.PDF for .NET segítségével.
type: docs
weight: 170
url: /hu/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá táblázatot egy PDF-dokumentum fejlécéhez vagy láblécéhez az Aspose.PDF for .NET használatával. A mellékelt C# forráskód megmutatja, hogyan hozhat létre üres PDF dokumentumot, hogyan adhat hozzá oldalt, konfigurálhatja a fejlécet, hozhat létre táblázatot, hogyan adhat hozzá sorokat és cellákat a táblázathoz, és végül hogyan mentheti el a PDF dokumentumot.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A PDF-dokumentum és az oldal létrehozása

 Az első lépés a példány létrehozása a`Document` osztályt, és adjunk hozzá egy oldalt a dokumentumhoz. Íme, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Példányosítson egy dokumentum objektumot
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a PDF dokumentumban
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Feltétlenül cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet annak a könyvtárnak az elérési útjára, ahová a PDF-dokumentumot menteni szeretné.

## 3. lépés: A fejléc szakasz konfigurálása

 Most a PDF-dokumentum fejlécrészét konfiguráljuk a példány létrehozásával`HeaderFooter` osztály. Íme, hogyan:

```csharp
// Hozzon létre egy fejléc részt a PDF-fájlhoz
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Határozza meg az oldal fejléc részét
page. Header = header;

// Állítsa be a fejlécrész felső margóját
header. Margin. Top = 20;
```

## 4. lépés: A táblázat létrehozása

 Most egy táblázatot fogunk létrehozni a`Table` osztályt, és adja hozzá a címsor szakasz bekezdésgyűjteményéhez. Íme, hogyan:

```csharp
// Példányosítson egy táblázat objektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adja hozzá a táblázatot a fejléc szakasz bekezdésgyűjteményéhez
header.Paragraphs.Add(tab1);

// Határozza meg a táblázat oszlopainak szélességét!
tab1.ColumnWidths = "60,300";
```

A fenti kód egy táblázatot hoz létre két megadott szélességű oszloppal.

## 5. lépés: Adjon hozzá sorokat és cellákat a táblázathoz

 Most sorokat és cellákat adunk a táblázathoz a`Row` osztály és a`Cell` osztály. Íme, hogyan:

```csharp
// Hozzon létre egy sort a táblázatban, és adjon hozzá cellákat
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Az első sor első cellájának egyesítése
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Hozzon létre egy másik sort a táblázatban, és adjon hozzá egy cellát egy képpel
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## 6. lépés: A PDF-dokumentum mentése

Miután a táblázatot hozzáadtuk a fejléc részhez, elmenthetjük a PDF dokumentumot. Íme, hogyan:

```csharp
// Mentse el a PDF fájlt
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Feltétlenül cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet annak a könyvtárnak az elérési útjára, ahová a PDF-dokumentumot menteni szeretné.

### Minta forráskód a Table In Header Footer Section-hez az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányosítsa a dokumentumpéldányt üres konstruktor meghívásával
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a pdf dokumentumban
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

//Hozzon létre egy fejléc részt a PDF-fájlban
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Állítsa be a PDF-fájl páratlan fejlécét
page.Header = header;

// Állítsa be a fejlécrész felső margóját
header.Margin.Top = 20;

// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
header.Paragraphs.Add(tab1);

// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Állítsa be a táblázat oszlopszélességeivel
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Az első sor sortartományának értékét állítsa 2-re
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Állítsa be a 2. sor háttérszínét
row2.BackgroundColor = Color.White;

// Adja hozzá a képet tartalmazó cellát
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Állítsa a kép szélességét 60-ra
img.FixWidth = 60;

// Adja hozzá a képet a táblázat cellájához
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Állítsa be a szöveg függőleges igazítását középre igazítottnak
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Mentse el a Pdf fájlt
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat hozzá táblázatot egy PDF-dokumentum fejléc- vagy láblécrészéhez az Aspose.PDF for .NET használatával. Mostantól személyre szabhatja fejléceit és lábléceit táblázatok hozzáadásával, amelyek további információkat jelenítenek meg PDF-dokumentumaiban.

### GYIK a fejléc lábléc szakaszában található táblázathoz

#### K: Mi a célja egy táblázat hozzáadásának a PDF-dokumentum fejlécéhez vagy láblécéhez?

V: Ha egy táblázatot hozzáad egy PDF-dokumentum fejlécéhez vagy láblécrészéhez, akkor strukturált és rendezett információkat jeleníthet meg, például címeket, feliratokat, logókat vagy bármilyen más tartalmat, amelyet konzisztensen szeretne megjeleníteni a dokumentum minden oldalán.

#### K: A megadott C#-forráskód hogyan teszi lehetővé egy táblázat hozzáadását a PDF-dokumentum fejléc- vagy láblécrészéhez?

V: A kód bemutatja az üres PDF-dokumentum létrehozásának, egy oldal hozzáadásának, a fejlécszakasz konfigurálásának, a sorokat és cellákat tartalmazó táblázat létrehozásának és végül a PDF-dokumentum mentésének folyamatát. Az eredmény egy táblázat, amely a PDF-dokumentum fejléc részében jelenik meg.

#### K: Testreszabhatom a táblázatcellák megjelenését, például a szegélyeket, a háttérszínt és a szövegstílust?

V: Igen, testreszabhatja a táblázatcellák megjelenését olyan tulajdonságok beállításával, mint a cellaszegély, a háttérszín, a szövegstílus, a betűtípus, a betűméret és egyebek.

#### K: Hogyan kerül a táblázat a PDF-dokumentum fejlécrészéhez?

V: A kód hozzáadja a táblázatot a fejléc szakasz bekezdésgyűjteményéhez, ami biztosítja, hogy a táblázat minden oldal fejlécében megjelenjen.

#### K: Hozzáadhatok további sorokat és cellákat a táblázathoz, ha szükséges?

 V: Természetesen további sorokat és cellákat is hozzáadhat a táblázathoz a`Rows.Add()` és`Cells.Add()` mód. Ez lehetővé teszi a táblázat tartalmának tetszőleges szerkezetét.

#### K: Beállítható a táblázat oszlopainak szélessége?
 V: Igen, beállíthatja a táblázat oszlopainak szélességét a`ColumnWidths` ingatlan. Ez lehetővé teszi a táblázat elrendezésének szabályozását.

#### K: Hogyan húzhatom át a cellákat több oszlopra vagy sorra a táblázaton belül?
 V: Ha a cellákat több oszlopra szeretné átívelni, használja a`ColSpan` megfelelő cella tulajdonsága. Hasonlóképpen használhatja a`RowSpan` tulajdonság a cellák több sorban való áthidalására.

#### K: Mi történik, ha a PDF-dokumentum fejlécéhez és láblécéhez is hozzá akarok adni egy táblázatot?

 V: Hasonló megközelítést követhet a fejléc és a lábléc részeknél is. Egyszerűen hozzon létre a`HeaderFooter` példányt a lábléchez, konfigurálja azt, és adja hozzá a táblázatot a bekezdésgyűjteményéhez.

#### K: Használhatok képeket a táblázat celláiban, és hogyan érhető el ez?

 V: Igen, képeket adhat hozzá a táblázat celláihoz. A kódpélda bemutatja egy kép hozzáadását egy cellához egy`Image` objektumot, állítsa be a fájl elérési útját és méreteit, majd adja hozzá egy cella bekezdéseihez.

#### K: Hogyan biztosíthatom, hogy a táblázat következetesen jelenjen meg a PDF-dokumentum összes oldalán?

 V: Amikor hozzáadja a táblázatot a fejléc- vagy láblécrészhez a`HeaderFooter` Például az Aspose.PDF biztosítja, hogy a táblázat következetesen jelenjen meg minden oldalon, egységes elrendezést biztosítva.