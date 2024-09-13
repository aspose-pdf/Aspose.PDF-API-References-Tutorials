---
title: Keressen és szerezzen szöveges oldalt PDF-fájlban
linktitle: Keressen és szerezzen szöveges oldalt PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveget, és hogyan tud lekérni egy adott oldalt PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 430
url: /hu/net/programming-with-text/search-and-get-text-page/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt a PDF-fájl egy adott oldaláról történő kereséshez és szöveg lekéréséhez. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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
```

## 3. lépés: Töltse be a PDF dokumentumot

 Állítsa be a PDF-dokumentumkönyvtár elérési útját, és töltse be a dokumentumot a segítségével`Document` osztály:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Szöveg keresése és kibontása egy oldalról

 Hozzon létre a`TextFragmentAbsorber`objektumot, hogy megtalálja a bemeneti keresési kifejezés összes előfordulását egy adott oldalon:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 Cserélje ki`"Figure"` a keresni kívánt szöveggel.

## 5. lépés: Keresés egy adott oldalon

Fogadja el az elnyelőt a dokumentum egy adott oldalához:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 6. lépés: szerezze be a kivont szövegrészleteket

 Szerezze be a kivont szövegrészleteket a`TextFragments` tulajdona a`TextFragmentAbsorber` objektum:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 7. lépés: Keresse át a szövegrészleteket és szegmenseket

Keresse át a kapott szövegrészleteket és szegmenseiket, és érje el tulajdonságaikat:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

Módosíthatja a kódot a cikluson belül, hogy további műveleteket hajtson végre az egyes szövegszegmenseken.

### Minta forráskód a Search and Get Text oldalhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// Hozzon létre TextAbsorber objektumot a bemeneti keresési kifejezés összes példányának megtalálásához
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// Fogadja el az összes oldal elnyelőjét
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Szerezze be a kivont szövegrészleteket
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Hurok át a töredékeken
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## Következtetés

Gratulálok! Sikeresen megtanulta, hogyan lehet szöveget keresni és lekérni egy PDF-dokumentum adott oldaláról az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a dokumentum betöltésétől a kivont szövegrészek eléréséig. Most beépítheti

### GYIK

#### K: Mi a "Szöveg oldal keresése és lekérése" oktatóanyag célja?

V: A "Szövegoldal keresése és lekérése" című oktatóanyag célja, hogy bemutassa, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez a PDF-fájl egy adott oldalának szövegének keresésére és lekérésére. Az oktatóanyag részletes utasításokat és minta C# kódot tartalmaz a folyamat bemutatásához.

#### K: Hogyan segít ez az oktatóanyag a szöveg kinyerésében egy PDF-dokumentum adott oldaláról?

V: Ez az oktatóanyag végigvezeti Önt a PDF-dokumentum egy adott oldaláról az Aspose.PDF könyvtár használatával történő szöveg kinyerésének folyamatán. Felvázolja a szükséges lépéseket, és C# kódot biztosít egy megadott szöveges kifejezés kereséséhez a kiválasztott oldalon, és a kapcsolódó szövegszegmensek lekéréséhez.

#### K: Melyek az oktatóanyag követésének előfeltételei?

V: Mielőtt elkezdené ezt az oktatóanyagot, alapvető ismeretekkel kell rendelkeznie a C# programozási nyelvről. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy a NuGet segítségével integrálhatja projektjébe.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: A kezdéshez hozzon létre egy új C# projektet az előnyben részesített integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ez lehetővé teszi a könyvtár képességeinek kihasználását a projektben.

#### K: Kereshetek szöveget a PDF-dokumentum egy adott oldalán?

V: Igen, ez az oktatóanyag bemutatja, hogyan kereshet szöveget egy PDF-dokumentum egy adott oldalán. Ez magában foglalja a`TextFragmentAbsorber` osztályt, hogy megkeresse egy adott szöveges kifejezés előfordulását a kiválasztott oldalon.

#### K: Hogyan érhetem el az adott oldalról kivont szövegszegmenseket?

 V: Miután megkereste a szöveget a kijelölt oldalon, a kivonatolt szövegszegmenseket a segítségével érheti el`TextSegments` tulajdona a`TextFragment` objektum. Ez az ingatlan hozzáférést biztosít a gyűjteményhez`TextSegment` objektumok, amelyek a kivont szöveget és a kapcsolódó információkat tartalmazzák.

#### K: Milyen információkat kérhetek le a kivont szövegrészekből?

V: A kivont szövegszegmensekből különféle részleteket kérhet le, beleértve a szöveg tartalmát, pozícióját (X és Y koordináták), betűtípus-információkat (név, méret, szín stb.). Az oktatóanyag mintakódja bemutatja, hogyan lehet elérni és kinyomtatni ezeket a részleteket az egyes szövegszegmensekhez.

#### K: Végezhetek egyéni műveleteket a kibontott szövegszegmenseken?

V: Természetesen. Miután megvan a kibontott szövegszegmens, testreszabhatja a kódot a cikluson belül, hogy további műveleteket hajtson végre az egyes szegmenseken. Ez magában foglalhatja a kivonatolt szöveg mentését, a szövegminták elemzését vagy a formázási módosítások alkalmazását.