---
title: Tájolás módosítása
linktitle: Tájolás módosítása
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a PDF oldal tájolásának megváltoztatásához az Aspose.PDF for .NET segítségével. Könnyen követhető és megvalósítható a projektekben.
type: docs
weight: 10
url: /hu/net/programming-with-pdf-pages/change-orientation/
---
## Bevezetés

Előfordult már, hogy olyan PDF-fájllal küszködött, ahol az oldal tájolása éppen... ki van kapcsolva? Lehet, hogy olyan dokumentummal van dolgod, amelyet hibásan szkennettek be vagy hoztak létre, és az oldalakat el kell forgatni, hogy értelmet kapjanak. Szerencsére a .NET-hez készült Aspose.PDF egyszerű és hatékony módot kínál a PDF-fájlok bármilyen elképzelhető módon történő manipulálására – beleértve az oldalak tájolásának megváltoztatását is. Akár állóról fekvőre szeretne váltani, akár fordítva, ez az útmutató lépésről lépésre végigvezeti a folyamaton.

Tehát, ha készen áll arra, hogy belemerüljön, és könnyedén forgatja a PDF-oldalakat, kezdjük!

## Előfeltételek

Mielőtt belemennénk az oldaltájolás megváltoztatásának részleteibe a PDF-fájlban, nézzük meg gyorsan, hogy mire lesz szükséged:

-  Aspose.PDF for .NET: Győződjön meg arról, hogy telepítette a .NET Aspose.PDF könyvtárát. Ha nem, akkor megteheti[töltse le itt](https://releases.aspose.com/pdf/net/).
- .NET fejlesztői környezet: Használhatja a Visual Studio, a JetBrains Rider vagy bármely előnyben részesített IDE-t a .NET-tel való munkához.
- Alapvető C# ismerete: Bár ez az útmutató egyszerű, a C# néhány alapvető ismerete még könnyebbé teszi a követést.
- PDF-fájl: Az alábbi példa feltételezi, hogy több oldalas PDF-fájlja van. Ha nincs kéznél, hozzon létre vagy töltsön le egy PDF-mintát a munkához.

 Ha még csak most kezdi, kipróbálhatja az Aspose.PDF fájlt a[ingyenes ideiglenes licenc](https://purchase.aspose.com/temporary-license/) mielőtt úgy döntene[vásárolja meg a teljes verziót](https://purchase.aspose.com/buy).

## Névterek importálása

Mielőtt módosítani tudná az oldalak tájolását a PDF-ben, importálnia kell a szükséges névtereket a C#-projektbe. Győződjön meg arról, hogy rendelkezik az alábbiakkal:

```csharp
using System.IO;
using Aspose.Pdf;
```

Ezzel az importáltal ugorjunk bele az oktatóanyag fő részébe.

## 1. lépés: Töltse be a PDF-dokumentumot

 Az első dolog, amit tennünk kell, hogy betöltsük a módosítani kívánt PDF-fájlt. Használhatja a`Document` osztályt az Aspose.PDF névtérből a PDF megnyitásához.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Ez a sor betölti a PDF-fájlt a megadott könyvtárból. Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a fájl tényleges elérési útjával. A`"input.pdf"` az a PDF, amelynek tájolását módosítani szeretné.

## 2. lépés: Lapozzon át minden oldalon

 Most, hogy a dokumentum betöltődött, lapozzuk át a PDF minden oldalát. Használjuk a`foreach` hurkot, hogy végigmenjen minden oldalon, így mindegyikre alkalmazhatjuk a tájolás módosítását.

```csharp
foreach (Page page in doc.Pages)
{
    // Manipuláljon minden oldalt
}
```

Ez a ciklus végighalad a dokumentum összes oldalán.

## 3. lépés: Szerezze be az oldal MediaBox-ját

 A PDF minden oldalán található egy`MediaBox` amely meghatározza az oldal határait. Ehhez hozzá kell férnünk az aktuális tájolás meghatározásához és módosításához.

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

 A`MediaBox` megadja az oldal méreteit, például szélességét, magasságát és elhelyezkedését.

## 4. lépés: Cserélje fel a szélességet és a magasságot

Ha az oldal tájolását állóról fekvőre vagy fekvőről állóra kívánja változtatni, egyszerűen felcseréljük a szélesség és magasság értékeket. Ez a lépés az oldal méreteit állítja be.

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

Ez a kód felcseréli a magasságot és a szélességet, és áthelyezi a bal alsó sarkot (`LLY`), hogy a tartalom elforgatás után szépen illeszkedjen.

## 5. lépés: Frissítse a MediaBoxot és a CropBoxot

Most, hogy megvan az új magasság és szélesség, alkalmazzuk a módosításokat az oldalra`MediaBox` és`CropBox` . A`CropBox` elengedhetetlen, ha az eredeti dokumentum egy készlettel rendelkezett, biztosítva a teljes oldal helyes megjelenítését.

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

Ez a lépés átméretezi az oldalt az újonnan kiszámított méretek alapján.

## 6. lépés: Forgassa el az oldalt

Végül beállítjuk az oldal elforgatási szögét. Az Aspose.PDF ezt rendkívül egyszerűvé teszi. Az oldalt 90 fokkal elforgathatjuk, hogy állóról fekvőre válthassunk, vagy fordítva.

```csharp
page.Rotate = Rotation.on90;
```

Ez a kód 90 fokkal elforgatja az oldalt, és a kívánt tájolásba fordítja.

## 7. lépés: Mentse el a kimeneti PDF-fájlt

Miután a tájolási változtatásokat az összes oldalon alkalmaztuk, a módosított dokumentumot egy új fájlba mentjük. 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

 Győződjön meg róla, hogy új fájlnevet ad meg (ebben az esetben`ChangeOrientation_out.pdf`) a kimenet mentéséhez. Így nem írja felül az eredeti fájlt.

### Következtetés

És megvan! A PDF-fájlok oldaltájolásának megváltoztatása az Aspose.PDF for .NET használatával egyszerű, mint a dokumentum betöltése, lapozás, a MediaBox beállítása és a frissített fájl mentése. Akár rosszul szkennelt dokumentumról van szó, akár az oldalak elforgatására van szüksége a formázási igényeinek megfelelően, ez a lépésenkénti útmutató biztosan megtalálja a választ.

## GYIK

### Elforgathatok bizonyos oldalakat a PDF összes oldala helyett?  
Igen, módosíthatja a ciklust úgy, hogy bizonyos oldalakat célozzon meg az indexük használatával, ahelyett, hogy az összes oldalt végigpörgetné.

###  Mi az a`MediaBox`?  
 A`MediaBox` meghatározza a PDF-fájlban lévő oldal méretét és alakját. Ide kerül az oldal tartalma.

### Működik az Aspose.PDF for .NET más fájlformátumokkal?  
Igen, az Aspose.PDF számos fájlformátumot képes kezelni, például HTML, XML, XPS stb.

### Létezik az Aspose.PDF ingyenes verziója .NET-hez?  
 Igen, kezdheti a[ingyenes próbaverzió](https://releases.aspose.com/) vagy kérjen a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).

### Visszavonhatom a módosításokat a mentés után?  
dokumentum mentése után a változtatások véglegesek. Ügyeljen arra, hogy az eredeti fájl másolatán dolgozzon, vagy készítsen biztonsági másolatot.