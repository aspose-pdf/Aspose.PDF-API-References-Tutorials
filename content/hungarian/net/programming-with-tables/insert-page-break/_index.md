---
title: Oldaltörés beszúrása PDF fájlba
linktitle: Oldaltörés beszúrása PDF fájlba
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan szúrhat be oldaltörést PDF-fájlba az Aspose.PDF for .NET segítségével.
type: docs
weight: 110
url: /hu/net/programming-with-tables/insert-page-break/
---
Ebben az oktatóanyagban megtanuljuk, hogyan lehet oldaltörést beszúrni PDF-fájlba az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a forráskódot C# nyelven. Ennek az oktatóanyagnak a végén tudni fogja, hogyan kell oldaltörést hozzáadni egy PDF-dokumentum táblázatához bizonyos számú sor után. Kezdjük!

## 1. lépés: A környezet beállítása
Győződjön meg arról, hogy a C# fejlesztői környezetet az Aspose.PDF for .NET segítségével konfigurálta. Adja hozzá a hivatkozást a könyvtárhoz, és importálja a szükséges névtereket.

## 2. lépés: A dokumentum és a táblázat létrehozása
Létrehozunk egy új dokumentumpéldányt, és hozzáadunk egy oldalt ehhez a dokumentumhoz. Ezután létrehozunk egy táblázatpéldányt, amely a táblázatunkat reprezentálja a PDF dokumentumban. Meghatározzuk a táblázat szegélystílusait is.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## 3. lépés: Adjon hozzá sorokat a táblázathoz
Egy ciklus segítségével 200 sort adunk a tömbhöz. Minden sorhoz létrehozunk egy Sor példányt, és hozzáadunk két cellát szöveges tartalommal.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // 10 sor hozzáadásakor új oldaltörést szúrunk be
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## 4. lépés: A táblázat hozzáadása a dokumentumhoz
A táblázatot hozzáadjuk a dokumentumoldal bekezdésgyűjteményéhez.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 5. lépés: Mentse el a dokumentumot
A PDF dokumentumot az oldaltörés beillesztésével mentjük.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### Példa forráskódra az Oldaltörés beszúrása az Aspose.PDF segítségével .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányos dokumentum példány
Document doc = new Document();
// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
doc.Pages.Add();
// Táblapéldány létrehozása
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// Állítsa be a táblázat keretének stílusát
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Állítsa be az alapértelmezett szegélystílust a szegélyszínnel rendelkező táblázathoz pirosra
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// Adja meg a táblázat oszlopainak szélességét
tab.ColumnWidths = "100 100";
// Hozzon létre egy hurkot 200 sor hozzáadásához a táblázathoz
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// 10 sor hozzáadása után új sort jelenít meg az új oldalon
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// Táblázat hozzáadása a PDF-fájl bekezdésgyűjteményéhez
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// Mentse el a PDF dokumentumot
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet oldaltörést beszúrni egy PDF-dokumentumba az Aspose.PDF for .NET használatával. Ezzel a lépésenkénti útmutatóval oldaltörést adhat hozzá egy táblázat bizonyos számú sora után egy PDF dokumentumban C# használatával.

### GYIK az oldaltörés beszúrásához PDF-fájlba

#### K: Hogyan változtathatom meg az oldaltörés után létrehozott új oldalak oldalméretét?

 V: Az oldaltörés után létrehozott új oldalak oldalméretének megváltoztatásához beállíthatja a`PageSize` tulajdona a`Page` objektum. Például a következő kóddal beállíthatja az oldalméretet A4-re:

```csharp
// Állítsa az oldalméretet A4-re
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### K: Szabályozhatom az új oldalak margóit az oldaltörés után?

 V: Igen, az oldaltörés után szabályozhatja az új oldalak margóit. Használja a`Margin` tulajdona a`Page` objektumot az oldalmargók beállításához. Ha például az összes margót 10 pontra szeretné beállítani, használja a következő kódot:

```csharp
// Állítsa be az összes margót 10 pontra
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### K: Lehetséges-e fejléceket és lábléceket hozzáadni az új oldalakhoz az oldaltörés után?

 V: Igen, az oldaltörés után fejléceket és lábléceket adhat hozzá az új oldalakhoz. Használja a`Page.Header` és`Page.Footer` tulajdonságokkal, amelyekkel tartalmat adhat hozzá az oldal fejlécéhez és láblécéhez. Például:

```csharp
// Adjon hozzá fejlécet az új oldalakhoz
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// Adjon hozzá láblécet az új oldalakhoz
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### K: Szúrhatok-e be oldaltöréseket bizonyos helyekre, kivéve bizonyos számú sor után?

 V: Igen, oldaltöréseket beszúrhat bizonyos helyekre, kivéve bizonyos számú sor után. Beállíthatja a`IsInNewPage` egy sor tulajdonsága ahhoz`true` hogy a táblázat az adott sor után új oldalt kezdjen.

#### K: Hogyan állíthatom be az oldaltörés viselkedését a tartalom magassága alapján?

 V: Használhatja a`IsBroken` A táblázat tulajdonsága az oldalak közötti automatikus sortörés engedélyezéséhez vagy letiltásához. Amikor be van állítva`true`, lehetővé teszi, hogy a sorok a tartalom magassága alapján törjenek oldalakra.