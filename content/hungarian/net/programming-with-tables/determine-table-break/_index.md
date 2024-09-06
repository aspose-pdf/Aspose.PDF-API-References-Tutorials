---
title: Határozza meg a táblázattörést a PDF-fájlban
linktitle: Határozza meg a táblázattörést a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan határozhatja meg a táblázattöréseket PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 60
url: /hu/net/programming-with-tables/determine-table-break/
---
Ebben az oktatóanyagban megtudjuk, hogyan határozható meg a táblázattörések PDF-fájlban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a forráskódot C# nyelven. Az oktatóanyag végén tudni fogja, hogyan állapíthatja meg, hogy egy táblázat túllépi-e az oldalmargót. Kezdjük!

## 1. lépés: A környezet beállítása
Először is győződjön meg arról, hogy beállította C# fejlesztői környezetét az Aspose.PDF for .NET segítségével. Adja hozzá a hivatkozást a könyvtárhoz, és importálja a szükséges névtereket.

## 2. lépés: A PDF dokumentum létrehozása
 Ebben a lépésben létrehozunk egy újat`Document` objektum a PDF dokumentum megjelenítésére.

```csharp
pdf-Document = new Document();
```

Ez a dokumentum szakaszok és táblázatok hozzáadására szolgál.

## 3. lépés: szakasz és táblázat hozzáadása
Most hozzáadunk egy részt a PDF dokumentumunkhoz, és létrehozunk egy táblázatot ebben a szakaszban.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

A táblázathoz 300 pontos felső margót is megadunk. Ezt az értéket igényei szerint állíthatja be.

## 4. lépés: A táblázat beállítása
Ebben a lépésben konfiguráljuk a táblázat tulajdonságait, például az oszlopszélességeket és a szegélyeket.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Itt határozzuk meg a táblázat oszlopainak szélességét és a cellaszegélyeket. Ezeket az értékeket saját igényei szerint módosíthatja.

## 5. lépés: Adjon hozzá sorokat és cellákat a táblázathoz
Most sorokat és cellákat hozunk létre a táblázatban egy hurok segítségével.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Itt 17 sort hozunk létre a táblázatban, és minden sorhoz adunk három cellát. A csatot igény szerint állíthatja be.

## 6. lépés: Táblatörések meghatározása
Most úgy határozzuk meg, hogy a táblázat meghaladja-e az oldalmargókat, összehasonlítva az oldal magasságát a táblázatban lévő objektumok teljes magasságával.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Az oldal magasságát és az objektumok teljes magasságát a margók figyelembevételével számítjuk ki. Ha a különbség 10 vagy kevesebb, a táblázat meghaladja az oldalmargókat.

## 7. lépés: Mentse el a PDF dokumentumot
Végül elmentjük a PDF dokumentumot az eredményekkel.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Ügyeljen arra, hogy a megfelelő dokumentumkönyvtárat adja meg. Az eredményül kapott PDF fájl a meghatározott táblázattörésekkel kerül mentésre.

### Példa forráskódra a Determine Table Break for Aspose.PDF for .NET fájlhoz

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objektum PDF osztály példányosítása
Document pdf = new Document();
// A szakasz hozzáadása a PDF dokumentum szakaszok gyűjteményéhez
Aspose.Pdf.Page page = pdf.Pages.Add();
// Példányosítson egy táblázatobjektumot
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
page.Paragraphs.Add(table1);
// Állítsa be a táblázat oszlopszélességeivel
table1.ColumnWidths = "100 100 100";
// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Állítsa be a táblázat szegélyét egy másik testreszabott BorderInfo objektum segítségével
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Hozzon létre MarginInfo objektumot, és állítsa be a bal, alsó, jobb és felső margókat
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Állítsa be az alapértelmezett cellakitöltést a MarginInfo objektumra
table1.DefaultCellPadding = margin;
// Ha 17-re növeli a számlálót, az asztal eltörik
// Mert ezen az oldalon már nem lehet elhelyezni
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Szerezze meg az oldal magasságára vonatkozó információkat
float PageHeight = (float)pdf.PageInfo.Height;
// Szerezze meg az oldal felső és alsó margójának teljes magasságát,
// Asztal felső margója és magassága.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Oldal magasságának, táblázat magasságának, táblázat felső margójának és oldal tetejének megjelenítése
// És az alsó margó információi
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Ellenőrizze, hogy levonjuk-e az Oldal felső margója + Oldal alsó margója összegét
// + A táblázat felső margója és a táblázat magassága az oldal magasságától és attól kevesebbtől
// 10-nél (egy átlagos sor nagyobb lehet 10-nél)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Ha az érték kisebb, mint 10, akkor jelenítse meg az üzenetet.
	//Ami azt mutatja, hogy nem lehet másik sort elhelyezni, és ha újat adunk hozzá
	// Sor, asztal megszakad. Ez a sormagasság értékétől függ.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Mentse el a pdf dokumentumot
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan határozhatjuk meg a táblázattöréseket egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ezzel a lépésenkénti útmutatóval ellenőrizheti, hogy egy táblázat túllépi-e a saját C#-projektjei oldalmargóit.

### GYIK a táblázattörés meghatározásához PDF-fájlban

#### K: Mi a célja a táblázattörések meghatározásának egy PDF-dokumentumban?

V: A táblázattörések meghatározásának célja egy PDF-dokumentumban annak ellenőrzése, hogy a táblázat meghaladja-e az oldalmargókat. Ez biztosítja, hogy a táblázat tartalma helyesen jelenjen meg a rendelkezésre álló oldalterületen belül. A táblázattörések észlelésével kezelheti a tartalomtúlcsordulást, és ennek megfelelően módosíthatja a táblázat elrendezését.

#### K: Hogyan állíthatom be a táblázat felső margóját?

 V: A mellékelt C# forráskódban beállíthatja a táblázat felső margóját az érték módosításával`table1.Margin.Top`ingatlan. Szükség szerint növelje vagy csökkentse az értéket a táblázat kívánt felső margójának beállításához.

#### K: Testreszabhatom a táblázat megjelenését, például a cellák színét és a betűméretet?

V: Igen, testreszabhatja a táblázat és celláinak megjelenését az Aspose.PDF for .NET által biztosított különféle tulajdonságokkal és módszerekkel. Módosíthatja például a cella háttérszínét, a betűméretet, a betűcsaládot, a szöveg igazítását stb. A táblázat megjelenésének testreszabásával kapcsolatos további információkért tekintse meg a hivatalos dokumentációt.

#### K: Mi történik, ha a táblázat meghaladja az oldalmargót?

V: Ha a táblázat túllépi az oldalmargót, az tartalom csonkolásához vagy átfedéséhez vezethet, ami kevésbé olvashatóvá és rendezettebbé teszi a PDF-dokumentumot. A táblázattörések észlelésével és a túlcsordulás kezelésével biztosíthatja, hogy a tartalom megfelelően jelenjen meg a rendelkezésre álló oldalterületen.

#### K: Meghatározhatok táblatöréseket több táblázathoz ugyanabban a PDF-dokumentumban?

V: Igen, ugyanabban a PDF-dokumentumban több táblázathoz is meghatározhat táblázattöréseket. Egyszerűen ismételje meg a lépéseket minden elemezni kívánt táblázathoz, és szükség szerint módosítsa a táblázat elrendezését a tartalom túlcsordulás elkerülése érdekében.