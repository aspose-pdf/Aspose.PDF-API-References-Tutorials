---
title: Keressen és kapjon szöveget
linktitle: Keressen és kapjon szöveget
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveget, és hogyan lehet szöveget lekérni egy PDF-dokumentum összes oldalán az Aspose.PDF for .NET segítségével.
type: docs
weight: 420
url: /hu/net/programming-with-text/search-and-get-text-all/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt a PDF-dokumentum összes oldalán történő kereséshez és szöveg lekéréséhez. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Szöveg keresése és kibontása

 Hozzon létre egy`TextFragmentAbsorber` objektumot a bemeneti keresési kifejezés összes példányának megtalálásához:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Cserélje ki`"text"` a keresni kívánt szöveggel.

## 5. lépés: Keresés az összes oldalon

Fogadja el az elnyelőt a dokumentum összes oldalán:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 6. lépés: szerezze be a kivont szövegrészleteket

Szerezze be a kivont szövegrészleteket a`TextFragments` tulajdona a`TextFragmentAbsorber` tárgy:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 7. lépés: Lapozzon át a szövegrészleteken

Lapozzon át a kapott szövegrészleteken, és érje el tulajdonságaikat:

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

Módosíthatja a kódot a cikluson belül, hogy további műveleteket hajtson végre az egyes szövegrészleteken.

### Minta forráskód a kereséshez és a szöveg lekéréséhez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Hozzon létre TextAbsorber objektumot a bemeneti keresési kifejezés összes példányának megtalálásához
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Fogadja el az összes oldal elnyelőjét
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Szerezze be a kivont szövegrészleteket
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Hurok át a töredékeken
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan lehet szöveget keresni és lekérni egy PDF-dokumentum összes oldalán az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a dokumentum betöltésétől a kivont szövegrészletek eléréséig. Mostantól ezt a kódot beépítheti saját C#-projektjeibe a PDF-fájlok szövegtartalmának elemzéséhez és feldolgozásához.

### GYIK

#### K: Mi a "Keresés és szöveg lekérése" oktatóanyag célja?

V: A "Minden szöveg keresése és lekérése" című oktatóanyag bemutatja, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez a PDF-dokumentum összes oldaláról történő kereséshez és szöveg kibontásához. Az oktatóanyag lépésről lépésre tartalmaz utasításokat, valamint minta C# kódot a szöveges kereséshez és visszakereséshez.

#### K: Hogyan segít ez az oktatóanyag szöveg kinyerésében PDF-dokumentumokból?

V: Ez az oktatóanyag végigvezeti Önt a PDF-dokumentum összes oldaláról történő szöveg kinyerésének folyamatán. Az Aspose.PDF könyvtárat használja bizonyos szöveges kifejezések megkeresésére és a kapcsolódó információk, például a pozíció, a betűtípus tulajdonságai és a színek lekérésére.

#### K: Melyek az oktatóanyag követésének előfeltételei?

V: Mielőtt elkezdené ezt az oktatóanyagot, alapvető ismeretekkel kell rendelkeznie a C# programozási nyelvről. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy a NuGet segítségével integrálhatja projektjébe.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: A kezdéshez hozzon létre egy új C# projektet az előnyben részesített integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ez lehetővé teszi a könyvtár funkcióinak elérését a projektben.

#### K: Hogyan kereshetek meghatározott szöveget egy PDF-dokumentumban?

V: Használhatja a`TextFragmentAbsorber`osztályban, hogy megtalálja egy adott keresési kifejezés előfordulását a PDF-dokumentumban. Az osztály példányának létrehozásával és a célszöveg megadásával a szöveg minden előfordulását rögzítheti.

#### K: Kereshetek szöveget a PDF-dokumentum összes oldalán?

 V: Igen, az oktatóanyag bemutatja, hogyan kereshet szöveget a PDF-dokumentum összes oldalán. A`pdfDocument.Pages.Accept(textFragmentAbsorber)` módszert alkalmazzák az abszorber elfogadására az összes oldalon, lehetővé téve, hogy minden oldalon megkeresse a kívánt szöveget.

#### K: Hogyan férhetek hozzá a kibontott szövegrészletekhez?

 V: Miután megkereste a szöveget, a kivonatolt szövegrészleteket a következővel érheti el`TextFragments` tulajdona a`TextFragmentAbsorber` tárgy. Ez az ingatlan hozzáférést biztosít a gyűjteményhez`TextFragment` objektumok, amelyek a kivont szöveget és a kapcsolódó információkat tartalmazzák.

#### K: Milyen információkat kérhetek le a kivonatolt szövegrészletekből?

V: A kibontott szövegrészletekből különféle részleteket kérhet le, mint például a tényleges szövegtartalom, pozíció (X és Y koordináták), betűtípus-információk (név, méret, szín stb.). Az oktatóanyag mintakódja bemutatja, hogyan lehet elérni és kinyomtatni ezeket a részleteket.

#### K: Végezhetek-e további műveleteket a kibontott szövegrészletekkel?

V: Abszolút. Miután megvan a kibontott szövegrészlet, módosíthatja a kódot a cikluson belül, hogy egyéni műveleteket hajtson végre minden egyes töredéken. Ez magában foglalhatja a kivonatolt szöveg mentését, a szövegminták elemzését vagy a formázási módosítások alkalmazását.