---
title: Szöveg keresése és téglalap rajzolása
linktitle: Szöveg keresése és téglalap rajzolása
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveget PDF-ben, hogyan rajzolhat téglalapokat a talált szöveg köré, és hogyan mentheti el a módosított dokumentumot az Aspose.PDF for .NET segítségével.
type: docs
weight: 460
url: /hu/net/programming-with-text/search-text-and-draw-rectangle/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt egy adott szöveg megkeresésére egy PDF-dokumentumban, rajzoljon egy téglalapot a talált szöveg köré, és hogyan mentse el a módosított dokumentumot. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## 3. lépés: Állítsa be a dokumentumkönyvtár elérési útját

 Állítsa be a dokumentumkönyvtár elérési útját a`dataDir` változó:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Töltse be a PDF dokumentumot

 Töltse be a PDF dokumentumot a`Document` osztály:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Cserélje ki`"SearchAndGetTextFromAll.pdf"` a PDF-fájl tényleges nevével.

## 5. lépés: Hozzon létre egy TextFragmentAbsorber-t

 Hozzon létre egy`TextFragmentAbsorber` objektumot a bemeneti keresési kifejezés összes példányának megtalálásához:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Cserélje ki`@"[\S]+"` a kívánt reguláris kifejezésmintával.

## 6. lépés: Engedélyezze a reguláris kifejezések keresését

 A reguláris kifejezések keresésének engedélyezése a`TextSearchOptions` az abszorber tulajdonságai:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 7. lépés: Keresés az összes oldalon

Fogadja el az elnyelőt a dokumentum összes oldalán:

```csharp
document.Pages.Accept(textAbsorber);
```

## 8. lépés: Rajzolj egy téglalapot a talált szöveg köré

 Hozzon létre egy`PdfContentEditor` objektumot, és a visszakeresett szövegtöredékek között görgessen, és rajzoljon egy téglalapot minden szövegszegmens köré:

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## 9. lépés: Mentse el a módosított dokumentumot

Mentse el a módosított dokumentumot:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Ügyeljen arra, hogy cserélje ki`"SearchTextAndDrawRectangle_out.pdf"` a kívánt kimeneti fájlnévvel.

### Minta forráskód a Szöveg kereséséhez és a Téglalap rajzolásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Hozzon létre TextAbsorber objektumot a reguláris kifejezésnek megfelelő kifejezések megtalálásához
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan kereshet meghatározott szöveget egy PDF-dokumentumban, hogyan rajzoljon téglalapot a talált szöveg köré, és mentse el a módosított dokumentumot az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a projekt beállításától a szükséges műveletek végrehajtásáig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy szöveget manipuláljon és téglalapokat rajzoljon PDF-fájlokba.

### GYIK

#### K: Mi a "Szöveg keresése és téglalap rajzolása" oktatóanyag célja?

V: A "Szöveg keresése és téglalap rajzolása" oktatóanyag célja, hogy végigvezesse a felhasználókat a .NET-hez készült Aspose.PDF könyvtár használatán, hogy konkrét szöveget kereshessenek egy PDF-dokumentumban, téglalapokat rajzoljanak a talált szövegszegmensek köré, és elmentsék a módosított szöveget. dokumentum. Az oktatóanyag részletes utasításokat és C# kódmintákat tartalmaz a folyamat egyes lépéseinek illusztrálására.

#### K: Hogyan segít ez az oktatóanyag téglalapok rajzolásában egy adott szöveg köré egy PDF-dokumentumban?

V: Ez az oktatóanyag átfogó útmutatót nyújt a PDF-dokumentum meghatározott szövegszegmensei körüli téglalapok megkereséséhez és rajzolásához. Bemutatja a projekt beállításának, a PDF-dokumentum betöltésének, a reguláris kifejezések keresésének engedélyezésének, a talált szövegszegmensek köré téglalapok rajzolásának és a módosított PDF mentésének folyamatát.

#### K: Milyen előfeltételek szükségesek az oktatóanyag követéséhez?

V: Mielőtt elkezdené az oktatóanyagot, ismernie kell a C# programozási nyelvet. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy telepítheti projektjébe a NuGet segítségével.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: Kezdje egy új C# projekt létrehozásával a preferált integrált fejlesztői környezetben (IDE). Ezután adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárra a projekthez. Ez lehetővé teszi a könyvtár funkcióinak használatát a PDF dokumentumok kezeléséhez.

#### K: Rajzolhatok téglalapokat adott szöveg köré ennek az oktatóanyagnak a segítségével?

V: Igen, az oktatóanyag a PDF-dokumentum meghatározott szövegszegmensei köré téglalapok rajzolására összpontosít. Bemutatja, hogyan keresheti meg a kívánt szöveget reguláris kifejezések segítségével, hogyan hozhat létre téglalapokat az azonosított szövegszegmensek köré, és hogyan mentheti el a módosított PDF-fájlt.

#### K: Hogyan adhatom meg a keresendő szöveget, és téglalapokat rajzolok köré?

 V: A keresendő szöveg megadásához és téglalapok rajzolásához hozzon létre a`TextFragmentAbsorber` objektumot, és állítsa be a mintáját a segítségével`Text` paraméter. Cserélje ki az alapértelmezett mintát`@"[\S]+"` az oktatóprogram kódjában a kívánt reguláris kifejezésmintával.

#### K: Hogyan engedélyezhetem a reguláris kifejezések keresését a szövegben?

 V: A reguláris kifejezések keresése az a. létrehozásával engedélyezhető`TextSearchOptions` objektumot, és állítsa be az értékét`true` . Rendelje hozzá ezt az objektumot a`TextSearchOptions` tulajdona a`TextFragmentAbsorber` példa. Ez biztosítja, hogy a szöveges keresés során a rendszer a reguláris kifejezésmintát használja.

#### K: Hogyan rajzolhatok téglalapokat a talált szöveg köré?

 V: Miután azonosította a szövegszegmenseket a`TextFragmentAbsorber` , az oktatóanyag ciklust biztosít ezeken a szegmenseken keresztüli ismétléshez. Az oktatóanyag minden szövegszegmenshez bemutatja, hogyan lehet körülötte téglalapot létrehozni a`DrawBox` módszert, és adja meg a téglalap megjelenését.

#### K: Milyen lépésekkel mentheti el a módosított PDF-et rajzolt téglalapokkal?

V: Miután téglalapokat rajzolt a kívánt szövegszegmensek köré, használja a`Document` osztályé`Save` módot a módosított dokumentum mentésére. Az oktatóanyag mintakódja bemutatja, hogyan mentheti el a szerkesztett PDF-fájlt, és hogyan jelenítheti meg a sikerüzenetet.

#### K: Testreszabhatom a rajzolt téglalapok megjelenését?

 V: Igen, testreszabhatja a rajzolt téglalapok megjelenését. Az oktatóanyag mintakódjában a`DrawBox` módszert használják téglalapok létrehozására. Módosíthatja az olyan tulajdonságokat, mint a szín, a stílus és a vastagság a rajzolt téglalapok megjelenésének testreszabásához.