---
title: Tájolás módosítása
linktitle: Tájolás módosítása
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a PDF oldal tájolásának megváltoztatásához az Aspose.PDF for .NET segítségével. Könnyen követhető és megvalósítható a projektekben.
type: docs
weight: 10
url: /hu/net/programming-with-pdf-pages/change-orientation/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a PDF-dokumentumok oldaltájolásának megváltoztatásának folyamatán az Aspose.PDF for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Az oktatóanyag végén tudni fogja, hogyan módosíthatja PDF-dokumentumai oldaltájolását az Aspose.PDF for .NET használatával.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Alapszintű C# programozási nyelv ismerete
- Aspose.PDF for .NET telepítve a fejlesztői környezetbe

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahol a bemeneti PDF-fájl található, és ahová menteni szeretné a módosított kimeneti PDF-fájlt. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a PDF dokumentumot
 Ezután betöltheti a PDF dokumentumot a bemeneti fájlból a`Document` osztályú Aspose.PDF. Ügyeljen arra, hogy a PDF-fájl helyes elérési útját adja meg.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3. lépés: Módosítsa az oldal tájolását
Most végigmegyünk a dokumentum minden oldalán, és megváltoztatjuk a tájolását. Minden oldalnál módosítjuk a médiadoboz méreteit (`MediaBox`) a szélesség és magasság felcserélésével, majd a médiadoboz koordinátáit állítjuk be az oldal helyzetének megőrzéséhez. Végül az oldalelforgatást 90 fokra állítjuk.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## 4. lépés: Mentse el a módosított PDF dokumentumot
 Végül a módosított PDF dokumentumot kimeneti fájlba mentheti a`Save()` módszere a`Document`osztály. Ügyeljen arra, hogy a megfelelő elérési utat és fájlnevet adja meg.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Forráskód minta a Tájolás módosításához az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Felfelé kell mozgatnunk az oldalt, hogy kompenzáljuk az oldalméret változását
	// (az oldal alsó széle 0,0 és az információ általában a
	// Az oldal tetejére. Ezért mozgatjuk a szerelmes szélét felfelé a különbségre
	// Régi és új magasság.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Néha be kell állítanunk a CropBoxot is (ha az eredeti fájlban volt beállítva)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Az oldal elforgatási szögének beállítása
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Mentse a kimeneti fájlt
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet megváltoztatni egy PDF-dokumentum oldaltájolását az Aspose.PDF for .NET használatával. A fent vázolt lépések követésével könnyedén megvalósíthatja ezt a funkciót saját projektjeiben. Nyugodtan fedezze fel az Aspose.PDF dokumentációt, hogy további hasznos funkciókat fedezzen fel a PDF-fájlokkal való munkavégzéshez.

### GYIK

#### K: Mi a célja az oldaltájolás megváltoztatásának egy PDF-dokumentumban?

V: Az oldal tájolásának megváltoztatása egy PDF dokumentumban lehetővé teszi az oldal tartalmának 90 fokkal történő elforgatását. Ez olyan esetekben lehet hasznos, amikor az eredeti tartalmat más tájolásban kell megjeleníteni vagy kinyomtatni, például át kell váltani álló módról fekvő módra vagy fordítva.

#### K: Módosíthatom bizonyos oldalak tájolását a PDF-dokumentumban?

 V: Igen, módosíthatja a PDF dokumentum egyes oldalainak tájolását. A megadott C# forráskódban a`foreach` A ciklus a dokumentum egyes oldalain való végighaladásra és a tájolás megváltoztatására szolgál. Ha csak bizonyos oldalak tájolását szeretné megváltoztatni, módosíthatja a hurkot, hogy az adott oldalakat oldalszámuk vagy egyéb kritériumok alapján célozza meg.

#### K: Az oldal tájolásának megváltoztatása befolyásolja a tartalom elrendezését az oldalon?

V: Igen, az oldal tájolásának megváltoztatása hatással lesz a tartalom elrendezésére az oldalon. A tartalom 90 fokkal elforgatásra kerül, az oldal szélessége és magassága felcserélődik. Ennek eredményeként a tartalom elhelyezése és igazítása az oldalon megváltozhat.

#### K: Elforgathatom az oldalt 90 foknál eltérő szögben?

 V: A mellékelt C# forráskódban az oldalelforgatás 90 fokra van állítva a használatával`page.Rotate = Rotate.on90;` . Szükség esetén azonban módosíthatja az elforgatási szöget más értékekre. Például használhatja`Rotate.on180` az oldal 180 fokkal történő elforgatásához vagy`Rotate.on270` 270 fokkal elforgatni.

#### K: Hogyan kezelhetem az oldal tartalmát, amely túlcsordul a tájolás megváltoztatása után?

V: Az oldal tájolásának megváltoztatásakor az oldal méretei megváltozhatnak, ami tartalom túlcsordulást eredményezhet. Ennek kezeléséhez szükség lehet az oldalon lévő tartalom elrendezésének és formázásának módosítására. Használhatja az Aspose.PDF for .NET szolgáltatásait, például az elemek átméretezését, a margók módosítását vagy a tartalom átszervezését, hogy az oldal tartalma megfelelően illeszkedjen a tájolás megváltoztatása után.