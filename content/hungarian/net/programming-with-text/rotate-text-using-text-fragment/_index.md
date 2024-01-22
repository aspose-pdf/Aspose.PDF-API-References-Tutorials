---
title: Szöveg elforgatása szövegrészlet használatával a PDF-fájlban
linktitle: Szöveg elforgatása szövegrészlet használatával a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan forgathat el szöveget szövegtöredékek használatával a PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 390
url: /hu/net/programming-with-text/rotate-text-using-text-fragment/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt a szöveg elforgatásához a PDF-fájlban lévő szövegrészletek használatával. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

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
using Aspose.Pdf.Text.TextBuilder;
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

 Több létrehozása`TextFragment` objektumokat, állítsa be a szövegüket és tulajdonságaikat, és adja meg pozíciójukat az oldalon:

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Igény szerint állítsa be a szöveget, a pozíciókat és az egyéb tulajdonságokat.

## 6. lépés: Hozzon létre egy TextBuilder programot, és fűzzen hozzá szövegrészleteket

 Hozzon létre egy`TextBuilder` objektum segítségével`pdfPage` és csatolja a szövegrészleteket a PDF-oldalhoz:

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

## 7. lépés: Mentse el a PDF dokumentumot

 Mentse el a módosított PDF-dokumentumot fájlba a`Save` módszer:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

 Ügyeljen arra, hogy cserélje ki`"TextFragmentTests_Rotated1_out.pdf"` a kívánt kimeneti fájlnévvel.

### Forráskód minta a Szövegforgatás szövegtöredék használatával az Aspose.PDF for .NET használatával programhoz 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentumobjektum inicializálása
Document pdfDocument = new Document();
// Szerezzen be egy adott oldalt
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Szövegrészlet létrehozása
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
// Állítsa be a szöveg tulajdonságait
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Elforgatott szövegrészlet létrehozása
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
// Állítsa be a szöveg tulajdonságait
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
// Elforgatott szövegrészlet létrehozása
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
// Állítsa be a szöveg tulajdonságait
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
// hozzon létre TextBuilder objektumot
TextBuilder textBuilder = new TextBuilder(pdfPage);
// A szövegrészlet hozzáfűzése a PDF-oldalhoz
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
// Dokumentum mentése
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

## Következtetés

Gratulálunk! Sikeresen megtanulta, hogyan forgathat el szöveget szövegrészletek használatával egy PDF-dokumentumban az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a dokumentum létrehozásától a módosított verzió mentéséig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy módosítsa a PDF-fájlok szövegforgatását.

### GYIK

#### K: Mi a célja a "Szöveg forgatása szövegtöredék használatával" oktatóanyagnak?

V: A "Szöveg elforgatása szövegtöredék használatával" oktatóanyag célja, hogy végigvezeti Önt a .NET-hez készült Aspose.PDF könyvtár használatával a szöveg elforgatásához szövegrészletek használatával egy PDF-dokumentumban. Az oktatóanyag lépésről lépésre tartalmaz utasításokat és mintakódot a funkció eléréséhez.

#### K: Mit jelent a "szöveg elforgatása szövegtöredékekkel"?

V: A szöveg elforgatása szövegtöredékekkel arra a lehetőségre utal, hogy az Aspose.PDF könyvtár használatával elforgatható egy PDF-dokumentum egyes szövegrészletei. Ez a technika lehetővé teszi a szöveg tájolásának szabályozását a PDF-tartalom különböző szögeiben vagy pozícióiban.

#### K: Miért szeretném elforgatni a szövegrészleteket egy PDF-dokumentumban?

V: A szövegrészletek elforgatása egy PDF-dokumentumban különféle célokra hasznos lehet, például konkrét tartalom kiemelésére, művészi tervek létrehozására vagy az elrendezés és az olvashatóság javítására.

#### K: Hogyan állíthatom be a projektet az oktatóanyaghoz?

V: A projekt beállításához:

1. Hozzon létre egy új C#-projektet a kívánt integrált fejlesztői környezetben (IDE).
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.
3. Adja hozzá a szükséges használati utasításokat a C# fájlhoz.

#### K: Hogyan hozhatok létre új PDF-dokumentumot?

 V: Új PDF-dokumentum létrehozásához inicializálja a`Document`objektumot az Aspose.PDF könyvtárból. Ezzel az objektummal oldalakat és tartalmat adhat hozzá a PDF-hez.

#### K: Hogyan forgathatom el a szövegrészleteket szövegtöredékekkel?

V: Szövegtöredékek elforgatása szövegtöredékekkel:

1.  Teremt`TextFragment` tárgyakat.
2. Állítsa be a szövegrészletek szövegét és tulajdonságait.
3. Adja meg a szövegrészletek pozícióját az oldalon.
4.  Állítsa be az elforgatási szöget a gombbal`TextState.Rotation` a szövegtöredékek tulajdonsága.
5.  Hozzon létre egy`TextBuilder`objektumot, és hozzáfűzi a szövegrészleteket a PDF-oldalhoz.

#### K: Alkalmazhatok különböző elforgatási szögeket a különböző szövegrészletekre?

 V: Igen, különböző elforgatási szögeket alkalmazhat a különbözőekhez`TextFragment` tárgyakat. Minden szövegrészletnek meg lehet adni saját elforgatási szögét a segítségével`TextState.Rotation` ingatlan.

#### K: Hogyan menthetem el a PDF dokumentumot elforgatott szövegrészletekkel?

 V: A PDF-dokumentum elforgatott szövegrészletekkel történő mentéséhez használja a`Save` módszere a`Document` objektumot, és adja meg a kívánt kimeneti fájl elérési útját és nevét.