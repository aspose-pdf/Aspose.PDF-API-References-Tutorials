---
title: Az oldalszámok testreszabása a tartalomjegyzék hozzáadása közben
linktitle: Az oldalszámok testreszabása a tartalomjegyzék hozzáadása közben
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésenkénti útmutatóból és kódpéldából megtudhatja, hogyan lehet testreszabni az oldalszámokat, miközben tartalomjegyzéket (TOC) ad hozzá az Aspose.PDF for .NET használatával.
type: docs
weight: 100
url: /hu/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet testreszabni az oldalszámokat, miközben tartalomjegyzéket (TOC) adunk hozzá az Aspose.PDF for .NET használatával. Lépésről lépésre útmutatást adunk egy kódpéldával együtt, hogy segítsük ezt elérni.

## 1. lépés: Meglévő PDF-fájl betöltése

Először is be kell töltenünk egy meglévő PDF-fájlt. Ehhez az oktatóanyaghoz a "42824.pdf" fájlt fogjuk használni, amely a "DOKUMENTUMKÖNYVTÁR" könyvtárban található. Cserélje ki ezt a könyvtár elérési útját a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## 2. lépés: TOC oldal hozzáadása

 Ezután egy új oldalt kell hozzáadnunk a dokumentum elejéhez, hogy a TOC oldalként szolgáljon. Ezt úgy érhetjük el, hogy a`Insert()` módszere a`Pages` gyűjteménye a`Document` tárgy.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## 3. lépés: TOC objektum létrehozása

 TOC objektum létrehozásához először létre kell hoznunk a`TocInfo` objektumot, és állítsa be a tulajdonságait. Ebben az oktatóanyagban a tartalomjegyzék címét "Tartalomjegyzék"-re, az oldalszám előtagját pedig "P"-re állítjuk.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## 4. lépés: TOC bejegyzések létrehozása

A tartalomjegyzék-bejegyzések létrehozásához a dokumentum összes oldalát a tartalomjegyzék-oldal kivételével végig kell tekintenünk, és minden oldalhoz létre kell hoznunk egy fejléc objektumot. Ezután hozzáadhatjuk a címsor objektumot a TOC oldalhoz, és megadhatjuk a céloldalt.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Címsor objektum létrehozása
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Adja meg a címsor objektum céloldalát
    heading2.DestinationPage = doc.Pages[i + 1];
    // Céloldal
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Cél koordináta
    segment2.Text = "Page " + i.ToString();
    // Címsor hozzáadása a tartalomjegyzéket tartalmazó oldalhoz
    tocPage.Paragraphs.Add(heading2);
}
```

## 5. lépés: Mentse el a frissített dokumentumot

Végül el kell mentenünk a frissített dokumentumot egy új fájlba. Ezt úgy érhetjük el, hogy a`Save()` módszere a`Document` tárgy.

```csharp
doc.Save(outFile);
```

### Példa forráskódra az oldalszámok testreszabásához a tartalomjegyzék hozzáadásához az Aspose.PDF for .NET használatával

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Töltsön be egy meglévő PDF fájlt
Document doc = new Document(inFile);
// Hozzáférés a PDF-fájl első oldalához
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Hozzon létre objektumot a TOC információk megjelenítéséhez
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Állítsa be a TOC címét
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Címsor objektum létrehozása
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Adja meg a címsor objektum céloldalát
	heading2.DestinationPage = doc.Pages[i + 1];
	// Céloldal
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Cél koordináta
	segment2.Text = "Page " + i.ToString();
	// Címsor hozzáadása a tartalomjegyzéket tartalmazó oldalhoz
	tocPage.Paragraphs.Add(heading2);
}

// Mentse el a frissített dokumentumot
doc.Save(outFile);
```

## Következtetés

Ebben az oktatóanyagban lépésről lépésre útmutatást adunk az oldalszámok testreszabásához, miközben tartalomjegyzéket ad hozzá az Aspose.PDF for .NET használatával. Adtunk egy kódpéldát is, amelyet referenciaként használhat a funkció implementálásakor

### GYIK

#### K: Mi az a tartalomjegyzék (TOC) egy PDF-dokumentumban?

V: A PDF-dokumentumban található tartalomjegyzék (TOC) egy navigációs segédeszköz, amely a dokumentumrészek vagy fejezetek rendezett listáját tartalmazza a hozzájuk tartozó oldalszámokkal együtt. Lehetővé teszi az olvasók számára, hogy gyorsan eligazodjanak a dokumentum bizonyos részeihez.

#### K: Miért szeretném személyre szabni az oldalszámokat a tartalomjegyzékben?

V: Az oldalszámok testreszabása a TOC-ban akkor lehet hasznos, ha egy adott oldalszámozási formátumot szeretne használni, vagy további információkat szeretne megadni az oldalszámokkal együtt. Lehetővé teszi személyre szabottabb és informatívabb tartalomjegyzék létrehozását.

#### K: Szerelhetek-e hiperhivatkozásokat a tartalomjegyzékbe, amelyek a PDF-dokumentum bizonyos szakaszaira vagy oldalaira hivatkoznak?

V: Igen, az Aspose.PDF for .NET lehetővé teszi hiperhivatkozások létrehozását a TOC-ban, amelyek a PDF-dokumentum meghatározott szakaszaira vagy oldalaira hivatkoznak. Ez javítja a PDF-dokumentum interaktivitását és navigációját.

#### K: Az Aspose.PDF for .NET kompatibilis a PDF/A szabványokkal?

V: Igen, az Aspose.PDF for .NET támogatja a PDF/A szabványokat, beleértve a PDF/A-1, PDF/A-2 és PDF/A-3 szabványokat. Lehetővé teszi olyan PDF dokumentumok létrehozását, amelyek megfelelnek az archiválási és hosszú távú megőrzési követelményeknek.

#### K: Hozzáadhatok további formázást a TOC bejegyzésekhez, például betűstílusokat vagy színeket?

V: Igen, az Aspose.PDF for .NET használatával további formázásokat is hozzáadhat a TOC bejegyzésekhez, például betűstílusokat, színeket és betűméreteket. Ez lehetővé teszi a TOC megjelenésének testreszabását az Ön igényei szerint.
