---
title: Stílus táblázat Cell
linktitle: Stílus táblázat Cell
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg a táblázatcellák stílusát az Aspose.PDF for .NET segítségével. Útmutató a táblázatok létrehozásához és testreszabásához lépésről lépésre.
type: docs
weight: 160
url: /hu/net/programming-with-tagged-pdf/style-table-cell/
---
Üdvözöljük ebben a részletes oktatóanyagban a táblázatcellák Aspose.PDF for .NET használatával történő formázásával kapcsolatban. Ebben az útmutatóban részletesen elmagyarázzuk a mellékelt C#-forráskód minden egyes lépését, hogy segítsen megérteni, hogyan kell stílusozni a táblázatcellákat. Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF for .NET fájlt, és állítsa be a fejlesztői környezetet.

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
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

Létrehoztunk egy új dokumentumot, és beállítottuk a dokumentum címét és nyelvét.

## 3. lépés: A gyökérstruktúra elem beszerzése

Ebben a lépésben megkapjuk a dokumentumunk gyökérstruktúra elemét.

```csharp
//Szerezze meg a gyökérszerkezet elemet
StructureElement rootElement = taggedContent.RootElement;
```

Megkaptuk a gyökérstruktúra elemet, amely a tömbelemek tárolójaként fog szolgálni.

## 4. lépés: A tömbstruktúra elem létrehozása

Most hozzunk létre egy új táblázatszerkezet elemet a dokumentumunkhoz.

```csharp
// Hozza létre a tömbszerkezet elemet
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Létrehoztunk egy új tömbstruktúra elemet, és hozzáadtuk a gyökérstruktúra elemhez. Elkészítettük a táblázat fejléce-, törzs- és lábléce-elemeit is.

## 5. lépés: Táblafejlécek hozzáadása

Ebben a lépésben hozzáadjuk a táblázat fejléceit a táblázatunkhoz.

```csharp
// A táblázat sorainak és oszlopainak száma
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// Hozza létre a táblázat fejlécsorát
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

Létrehoztunk egy fejlécsort a táblázatunkhoz, és fejléccellákat adtunk hozzá olyan formázási tulajdonságokkal, mint a háttérszín, a szegélyek, a margók és az igazítás.

## 6. lépés: A táblázat törzssorainak hozzáadása

Most adjuk hozzá a táblázat törzssorait a táblázatunkhoz.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

Sorokat adtunk hozzá a táblázat törzséhez hurkokkal, hogy az egyes táblázatcellákon ismételjünk. Minden cellához beállítjuk a formázási tulajdonságokat, mint a háttérszín, a szegélyek, a margók, a szöveg igazítása stb.

## 7. lépés: A lábléc hozzáadása

Végül hozzáadjuk a táblázat láblécét a táblázatunkhoz.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

Létrehoztunk egy láblécet a táblázatunkhoz, és lábléccellákat adtunk hozzá szöveggel.



## 8. lépés: Mentse el a címkézett PDF-dokumentumot

Most, hogy elkészítettük dokumentumunkat a stílusos táblázattal, címkézett PDF dokumentumként mentjük el.

```csharp
// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "StyleTableCell.pdf");
```

A címkézett PDF dokumentumot a megadott könyvtárba mentettük.

## 9. lépés: PDF/UA megfelelőség ellenőrzése

Ezután ellenőrizni fogjuk dokumentumunk PDF/UA megfelelőségét.

```csharp
// PDF/UA megfelelőségi ellenőrzés
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

Feltöltöttük a címkézett PDF-dokumentumot, és egy XML-jelentés generálásával ellenőriztük annak PDF/UA megfelelőségét.

### Minta forráskód a Style Table Cell számára az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum létrehozása
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// Gyökérstruktúra elem lekérése
StructureElement rootElement = taggedContent.RootElement;

// Táblázatstruktúra elem létrehozása
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
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
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA megfelelőség ellenőrzése
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet stílust készíteni a táblázatcellákon az Aspose.PDF for .NET használatával. Láttuk, hogyan hozhat létre dokumentumot, hogyan adhat hozzá táblázatot fejlécekkel, törzssorokkal és láblécekkel, és hogyan testreszabhatja a cellastílusokat. Végül elmentettük a címkézett PDF dokumentumot, és ellenőriztük annak PDF/UA megfelelőségét. Mostantól az Aspose.PDF for .NET segítségével táblákat hozhat létre és stílusozhat .NET-alkalmazásaiban.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak a táblázatcellák formázásához az Aspose.PDF for .NET használatával?

V: Ennek az oktatóanyagnak az a célja, hogy átfogó útmutatót nyújtson a PDF-dokumentumok táblázatcelláinak stílusához az Aspose.PDF-könyvtár használatával a .NET-hez. Részletes utasításokat és C# forráskód példákat tartalmaz, amelyek segítenek megérteni és megvalósítani a táblázatcellák formázását.

#### K: Melyek az oktatóanyag követésének előfeltételei?

V: Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF for .NET fájlt, és beállította a fejlesztői környezetet. Ez magában foglalja a projekt konfigurálását úgy, hogy az Aspose.PDF könyvtárra hivatkozzon.

#### K: Hogyan hozhatok létre új PDF-dokumentumot az Aspose.PDF for .NET használatával?

V: Új PDF-dokumentum létrehozásához példányosítania kell a`Document` objektum az Aspose.PDF könyvtárból. A mellékelt C# forráskód bemutatja, hogyan hozhat létre dokumentumot, és hogyan állíthatja be a címét és a nyelvét.

#### K: Mi a jelentősége a gyökérstruktúra elemnek egy PDF dokumentumban?

V: A gyökérstruktúra elem tárolóként szolgál más szerkezeti elemek számára, segítve a PDF-dokumentum tartalmának rendszerezését és kategorizálását. Döntő szerepet játszik a dokumentum logikai szerkezetének kialakításában.

#### K: Hogyan hozhatok létre táblázatszerkezeti elemet és testreszabhatom a megjelenését az Aspose.PDF for .NET használatával?

 V: Létrehozhat táblázatszerkezeti elemet a`CreateTableElement()` módszer. A mellékelt forráskód bemutatja, hogyan lehet testreszabni a táblázat megjelenését, beleértve a fejlécét, törzsét és láblécét, olyan tulajdonságok beállításával, mint a háttérszín, a szegélyek, a margók és az igazítás.

#### K: Hozzáadhatok több sort és oszlopot a táblázat törzséhez, és testreszabhatom a formázásukat?

V: Igen, az oktatóanyag bemutatja, hogyan lehet több sort és oszlopot hozzáadni a táblázat törzséhez hurkok segítségével. Példákat ad a cellaformázás testreszabására is, mint például a háttérszín, a szegélyek, a szövegigazítás, a betűstílus stb.

#### K: Mi a célja a PDF/UA megfelelőség ellenőrzésének, és hogyan végezhetem el ezt az ellenőrzést?

 V: A PDF/UA megfelelőség ellenőrzése biztosítja, hogy a PDF-dokumentum megfeleljen az akadálymentesítési szabványoknak, így a fogyatékkal élő felhasználók számára is hozzáférhetőbbé válik. Az oktatóanyag bemutatja, hogyan ellenőrizheti a PDF/UA megfelelőséget a`Validate()` módszert, és készítsen XML jelentést.

#### K: Hogyan alkalmazhatom ezeket a fogalmakat a saját .NET-alkalmazásaimra?

V: A mellékelt C#-forráskód-példákat útmutatóként használhatja a táblázatcellák formázásának megvalósításához saját .NET-alkalmazásaiban. Igény szerint testreszabhatja a kódot, és integrálhatja projektjeibe.

#### K: Vannak-e ajánlott bevált módszerek a táblázatcellák stíluszására a PDF dokumentumokban?

V: A táblázatcellák stílusának kialakítása során vegye figyelembe a közönség igényeit, beleértve a kisegítő lehetőségeket is. Használjon kontrasztos színeket, megfelelő betűtípusokat és tiszta cellaigazítást az olvashatóság javítása érdekében. Ezenkívül ellenőrizze a PDF/UA megfelelőséget, hogy biztosítsa a kisegítő lehetőségek betartását.

#### K: A .NET-hez készült Aspose.PDF mely egyéb funkcióit fedezhetem fel a PDF-dokumentumok kezeléséhez?

V: Az Aspose.PDF for .NET szolgáltatások széles skáláját kínálja a PDF-dokumentumok manipulálásához, beleértve a szövegkivonást, képbeszúrást, űrlapmező-kezelést, digitális aláírásokat stb. Fedezze fel a hivatalos dokumentációt és forrásokat a további funkciók megismeréséhez.
