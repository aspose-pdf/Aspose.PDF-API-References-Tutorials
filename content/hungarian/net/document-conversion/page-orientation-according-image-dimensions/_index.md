---
title: Oldaltájolás a képméretek szerint
linktitle: Oldaltájolás a képméretek szerint
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre az oldal tájolásának beállításához a kép mérete alapján az Aspose.PDF for .NET segítségével.
type: docs
weight: 80
url: /hu/net/document-conversion/page-orientation-according-image-dimensions/
---
Ebben az oktatóanyagban végigvezetjük az oldaltájolás beállításának folyamatán a kép méretei alapján az Aspose.PDF for .NET használatával. Végigpörgetjük az adott könyvtárban található JPG képek listáját, és automatikusan beállítjuk az oldal tájolását az egyes képek szélessége alapján. Ennek eléréséhez kövesse az alábbi lépéseket.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: JPG képek böngészése
Ennél a lépésnél meg fogjuk böngészni az adott könyvtárban található összes JPG képet. Kövesse az alábbi kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy új PDF dokumentumot
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Lekérheti az összes JPG fájl nevét egy adott könyvtárban
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol a JPG képei találhatók.

## 2. lépés: Az oldal és a kép létrehozása
JPG fájlok böngészése után minden fájlhoz készítünk egy oldalt és egy képet. Használja a következő kódot:

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Hozzon létre egy oldalobjektumot
Aspose.Pdf.Page page = doc.Pages.Add();

// Hozzon létre egy Image objektumot
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## 3. lépés: A képméretek ellenőrzése
Most nézzük meg az egyes képek méreteit az oldal tájolásának meghatározásához. Használja a következő kódot:

```csharp
// Hozzon létre egy BitMap objektumot, hogy információkat kapjon a képfájlból
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Ellenőrizze, hogy a kép szélessége nagyobb-e, mint az oldal szélessége
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Ha a kép szélessége kisebb, mint az oldal szélessége, állítsa az oldal tájolását állóra
page.PageInfo.IsLandscape = false;
```

## 4. lépés: A kép hozzáadása a PDF dokumentumhoz
A kép méreteinek ellenőrzése után a képet hozzáadjuk a PDF dokumentum bekezdésgyűjteményéhez. Használja a következő kódot:

```csharp
// Adja hozzá a képet a PDF-dokumentum bekezdésgyűjteményéhez
page.Paragraphs.Add(image1);
```

## 5. lépés: Mentse el a PDF fájlt
Miután az összes képet hozzáadtuk a PDF dokumentumhoz, most már menthetjük a kapott PDF fájlt. Íme az utolsó lépés:

```csharp
// Mentse el a PDF fájlt
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a kívánt könyvtárral, ahová menteni szeretné a kimeneti PDF-fájlt.

### Példa forráskód az oldal tájolása képméretek szerint Aspose.PDF for .NET használatával

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Lekérheti az összes JPG fájl nevét egy adott könyvtárban
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Hozzon létre egy oldalobjektumot
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Hozzon létre egy képobjektumot
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Hozzon létre egy BitMap objektumot a képfájl információinak beszerzéséhez
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Ellenőrizze, hogy a képfájl szélessége nagyobb-e, mint az oldal szélessége
	if (myimage.Width > page.PageInfo.Width)
		// Ha a kép szélessége nagyobb, mint az oldal szélessége, állítsa az oldal tájolását Fekvőre
		page.PageInfo.IsLandscape = true;
	else
		// Ha a kép szélessége kisebb, mint az oldal szélessége, állítsa az oldaltájolást Álló értékre
		page.PageInfo.IsLandscape = false;
	// Adja hozzá a képet a PDF-dokumentum bekezdésgyűjteményéhez
	page.Paragraphs.Add(image1);
}
// Mentse el a Pdf fájlt
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Következtetés
Ebben az oktatóanyagban az Aspose.PDF for .NET használatával lépésről lépésre bemutatjuk az oldaltájolás beállítását egy kép mérete alapján. A fent vázolt utasításokat követve most már képesnek kell lennie minden képhez megfelelő oldaltájolású PDF-dokumentumot létrehozni. Ez a funkció akkor hasznos, ha különböző méretű képei vannak, és PDF dokumentumba szeretné beágyazni.

### GYIK

#### K: Használhatok más képformátumokat a JPG helyett az oldal tájolásának beállításához a kép mérete alapján?

V: Igen, a JPG mellett más képformátumokat is használhat, például PNG, BMP vagy GIF, hogy beállítsa az oldaltájolást a kép mérete alapján. A mellékelt kód végigfut az összes ".JPG" kiterjesztésű képfájlon, de módosíthatja, hogy más képformátumokat is tartalmazzon.

#### K: Mi történik, ha egy kép mérete pontosan megegyezik az oldal szélességével?

V: Ha egy kép szélessége pontosan megegyezik az oldal szélességével, az oldal tájolása állóra lesz állítva. A megadott kódban az oldal tájolása csak akkor van fekvőre állítva, ha a kép szélessége nagyobb, mint az oldal szélessége.

#### K: Testreszabhatom az oldaltájolás logikáját konkrét követelmények alapján?

V: Igen, testreszabhatja az oldaltájolás logikáját a konkrét követelmények alapján. Például beállíthat egy küszöbértéket annak meghatározására, hogy az oldal tájolását mikor kell fekvőre vagy állóra állítani. Ezenkívül az oldal tájolásának meghatározásához olyan tényezőket is figyelembe vehet, mint a kép magassága vagy képaránya.

#### K: Hozzáadhatok más tartalmat, például szöveget vagy táblázatokat a PDF-dokumentumhoz a képekkel együtt?

V: Igen, a képekkel együtt más tartalmat, például szöveget vagy táblázatokat is hozzáadhat a PDF-dokumentumhoz. Az Aspose.PDF for .NET funkciók gazdag készletét kínálja a PDF-dokumentumok kezeléséhez, beleértve a szövegek, képek, táblázatok és egyéb elemek hozzáadását az oldalakhoz.