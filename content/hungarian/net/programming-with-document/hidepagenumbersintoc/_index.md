---
title: Oldalszámok elrejtése a TOC-ban
linktitle: Oldalszámok elrejtése a TOC-ban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan rejtheti el az oldalszámokat a tartalomjegyzékben az Aspose.PDF for .NET használatával.
type: docs
weight: 220
url: /hu/net/programming-with-document/hidepagenumbersintoc/
---
Ebben a cikkben az Aspose.PDF for .NET oldalszámok elrejtése a tartalomjegyzékben funkciójának megvalósítását tárgyaljuk C# használatával. Kezdjük az Aspose.PDF for .NET rövid bemutatásával, majd belevessünk a funkció megvalósításának lépésenkénti útmutatójába. 

## Az Aspose.PDF .NET-hez bemutatása

Az Aspose.PDF for .NET egy hatékony PDF-manipulációs összetevő, amely lehetővé teszi a fejlesztők számára, hogy programozottan hozzanak létre, szerkesszenek és kezeljenek PDF-fájlokat. Funkciók és funkciók széles skáláját kínálja, amelyek megkönnyítik a PDF-dokumentumok kezelését. Az Aspose.PDF for .NET támogatja a 32 bites és 64 bites operációs rendszereket is, és használható .NET Framework, .NET Core és Xamarin platformokkal. 

## Mi az az oldalszámok elrejtése a tartalomjegyzékben funkció?

A tartalomjegyzék (TOC) a PDF-dokumentum lényeges része, amely gyors áttekintést nyújt a felhasználóknak a tartalomról. Előfordulhat, hogy a felhasználók el akarják rejteni az oldalszámokat a tartalomjegyzékben, hogy felhasználóbarátabbá tegyék. Az Aspose.PDF for .NET beépített funkciót biztosít az oldalszámok elrejtésére a tartalomjegyzékben. Ezzel a funkcióval felhasználóbarátabb PDF dokumentumokat lehet létrehozni. 

## Előfeltételek

Az oktatóanyag követéséhez a következőkre lesz szüksége:

- Visual Studio 2010 vagy újabb
- Aspose.PDF for .NET telepítve van a rendszerére
- C# programozási nyelv alapismerete

## Útmutató lépésről lépésre az Oldalszámok elrejtése a tartalomjegyzékben funkció megvalósításához

Kövesse az alábbi lépéseket az Oldalszámok elrejtése a tartalomjegyzékben funkció megvalósításához az Aspose.PDF for .NET használatával:

## 1. lépés: Hozzon létre egy új C# konzolalkalmazást a Visual Studióban

Nyissa meg a Visual Studio-t, és hozzon létre egy új C# konzolalkalmazást.

## 2. lépés: Adjon hozzá hivatkozást az Aspose.PDF fájlhoz a .NET-hez

Kattintson a jobb gombbal a References mappára a projektben, és válassza a Hivatkozás hozzáadása lehetőséget. Keresse meg azt a helyet, ahol az Aspose.PDF for .NET telepítve van a rendszerén, és adjon hozzá hivatkozást.

## 1. lépés: Hozzon létre egy új PDF-dokumentumot

Hozzon létre egy új PDF dokumentumot a következő kóddal:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 2. lépés: Hozzon létre egy TOC oldalt

Hozzon létre egy új oldalt a TOC számára, és adja hozzá a PDF dokumentumhoz a következő kóddal:

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## 3. lépés: Adja hozzá a lista szakaszt a PDF dokumentum szakaszgyűjteményéhez

Adja hozzá a lista részt a PDF-dokumentum szakaszgyűjteményéhez a következő kóddal:

```csharp
tocPage.TocInfo = tocInfo;
```

## 4. lépés: Határozza meg a négyszintű lista formátumát

Határozza meg a négyszintű lista formátumát az egyes szintek bal margóinak és szövegformátum-beállításainak megadásával a következő kód segítségével:

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## 5. lépés: Adjon hozzá négy címsort a szakaszhoz

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Példa forráskód az oldalszámok elrejtéséhez a tartalomjegyzékben az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Adja hozzá a lista részt a PDF dokumentum szakaszgyűjteményéhez
tocPage.TocInfo = tocInfo;
//Határozza meg a négyszintű lista formátumát a bal margók és a
//az egyes szintek szövegformátum beállításait

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Adjon hozzá négy címsort a szakaszhoz
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan dolgozhatunk XMP-metaadatokkal egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Az XMP metaadatok értékes információkat nyújtanak a PDF-dokumentumról, beleértve a címet, a szerzőt, a létrehozás dátumát és egyebeket. Az Aspose.PDF for .NET lehetővé teszi a fejlesztők számára a metaadatok elérését és kezelését, rugalmas és hatékony API-t biztosítva a PDF-dokumentumok kezeléséhez.

### GYIK

#### K: Mi az XMP-metaadat egy PDF-dokumentumban?

V: A PDF-dokumentumban lévő XMP (Extensible Metadata Platform) metaadatok szabványos formátum a dokumentum metaadat-információinak tárolására. Olyan részleteket tartalmaz, mint a dokumentum címe, szerzője, létrehozásának dátuma, kulcsszavak stb. Az XMP metaadatok strukturált és szabványosított módot biztosítanak a PDF-dokumentum információinak tárolására és megosztására.

#### K: Módosíthatom egy PDF-dokumentum XMP-metaadatait az Aspose.PDF for .NET használatával?

 V: Igen, a PDF-dokumentumok XMP-metaadatait programozottan módosíthatja az Aspose.PDF for .NET használatával. Hozzáférhet a`Info` tulajdona a`Document` objektum, amely hozzáférést biztosít az XMP metaadat tulajdonságaihoz. Ezután frissítheti ezen tulajdonságok értékeit a PDF-dokumentum XMP-metaadatainak módosításához.

#### K: Kibonthatok egyéni XMP-metaadat-tulajdonságokat egy PDF-dokumentumból az Aspose.PDF for .NET használatával?

 V: Igen, az Aspose.PDF for .NET használatával kinyerhet egyéni XMP-metaadat-tulajdonságokat egy PDF-dokumentumból. Használhatja a`Metadata` tulajdona a`Document`objektum, amely hozzáférést biztosít a PDF-dokumentum összes XMP-metaadat-tulajdonságához. Ezután kibonthatja az egyéni tulajdonságokat, és szükség szerint használhatja azok értékeit.