---
title: Keressen és szerezzen szöveges oldalt PDF-fájlban
linktitle: Keressen és szerezzen szöveges oldalt PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveget, és hogyan tud lekérni egy adott oldalt PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 430
url: /hu/net/programming-with-text/search-and-get-text-page/
---
## Bevezetés

Előfordult már, hogy konkrét szöveget kell keresnie egy PDF-dokumentumban, és ki kell bontania a további felhasználáshoz? Lehet, hogy olyan alkalmazást készít, amely dokumentumokat dolgoz fel, és pontos adatkinyerést igényel, vagy egyszerűen csak hatékonyan kell elemeznie a PDF-fájlokat. Bármi is legyen az eseted, jó helyen jársz! Ebben az oktatóanyagban azt mutatjuk be, hogyan lehet szöveget keresni és lekérni egy oldalról egy PDF-fájlban az Aspose.PDF for .NET használatával. Akár kezdő, akár tapasztalt fejlesztő vagy, ez az útmutató minden lépésen végigvezeti Önt társalgási és vonzó módon. Tekerésre készen állsz? Kezdjük is!

## Előfeltételek

Mielőtt belevágnánk a kódolásba, győződjünk meg arról, hogy mindennel rendelkezik, amire szüksége van:

1.  Aspose.PDF for .NET Library: Letöltheti innen[itt](https://releases.aspose.com/pdf/net/) vagy szerezzen be egy ingyenes próbaverziót ugyanarról a linkről. A vásárláshoz menjen a[Aspose üzlet](https://purchase.aspose.com/buy).
2. .NET-keretrendszer: Szüksége lesz egy működő .NET-fejlesztői környezetre, például a Visual Studiora.
3. PDF-fájl: Szüksége lesz egy minta PDF-fájlra, amelyben kereshetünk és kibonthatjuk a szöveget. Ebben az oktatóanyagban tegyük fel, hogy a fájl neve van`SearchAndGetTextPage.pdf`.

## Csomagok importálása

Először is importálnunk kell a szükséges névtereket az Aspose.PDF for .NET-hez való használatához. Győződjön meg arról, hogy ezek szerepelnek a kód tetején.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Most, hogy lefedtük az előfeltételeket, bontsuk le a kódot lépésről lépésre. Minden egyes lépést világosan körvonalaztunk, hogy könnyen követhető legyen.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

Mielőtt kapcsolatba lépne a PDF-fájllal, meg kell határoznia a PDF-dokumentum tárolási útvonalát. Ez biztosítja, hogy a program hozzáférjen a fájlhoz.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Ez annak a mappának az elérési útja, ahol a PDF-fájlokat tárolja. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahol a PDF található.

## 2. lépés: Töltse be a PDF-dokumentumot

A következő lépés a PDF dokumentum betöltése a memóriába, hogy dolgozhasson vele. Íme, hogyan:

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Dokumentum: Ez az Aspose.PDF osztály, amely betölti a PDF fájlt.
- pdfDocument: Az a változó, ahol a PDF-fájl tárolásra kerül a betöltés után.

## 3. lépés: Hozzon létre egy szövegelnyelő objektumot

 A`TextFragmentAbsorber`osztály lehetővé teszi, hogy adott szöveget keressen a PDF-ben. Hozzuk létre ennek az osztálynak egy példányát, hogy megtaláljuk az adott keresési kifejezés összes példányát.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber: Ez az osztály felelős a szöveg megtalálásáért és kinyeréséért a PDF-ből.
- "Ábra": Cserélje ki ezt a PDF-ben keresni kívánt szöveggel.

## 4. lépés: Alkalmazza a szövegelnyelőt a teljes PDF-re

Miután beállította a szövegelnyelőt, meg kell mondania a programnak, hogy keressen a PDF összes oldalán.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept(): Ez a módszer a szövegelnyelőt alkalmazza a PDF-re, minden oldalt beolvasva a megadott szövegért.

## 5. lépés: Töltse le és ismételje meg a kivont szöveget

Most, hogy beszkenneltük a PDF-fájlt, ideje lekérni és megjeleníteni az eredményeket. Végignézzük a kivont szövegrészleteket.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection: Ez a gyűjtemény tartalmazza a szövegelnyelő által talált szövegrészletek összes példányát.

## 6. lépés: Végezzen hurkot az egyes töredékeken és vonja ki az adatokat

Most végignézzük a`textFragmentCollection` és kivonja az egyes szövegszegmensek különféle tulajdonságait, például a helyzetét, a betűtípus részleteit és a színét.

```csharp
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

- Szövegtöredék: Minden töredék a talált szöveg egy részét tartalmazza.
- Szövegszegmens: Minden töredék több szegmensből állhat, amelyek a szöveg különböző részeit képviselik.
- TextState: Ez részletes információkat nyújt a szöveg betűtípusáról, méretéről és színéről.

Ebben a ciklusban kinyomtatjuk a részleteket, például a tényleges szöveget, annak helyzetét (X és Y koordináták), a betűtípust, azt, hogy a betűtípus be van-e ágyazva a PDF-be, és a szöveg előtér színét.

## Következtetés

És megvan! Az Aspose.PDF for .NET segítségével sikeresen megkeresett és kibontott szöveget egy PDF-fájlból. Hihetetlen, hogy mekkora rugalmasságot tud használni ezzel a könyvtárral. Akár konkrét szöveget kell keresnie egy nagy dokumentumban, akár ki kell bontania, vagy elemeznie kell tulajdonságait, az Aspose.PDF gyerekjáték. Ráadásul az általunk ismertetett kóddal jól felkészült arra, hogy az igényeihez igazítsa. 

## GYIK

### Kereshetek több kifejezésre egyszerre?  
 Igen, több kifejezés létrehozásával módosíthatja a kódot, hogy több kifejezést keressen`TextFragmentAbsorber` tárgyakat.

### Hogyan tudok szöveget kivonni egy adott oldalról?  
 Egy adott oldalt célozhat meg a`TextFragmentAbsorber` egyetlen oldalra a teljes dokumentum helyett. Például:`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Ingyenes az Aspose.PDF for .NET?  
 Az Aspose.PDF kereskedelmi termék, de használhatja a[ingyenes próbaverzió](https://releases.aspose.com/).

### Kivonhatok képeket a PDF-ből az Aspose.PDF segítségével?  
 Igen, az Aspose.PDF lehetővé teszi a képek kinyerését a szöveg mellett. Ellenőrizze a[dokumentáció](https://reference.aspose.com/pdf/net/) további részletekért.

### Mi van, ha további segítségre vagy támogatásra van szükségem?  
 Mindig kaphat segítséget a[Aspose támogatási fórum](https://forum.aspose.com/c/pdf/10).