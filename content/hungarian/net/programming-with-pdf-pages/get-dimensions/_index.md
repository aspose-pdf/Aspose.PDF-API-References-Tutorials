---
title: PDF oldalméretek lekérése
linktitle: PDF oldalméretek lekérése
second_title: Aspose.PDF for .NET API Reference
description: Ebben az oktatóanyagban elmagyarázzuk, hogyan szerezheti be a PDF-oldal méreteit, és hogyan hajthat végre manipulációkat az Aspose.PDF for .NET használatával. A részletes lépések segítségével végigvezeti Önt a folyamaton.
type: docs
weight: 60
url: /hu/net/programming-with-pdf-pages/get-dimensions/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük az Aspose.PDF for .NET segítségével az oldalméretek PDF-fájlba állításán. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végén tudni fogja, hogyan szerezheti be egy oldal méretét egy PDF-fájlban az Aspose.PDF for .NET segítségével.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Alapszintű C# programozási nyelv ismerete
- Aspose.PDF for .NET telepítve a fejlesztői környezetbe

## 1. lépés: Határozza meg a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez az a hely, ahol a PDF-fájl található. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF dokumentumot
 Ezután megnyithatja a PDF fájlt a`Document` osztályú Aspose.PDF. Ügyeljen arra, hogy a PDF-fájl helyes elérési útját adja meg.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3. lépés: Adjon hozzá egy üres oldalt (ha szükséges)
 Ha a PDF-dokumentum már tartalmaz oldalakat, az index segítségével egy meglévő oldalra ugorhat`1` (az első oldal indexe 1). Ellenkező esetben hozzáadhat egy új oldalt a dokumentumhoz.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 4. lépés: Szerezze meg az oldal méreteit
 Mostantól az oldalméreteket a`GetPageRect()` módszere a`Page` tárgy. Ez a metódus visszaadja a`Rectangle` az oldal méreteit tartalmazó objektum. A szélességet és magasságot a gombbal érheti el`Width` és`Height` tulajdonságait.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 5. lépés: Forgassa el az oldalt
 Ha el akarja forgatni az oldalt, használhatja a`Rotate` tulajdona a`Page`tárgy. Ebben a példában az oldal 90 fokkal el van forgatva.

```csharp
page. Rotate = Rotate. on90;
```

## 6. lépés: Állítsa be újra az oldalméreteket
 Az oldal elforgatása után az oldalméreteket újra lekérheti a`GetPageRect()` módszer.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Minta forráskód a Dimensions letöltéséhez az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Üres oldalt ad a pdf dokumentumhoz
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Információk az oldal magasságáról és szélességéről
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Az oldal elforgatása 90 fokos szögben
page.Rotate = Rotation.on90;
// Információk az oldal magasságáról és szélességéről
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan lehet PDF-fájlban egy oldal méreteit lekérni az Aspose.PDF for .NET használatával. A megadott lépések követésével könnyedén kibonthatja az oldalméreteket, és más PDF-kezelési műveleteket hajthat végre. Az Aspose.PDF for .NET nagy rugalmasságot kínál a PDF-fájlokkal való munkavégzéshez, és lehetővé teszi hatékony és testreszabott megoldások fejlesztését.

Nyugodtan tanulmányozza tovább az Aspose.PDF dokumentációját, hogy felfedezze a könyvtár által kínált összes funkciót.

### GYIK a PDF oldalméretek lekéréséhez

#### K: Hogyan szerezhetem meg egy adott oldal méreteit egy PDF-fájlban?

V: Egy adott oldal méreteinek PDF-fájlban való lekéréséhez használhatja a`GetPageRect()` módszere a`Page` objektum az Aspose.PDF-ben .NET-hez. Ez a módszer visszaadja a`Rectangle` az oldal méreteit (szélesség és magasság) tartalmazó objektum.

####  K: Mit jelent a`GetPageRect(true)` method do in the provided C# source code?

 V: A`GetPageRect(true)` metódus a megadott C# forráskódban visszaadja az oldal méreteit az elforgatások alkalmazása után. Ha az oldal el van forgatva, a metódus visszaadja az elforgatott oldal méreteit, amelyek eltérhetnek az eredeti méretektől.

#### K: Megtudhatom a PDF-dokumentum összes oldalának méretét az Aspose.PDF for .NET használatával?

 V: Igen, a PDF-dokumentum összes oldalának méretét a következőn keresztül iterálva megkaphatja`Pages` gyűjteménye a`Document` objektum és a`GetPageRect(true)` módszer minden oldalhoz.

#### K: Hogyan határozhatom meg egy oldal tájolását (álló vagy fekvő) a méretei alapján?

V: Az oldal tájolásának a méretei alapján történő meghatározásához összehasonlíthatja az oldal szélességét és magasságát. Ha a szélesség nagyobb, mint a magasság, az oldal fekvő tájolású, ha pedig a magasság nagyobb, mint a szélesség, akkor az oldal álló tájolású.

#### K: Módosíthatom egy oldal méreteit az Aspose.PDF for .NET használatával?

 V: Igen, módosíthatja egy oldal méreteit az Aspose.PDF for .NET fájlban. Miután megkapta a`Rectangle` Az oldal méreteit képviselő objektum, igény szerint beállíthatja a szélességet és magasságot, majd alkalmazhatja a módosításokat az oldalon.