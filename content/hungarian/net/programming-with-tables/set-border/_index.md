---
title: Szegély beállítása PDF-ben a táblázathoz
linktitle: Szegély beállítása PDF-ben a táblázathoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthat be szegélyt PDF-ben a táblázathoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 200
url: /hu/net/programming-with-tables/set-border/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan állítson be szegélyt egy PDF-dokumentum táblázatában az Aspose.PDF for .NET használatával. Elmagyarázzuk a megadott C# forráskódot, és megmutatjuk, hogyan kell megvalósítani.

## 1. lépés: A dokumentum objektum példányosítása
Először példányosítunk egy dokumentum objektumot:

```csharp
Document doc = new Document();
```

## 2. lépés: Oldal hozzáadása a PDF dokumentumhoz
Ezután hozzáadunk egy oldalt a PDF-dokumentumhoz:

```csharp
Page page = doc.Pages.Add();
```

## 3. lépés: A BorderInfo objektum létrehozása
Most létrehozunk egy BorderInfo objektumot a táblázat szegélyének meghatározásához:

```csharp
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
```

## 4. lépés: A felső és alsó szegélyek megadása
Meghatározzuk, hogy a felső és az alsó szegély dupla lesz:

```csharp
border.Top.IsDoubled = true;
border.Bottom.IsDoubled = true;
```

## 5. lépés: A Table objektum példányosítása
Most példányosítsunk egy Table objektumot:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 6. lépés: Oszlopszélességek megadása
Megadjuk a táblázat oszlopainak szélességét:

```csharp
table. ColumnWidths = "100";
```

## 7. lépés: A sorobjektum létrehozása
Létrehozunk egy sor objektumot:

```csharp
Aspose.Pdf.Row row = table.Rows.Add();
```

## 8. lépés: Adjon hozzá egy cellát a sorhoz
Ezután hozzáadunk egy cellát a sorhoz:

```csharp
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
```

## 9. lépés: A cellaszegély beállítása
Meghatározzuk a cella határát (kettős szegély):

```csharp
cell. Border = border;
```

## 10. lépés: A táblázat hozzáadása az oldalhoz
Most adjuk hozzá a táblázatot a dokumentum oldalához:

```csharp
page.Paragraphs.Add(table);
```

## 11. lépés: Mentse el a PDF dokumentumot
Végül elmentjük a PDF dokumentumot:

```csharp
dataDir = dataDir + "TableBorderTest_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

### Példa a Set Border for Aspose.PDF for .NET forráskódjához

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum objektum példányosítása
Document doc = new Document();
// Oldal hozzáadása a PDF dokumentumhoz
Page page = doc.Pages.Add();
// Hozzon létre BorderInfo objektumot
Aspose.Pdf.BorderInfo border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All);
//Adja meg, hogy a felső szegély dupla legyen
border.Top.IsDoubled = true;
// Adja meg, hogy az alsó szegély dupla legyen
border.Bottom.IsDoubled = true;
// Table objektum példányosítása
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Adja meg az oszlopok szélességére vonatkozó információkat
table.ColumnWidths = "100";
// Sor objektum létrehozása
Aspose.Pdf.Row row = table.Rows.Add();
// Adjon hozzá egy táblázatcellát a sor cellagyűjteményéhez
Aspose.Pdf.Cell cell = row.Cells.Add("some text");
// Állítsa be a cellaobjektum szegélyét (dupla szegély)
cell.Border = border;
// Táblázat hozzáadása az oldal bekezdésgyűjteményéhez
page.Paragraphs.Add(table);
dataDir = dataDir + "TableBorderTest_out.pdf";
// Mentse el a PDF dokumentumot
doc.Save(dataDir);

Console.WriteLine("\nBorder setup successfully.\nFile saved at " + dataDir);
```

## Következtetés
Gratulálok ! Most megtanulta, hogyan állíthat be szegélyt egy PDF-dokumentum táblázatában az Aspose.PDF for .NET használatával. Ez a lépésenkénti útmutató bemutatja, hogyan hozhat létre dokumentumot, hogyan adhat hozzá oldalt, konfigurálhatja a táblázat szegélyét és mentheti a PDF-dokumentumot. Most már alkalmazhatja ezt a tudást saját projektjeihez.

### GYIK

#### K: Beállíthatok különböző szegélystílusokat (pl. szaggatott vagy pontozott) a táblázat felső és alsó szegélyéhez?

 V: Igen, különböző szegélystílusokat állíthat be a táblázat felső és alsó szegélyéhez, ha módosítja a`border.Top.Style` és`border.Bottom.Style`tulajdonságokat a megadott C# forráskódban. Az Aspose.PDF for .NET lehetővé teszi, hogy különféle szegélystílusok közül válasszon, beleértve a tömör, szaggatott, pontozott, dupla és egyebeket.

#### K: Hogyan állíthatom be a táblázat szegélyének színét?

 V: Beállíthatja a táblázat szegélyének színét a`border.Color` tulajdonság a C# forráskódban. Egyszerűen adja meg a kívánt színt, mint pl`Aspose.Pdf.Color.Red` vagy bármely más érvényes színábrázolás, a keret színének testreszabásához.

#### K: Lehetséges-e szegélyeket alkalmazni a táblázat egyes celláira különböző beállításokkal (pl. különböző színekkel vagy szegélystílusokkal)?

 V: Igen, szegélyeket alkalmazhat a táblázat egyes celláira, különböző beállításokkal, ha konfigurálja a`cell.Border` tulajdonság minden cellához külön-külön. Ez lehetővé teszi, hogy cellaspecifikus szegélystílusokat és -színeket állítson be az Ön igényei szerint.

#### K: Eltávolíthatom a szegélyt az asztal bizonyos oldalairól (pl. bal és jobb oldali szegély)?

 V: Igen, eltávolíthatja a szegélyt a táblázat bizonyos oldalairól a`border.Left`, `border.Right`, `border.Top` , és`border.Bottom`tulajdonságok a C# forráskódban. Ezeknek a tulajdonságoknak a beállítása`null` eltávolítja a szegélyt a táblázat megfelelő oldalairól.

#### K: Hogyan állíthatom be az asztal szegélyének vastagságát?

 V: Beállíthatja az asztal szegélyének vastagságát a`border.Width` tulajdonság a C# forráskódban. Egyszerűen állítsa be a kívánt szegélyszélességet (pontokban), hogy elérje a kívánt vastagságot.