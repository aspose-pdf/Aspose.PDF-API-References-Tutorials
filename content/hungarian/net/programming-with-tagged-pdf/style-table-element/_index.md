---
title: Stílusú táblázatelem
linktitle: Stílusú táblázatelem
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan formázhat táblázatelemet az Aspose.PDF for .NET segítségével. Lépésről lépésre szóló útmutató a stílusok és tulajdonságok testreszabásához.
type: docs
weight: 170
url: /hu/net/programming-with-tagged-pdf/style-table-element/
---
Ebben a részletes oktatóanyagban lépésről lépésre végigvezetjük a megadott C# forráskódon, hogy formázhassuk a tömbelemet az Aspose.PDF for .NET használatával. Kövesse az alábbi utasításokat a tömbelem stílusainak és tulajdonságainak testreszabásához.

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
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

Létrehoztunk egy új dokumentumot, és beállítottuk a dokumentum címét és nyelvét.

## 3. lépés: A gyökérstruktúra elem beszerzése

Ebben a lépésben megkapjuk a dokumentumunk gyökérstruktúra elemét.

```csharp
// Szerezze meg a gyökérszerkezet elemet
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

## 5. lépés: A tömbelemstílusok és -tulajdonságok testreszabása

Ebben a lépésben testre szabjuk a tömbelem stílusait és tulajdonságait.

```csharp
// Testreszabhatja a tömbelem stílusait és tulajdonságait
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

// Szabja testre az ismétlődő sorok stílusát
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

A táblázatelem testreszabásához különféle tulajdonságokat használtunk, mint például a háttérszín, a szegélyek, az igazítás, az alapértelmezett cella stílus, a margók, az oszlopszélesség stb.

## 6. lépés: Adja hozzá a táblázat fejléceit, törzsét és láblécét

Most adjuk hozzá a táblázat fejléceit, törzsét és láblécét a táblázatelemhez.
```csharp
// Táblázatfejlécek hozzáadása
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// A táblázat sorainak és oszlopainak száma
int rowCount = 10;
int colCount = 5;
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

//Adja hozzá a táblázat törzsének sorait
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// Adja hozzá a táblázat alapvonalát
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

A megfelelő elemek segítségével hozzáadtuk a táblázathoz a fejléceket, törzssorokat és láblécsorokat.

## 7. lépés: Mentse el a címkézett PDF-dokumentumot

Most, hogy elkészítettük dokumentumunkat a stílusos táblázatelemmel, elmentjük címkézett PDF dokumentumként.

```csharp
// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "StyleTableElement.pdf");
```

A címkézett PDF dokumentumot a megadott könyvtárba mentettük.

## 8. lépés: PDF/UA megfelelőség ellenőrzése

Ezután ellenőrizni fogjuk dokumentumunk PDF/UA megfelelőségét.

```csharp
// PDF/UA megfelelőségi ellenőrzés
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Feltöltöttük a címkézett PDF-dokumentumot, és egy XML-jelentés generálásával ellenőriztük annak PDF/UA megfelelőségét.

### Minta forráskód a Style Table Elementhez az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum létrehozása
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

// Gyökérstruktúra elem lekérése
StructureElement rootElement = taggedContent.RootElement;

// Táblázatszerkezet elem létrehozása
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
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
document.Save(dataDir + "StyleTableElement.pdf");

// PDF/UA megfelelőség ellenőrzése
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan kell formázni a tömbelemet az Aspose.PDF for .NET segítségével. Testreszabtuk a táblázatelem stílusát és tulajdonságait, fejléceket, törzssorokat és láblécet adtunk hozzá, elmentettük a címkézett PDF dokumentumot, és ellenőriztük a PDF/UA megfelelőségét.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak a tömbelem formázásához az Aspose.PDF for .NET használatával?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezesse a tömbelem formázási folyamatán egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Részletes utasításokat és C#-forráskód-példákat tartalmaz, amelyek segítenek testreszabni a tömbelem stílusait és tulajdonságait.

#### K: Melyek az oktatóanyag követésének előfeltételei?

V: Mielőtt elkezdené, győződjön meg arról, hogy a fejlesztői környezetet az Aspose.PDF for .NET használatára állította be. Ez magában foglalja az Aspose.PDF könyvtár telepítését és a projekt konfigurálását, hogy hivatkozzon rá.

#### K: Hogyan hozhatok létre új PDF-dokumentumot, és állíthatom be a címét és a nyelvét az Aspose.PDF for .NET használatával?

 V: Új PDF-dokumentum létrehozásához létre kell hoznia a`Document` objektumot az Aspose.PDF könyvtárból. Az oktatóanyagban található C# forráskód bemutatja, hogyan hozhat létre dokumentumot, és hogyan állíthatja be a címét és a nyelvi tulajdonságait.

#### K: Mi a jelentősége a gyökérstruktúra elemnek egy PDF dokumentumban?

V: A gyökérstruktúra elem a többi szerkezeti elem tárolójaként működik, segítve a PDF-dokumentum tartalmának rendszerezését és kategorizálását. Döntő szerepet játszik a dokumentum logikai szerkezetének kialakításában.

#### K: Hogyan hozhatok létre és szabhatok testre egy tömbstruktúra elemet az Aspose.PDF for .NET használatával?

 V: A tömbszerkezet elemet a`CreateTableElement()` módszer. Az oktatóanyag forráskódja példákat ad a táblázatelem különféle tulajdonságainak testreszabására, mint például a háttérszín, a szegélyek, az igazítás, az oszlopszélesség és egyebek.

#### K: Testreszabhatom a táblázatcellák stílusát és tulajdonságait a tömbelemen belül?

V: Igen, az oktatóanyag leírja, hogyan lehet testreszabni a teljes táblázatelem stílusát és tulajdonságait, beleértve a fejléceket, törzssorokat és láblécet. Ez azonban nem foglalkozik kifejezetten az egyes táblázatcellák testreszabásával.

#### K: Hogyan adhatok fejléceket, törzssorokat és láblécet a táblázatelemhez?

V: Az oktatóanyag elmagyarázza, hogyan lehet fejléceket, törzssorokat és láblécet létrehozni és hozzáadni a táblázatelemhez az Aspose.PDF for .NET által biztosított megfelelő módszerekkel.

#### K: Mi a PDF/UA megfelelőség, és hogyan tudom érvényesíteni a címkézett PDF-dokumentumhoz?

 V: A PDF/UA megfelelőség biztosítja, hogy a PDF-dokumentum megfeleljen az akadálymentesítési szabványoknak, így a fogyatékkal élő felhasználók számára könnyebben elérhető. Az oktatóanyag bemutatja, hogyan ellenőrizheti a PDF/UA megfelelőséget a`Validate()` módszert, és készítsen XML megfelelőségi jelentést.

#### K: Hogyan építhetem be ezeket a fogalmakat a saját .NET alkalmazásaimba?

V: A mellékelt C#-forráskód-példákat útmutatóként használhatja a tömbelem-formázás megvalósításához saját .NET-alkalmazásaiban. Módosítsa és adaptálja a kódot az igényeinek megfelelően, és integrálja projektjeibe.

#### K: Vannak-e ajánlott bevált módszerek a tömbelemek formázására a PDF dokumentumokban?

V: A tömbelemek (táblázatok) formázásakor vegye figyelembe a tartalom olvashatóságát és hozzáférhetőségét. Használjon világos és olvasható betűtípusokat, megfelelő színeket, és tartson fenn egységes elrendezést. Érvényesítse a PDF/UA-megfelelőséget, hogy biztosítsa az akadálymentesítési szabványok betartását.

#### K: Az Aspose.PDF for .NET mely egyéb funkcióit fedezhetem fel a PDF-dokumentumok testreszabásához?

V: Az Aspose.PDF for .NET számos szolgáltatást kínál a PDF-dokumentumok testreszabásához, beleértve a szövegkezelést, a képbeszúrást, az űrlapmezők kezelését, a digitális aláírásokat, a megjegyzéseket és egyebeket. A további funkciók felfedezéséhez tekintse meg a hivatalos dokumentációt és forrásokat.