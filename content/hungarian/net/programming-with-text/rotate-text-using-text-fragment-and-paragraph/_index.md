---
title: Szöveg elforgatása szövegtöredék és bekezdés használatával
linktitle: Szöveg elforgatása szövegtöredék és bekezdés használatával
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan forgathat el szöveget szövegrészlet és bekezdés használatával egy PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 400
url: /hu/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Ez az oktatóanyag elmagyarázza, hogyan használható az Aspose.PDF for .NET a szöveg elforgatásához szövegrészlet és bekezdés használatával. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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

## 3. lépés: Hozza létre a PDF dokumentumot

 Inicializálja a`Document` objektum új PDF dokumentum létrehozásához:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Adjon hozzá egy oldalt

 Egy adott oldal lekérése a dokumentumból a`Pages.Add()` módszer:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 5. lépés: Hozzon létre szövegrészleteket

 Több létrehozása`TextFragment` objektumokat, állítsa be szövegüket és tulajdonságaikat, és adja meg az elforgatási szöget:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Igény szerint állítsa be a szöveget, az elforgatási szöget és az egyéb tulajdonságokat.

## 6. lépés: Adjon hozzá szövegrészleteket az oldalhoz

 Adja hozzá a létrehozott szövegrészleteket az oldalhoz úgy, hogy hozzáfűzi őket a`Paragraphs` Gyűjtemény:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## 7. lépés: Mentse el a PDF dokumentumot

 Mentse el a módosított PDF-dokumentumot fájlba a`Save` módszer:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Ügyeljen arra, hogy cserélje ki`"TextFragmentTests_Rotated3_out.pdf"` a kívánt kimeneti fájlnévvel.

### Forráskód minta a Szöveg elforgatásához szövegtöredékekkel és bekezdésekkel az Aspose.PDF segítségével .NET-hez 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentumobjektum inicializálása
Document pdfDocument = new Document();
// Szerezzen be egy adott oldalt
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Szövegrészlet létrehozása
TextFragment textFragment1 = new TextFragment("main text");
// Állítsa be a szöveg tulajdonságait
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Szövegrészlet létrehozása
TextFragment textFragment2 = new TextFragment("rotated text");
// Állítsa be a szöveg tulajdonságait
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Állítsa be a forgatást
textFragment2.TextState.Rotation = 315;
// Szövegrészlet létrehozása
TextFragment textFragment3 = new TextFragment("rotated text");
// Állítsa be a szöveg tulajdonságait
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Állítsa be a forgatást
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Dokumentum mentése
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan forgathat el szöveget szövegrészletek és bekezdések használatával egy PDF-dokumentumban az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a dokumentum létrehozásától a módosított verzió mentéséig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy módosítsa a PDF-fájlok szövegforgatását.

### GYIK

#### K: Mi a célja a "Szöveg forgatása szövegtöredék és bekezdés használatával" oktatóanyag célja?

V: A "Szöveg elforgatása szövegtöredékek és bekezdések használatával" oktatóanyag célja, hogy végigvezeti Önt a .NET-hez készült Aspose.PDF könyvtár használatán a szöveg forgatásához a PDF-dokumentum szövegrészeinek és bekezdéseinek használatával. Az oktatóanyag lépésről lépésre tartalmaz utasításokat és mintakódot a funkció eléréséhez.

#### K: Miben különbözik ez az oktatóanyag a korábbi szövegforgató oktatóanyagoktól?

V: Ez az oktatóanyag a szövegtöredékek és a bekezdések használatát kombinálja a szövegforgatás eléréséhez egy PDF-dokumentumban. Bemutatja, hogyan lehet egyenként elforgatni a szövegrészleteket, majd hozzáadni őket egy oldalhoz`Paragraphs` gyűjtemény átfogóbb szövegforgató hatás elérése érdekében.

#### K: Milyen előnyökkel jár a szövegtöredékek és bekezdések használata a szövegforgatáshoz?

V: A szövegrészletek és bekezdések együttes használata nagyobb rugalmasságot tesz lehetővé a szövegforgatásban. A szövegtöredékek egyedi elforgatási és formázási beállításokat tesznek lehetővé, míg a bekezdések struktúrát biztosítanak a szövegrészletek oldalon belüli elrendezéséhez és elhelyezéséhez.

#### K: Alkalmazhatok különböző elforgatási szögeket ugyanazon a bekezdésen belüli különböző szövegrészletekre?

 V: Igen, különböző elforgatási szögeket alkalmazhat a különbözőekhez`TextFragment` objektumok ugyanabban a bekezdésben. Minden szövegrészletnek meg lehet adni saját elforgatási szögét a segítségével`TextState.Rotation` ingatlan.

#### K: Lehetséges összetett szövegforgatási hatásokat elérni ezzel a módszerrel?

V: Igen, a különböző elforgatási szögekkel rendelkező szövegrészletek kombinálásával és bekezdéseken belüli elrendezésével összetett és testreszabott szövegelforgatási effektusokat érhet el, javítva a PDF-dokumentumok vizuális vonzerejét.

#### K: Milyen lépésekből áll a szöveg elforgatása szövegrészletek és bekezdések használatával?

V: A lépések a következők:

1. A projekt beállítása egy új C# projekt létrehozásával és hivatkozás hozzáadásával az Aspose.PDF for .NET könyvtárhoz.
2. PDF dokumentum létrehozása és oldal hozzáadása.
3. Szövegtöredékek létrehozása, tulajdonságaik beállítása, elforgatási szögek megadása.
4.  Szövegtöredékek hozzáadása az oldalhoz a`Paragraphs` Gyűjtemény.
5. A módosított PDF dokumentum mentése.

#### K: Alkalmazhatom a forgatást a teljes bekezdésekre?

 V: Igen, a teljes bekezdésekre alkalmazhatja a forgatást a`TextState.Rotation` magának a bekezdésnek a tulajdonsága. Ezzel elforgatja az összes szövegrészletet a bekezdésben.