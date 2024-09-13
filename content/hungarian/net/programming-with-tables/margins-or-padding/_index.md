---
title: Margók vagy Padding
linktitle: Margók vagy Padding
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthat be margókat vagy kitöltést egy táblázatban az Aspose.PDF for .NET használatával.
type: docs
weight: 140
url: /hu/net/programming-with-tables/margins-or-padding/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük az Aspose.PDF for .NET használatával a táblázat margóinak vagy kitöltésének beállításához. Magyarázatokat és kódrészleteket biztosítunk, amelyek segítenek megérteni és megvalósítani ezt a funkciót a C# forráskódban.

## 1. lépés: A dokumentum és az oldal beállítása
A kezdéshez be kell állítania a dokumentumot és az oldalt a következő kóddal:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányosítsa a Dokumentum objektumot az üres konstruktor meghívásával
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 2. lépés: Táblázat létrehozása
Ezután létrehozunk egy táblázatobjektumot az Aspose.Pdf.Table osztály használatával:

```csharp
// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
page.Paragraphs.Add(tab1);
```

## 3. lépés: Az oszlopszélességek és az alapértelmezett cellaszegély beállítása
A táblázat oszlopszélességének és alapértelmezett cellaszegélyének beállításához használja a következő kódot:

```csharp
// Állítsa be a táblázat oszlopszélességeit
tab1. ColumnWidths = "50 50 50";
// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 4. lépés: A táblázat szegélyének és a cellák kitöltésének beállítása
táblázatszegély és a cella kitöltésének beállításához hozzon létre egy MarginInfo objektumot, és állítsa be a tulajdonságait:

```csharp
// Hozzon létre egy MarginInfo objektumot, és állítsa be a bal, alsó, jobb és felső margókat
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

// Állítsa be az alapértelmezett cellakitöltést a MarginInfo objektumra
tab1. DefaultCellPadding = margin;

// Állítsa be a táblázat szegélyét egy másik testreszabott BorderInfo objektum segítségével
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## 5. lépés: Sorok és cellák hozzáadása
Most adjunk hozzá sorokat és cellákat a táblázathoz. Létrehozunk egy új sort, és cellákat adunk hozzá:

```csharp
//Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## 6. lépés: Szöveg hozzáadása a cellákhoz
Ha szöveget szeretne hozzáadni egy cellához, hozzon létre egy TextFragment objektumot, és adja hozzá a kívánt cellához:

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## 7. lépés: A PDF mentése
A PDF dokumentum mentéséhez használja a következő kódot:

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Mentse el a PDF-et
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### Példa a Margins Or Padding forráskódhoz az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Helyezze el a Dokumentum objektumot az üres konstruktor meghívásával
Document doc = new Document();
Page page = doc.Pages.Add();
// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
page.Paragraphs.Add(tab1);
// Állítsa be a táblázat oszlopszélességeivel
tab1.ColumnWidths = "50 50 50";
// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Állítsa be a táblázat szegélyét egy másik testreszabott BorderInfo objektum segítségével
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Hozzon létre MarginInfo objektumot, és állítsa be a bal, alsó, jobb és felső margókat
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Állítsa be az alapértelmezett cellakitöltést a MarginInfo objektumra
tab1.DefaultCellPadding = margin;
//Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
// Row1.Cells.Add("col3 nagy szöveges karakterlánccal a cellába helyezendő");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// 1. sor.Cellák[2].Bekezdések[0].Rögzített szélesség= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
// Mentse el a PDF-et
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## Következtetés
Gratulálok! Sikeresen megtanulta, hogyan állíthat be margókat vagy kitöltést egy táblázatban az Aspose.PDF for .NET segítségével. Ez a tudás segít a dokumentum formázási képességeinek fejlesztésében, és a táblázatok látványossá tételében.

### GYIK

#### K: Beállíthatok különböző margókat vagy kitöltéseket a táblázat egyes celláihoz?

 V: Igen, az Aspose.PDF for .NET használatával különböző margókat vagy kitöltést állíthat be egy táblázat egyes celláihoz. A megadott példában beállítjuk az alapértelmezett cellakitöltést a teljes táblázathoz a`DefaultCellPadding` ingatlan. Az egyes cellákhoz különböző kitöltés beállításához elérheti a`MarginInfo` minden cellát külön-külön, és módosítsa margóikat.

#### K: Hogyan változtathatom meg a táblázat keretének színét vagy stílusát?

 V: A táblázat szegélyszínének vagy stílusának megváltoztatásához módosíthatja a`Color` és`Width` tulajdonságai a`BorderInfo` objektum. Az adott példában a szegély színét feketére és 1F (egy pont) szélesre állítottuk a segítségével`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`. A színt és a szélességet igény szerint állíthatja be.

#### K: Lehetséges-e fejléceket vagy lábléceket hozzáadni a táblázathoz?

V: Igen, az Aspose.PDF for .NET használatával fejlécet vagy láblécet adhat hozzá a táblázathoz. A fejlécek és láblécek általában különálló sorok, amelyek további információkat, például oszlopcímkéket, táblázatcímeket vagy összefoglaló adatokat tartalmaznak. Létrehozhat további sorokat, eltérő stílust állíthat be, és hozzáadhatja őket a táblázat tartalma fölé vagy alá.

#### K: Hogyan állíthatom be a szöveg igazítását egy táblázatcellán belül?

 V: A táblázatcellán belüli szövegigazítás beállításához használhatja a`HorizontalAlignment` és`VerticalAlignment` tulajdonságai a`TextFragment` objektum. Például a szöveg vízszintes középre igazításához beállíthatja`mytext.HorizontalAlignment = HorizontalAlignment.Center;` . Hasonlóképpen beállíthatja`mytext.VerticalAlignment` a függőleges igazítás szabályozásához.

#### K: Hozzáadhatok képeket a táblázat celláihoz szöveg helyett?

 V: Igen, képeket adhat hozzá a táblázat celláihoz az Aspose.PDF for .NET használatával. Létrehozása helyett a`TextFragment` objektumot, létrehozhat egy`Image` objektumot, töltse be a képfájlt, és adja hozzá a kívánt cellához a segítségével`cell.Paragraphs.Add(image);`módszer. Ez lehetővé teszi képek beszúrását a táblázatba a szöveges tartalom mellé.