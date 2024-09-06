---
title: Szöveg elhelyezése a kép körül a PDF-fájlban
linktitle: Szöveg elhelyezése a kép körül a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan helyezhet el szöveget egy kép körül PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 260
url: /hu/net/programming-with-text/placing-text-around-image/
---
Ebben az oktatóanyagban elmagyarázzuk, hogyan helyezhet el szöveget egy kép körül a PDF-fájlban az Aspose.PDF könyvtár segítségével a .NET-hez. Lépésről lépésre végigvesszük a táblázat létrehozásának, kép hozzáadásának és a kép körüli szöveg elhelyezésének folyamatát a mellékelt C# forráskód segítségével.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Az Aspose.PDF for .NET könyvtár telepítve van.
- A C# programozás alapvető ismerete.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

 Először is be kell állítania annak a könyvtárnak az elérési útját, ahová a létrehozott PDF-fájlt menteni szeretné. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változót a kívánt könyvtár elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és oldalt

 Ezután létrehozzuk a`Document` objektumot, és adjon hozzá egy oldalt a segítségével`Pages.Add()` módszer.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3. lépés: Hozzon létre egy táblázatot

 A táblázat segítségével készítünk`Table` osztályt, és adja hozzá az oldal bekezdésgyűjteményéhez.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## 4. lépés: Állítsa be a táblázat oszlopszélességeit és margóit

 Beállítjuk a táblázat oszlopszélességeit és létrehozzuk a`MarginInfo` objektumot a margók beállításához.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## 5. lépés: Adjon hozzá egy képet a táblázathoz

 Létrehozunk egy`Image` objektumot, adja meg a képfájl elérési útját, és állítsa be a kép rögzített magasságát és szélességét. Ezután hozzáadjuk a képet a táblázatcella bekezdésgyűjteményéhez.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## 6. lépés: Szöveg hozzáadása a képhez

 Létrehozunk HTML-formátumú szöveget tartalmazó karakterlánc-változókat, és létrehozunk egy`HtmlFragment`objektum. Ezután hozzáadjuk a HTML szöveget a képet tartalmazó táblázatcellához.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## 7. lépés: További szöveg hozzáadása

 Létrehozunk egy másikat`HtmlFragment` további HTML-formátumú szöveget tartalmazó objektumot, és adja hozzá egy külön táblázatcellához.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## 8. lépés: Mentse el a PDF-dokumentumot

Végül elmentjük a PDF dokumentumot a megadott kimeneti fájlba.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### Minta forráskód a kép körüli szöveg elhelyezéséhez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentumobjektum példányosítása
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Hozzon létre egy oldalt a PDF-ben
Aspose.Pdf.Page page = doc.Pages.Add();
// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
page.Paragraphs.Add(table1);
// Állítsa be a táblázat oszlopszélességeivel
table1.ColumnWidths = "120 270";
// Hozzon létre MarginInfo objektumot, és állítsa be a bal, alsó, jobb és felső margókat
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Állítsa be az alapértelmezett cellakitöltést a MarginInfo objektumra
table1.DefaultCellPadding = margin;
// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row row1 = table1.Rows.Add();
// Hozzon létre egy képobjektumot
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// Adja meg a képfájl elérési útját
logo.File = dataDir + "aspose-logo.jpg";
// Adja meg a kép rögzített magasságát
logo.FixHeight = 120;
// Adja meg a kép fix szélességét
logo.FixWidth = 110;
row1.Cells.Add();
// Adja hozzá a képet a táblázatcella bekezdésgyűjteményéhez
row1.Cells[0].Paragraphs.Add(logo);
// Hozzon létre karakterlánc-változókat html címkéket tartalmazó szöveggel
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//Hozzon létre egy szöveges objektumot, amelyet a kép jobb oldalán kíván hozzáadni
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// Adja hozzá a HTML szöveget tartalmazó szöveges bekezdéseket a táblázat cellájához
row1.Cells[1].Paragraphs.Add(TitleText);
// Állítsa be a sor tartalmának függőleges igazítását Top értékre
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// Állítsa be a második sor sortartományának értékét 2-re
SecondRow.Cells[0].ColSpan = 2;
// Állítsa be a második sor függőleges igazítását Top értékre
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// Adja hozzá a HTML szöveget tartalmazó szöveges bekezdéseket a táblázat cellájához
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// Mentse el a Pdf fájlt
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan helyezhet el szöveget egy kép körül egy PDF-dokumentumban az Aspose.PDF könyvtár segítségével a .NET-hez. A lépésenkénti útmutató követésével és a mellékelt C# kód végrehajtásával táblázatot hozhat létre, képet adhat hozzá, és szöveget helyezhet el a kép körül egy PDF dokumentumban.

### GYIK

#### K: Mi a célja a „Szöveg elhelyezése a kép körül PDF-fájlban” oktatóanyagnak?

V: A „Szöveg elhelyezése a kép körül PDF-fájlban” oktatóanyag bemutatja, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez, hogy szöveget helyezzen el egy kép körül egy PDF-dokumentumban. Az oktatóanyag lépésenkénti útmutatót és C#-forráskódot tartalmaz, amely segít táblázat létrehozásában, kép hozzáadása és szöveg elhelyezése a kép körül.

#### K: Miért szeretnék szöveget elhelyezni egy kép körül egy PDF-dokumentumban?

V: Szöveg elhelyezése egy kép körül javítja a PDF-dokumentumok vizuális megjelenítését, így vonzóbbá és informatívabbá válik. Ezt a technikát gyakran használják dokumentumokban, brosúrákban, jelentésekben és egyéb anyagokban, ahol a képeket és a szöveget esztétikusan kívánják kombinálni.

#### K: Hogyan állíthatom be a dokumentumkönyvtárat?

V: A dokumentumkönyvtár beállításához:

1.  Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változó annak a könyvtárnak az elérési útjával, ahová a generált PDF fájlt menteni szeretné.

#### K: Hogyan hozhatok létre táblázatot és adhatok hozzá képet?

 V: Az oktatóanyag végigvezeti Önt a táblázat segítségével a`Table` osztályt és képet adunk a táblázathoz a segítségével`Image` osztály. Meg kell adnia a képfájl elérési útját, magasságát és szélességét, mielőtt hozzáadná egy táblázatcellához.

#### K: Hogyan helyezhetek el szöveget a kép körül?

 V: A szöveg kép körüli elhelyezéséhez HTML-formátumú szöveget kell létrehoznia a`HtmlFragment` osztály. Ez a szöveg címet és törzsszöveget is tartalmaz. Ezután hozzáadja ezt a HTML-szöveget egy táblázatcellához, amely a képcellával szomszédos.

#### K: Testreszabhatom a szöveg és a kép megjelenését?

V: Igen, testreszabhatja a szöveg és a kép megjelenését HTML-címkék és tulajdonságok segítségével. Például beállíthat betűméretet, színt, stílust és igazítást a szöveghez. Ezenkívül beállíthatja a kép méretét és méreteit.

#### K: Hogyan menthetem el a PDF dokumentumot?

 V: Miután hozzáadta a képet és a szöveget a táblázathoz, elmentheti a PDF dokumentumot a`Save` módszere a`Document` osztály. Adja meg a kívánt kimeneti fájl elérési útját argumentumként a`Save` módszer.

#### K: Mi az oktatóanyag várható eredménye?

V: Az oktatóanyag követésével és a mellékelt C# kód végrehajtásával PDF-dokumentumot fog létrehozni, amely bemutatja, hogyan helyezhet el szöveget egy kép körül. A kimeneti dokumentum egy táblázatot tartalmaz egy képpel és szöveggel körülötte.

#### K: Használhatok más képformátumokat a JPG-n kívül?

 V: Igen, használhat különböző, az Aspose.PDF könyvtár által támogatott képformátumokat, például PNG, BMP, GIF stb. Amikor létrehozza a`Image` objektumot, adja meg a kívánt képformátum fájl elérési útját.

#### K: Szükséges érvényes Aspose-licenc ehhez az oktatóanyaghoz?

V: Igen, az oktatóanyag megfelelő működéséhez érvényes Aspose-licenc szükséges. Az Aspose webhelyén vásárolhat teljes licencet vagy szerezhet 30 napos ideiglenes licencet.