---
title: Cserélhető szimbólumok a fejléc láblécében
linktitle: Cserélhető szimbólumok a fejléc láblécében
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan használhat cserélhető szimbólumokat a PDF-dokumentumok fejlécében és láblécében az Aspose.PDF for .NET segítségével.
type: docs
weight: 320
url: /hu/net/programming-with-text/replaceable-symbols-in-header-footer/
---
Ebben az oktatóanyagban elmagyarázzuk, hogyan lehet cserélhető szimbólumokat használni a PDF-dokumentumok fejlécében és láblécében az Aspose.PDF könyvtár használatával a .NET-hez. Lépésről lépésre végigvezetjük a PDF létrehozásának, a margók beállításának, a fejléc és lábléc cserélhető szimbólumokkal történő hozzáadásának, valamint a PDF mentésének a mellékelt C# forráskóddal.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Az Aspose.PDF for .NET könyvtár telepítve van.
- A C# programozás alapvető ismerete.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

 Először is be kell állítania annak a könyvtárnak az elérési útját, ahová a létrehozott PDF-fájlt menteni szeretné. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változót a kívánt könyvtár elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy PDF dokumentumot és oldalt

 Ezután létrehozunk egy új PDF dokumentumot, és hozzáadunk egy oldalt a segítségével`Document` osztály és`Page` osztály az Aspose.PDF könyvtárból.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3. lépés: Állítsa be a margókat

 Az oldal margóit a segítségével állítjuk be`MarginInfo` osztály. Állítsa be a margóértékeket igényei szerint.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## 4. lépés: Adjon hozzá fejlécet cserélhető szimbólumokkal

 Létrehozunk a`HeaderFooter` objektumot az oldalhoz, és add hozzá a`TextFragment` cserélhető szimbólumokkal hozzá.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// Ha szükséges, állítsa be a szöveg tulajdonságait
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// Adjon hozzá további szövegtöredékeket, vagy szabja testre szükség szerint
```

## 5. lépés: Adjon hozzá láblécet cserélhető szimbólumokkal

 Hasonlóképpen létrehozunk a`HeaderFooter` objektumot az oldal láblécéhez, és add hozzá`TextFragment` cserélhető szimbólumokkal ellátott objektumok hozzá.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// Adjon hozzá további szövegtöredékeket, vagy szabja testre szükség szerint

hfFoot.Paragraphs.Add(tab2);
```

## 6. lépés: Mentse el a PDF-dokumentumot

Végül elmentjük a PDF dokumentumot a megadott kimeneti fájlba.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### Minta forráskód a fejléc láblécében lévő cserélhető szimbólumokhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//Rendelje hozzá a marginInfo példányt a sec1.PageInfo Margin tulajdonságához
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// Példányosítson egy szöveges bekezdést, amely eltárolja a tartalmat, hogy fejlécként jelenjen meg
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// Hozzon létre egy HeaderFooter objektumot a szakaszhoz
HeaderFooter hfFoot = new HeaderFooter();
// Állítsa a HeaderFooter objektumot páratlan és páros láblécre
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// Adjon hozzá egy szöveges bekezdést, amely tartalmazza az aktuális oldalszámot a teljes oldalszámból
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// Példányosítson egy táblázatobjektumot
Table tab2 = new Table();
// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
hfFoot.Paragraphs.Add(tab2);
// Állítsa be a táblázat oszlopszélességeivel
tab2.ColumnWidths = "165 172 165";
//Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// Állítsa be a szöveg függőleges igazítását középre igazítottnak
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Az Aspose.Total for Java az Aspose által kínált összes Java komponens összeállítása. A#$NL" + "napi rendszerességgel fordítják, hogy biztosítsa az egyes legfrissebb verziókat Java komponenseink közül #$NL " + "Az Aspose.Total for Java fejlesztők számos alkalmazást hozhatnak létre #$NL #$NP" + "Az Aspose.Total for Java minden Java komponens összeállítása. Az Aspose által kínált #$NL" + "napi alapon, hogy biztosítsa az egyes Java komponenseink legfrissebb verzióit " + " #$NL #$NL #$NP" + "Az Aspose.Total for Java az Aspose által kínált összes Java komponens összeállítása" + "napi alapon, hogy a legtöbbet tartalmazza Az Aspose.Total for Java fejlesztők számos alkalmazást hozhatnak létre. #$NL " + ".
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// Adja hozzá a táblázatot a kívánt szakasz bekezdésgyűjteményéhez
page.Paragraphs.Add(table);
// Állítsa be az alapértelmezett cellaszegélyt a BorderInfo objektum segítségével
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// Állítsa be a táblázat szegélyét egy másik testreszabott BorderInfo objektum segítségével
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//Hozzon létre sorokat a táblázatban, majd cellákat a sorokban
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan lehet cserélhető szimbólumokat használni a PDF-dokumentumok fejlécében és láblécében az Aspose.PDF könyvtár segítségével a .NET-hez. A lépésenkénti útmutató követésével és a mellékelt C# kód végrehajtásával PDF-et hozhat létre, margókat állíthat be, fejlécet és láblécet adhat hozzá cserélhető szimbólumokkal, és mentheti a PDF-fájlt.

### GYIK

#### K: Mi a célja a „Cserélhető szimbólumok a fejléc láblécében” oktatóanyagnak?

V: A „Cserélhető szimbólumok a fejléc láblécében” című oktatóanyag célja, hogy végigvezeti Önt a .NET Aspose.PDF könyvtárának használatán, amellyel cserélhető szimbólumokat adhat hozzá egy PDF-dokumentum fejlécéhez és láblécéhez. A cserélhető szimbólumok lehetővé teszik az adott helyőrzők dinamikus lecserélését tényleges értékekkel a PDF létrehozásakor.

#### K: Mik azok a cserélhető szimbólumok a PDF fejlécben és láblécben?

V: A cserélhető szimbólumok olyan helyőrzők, amelyeket beilleszthet egy PDF-dokumentum fejlécébe és láblécébe. Ezek a szimbólumok dinamikus helyőrzőként működnek a futás közben kitölthető értékekhez, például oldalszámokhoz, dátumokhoz és egyéni információkhoz.

#### K: Miért szeretnék cserélhető szimbólumokat használni a PDF fejlécben és láblécben?

V: A fejlécben és a láblécben található cserélhető szimbólumok akkor hasznosak, ha dinamikus információkat szeretne beilleszteni a PDF-dokumentumba, például oldalszámokat, dátumokat vagy más változó adatokat, amelyek a dokumentum előállítása során változhatnak.

#### K: Hogyan állíthatom be a margókat a PDF-oldalhoz?

 V: A PDF-oldal margóit a gombbal állíthatja be`MarginInfo` osztályba, és hozzárendeljük a`Margin` tulajdona a`PageInfo` az oldalról. Szükség szerint állítsa be a margóértékeket.

#### K: Hogyan adhatok cserélhető szimbólumokat a fejléchez és a lábléchez?

 V: Cserélhető szimbólumokat adhat hozzá az a`HeaderFooter` objektum az oldal fejlécéhez és láblécéhez. Ezután hozzáadhatja`TextFragment`objektumok a kívánt szöveggel, beleértve a cserélhető szimbólumokat, a`Paragraphs` gyűjteménye a`HeaderFooter` objektum.

#### K: Testreszabhatom a cserélhető szimbólumok megjelenését?

 V: Igen, testreszabhatja a cserélhető szimbólumok megjelenését a tulajdonságainak módosításával`TextFragment` szimbólumokat tartalmazó objektumok. Beállíthat olyan tulajdonságokat, mint a betűtípus, a betűméret, a szín, az igazítás és a sorköz.

#### K: Milyen cserélhető szimbólumokat használhatok?

V: Számos cserélhető szimbólumot használhat, például:

- `$p`: Aktuális oldalszám.
- `$P`: Teljes oldalszám.
- `$d`: Aktuális dátum.
- `$t`: Jelenlegi idő.
- Ön által meghatározott egyéni helyőrzők.

#### K: Beilleszthetek más szöveget és formázást a cserélhető szimbólumok köré?

 V: Igen, a cserélhető szimbólumok köré más szöveget és formázást is megadhat`TextFragment` tárgyakat. Ez lehetővé teszi összetettebb fejlécek és láblécek létrehozását, amelyek dinamikus és statikus tartalmat tartalmaznak.

#### K: Hogyan menthetem el a létrehozott PDF dokumentumot?

 V: A létrehozott PDF dokumentum mentéséhez használhatja a`Save` módszere a`Document`osztály. Adja meg a kívánt kimeneti fájl elérési útját és nevét argumentumként.

#### K: Szükséges érvényes Aspose-licenc ehhez az oktatóanyaghoz?

V: Igen, érvényes Aspose Licenc szükséges a kód sikeres végrehajtásához ebben az oktatóanyagban. Teljes licencet vagy 30 napos ideiglenes licencet szerezhet be az Aspose webhelyéről.