---
title: Stílusú táblázatelem
linktitle: Stílusú táblázatelem
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre és stílusozhat táblázatelemeket az Aspose.PDF for .NET-ben a lépésenkénti utasítások, az egyéni stílus és a PDF/UA megfelelőség segítségével.
type: docs
weight: 170
url: /hu/net/programming-with-tagged-pdf/style-table-element/
---
## Bevezetés

Ebben a cikkben bemutatjuk, hogyan hozhat létre és stílusozhat táblázatelemeket az Aspose.PDF for .NET használatával. Megtanulja, hogyan strukturálhat táblázatot, hogyan alkalmazhat egyéni stílusokat, és ellenőrizheti a dokumentum PDF/UA megfelelőségét. Az oktatóanyag végére könnyedén készíthet professzionális megjelenésű táblázatokat PDF-fájljaiban!

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, meg kell győződnie a következőkről:

1. Visual Studio vagy egy hasonló IDE telepítve a gépre.
2. .NET Framework vagy .NET Core SDK az alkalmazás futtatásához.
3.  Aspose.PDF for .NET könyvtár letöltve és hivatkozva a projektben. A legújabb verziót letöltheti innen[itt](https://releases.aspose.com/pdf/net/).
4.  Érvényes Aspose engedély vagy a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) a könyvtár teljes funkcióinak feloldásához.

## Csomagok importálása

A kezdéshez importálja a szükséges névtereket a projektbe:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ezek a névterek az alapvető PDF-műveleteket, a címkézett tartalmat, a táblázatokat és a szövegformázást fedik le.

Most bontsuk le az Aspose.PDF-ben lévő táblázat létrehozásának és stílusának elkészítésének folyamatát. Részletesen végigmegyünk az egyes szakaszokon, hogy nyomon tudja követni.

## 1. lépés: Hozzon létre egy új PDF-dokumentumot, és állítsa be a címkézett tartalmat

Ebben az első lépésben létrehozunk egy üres PDF-dokumentumot, és beállítjuk a címkézett tartalmát.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Hozzon létre egy új PDF dokumentumot
Document document = new Document();

// Címkézett tartalom beállítása
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 Kezdjük egy új létrehozásával`Document` objektum, amely a PDF-ünket reprezentálja. A`TaggedContent`objektum a dokumentum szerkezetének kezelésére szolgál, biztosítva az akadálymentesítési szabványoknak való megfelelést. A megfelelő címkézés érdekében beállítjuk a dokumentum címét és nyelvét.

## 2. lépés: Határozza meg a gyökérelemet

Ezután létrehozzuk a gyökérstruktúra elemet, amely a PDF-ben található összes tartalom tárolójaként működik.

```csharp
// Szerezd meg a gyökérstruktúra elemet
StructureElement rootElement = taggedContent.RootElement;
```

 A`RootElement` alapkonténerként szolgál minden strukturált elemhez, beleértve az asztalunkat is. Segít fenntartani a dokumentum szerkezeti hierarchiáját, ami mind a szervezés, mind a hozzáférhetőség szempontjából fontos.

## 3. lépés: A táblázatelem létrehozása és stílusa

 Most, hogy a gyökérelem be van állítva, létrehozzuk a`TableElement` és alkalmazzon olyan stílusokat, mint a háttérszín, a szegélyek és az igazítás.

```csharp
// Táblázatstruktúra elem létrehozása
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// Stílusozd az asztalt
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 Létrehozunk a`TableElement` , amely meghatározza a táblázat szerkezetünket. A`BackgroundColor`, `Border` , és`Alignment` A tulajdonságok lehetővé teszik a táblázat megjelenésének testreszabását. A`Broken` tulajdonság biztosítja, hogy ha a táblázat több oldalra tör, függőlegesen törjön.

## 4. lépés: Állítsa be a táblázat méreteit és cellastílusait

Ebben a lépésben meghatározzuk az oszlopok számát, a cellák kitöltését és a táblázat egyéb fontos tulajdonságait.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 Megadjuk az oszlopszélességeket, hogy a táblázat minden oszlopa egyenletesen legyen elhelyezve. A`DefaultCellBorder`, `DefaultCellPadding` , és`DefaultCellTextState` meghatározza a cellák alapértelmezett stílusait, beleértve a szegélyeket, a kitöltést, a szöveg színét és a betűméretet.

## 5. lépés: Ismétlődő sorok és egyéni stílusok hozzáadása

Stílusokat is meghatározhatunk ismétlődő sorokhoz és más speciális táblázatelemekhez, például fejlécekhez és láblécekhez.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 A`RepeatingRowsCount` biztosítja, hogy az első három sor megismétlődik, ha a táblázat több oldalt ölel fel. Beállítottuk a`RepeatingRowsStyle` hogy egyéni háttérszínt alkalmazzon ezekre a sorokra.

## 6. lépés: Adja hozzá az asztalfejet, a testet és a lábfejet

Most hozzuk létre a táblázat fejlécét, törzsét és láblécét, és töltsük fel tartalommal.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// Hozzon létre fejlécsort
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// Töltse fel a táblázat törzsét
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 Az asztal három részre oszlik: fejre, testre és lábra. Először a fejlécsort hozzuk létre a segítségével`TableTHElement`és adja hozzá az oszlopfejléceket. Ezután feltöltjük a tábla törzsét a következővel:`TableTDElement`, minden cellát kitölt egy címkével, amely tartalmazza a pozícióját.

## 7. lépés: Mentse el a dokumentumot

Végül elmentjük a PDF dokumentumot a megadott könyvtárba.

```csharp
// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "StyleTableElement.pdf");
```

Ez a lépés a PDF-fájl stílusos táblázattal való mentésével zárja le a dokumentum létrehozási folyamatát.

## 8. lépés: Érvényesítse a PDF/UA megfelelőséget

A dokumentum mentése után elengedhetetlen annak biztosítása, hogy megfeleljen a PDF/UA (Universal Accessibility) szabványoknak.

```csharp
// Ellenőrizze a PDF/UA megfelelőséget
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

Itt újratöltjük a dokumentumot, és ellenőrizzük a PDF/UA szabványok szerint. A megfelelőség biztosítja, hogy PDF-je megfeleljen a kisegítő lehetőségek követelményeinek, így a felhasználók széles köre számára alkalmas.

## Következtetés

Az Aspose.PDF for .NET segítségével a táblázatok létrehozása és formázása a PDF-dokumentumokban egyszerű és intuitív. Az oktatóanyagban ismertetett lépések követésével testreszabott stílusú táblázatokat hozhat létre, és biztosíthatja, hogy PDF-fájljai megfeleljenek a kisegítő lehetőségek szabványainak. Akár jelentéseket, akár strukturált dokumentumokat hoz létre, a táblázatok hatékony eszközt jelentenek az adatok egyértelmű bemutatására.

## GYIK

### Hozzáadhatok képeket a táblázat celláihoz?
 Igen, képeket szúrhat be táblázatcellákba a`Image` elem.

### Hogyan állíthatom be dinamikusan az oszlopszélességet?
 Beállíthatja a`ColumnAdjustment` tulajdonát`AutoFitToWindow` az oszlopszélességek automatikus beállításához a tartalom alapján.

### Minden dokumentum esetében kötelező a PDF/UA megfelelőség?
Bár nem kötelező, ajánlott olyan dokumentumokhoz, amelyek magas szintű akadálymentesítést igényelnek.

### Alkalmazhatok különböző stílusokat adott sorokra?
 Igen, személyre szabhatja az egyes sorokat vagy cellákat azok módosításával`TextState` vagy`BackgroundColor`.

### Mi az előnye a címkézett tartalom használatának?
címkézett tartalom javítja a dokumentumok hozzáférhetőségét, és segít biztosítani a szabványoknak, például a PDF/UA-nak való megfelelést.