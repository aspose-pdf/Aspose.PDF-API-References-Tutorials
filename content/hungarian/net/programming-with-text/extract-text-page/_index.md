---
title: Szöveges oldal kibontása PDF fájlba
linktitle: Szöveges oldal kibontása PDF fájlba
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthat ki szöveget egy adott oldalról PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 200
url: /hu/net/programming-with-text/extract-text-page/
---
Ez az oktatóanyag végigvezeti Önt a szöveg kinyerésének folyamatán egy adott oldalról PDF-fájlban az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelybe szöveget szeretne kivonni, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Nyissa meg a PDF dokumentumot
 Nyisson meg egy meglévő PDF dokumentumot a`Document`konstruktort, és átadja a bemeneti PDF-fájl elérési útját.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 5. lépés: Szöveg kibontása egy adott oldalról
 Hozzon létre a`TextAbsorber` objektumot, hogy szöveget vonjon ki a dokumentumból. Fogadja el a kívánt oldal abszorberét a következőn keresztül való hozzáféréssel`Pages` gyűjteménye a`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## 6. lépés: Szerezze be a kivont szöveget
 A kivont szöveg elérése a`TextAbsorber` objektum.

```csharp
string extractedText = textAbsorber.Text;
```

## 7. lépés: Mentse el a kicsomagolt szöveget
 Hozzon létre a`TextWriter` és nyissa meg a fájlt, ahová a kicsomagolt szöveget menteni szeretné. Írja be a kicsomagolt szöveget a fájlba, és zárja be az adatfolyamot.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### Minta forráskód a szövegoldal kibontásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// Hozzon létre TextAbsorber objektumot a szöveg kivonásához
TextAbsorber textAbsorber = new TextAbsorber();
//Fogadja el az abszorbert egy adott oldalhoz
pdfDocument.Pages[1].Accept(textAbsorber);
// Szerezd meg a kivont szöveget
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// Hozzon létre egy írót, és nyissa meg a fájlt
TextWriter tw = new StreamWriter(dataDir);
// Írjon egy sort a fájlba
tw.WriteLine(extractedText);
// Zárd be a patakot
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## Következtetés
Sikeresen kinyert szöveget egy PDF-dokumentum adott oldaláról az Aspose.PDF for .NET segítségével. A kivont szöveget a rendszer a megadott kimeneti fájlba mentette.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ez az oktatóanyag végigvezeti Önt a PDF-fájl egy adott oldaláról a szöveg kinyerésének folyamatán az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a feladat végrehajtásához szükséges lépéseket.

#### K: Milyen névtereket kell importálnom?

V: Abba a kódfájlba, amelybe szöveget kíván kivonni, a fájl elején direktívák használatával adja meg a következőket:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: Keresse meg a kódban azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan nyithatok meg egy meglévő PDF-dokumentumot?

 V: A 4. lépésben megnyit egy meglévő PDF-dokumentumot a`Document` konstruktort, és megadja a bemeneti PDF-fájl elérési útját.

#### K: Hogyan tudok szöveget kivonni egy adott oldalról?

 V: Az 5. lépés az a`TextAbsorber` objektum a szöveg kinyeréséhez a PDF dokumentumból. Ezután elfogadja a kívánt oldal elnyelőjét a következőn keresztül`Pages` gyűjteménye a`pdfDocument`.

#### K: Hogyan férhetek hozzá a kivonatolt szöveghez?

 V: A 6. lépés végigvezeti Önt a kivonatolt szöveg elérésén`TextAbsorber` objektum.

#### K: Hogyan menthetem el a kicsomagolt szöveget fájlba?

 V: A 7. lépésben létrehoz egy`TextWriter`, nyissa meg azt a fájlt, ahová a kicsomagolt szöveget menteni szeretné, írja be a kibontott szöveget a fájlba, majd zárja be az adatfolyamot.

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan lehet szöveget kivonni egy PDF-dokumentum adott oldaláról az Aspose.PDF for .NET használatával. A kivont szöveget egy megadott kimeneti fájlba mentette, lehetővé téve az adott oldalak szövegtartalmának megcélzását és elemzését.