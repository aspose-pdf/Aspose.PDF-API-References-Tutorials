---
title: Reguláris kifejezés keresése PDF fájlban
linktitle: Reguláris kifejezés keresése PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet és kérhet le szöveget reguláris kifejezések használatával PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 440
url: /hu/net/programming-with-text/search-regular-expression/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt a PDF-fájlban található reguláris kifejezésnek megfelelő szöveg keresésére és lekérésére. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Keresés reguláris kifejezéssel

 Hozzon létre a`TextFragmentAbsorber` objektumot, és állítsa be a reguláris kifejezés mintáját, hogy megtalálja a mintának megfelelő összes kifejezést:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Mint 1999-2000
```

 Cserélje ki`"\\d{4}-\\d{4}"` a kívánt reguláris kifejezésmintával.

## 5. lépés: Állítsa be a szöveges keresési beállításokat

 Hozzon létre a`TextSearchOptions` objektumot, és állítsa be a`TextSearchOptions` tulajdona a`TextFragmentAbsorber` objektum a reguláris kifejezés használatának engedélyezéséhez:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 6. lépés: Keresés az összes oldalon

Fogadja el az elnyelőt a dokumentum összes oldalán:

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 7. lépés: Töltse le a kivont szövegrészleteket

 Szerezze be a kivont szövegrészleteket a`TextFragments` tulajdona a`TextFragmentAbsorber` objektum:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8. lépés: Lapozzon át a szövegrészleteken

Lapozzon át a letöltött szövegrészleteken, és érje el tulajdonságaikat:

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

### Minta forráskód a Reguláris kifejezés kereséséhez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//Hozzon létre TextAbsorber objektumot a reguláris kifejezésnek megfelelő kifejezések megtalálásához
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Mint 1999-2000
// Állítsa be a szöveges keresési beállítást a reguláris kifejezés használatának megadásához
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
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

Gratulálok! Sikeresen megtanulta, hogyan kereshet és kérhet le olyan szöveget, amely megfelel a reguláris kifejezéseknek egy PDF-dokumentumban az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a dokumentum betöltésétől a kivont szövegrészletek eléréséig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy speciális szöveges kereséseket végezhessen PDF-fájlokban.

### GYIK

#### K: Mi a célja a „Reguláris kifejezés keresése PDF-fájlban” című oktatóanyagnak?

V: A „Reguláris kifejezés keresése PDF-fájlban” című oktatóanyag célja, hogy bemutassa, hogyan használható az Aspose.PDF könyvtár .NET-hez a PDF-fájlban meghatározott reguláris kifejezés-mintának megfelelő szöveg keresésére és kibontására. Az oktatóanyag átfogó útmutatást és minta C# kódot kínál a folyamat bemutatásához.

#### K: Hogyan segít ez az oktatóanyag a szöveg reguláris kifejezésekkel történő keresésében egy PDF-dokumentumban?

V: Ez az oktatóanyag lépésről lépésre bemutatja az Aspose.PDF könyvtár használatát, amellyel szöveges kereséseket végezhet egy PDF-dokumentumban reguláris kifejezésminta alapján. Részletesen leírja, hogyan kell beállítani a projektet, betölteni a PDF-dokumentumot, meghatározni egy reguláris kifejezés-mintát, és lekérni a megfelelő szövegrészleteket.

#### K: Melyek az oktatóanyag követésének előfeltételei?

V: Mielőtt elkezdené ezt az oktatóanyagot, alapvető ismeretekkel kell rendelkeznie a C# programozási nyelvről. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy a NuGet segítségével integrálhatja projektjébe.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: Kezdésként hozzon létre egy új C# projektet a kívánt integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ez lehetővé teszi a könyvtár képességeinek kiaknázását a projekten belül.

#### K: Használhatok reguláris kifejezéseket szöveg keresésére egy PDF-dokumentumban?

 V: Igen, ez az oktatóanyag bemutatja, hogyan lehet reguláris kifejezésekkel szöveget keresni és kivonni egy PDF-dokumentumból. Ez magában foglalja a`TextFragmentAbsorber` osztályt, és adjon meg egy reguláris kifejezésmintát, hogy megtalálja a megadott mintának megfelelő kifejezéseket.

#### K: Hogyan határozhatom meg a reguláris kifejezés mintáját a szöveges kereséshez?

 V: Ha reguláris kifejezésmintát szeretne megadni a szöveges kereséshez, hozzon létre a`TextFragmentAbsorber` objektumot, és állítsa be a mintáját a segítségével`Text` paraméter. Cserélje ki az alapértelmezett mintát`"\\d{4}-\\d{4}"` az oktatóprogram kódjában a kívánt reguláris kifejezésmintával.

#### K: Hogyan engedélyezhetem a reguláris kifejezés használatát a szöveges kereséshez?

 V: A reguláris kifejezések használatát az a. létrehozásával engedélyezheti`TextSearchOptions` objektumot, és állítsa be az értékét`true` . Rendelje hozzá ezt az objektumot a`TextSearchOptions` tulajdona a`TextFragmentAbsorber` példa. Ez biztosítja, hogy a rendszer a reguláris kifejezésmintát alkalmazza a szöveges keresés során.

#### K: Lekérhetek olyan szövegrészleteket, amelyek megfelelnek a reguláris kifejezés mintájának?

 V: Abszolút. Miután alkalmazta a reguláris kifejezésre vonatkozó keresést a PDF-dokumentumban, a kivonatolt szövegrészleteket a következővel kérheti le`TextFragments` tulajdona a`TextFragmentAbsorber` objektum. Ezek a szövegtöredékek a megadott reguláris kifejezésmintának megfelelő szövegszegmenseket tartalmazzák.

#### K: Mihez férhetek hozzá a visszakeresett szövegrészletekből?

V: A visszakeresett szövegrészletekből különféle tulajdonságokat érhet el, mint például az egyező szövegtartalom, pozíció (X és Y koordináták), betűtípus-információk (név, méret, szín) és egyebek. Az oktatóanyag ciklusában található mintakód bemutatja, hogyan lehet elérni és megjeleníteni ezeket a tulajdonságokat.

#### K: Hogyan szabhatom testre a műveleteket a kivont szövegrészleteken?

V: A kicsomagolt szövegrészletek birtokában testreszabhatja a kódot a cikluson belül, hogy további műveleteket hajtson végre minden egyes szövegrészleten. Ez magában foglalhatja a kivonatolt szöveg mentését, a minták elemzését vagy a formázási módosítások végrehajtását az Ön igényei alapján.