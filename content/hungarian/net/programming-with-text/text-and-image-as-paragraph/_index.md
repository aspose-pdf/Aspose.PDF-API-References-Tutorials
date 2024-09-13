---
title: Szöveg és kép Bekezdésként PDF-fájlban
linktitle: Szöveg és kép Bekezdésként PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat szöveget és képet sorközi bekezdésként PDF-fájlhoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 530
url: /hu/net/programming-with-text/text-and-image-as-paragraph/
---
Ez az oktatóanyag elmagyarázza, hogyan adhat hozzá szöveget és képet sorközi bekezdésként PDF-fájlhoz az Aspose.PDF for .NET használatával. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

## Előfeltételek

Mielőtt folytatná az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következőkkel:

- C# programozási nyelv alapismerete.
- Aspose.PDF for .NET könyvtár telepítve. Beszerezheti az Aspose webhelyéről, vagy a NuGet segítségével telepítheti a projektbe.

## 1. lépés: Állítsa be a projektet

Kezdje azzal, hogy hozzon létre egy új C# projektet a kívánt integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket

Adja hozzá a következőket direktívák használatával a C# fájl elejéhez a szükséges névterek importálásához:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## 3. lépés: Állítsa be a dokumentumkönyvtár elérési útját

 Állítsa be a dokumentumkönyvtár elérési útját a`dataDir` változó:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Hozzon létre egy új dokumentumot és oldalt

 Hozzon létre egy újat`Document` objektumot, és adjon hozzá egy oldalt az oldalgyűjteményéhez:

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 5. lépés: Hozzon létre egy szövegtöredéket, és adja hozzá bekezdésként

 Hozzon létre a`TextFragment` objektumot, és adja hozzá az oldal bekezdésgyűjteményéhez:

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## 6. lépés: Adjon hozzá egy képet sorközi bekezdésként

 Hozzon létre egy`Aspose.Pdf.Image` objektumot, és állítsa be sorközi bekezdésként, hogy az közvetlenül az előző bekezdés után jelenjen meg:

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // Opcionális: Állítsa be a kép magasságát
image.FixWidth = 100; // Opcionális: Állítsa be a kép szélességét
page.Paragraphs.Add(image);
```

 Cserélje ki`"aspose-logo.jpg"` a tényleges képfájlnévvel, és tetszés szerint állítsa be az opcionális kép magasságát és szélességét.

## 7. lépés: Adjon hozzá egy másik szövegtöredéket sorközi bekezdésként

 Inicializálja újra a`TextFragment` eltérő tartalmú objektum, és adja hozzá soron belüli bekezdésként:

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## 8. lépés: Mentse el a PDF dokumentumot

Mentse el a módosított PDF dokumentumot:

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 Ügyeljen arra, hogy cserélje ki`"TextAndImageAsParagraph_out.pdf"` a kívánt kimeneti fájlnévvel.

### Minta forráskód a szöveg és kép mint bekezdéshez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Példányos dokumentum példány
Document doc = new Document();
// Oldal hozzáadása a Dokumentumpéldány oldalgyűjteményéhez
Page page = doc.Pages.Add();
// TextFragmnet létrehozása
TextFragment text = new TextFragment("Hello World.. ");
// Szövegrészlet hozzáadása az Oldal objektum bekezdésgyűjteményéhez
page.Paragraphs.Add(text);
// Hozzon létre egy képpéldányt
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Állítsa be a képet sorközi bekezdésként, hogy közvetlenül utána jelenjen meg
// Az előző bekezdés objektum (TextFragment)
image.IsInLineParagraph = true;
// Adja meg a képfájl elérési útját
image.File = dataDir + "aspose-logo.jpg";
// Kép magasságának beállítása (opcionális)
image.FixHeight = 30;
// Képszélesség beállítása (opcionális)
image.FixWidth = 100;
// Kép hozzáadása az oldalobjektum bekezdésgyűjteményéhez
page.Paragraphs.Add(image);
// Inicializálja újra a TextFragment objektumot különböző tartalommal
text = new TextFragment(" Hello Again..");
// A TextFragment beállítása sorközi bekezdésként
text.IsInLineParagraph = true;
// Újonnan létrehozott TextFragment hozzáadása az oldal bekezdésgyűjteményéhez
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálok! Sikeresen megtanulta, hogyan adhat szöveget és képet sorközi bekezdésként egy PDF-dokumentumhoz az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a projekt beállításától a módosított dokumentum mentéséig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy testreszabhassa a PDF-fájlok szövegének és képeinek elrendezését.

### GYIK

#### K: Mi a "Szöveg és kép mint bekezdés PDF-fájlban" oktatóanyag célja?

V: A "Szöveg és kép bekezdésként PDF-fájlban" oktatóanyag célja, hogy eligazítsa a felhasználókat, hogyan adhatnak hozzá szöveget és képeket sorközi bekezdésként egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Az oktatóanyag lépésenkénti utasításokat és C# kódmintákat tartalmaz a folyamat bemutatásához.

#### K: Hogyan segít ez az oktatóanyag szövegek és képek sorközi bekezdésként történő hozzáadásához?

V: Ez az oktatóanyag segít a felhasználóknak megérteni, hogyan használhatják az Aspose.PDF for .NET fájlt, hogy szöveget és képeket is beépíthessenek sorközi bekezdésként egy PDF-dokumentumba. A megadott lépések és kódpéldák követésével a felhasználók szöveget és képeket kombináló egyéni elrendezésű PDF-fájlokat hozhatnak létre.

#### K: Milyen előfeltételek szükségesek az oktatóanyag követéséhez?

V: Mielőtt elkezdené az oktatóanyagot, ismernie kell a C# programozási nyelvet. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy telepítheti projektjébe a NuGet segítségével.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: Kezdésként hozzon létre egy új C# projektet a kívánt integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ez lehetővé teszi a könyvtár funkcióinak használatát a PDF-dokumentumok, szövegtöredékek és képek kezelésére.

#### K: Használhatom ezt az oktatóanyagot több szöveges és képi bekezdés hozzáadására egy PDF-fájlhoz?

V: Igen, a megadott kódminták segítségével több szöveges és képi bekezdést is hozzáadhat ugyanabban a PDF-dokumentumban. Ez az oktatóanyag bemutatja, hogyan hozható létre sorközi bekezdések, amelyek megkönnyítik a szövegek és képek különböző kombinációinak beillesztését.

#### K: Hogyan határozhatom meg a szöveges bekezdések és képek tartalmát és megjelenését?

 V: Az oktatóanyag bemutatja, hogyan kell létrehozni`TextFragment`objektumok szöveges bekezdések ábrázolására és`Aspose.Pdf.Image` tárgyakat a képek ábrázolására. A mellékelt kódminták segítségével testreszabhatja a szöveg és a képek tartalmát, méreteit és megjelenését.

#### K: Módosíthatom a soron belüli bekezdések elrendezését?

 V: Igen, módosíthatja a soron belüli bekezdések elrendezését azáltal, hogy szabályozza azok elhelyezését, méretét és sorrendjét az oldalon. Az oktatóanyag bemutatja, hogyan állíthat be soron belüli attribútumokat, mint pl`IsInLineParagraph`, a szöveges és képi bekezdések elrendezésének szabályozására.

#### K: Hogyan menthetem el a módosított PDF dokumentumot?

 V: A módosított PDF dokumentum mentéséhez használhatja a`Save` módszere a`Document` objektum. Az oktatóanyag kódmintákat tartalmaz, amelyek bemutatják, hogyan kell menteni az eredményül kapott PDF-dokumentumot.