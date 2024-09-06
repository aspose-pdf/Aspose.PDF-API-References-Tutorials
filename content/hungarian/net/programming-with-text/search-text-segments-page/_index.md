---
title: Szövegszegmensek oldal keresése PDF-fájlban
linktitle: Szövegszegmensek oldal keresése PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveges szegmenseket egy oldalon PDF-fájlban, és hogyan kérheti le azok tulajdonságait az Aspose.PDF for .NET segítségével.
type: docs
weight: 470
url: /hu/net/programming-with-text/search-text-segments-page/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt meghatározott szövegszegmensek kereséséhez a PDF-fájl egy oldalán, és lekérheti azok tulajdonságait. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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

## 3. lépés: Állítsa be a dokumentumkönyvtár elérési útját

 Állítsa be a dokumentumkönyvtár elérési útját a`dataDir` változó:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Töltse be a PDF dokumentumot

 Töltse be a PDF dokumentumot a`Document` osztály:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 Cserélje ki`"SearchTextSegmentsPage.pdf"` a PDF-fájl tényleges nevével.

## 5. lépés: Hozzon létre egy TextFragmentAbsorber-t

 Hozzon létre a`TextFragmentAbsorber` objektumot a bemeneti keresési kifejezés összes példányának megtalálásához:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 Cserélje ki`"text"` a kívánt keresési kifejezéssel.

## 6. lépés: Fogadja el az abszorbert egy adott oldalhoz

Fogadja el az elnyelőt a dokumentum kívánt oldalához:

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 Cserélje ki`2` a kívánt oldalszámmal (1 alapú index).

## 7. lépés: Töltse le a kibontott szövegrészeket

 Szerezze be a kivont szövegszegmenseket a`TextFragments` tulajdona a`TextFragmentAbsorber` objektum:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8. lépés: Lapozzon át a szövegrészeken

Lapozzon át a letöltött szövegszegmenseken, és érje el tulajdonságaikat:

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

Módosítsa a kódot a cikluson belül, hogy szükség esetén további műveleteket hajtson végre az egyes szövegszegmenseken.

### Forráskód minta a Search Text Segments oldalhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// Hozzon létre TextAbsorber objektumot a bemeneti keresési kifejezés összes példányának megtalálásához
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Fogadja el az összes oldal elnyelőjét
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// Szerezze be a kivont szövegrészleteket
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Hurok át a töredékeken
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## Következtetés

Gratulálok! Sikeresen megtanulta, hogyan kereshet meghatározott szövegszegmenseket egy PDF-dokumentum oldalán az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a dokumentum betöltésétől a kivont szövegrészek eléréséig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy speciális szövegszegmens-kereséseket hajtson végre PDF-fájlokban.

### GYIK

#### K: Mi a célja a „Szövegszegmensek oldal keresése PDF-fájlban” oktatóanyagnak?

V: A "Szövegszegmensek keresése a PDF-fájlban" oktatóanyag átfogó útmutatót nyújt az Aspose.PDF könyvtár használatához a .NET-hez a PDF-dokumentum adott oldalán található szövegszegmensek kereséséhez. Tartalmazza a projekt beállításának, a PDF dokumentum betöltésének, a szövegszegmensek keresésének és a tulajdonságaik lekérésének folyamatát C# kóddal.

#### K: Hogyan segít ez az oktatóanyag meghatározott szövegszegmensek keresésében egy PDF-dokumentumban?

V: Ez az oktatóanyag azt a folyamatot mutatja be, amellyel meghatározott szövegszegmenseket kereshet meg és nyerhet ki egy PDF-dokumentum egy adott oldalán. A megadott lépések és kódminták követésével a felhasználók hatékonyan kereshetnek a kívánt szövegszegmensek között, és információkat kaphatnak a tulajdonságaikról.

#### K: Milyen előfeltételek szükségesek az oktatóanyag követéséhez?

V: Mielőtt elkezdené az oktatóanyagot, ismernie kell a C# programozási nyelvet. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy telepítheti projektjébe a NuGet segítségével.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: A kezdéshez hozzon létre egy új C# projektet az előnyben részesített integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ez lehetővé teszi a könyvtár funkcióinak használatát a PDF-dokumentumok keresésére és kezelésére.

#### K: Használhatom ezt az oktatóanyagot meghatározott szövegszegmensek keresésére a PDF bármely oldalán?

V: Igen, ez az oktatóanyag útmutatást nyújt arra vonatkozóan, hogyan kereshet meghatározott szövegszegmenseket a PDF-dokumentum egy kiválasztott oldalán. Útmutatást ad a felhasználóknak a projekt beállításához, a PDF betöltéséhez, valamint az Aspose.PDF könyvtár használatához a kívánt szövegszegmensek tulajdonságainak megkereséséhez és lekéréséhez.

#### K: Hogyan adhatom meg a keresni kívánt szöveget ebben az oktatóanyagban?

 V: A keresni kívánt szöveg megadásához hozzon létre a`TextFragmentAbsorber` objektumot, és állítsa be a keresési paraméterét a`Text` ingatlan. Cserélje ki az alapértelmezettet`"text"` az oktatóprogram kódjában a kívánt keresési kifejezéssel.

#### K: Hogyan kérhetem le a kivont szövegszegmensek tulajdonságait?

Miután elfogadta a`TextFragmentAbsorber` a PDF egy adott oldalához a kivonatolt szövegrészeket a következővel kérheti le`TextFragments` az elnyelő tárgy tulajdonsága. Ez hozzáférést biztosít a szövegrészletek gyűjteményéhez, amelyek mindegyike több szövegszegmenst tartalmaz.

#### K: Testreszabhatom a kódot úgy, hogy minden szövegszegmensen további műveleteket hajtson végre?

V: Abszolút. Az oktatóanyag mintakódja egy ciklust biztosít a lekért szövegszegmensek ismétléséhez. Testreszabhatja a kódot ebben a ciklusban, hogy további műveleteket hajtson végre minden szövegszegmensen, a projekt követelményei alapján.

#### K: Hogyan menthetem el a módosított PDF-dokumentumot a szövegszegmensek kibontása után?

V: Ez az oktatóanyag elsősorban a szövegszegmensek keresésére és tulajdonságaik lekérésére összpontosít. Ha módosítani kívánja a PDF-fájlt, tekintse meg a többi Aspose.PDF dokumentációt, ahol megtudhatja, hogyan kezelheti és mentheti el a dokumentumot sajátos igényei szerint.