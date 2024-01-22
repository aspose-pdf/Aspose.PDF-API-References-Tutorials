---
title: Táblázatelem létrehozása
linktitle: Táblázatelem létrehozása
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató egy tömbelem létrehozásához az Aspose.PDF segítségével .NET-hez. Egyszerűen generálhat dinamikus PDF-eket táblázatokkal.
type: docs
weight: 80
url: /hu/net/programming-with-tagged-pdf/create-table-element/
---
Ebben a lépésenkénti útmutatóban végigvezetjük egy tömbelem létrehozásának folyamatán az Aspose.PDF for .NET használatával. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi a PDF-dokumentumok programozott kezelését. A tömbelem létrehozása általános követelmény a dinamikus PDF-ek generálásakor, és az Aspose.PDF egyszerű és hatékony módot kínál ennek megvalósítására.

Merüljünk el a kódban, és tanuljuk meg, hogyan hozhatunk létre tömbelemeket az Aspose.PDF for .NET használatával.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Aspose.PDF könyvtár a .NET-hez telepítve.
2. Alapszintű C# programozási nyelv ismerete.

## 1. lépés: A környezet beállítása

A kezdéshez nyissa meg a C# fejlesztői környezetet, és hozzon létre egy új projektet. Győződjön meg arról, hogy a projektben hozzáadott egy hivatkozást a .NET Aspose.PDF könyvtárára.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum létrehozása

 Az első lépés egy új PDF dokumentum létrehozása a`Document` osztály.

```csharp
// Hozd létre a dokumentumot
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

Itt beállítjuk a címkézett tartalom címét és nyelvét is.

## 3. lépés: A tömbelem létrehozása

Ezután létre kell hoznunk a tömbelemet, és hozzá kell adnunk a dokumentumhoz. Kezdjük a gyökérstruktúra elem beszerzésével, majd a segítségével létrehozunk egy új táblázatelemet`CreateTableElement` módszer.

```csharp
// Szerezd meg a gyökérstruktúra elemet
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA megfelelőségi ellenőrzés
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### Minta forráskód a Táblázatelem létrehozásához az Aspose.PDF segítségével .NET-hez 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum létrehozása
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// Gyökérstruktúra elem lekérése
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// Címkézett PDF dokumentum mentése
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA megfelelőség ellenőrzése
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Megtanulta, hogyan hozhat létre tömbelemeket az Aspose.PDF for .NET használatával. Ezzel a módszerrel PDF-dokumentumokat hozhat létre dinamikus táblázatokkal. Nyugodtan fedezze fel az Aspose.PDF további funkcióit, hogy felfedezze a benne rejlő lehetőségeket.

### GYIK

#### K: Mi az a tömbelem a PDF-dokumentumban, és miért kell egyet létrehoznom az Aspose.PDF for .NET használatával?

V: A PDF-dokumentumban lévő tömbelemek strukturált adatgyűjteményt képviselnek, amelyet gyakran táblázatok vagy rácsok létrehozására használnak. Előfordulhat, hogy létre kell hoznia egy tömbelemet az Aspose.PDF for .NET használatával, amikor olyan dinamikus PDF-eket hoz létre, amelyek strukturált adatmegjelenítést igényelnek, például táblázatos információkat vagy rácsokat.

#### K: Hogyan egyszerűsíti le az Aspose.PDF for .NET a tömbelemek létrehozásának folyamatát?

V: Az Aspose.PDF for .NET olyan osztályok és metódusok átfogó készletét kínálja, amelyek lehetővé teszik a PDF-dokumentumok tömbelemeinek (táblázatainak) programozott létrehozását, testreszabását és kezelését. Ez kiküszöböli a PDF kézi kezelésének szükségességét, és leegyszerűsíti a strukturált adatábrázolások létrehozását.

#### K: Melyek a legfontosabb lépések egy tömbelem létrehozásához az Aspose.PDF for .NET használatával?

V: A legfontosabb lépések közé tartozik a környezet beállítása, a dokumentum létrehozása, a gyökérstruktúra elem beszerzése, a táblázatelem létrehozása, a táblázaton belüli sorok és cellák meghatározása, valamint az elemek formázásának és tulajdonságainak megadása. A mellékelt kódpélda bemutatja ezeket a lépéseket.

####  K: Milyen szerepet tölt be a`taggedContent` object play in creating an array element?

 V: A`taggedContent` objektum, amelyet a dokumentumból szereztünk be`TaggedContent`tulajdonság lehetővé teszi a címkézett tartalom szerkezetének meghatározását a PDF-dokumentumban. Ez magában foglalja a tömbelemek és gyermekelemeik hierarchikus létrehozását és rendszerezését.

#### K: Hogyan biztosítja a kód a létrehozott tömbelem elérhetőségét és szemantikáját?

 V: A kód olyan attribútumokat állít be, mint pl`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , és`ColSpan` a tömbelem elérhetőségének és szemantikájának javítása érdekében. Ezek az attribútumok hozzájárulnak az adatok jól strukturált, informatív és tetszetős megjelenítéséhez.

#### K: Mi a jelentősége a PDF/UA megfelelőségnek a tömbelemek létrehozásával összefüggésben?

 V: A PDF/UA (Universal Accessibility) megfelelőség biztosítja, hogy az előállított PDF-dokumentumok hozzáférhetők legyenek a fogyatékkal élő felhasználók számára, és megfeleljenek bizonyos akadálymentesítési szabványoknak. A kódpélda a PDF/UA megfelelőséget a következővel ellenőrzi`Validate` módszer, amely segít a befogadó és hozzáférhető dokumentumok létrehozásában.

#### K: Testreszabhatom a tömbelemek formázását és megjelenését?

V: Igen, testreszabhatja a tömbelemek formázását és megjelenését olyan attribútumok beállításával, mint a háttérszín, a szegélystílus, a betűméret és az igazítás. Az Aspose.PDF for .NET tulajdonságok széles skáláját kínálja a vizuális megjelenítés igényeinek megfelelő testreszabásához.

#### K: Hogyan bővíthetem ezt a tudást bonyolultabb táblázatszerkezetek létrehozására vagy tömbelemek beépítésére nagyobb PDF dokumentumokba?

V: Ezt a tudást bővítheti az Aspose.PDF for .NET további funkcióinak felfedezésével, például több tömbelem egyesítésével, beágyazott táblázatok létrehozásával, fejlécek és láblécek hozzáadásával, valamint a tömbelemek nagyobb PDF-elrendezésekbe való integrálásával. A könyvtár dokumentációja és példái útmutatást adnak ezekhez a fejlett forgatókönyvekhez.

#### K: Lehetséges-e adatokat importálni külső forrásokból, például adatbázisokból vagy táblázatokból a tömbelemek feltöltéséhez?

V: Igen, importálhat adatokat külső forrásokból a tömbelemek feltöltéséhez. Használhat adatlekérési és -átalakítási technikákat a C# nyelven, hogy lekérjen adatokat adatbázisokból, táblázatokból vagy más forrásokból, majd ennek megfelelően töltse fel a tömbelemeket.

#### K: Hogyan használhatom fel az oktatóanyagból megszerzett tudást a programozottan létrehozott PDF-dokumentumok minőségének és használhatóságának javítására?

V: Az oktatóanyagból szerzett ismeretek lehetővé teszik, hogy strukturált és tetszetős tömbelemeket (táblázatokat) hozzon létre PDF dokumentumokban. Ezen technikák beépítésével javíthatja a dinamikusan generált PDF-ek olvashatóságát, hozzáférhetőségét és felhasználói élményét, így azok informatívabbak és felhasználóbarátabbak.