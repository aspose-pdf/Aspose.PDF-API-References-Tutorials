---
title: TOC hozzáadása PDF fájlhoz
linktitle: TOC hozzáadása PDF fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá tartalomjegyzéket PDF-fájlhoz az Aspose.PDF for .NET használatával. Lépésről lépésre, példaforráskóddal. Fokozza a dokumentumnavigációt!
type: docs
weight: 40
url: /hu/net/programming-with-document/addtoc/
---
Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatjuk az Aspose.PDF for .NET TOC (Tartalomjegyzék) hozzáadása PDF-fájlhoz funkcióját tartalomjegyzék hozzáadásához PDF-dokumentumokhoz. Lépésről lépésre útmutatót adunk, és elmagyarázzuk az ehhez szükséges C# forráskódot. Az oktatóanyag végére az Aspose.PDF for .NET használatával PDF-dokumentumot hozhat létre tartalomjegyzékkel.


## 1. lépés: Töltse be a meglévő PDF-fájlt

 A kezdéshez be kell töltenünk egy meglévő PDF fájlt. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a következő kódban a PDF-fájl tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## 2. lépés: Hozzon létre egy új oldalt a tartalomjegyzékhez

Létrehozunk egy új oldalt a tartalomjegyzék tárolására. A következő kód új oldalt szúr be az 1. indexbe:

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## 3. lépés: Határozza meg a tartalomjegyzék információit

Ezután meg kell határoznunk a tartalomjegyzék információkat. Beállítjuk a tartalomjegyzék címét és egyéb tulajdonságait. Adja hozzá a következő kódot:

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## 4. lépés: Hozzon létre TOC elemeket

Most létrehozzuk a tartalomjegyzék elemeit. Ebben az oktatóanyagban négy TOC elemet fogunk létrehozni, amelyek különböző oldalakhoz tartoznak. Módosítsa a következő kódot igényei szerint:

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## 5. lépés: Mentse el a frissített dokumentumot

 Végül el kell mentenünk a módosított dokumentumot a tartalomjegyzékkel együtt. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` az alábbi kódban a kívánt kimeneti fájl elérési útjával:

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Példa forráskódra TOC hozzáadásához PDF dokumentumokhoz az Aspose.PDF for .NET használatával

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Töltsön be egy meglévő PDF fájlt
Document doc = new Document(dataDir + "AddTOC.pdf");

// Hozzáférés a PDF-fájl első oldalához
Page tocPage = doc.Pages.Insert(1);

// Hozzon létre objektumot a TOC információk megjelenítéséhez
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Állítsa be a TOC címét
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//Hozzon létre karakterlánc objektumokat, amelyeket TOC elemként fog használni
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Címsor objektum létrehozása
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Adja meg a címsor objektum céloldalát
	heading2.DestinationPage = doc.Pages[i + 2];

	// Céloldal
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Cél koordináta
	segment2.Text = titles[i];

	// Címsor hozzáadása a tartalomjegyzéket tartalmazó oldalhoz
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Mentse el a frissített dokumentumot
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan adhatunk hozzá tartalomjegyzéket (TOC) PDF-dokumentumokhoz az Aspose.PDF for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt C# forráskód felhasználásával könnyedén hozhat létre PDF dokumentumot tartalomjegyzékkel. A TOC javítja a dokumentum használhatóságát, lehetővé téve a felhasználók számára, hogy hatékonyabban navigáljanak adott szakaszokhoz vagy oldalakhoz. Az Aspose.PDF for .NET robusztus és felhasználóbarát megoldást kínál a PDF-fájlokkal való munkavégzéshez .NET-alkalmazásokban, lehetővé téve dinamikus és interaktív PDF-dokumentumok egyszerű létrehozását.

### GYIK a TOC PDF-fájlhoz való hozzáadásához

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy hatékonyan dolgozzanak PDF-fájlokkal .NET-alkalmazásokban. Funkciók széles skáláját kínálja a PDF-dokumentumok programozott létrehozásához, kezeléséhez és kezeléséhez.

#### K: Mi a célja a tartalomjegyzék (TOC) hozzáadásának egy PDF-dokumentumhoz?

V: A tartalomjegyzék (TOC) navigációs segítséget nyújt a felhasználók számára, lehetővé téve számukra, hogy gyorsan ugorjanak a PDF-dokumentum adott szakaszaira vagy oldalaira. Javítja a dokumentum használhatóságát és a felhasználói élményt.

#### K: Hogyan adhatok hozzá tartalomjegyzéket egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával?

V: Ha tartalomjegyzéket szeretne hozzáadni egy PDF dokumentumhoz az Aspose.PDF for .NET használatával, létre kell hoznia egy új oldalt a tartalomjegyzék tárolására, meg kell határoznia a tartalomjegyzék információkat, majd létre kell hoznia a tartalomjegyzék-elemeket, amelyek megfelelnek bizonyos oldalaknak vagy szakaszai a dokumentumban.

#### K: Testreszabhatom a tartalomjegyzék megjelenését?

V: Igen, testreszabhatja a tartalomjegyzék megjelenését a tartalomjegyzék-elemek különféle tulajdonságainak beállításával, például betűméret, betűstílus és igazítás. Az Aspose.PDF for .NET rugalmasságot biztosít a tartalomjegyzék megtervezésében, hogy megfeleljen a kívánt megjelenésnek.

#### K: Az Aspose.PDF for .NET alkalmas arra, hogy speciális funkciókat adjon a PDF-dokumentumokhoz?

V: Az Aspose.PDF for .NET egy olyan funkciókban gazdag könyvtár, amely lehetővé teszi, hogy fejlett funkciókat adjon a PDF-dokumentumokhoz, beleértve az interaktív elemeket, űrlapmezőket, digitális aláírásokat és egyebeket.