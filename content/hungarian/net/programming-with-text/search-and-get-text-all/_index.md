---
title: Keressen és kapjon szöveget
linktitle: Keressen és kapjon szöveget
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveget, és hogyan lehet szöveget lekérni egy PDF-dokumentum összes oldalán az Aspose.PDF for .NET segítségével.
type: docs
weight: 420
url: /hu/net/programming-with-text/search-and-get-text-all/
---
## Bevezetés

Előfordult már, hogy konkrét szöveget kellett kivonnia egy PDF-ből, de trükkösnek találta? A PDF-fájlok néha zárt tárolóknak tűnhetnek, ami megnehezíti a szükséges információk megszerzését. De itt van a jó hír: az Aspose.PDF for .NET segítségével könnyedén kereshet szöveget, és bármilyen PDF-fájlból visszakereshet. Ez a nagy teljesítményű könyvtár mindent tartalmaz, amire szüksége van a .NET-alkalmazások PDF-fájljainak kezeléséhez, így a szövegek kivonatolása gyerekjáték. Ebben az oktatóanyagban végigvezetjük a PDF-fájlból történő szöveg keresésének és kibontásának folyamatán az Aspose.PDF for .NET használatával. Akár szövegelemző eszközt épít, akár csak automatizálnia kell a PDF-jelentésekből való adatkinyerést, jó helyen jár!

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjön meg arról, hogy mindent beállított:

1. Aspose.PDF for .NET: Le kell töltenie és telepítenie kell az Aspose.PDF for .NET fájlt. A letöltési oldalról szerezheti be[itt](https://releases.aspose.com/pdf/net/).
2. .NET-környezet: Győződjön meg arról, hogy a fejlesztőgépen be van állítva a .NET-keretrendszer vagy a .NET Core.
3. Alapszintű C## ismeretek: A C# ismerete és a .NET projektekkel való munka némi ismerete ajánlott.
4.  PDF-dokumentum: egy minta PDF-fájl, amelyből szöveget kinyerünk. Ebben a példában azt fogjuk használni`SearchAndGetTextFromAll.pdf`.

## Csomagok importálása

Mielőtt bármilyen kódot írna, importálnia kell a szükséges névtereket a projektbe, hogy működjön az Aspose.PDF fájllal.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Ezek a névterek hozzáférést biztosítanak a PDF dokumentum objektum modelljéhez, és lehetővé teszik számunkra a fájlon belüli szövegek kezelését.

Bontsuk le a folyamatot egyszerű lépésekre, hogy könnyedén követhesse.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Először is meg kell adnia annak a könyvtárnak az elérési útját, ahol a PDF található. Ez segít az alkalmazásnak megtalálni azt a fájlt, amelyből ki szeretné bontani a szöveget.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  A`dataDir` változónak arra a könyvtárra kell mutatnia, ahol a`SearchAndGetTextFromAll.pdf` fájl tárolva van.
-  Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal a gépen.

## 2. lépés: Nyissa meg a PDF-dokumentumot

Ezután megnyitjuk a PDF dokumentumot az Aspose.PDF segítségével`Document` objektum.

```csharp
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  Új példányt hozunk létre a`Document` osztályba a PDF teljes fájlútvonalának átadásával.
- Ez betölti a PDF-fájlt a memóriába, és készen áll a feldolgozásra.

## 3. lépés: Hozzon létre egy szövegelnyelőt

 A`TextFragmentAbsorber` Az objektum meghatározott szöveg keresésére szolgál a PDF-ben. Ebben az esetben a „szöveg” szót fogjuk keresni.

```csharp
// Hozzon létre TextAbsorber objektumot a bemeneti keresési kifejezés összes példányának megtalálásához
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  A`TextFragmentAbsorber` a karakterlánccal inicializálódik`"text"`. Ez azt jelenti, hogy megkeresi a „text” szó minden előfordulását a PDF-dokumentumban.

## 4. lépés: Fogadja el az Absorber for All Pages

Most utasítjuk a PDF dokumentumot, hogy fogadja el az elnyelőt, és keresse meg a szöveget az összes oldalán.

```csharp
// Fogadja el az összes oldal elnyelőjét
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  A`Accept` módszert alkalmazzák a dokumentum oldalaira. Ezzel az összes oldalon megkeresi a megadott szöveget.

## 5. lépés: Szövegtöredékek kibontása

Miután az abszorber beszkennelte a dokumentumot, visszakereshetjük a kinyert szövegrészleteket.

```csharp
// Szerezze be a kivont szövegrészleteket
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  A`TextFragments` tulajdona a`TextFragmentAbsorber` a keresési kifejezésnek megfelelő összes szövegrészlet gyűjteményét adja vissza.

## 6. lépés: Ismételje meg a szövegrészleteket

Most, hogy megvan a szövegrészletek gyűjteménye, végignézzük őket, és kibontjuk a részleteket.

```csharp
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

-  A`foreach` ciklus mindegyiken keresztül iterál`TextFragment` a gyűjteményben.
- Az egyes töredékek különféle tulajdonságait nyomtatjuk ki, például a tényleges szöveget, az oldalon elfoglalt helyét, a betűtípus részleteit és a betűméretet.
-  A`XIndent` és`YIndent` A tulajdonságok megadják a PDF-en belüli szövegrészlet pontos koordinátáit.

## Következtetés

És megvan! Néhány sornyi kóddal sikeresen megkerestük és kivontuk a szöveget egy PDF-fájlból az Aspose.PDF for .NET segítségével. Az Aspose.PDF rugalmassága lehetővé teszi a PDF-ek számos módon történő kezelését, így kiváló választás azoknak a fejlesztőknek, akiknek robusztus PDF-megoldásokra van szükségük .NET-környezetekben. Könnyedén kiterjesztheti ezt a példát más szavak keresésére, további részletek kinyerésére, vagy akár a PDF-tartalom módosítására az igényei szerint. Remélhetőleg ez az útmutató világos és egyértelmű megközelítést adott a PDF-ekkel való munkavégzéshez. Próbáld ki saját PDF-eddel!

## GYIK

### Kereshetek több szóra egyszerre?  
 Igen, módosíthatja a`TextFragmentAbsorber` több kifejezés kereséséhez a keresési karakterlánc megfelelő módosításával.

### Mi van akkor, ha a szöveg több sort is átível?  
Az Aspose.PDF akkor is felismeri és kibontja a szöveget, ha az több sort is átível. Ezeket a töredékeket egyenként is kezelheti.

### Hogyan menthetem el a kicsomagolt szöveget fájlba?  
 A kibontott szöveget fájlba írhatja szabványos C# fájl I/O műveletekkel, mint pl`StreamWriter`.

### Támogatja az Aspose.PDF a szöveg kivonatát a beolvasott PDF-ekből?  
Az Aspose.PDF nem támogatja az OCR-t. A beszkennelt PDF-ek esetében szükség van egy OCR-eszközre a szöveg felismeréséhez.

### Hogyan kezelhetem a titkosított PDF-eket?  
Ha a PDF-fájl jelszóval védett, az Aspose.PDF használatával feloldhatja a zárolást, ha megadja a jelszót a dokumentum betöltésekor.