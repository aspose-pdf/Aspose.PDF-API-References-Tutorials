---
title: Stílus táblázat sor
linktitle: Stílus táblázat sor
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan testreszabhatja a táblázatsorokat az Aspose.PDF for .NET segítségével lépésről lépésre szóló útmutatója a sorok stílusához és formázásához.
type: docs
weight: 180
url: /hu/net/programming-with-tagged-pdf/style-table-row/
---
Ebben a részletes oktatóanyagban lépésről lépésre végigvezetjük a megadott C# forráskódon, hogy formázhassa a táblázatsort az Aspose.PDF for .NET használatával. Kövesse az alábbi utasításokat a táblázatsorstílusok és -tulajdonságok testreszabásához.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy a fejlesztői környezetet úgy konfigurálta, hogy az Aspose.PDF for .NET fájlt használja. Ez magában foglalja az Aspose.PDF könyvtár telepítését és a projekt konfigurálását, hogy hivatkozzon rá.

## 2. lépés: Dokumentum létrehozása

Ebben a lépésben létrehozunk egy új Aspose.PDF dokumentumobjektumot.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentumkészítés
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

Létrehoztunk egy új dokumentumot, és beállítottuk a dokumentum címét és nyelvét.

## 3. lépés: A gyökérstruktúra elem beszerzése

Ebben a lépésben megkapjuk a dokumentumunk gyökérstruktúra elemét.

```csharp
//Szerezze meg a gyökérszerkezet elemet
StructureElement rootElement = taggedContent.RootElement;
```

Megkaptuk a gyökérstruktúra elemet, amely a tömbelem tárolójaként fog szolgálni.

## 4. lépés: A tömbstruktúra elem létrehozása

Most hozzunk létre egy új táblázatszerkezet elemet a dokumentumunkhoz.

```csharp
// Hozd létre a tömbstruktúra elemet
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

Létrehoztunk egy új tömbstruktúra elemet, és hozzáadtuk a gyökérstruktúra elemhez.

## 5. lépés: A táblázat sorstílusainak és tulajdonságainak testreszabása

Ebben a lépésben testre szabjuk a táblázat sorstílusait és tulajdonságait.

```csharp
// Testreszabhatja a táblázatsor stílusait és tulajdonságait
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

// Hozza létre a táblázat fejlécsorát
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// Szabja testre a táblázat törzsének sorait
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Hozza létre a táblázat láblécsorát
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Testreszabtuk a táblázat sorának különféle szempontjait, például a háttérszínt, a szegélyeket, a sor magasságát, az oldalszámozást, az alapértelmezett cellastílust és egyebeket.

## 6. lépés: Mentse el a címkézett PDF-dokumentumot

Most, hogy elkészítettük dokumentumunkat a stílusos táblázatsorral, címkézett PDF-dokumentumként mentjük el.
```csharp
// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "StyleTableRow.pdf");
```

A címkézett PDF dokumentumot a megadott könyvtárba mentettük.

## 7. lépés: PDF/UA megfelelőség ellenőrzése

Ezután ellenőrizni fogjuk dokumentumunk PDF/UA megfelelőségét.

```csharp
// PDF/UA megfelelőségi ellenőrzés
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Feltöltöttük a címkézett PDF-dokumentumot, és egy XML-jelentés generálásával ellenőriztük annak PDF/UA megfelelőségét.


### Minta forráskód a Style Table Row számára az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum létrehozása
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// Gyökérstruktúra elem lekérése
StructureElement rootElement = taggedContent.RootElement;

// Táblázatstruktúra elem létrehozása
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	trElement.BackgroundColor = Color.LightGoldenrodYellow;
	trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
	trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
	trElement.MinRowHeight = 100.0;
	trElement.FixedRowHeight = 120.0;
	trElement.IsInNewPage = (rowIndex % 3 == 1);
	trElement.IsRowBroken = true;
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// Címkézett PDF dokumentum mentése
document.Save(dataDir + "StyleTableRow.pdf");

// PDF/UA megfelelőség ellenőrzése
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan formázhat táblázatsort az Aspose.PDF for .NET segítségével. Testreszabtuk a táblázat sorstílusait és tulajdonságait, hozzáadtuk a fejléceket, törzssorokat és láblécet, elmentettük a címkézett PDF dokumentumot, és ellenőriztük a PDF/UA megfelelőségét.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak a táblázatsorok formázásához az Aspose.PDF for .NET használatával?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezesse a táblázat sorainak formázásán egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Részletes utasításokat és C#-forráskód-példákat tartalmaz, amelyek segítenek testreszabni a táblázatsor stílusait és tulajdonságait.

#### K: Melyek az oktatóanyag követésének előfeltételei?

V: Mielőtt elkezdené, győződjön meg arról, hogy a fejlesztői környezetet az Aspose.PDF for .NET használatára állította be. Ez magában foglalja az Aspose.PDF könyvtár telepítését és a projekt konfigurálását, hogy hivatkozzon rá.

#### K: Hogyan hozhatok létre új PDF-dokumentumot, és állíthatom be a címét és a nyelvét az Aspose.PDF for .NET használatával?

 V: Új PDF-dokumentum létrehozásához létre kell hoznia a`Document` objektumot az Aspose.PDF könyvtárból. Az oktatóanyagban található C# forráskód bemutatja, hogyan hozhat létre dokumentumot, és hogyan állíthatja be a címét és a nyelvi tulajdonságait.

#### K: Mi a jelentősége a gyökérstruktúra elemnek egy PDF dokumentumban?

V: A gyökérstruktúra elem a többi szerkezeti elem tárolójaként működik, segítve a PDF-dokumentum tartalmának rendszerezését és kategorizálását. Döntő szerepet játszik a dokumentum logikai szerkezetének kialakításában.

#### K: Hogyan hozhatok létre és szabhatok testre egy táblázatszerkezet-elemet a táblázatsorok formázásához az Aspose.PDF for .NET használatával?

V: Az oktatóanyag elmagyarázza, hogyan hozhat létre táblázatszerkezet-elemet, és hogyan szabhatja testre tulajdonságait a táblázatsorok formázásához. Olyan szempontokra terjed ki, mint a háttérszín, a szegélyek, a sor magassága, az oldalszámozás, az alapértelmezett cellastílus stb.

#### K: Testreszabhatom az egyes cellák stílusát és tulajdonságait egy táblázatsorban?

V: Igen, testreszabhatja az egyes cellák stílusát és tulajdonságait egy táblázatsorban. Az oktatóanyag bemutatja, hogyan állíthat be tulajdonságokat, például háttérszínt, szegélyeket, szövegszínt, kitöltést és egyebeket a táblázatcellákhoz a formázott táblázatsorban.

#### K: Hogyan adhatok fejléceket, törzssorokat és láblécet a formázott táblázatsorhoz?

V: Az oktatóanyag példákat mutat be fejlécek, törzssorok és lábléc létrehozására és hozzáadására a táblázatszerkezet elemhez. Ezek az elemek az oktatóanyagban leírt tulajdonságok segítségével tovább testreszabhatók.

#### K: Mi a PDF/UA megfelelőség, és hogyan tudom érvényesíteni a címkézett PDF-dokumentumhoz?

 V: A PDF/UA megfelelőség biztosítja, hogy a PDF-dokumentum megfeleljen az akadálymentesítési szabványoknak, így a fogyatékkal élő felhasználók számára könnyebben elérhető. Az oktatóanyag bemutatja, hogyan ellenőrizheti a PDF/UA megfelelőséget a`Validate()` módszert, és készítsen XML megfelelőségi jelentést.

#### K: Hogyan építhetem be ezeket a fogalmakat a saját .NET alkalmazásaimba?

V: A mellékelt C#-forráskód-példákat útmutatóként használhatja a táblázatsor-formázás megvalósításához saját .NET-alkalmazásaiban. Módosítsa és alakítsa át a kódot az igényeinek megfelelően, és integrálja projektjeibe.

#### K: Vannak-e ajánlott bevált módszerek a táblázatsorok formázására a PDF dokumentumokban?

V: A táblázat sorainak formázásakor vegye figyelembe a tartalom olvashatóságát és hozzáférhetőségét. Gondoskodjon arról, hogy a színek megfelelő kontraszttal rendelkezzenek, használjon világos és olvasható betűtípusokat, és tartson fenn egységes elrendezést. Érvényesítse a PDF/UA-megfelelőséget, hogy biztosítsa az akadálymentesítési szabványok betartását.

#### K: Az Aspose.PDF for .NET mely egyéb funkcióit fedezhetem fel a PDF-dokumentumok testreszabásához?

V: Az Aspose.PDF for .NET funkciók széles skáláját kínálja a PDF-dokumentumok testreszabásához, beleértve a szövegkezelést, a képbeszúrást, az űrlapmezők kezelését, a digitális aláírásokat, a megjegyzéseket és egyebeket. A további funkciók felfedezéséhez tekintse meg a hivatalos dokumentációt és forrásokat.