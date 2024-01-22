---
title: Adja meg a sorközt a PDF-fájlban
linktitle: Adja meg a sorközt a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat meg sorközt PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 510
url: /hu/net/programming-with-text/specify-line-spacing/
---
Ez az oktatóanyag elmagyarázza, hogyan adhat meg sortávolságot PDF-fájlban az Aspose.PDF for .NET használatával. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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
using System.IO;
```

## 3. lépés: Állítsa be a dokumentumkönyvtár elérési útját

 Állítsa be a dokumentumkönyvtár elérési útját a`dataDir` változó:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Töltse be a bemeneti PDF-fájlt

 Töltse be a bemeneti PDF-fájlt a`Document` osztály:

```csharp
Document doc = new Document();
```

## 5. lépés: Hozzon létre TextFormattingOptions

 Hozzon létre egy`TextFormattingOptions` objektumot, és állítsa be a sorköz módot`FullSize`:

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

## 6. lépés: Hozzon létre egy szövegrészletet

 Hozzon létre egy`TextFragment` objektumot, és adja meg a szöveg tartalmát:

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

## 7. lépés: Töltse be a betűtípusfájlt (opcionális)

 Ha egy adott betűtípust szeretne használni a szöveghez, töltse be a TrueType betűtípusfájlt a`FileStream` tárgy:

```csharp
string fontFile = dataDir + "HPSimplified.TTF";
using (FileStream fontStream = File.OpenRead(fontFile))
{
    textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
}
```

 Cserélje ki`"HPSimplified.TTF"` a tényleges font fájlnévvel.

## 8. lépés: Adja meg a szöveg pozícióját és sorközét

 Állítsa be a szövegrészlet pozícióját, és rendelje hozzá a`TextFormattingOptions` hoz`TextState.FormattingOptions` ingatlan:

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

## 9. lépés: Adja hozzá a szöveget a dokumentumhoz

 Adja hozzá a szövegrészletet a dokumentumhoz, akár az a-hoz fűzve`TextBuilder` vagy közvetlenül egy oldalra`Paragraphs` Gyűjtemény:

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

## 10. lépés: Mentse el a kapott PDF-dokumentumot

Mentse el a módosított PDF dokumentumot:

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

 Ügyeljen arra, hogy cserélje ki`"SpecifyLineSpacing_out.pdf"` a kívánt kimeneti fájlnévvel.

### Minta forráskód a sorköz megadásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
// Bemeneti PDF fájl betöltése
Document doc = new Document();
//Hozzon létre TextFormattingOptions-t a LineSpacingMode.FullSize segítségével
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
// Szövegkészítő objektum létrehozása a dokumentum első oldalához
//TextBuilder textBuilder = new TextBuilder(doc.Pages[1]);
// Szövegrészlet létrehozása mintakarakterlánccal
TextFragment textFragment = new TextFragment("Hello world");
if (fontFile != "")
{
	// Töltse be a TrueType betűtípust az adatfolyam objektumba
	using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
	{
		//Állítsa be a betűtípus nevét a szöveges karakterlánchoz
		textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
		// Adja meg a szövegtöredék pozícióját
		textFragment.Position = new Position(100, 600);
		//Állítsa be az aktuális töredék TextFormattingOptions beállítását előre meghatározott értékre (ami a LineSpacingMode.FullSize-re mutat)
		textFragment.TextState.FormattingOptions = formattingOptions;
		// Adja hozzá a szöveget a TextBuilderhez, hogy a PDF-fájl fölé helyezhesse
		//textBuilder.AppendText(textFragment);
		var page = doc.Pages.Add();
		page.Paragraphs.Add(textFragment);
	}
	dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
	// Mentse el a kapott PDF dokumentumot
	doc.Save(dataDir);
}
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan adhat meg sorközt egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a projekt beállításától a módosított dokumentum mentéséig. Most már beépítheti ezt a kódot saját C#-projektjébe, hogy testreszabhassa a PDF-fájlok szövegének sorközét.

### GYIK

#### K: Mi a célja a „Sorköz megadása a PDF-fájlban” oktatóanyagnak?

V: A "Sorköz megadása PDF-fájlban" oktatóanyag célja, hogy eligazítsa a felhasználókat a .NET-hez készült Aspose.PDF könyvtár használatával a szöveg sorközének testreszabásához a PDF-dokumentumban. Az oktatóanyag lépésenkénti utasításokat és C# kódmintákat tartalmaz a folyamat bemutatásához.

#### K: Hogyan segít ez az oktatóanyag a sortávolság meghatározásában egy PDF-dokumentumban?

V: Ez az oktatóanyag segít a felhasználóknak megérteni, hogyan használhatják ki az Aspose.PDF for .NET képességeit a szöveg sorközének megadásához egy PDF-dokumentumban. A megadott lépések és kódpéldák követésével a felhasználók saját igényeiknek megfelelően módosíthatják a sorközt.

#### K: Milyen előfeltételek szükségesek az oktatóanyag követéséhez?

V: Mielőtt elkezdené az oktatóanyagot, ismernie kell a C# programozási nyelvet. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat. Beszerezheti az Aspose webhelyéről, vagy telepítheti projektjébe a NuGet segítségével.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: A kezdéshez hozzon létre egy új C# projektet az előnyben részesített integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ez lehetővé teszi a könyvtár funkcióinak kihasználását a PDF-dokumentumok kezeléséhez és a sorközök testreszabásához.

#### K: Használhatom ezt az oktatóanyagot sorköz megadására bármilyen típusú szöveghez?

V: Igen, ez az oktatóanyag útmutatást ad arra vonatkozóan, hogy miként adhat meg sorközt a PDF-dokumentum szövegtartalmához az Aspose.PDF for .NET használatával. A mellékelt kódminták segítségével igény szerint állíthatja be a szöveg sorközét.

#### K: Hogyan adhatom meg a sorköz módot az oktatóanyagban?

 V: Az oktatóanyag bemutatja, hogyan kell létrehozni a`TextFormattingOptions` objektumot, és állítsa be`LineSpacing` tulajdonát`TextFormattingOptions.LineSpacingMode.FullSize`. Ez a mód a szövegtartalom teljes sorközét határozza meg.

#### K: Hogyan tölthetek be egy adott betűtípust a szöveghez?

 V: Ha egy adott betűtípust szeretne használni a szöveges tartalomhoz, az oktatóanyag útmutatást ad a TrueType betűtípus-fájl betöltéséhez`FileStream` objektumot, és állítsa be betűtípusként a`TextFragment`. Ez lehetővé teszi a szöveg betűtípusának és sorközének testreszabását.

#### K: Hogyan szabhatom testre a szöveg pozícióját a PDF-dokumentumban?

 V: A szöveg pozíciójának testreszabásához hozzon létre a`TextFragment` objektumot, és állítsa be`Position`tulajdonságot a kívánt koordinátákhoz (X és Y). Ezzel szabályozhatja, hogy a szöveg hova kerüljön a PDF-dokumentumban.

#### K: Alkalmazhatom ezeket a sortávolság-módosításokat meglévő PDF-dokumentumokra?

 V: Igen, módosíthatja a sorközt a meglévő PDF dokumentumokban. Az oktatóanyag bemutatja, hogyan kell létrehozni a`TextFragment` a megadott sortávolsággal és pozícióval, majd adja hozzá egy oldalhoz`Paragraphs` Gyűjtemény.