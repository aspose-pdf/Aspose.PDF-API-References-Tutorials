---
title: PDF-tulajdonságok beszerzése
linktitle: PDF-tulajdonságok beszerzése
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a PDF-tulajdonságok, például a dobozméretek és az elforgatás megszerzéséhez az Aspose.PDF for .NET használatával.
type: docs
weight: 100
url: /hu/net/programming-with-pdf-pages/get-properties/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a PDF-fájlok tulajdonságainak megismeréséhez az Aspose.PDF for .NET használatával. Elmagyarázzuk a csomagban lévő C# forráskódot, és átfogó útmutatót adunk, amely segít megérteni és megvalósítani ezt a funkciót saját projektjeiben. Ennek az oktatóanyagnak a végén megtudhatja, hogyan érheti el a PDF-oldal különböző tulajdonságait, például rajzdobozt, vágódobozt, vágódobozt stb. az Aspose.PDF for .NET használatával.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Alapszintű C# programozási nyelv ismerete
- Aspose.PDF for .NET telepítve a fejlesztői környezetbe

## 1. lépés: Állítsa be a dokumentumkönyvtárat
Először is be kell állítania a dokumentumkönyvtár elérési útját. Ez annak a PDF-fájlnak a helye, amelynek tulajdonságait le szeretné szerezni. Cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet a megfelelő elérési útra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF dokumentumot
 Ezután meg kell nyitnia a PDF dokumentumot a`Document` osztályú Aspose.PDF. Ügyeljen arra, hogy a PDF-fájl helyes elérési útját adja meg.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 3. lépés: Nyissa meg az oldalgyűjteményt
 Mostantól elérheti a dokumentum oldalgyűjteményét a`Pages` tulajdona a`pdfDocument` objektum.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4. lépés: Lépjen egy adott oldalra
Ezután egy adott oldalra ugorhat a gyűjteményben lévő oldal indexének használatával. Az alábbi példában elérjük a második oldalt (1. index).

```csharp
Page pdfPage = pageCollection[1];
```

## 5. lépés: Szerezze be az oldal tulajdonságait
 Mostantól megkaphatja a PDF-oldal különböző tulajdonságait, például rajzdobozt, vágódobozt, vágódobozt stb., a megfelelő tulajdonságok használatával`pdfPage` objektum.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Minta forráskód a Properties beszerzéséhez az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Oldalgyűjtemény letöltése
PageCollection pageCollection = pdfDocument.Pages;
// Szerezzen be egy adott oldalt
Page pdfPage = pageCollection[1];
// Az oldal tulajdonságainak lekérése
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Következtetés
Gratulálok ! Sikeresen megszerezte a PDF tulajdonságait az Aspose.PDF for .NET használatával. Megtanulta, hogyan nyithat meg egy PDF-dokumentumot, hogyan navigálhat egy adott oldalra, és hogyan kaphat különféle oldaltulajdonságokat, például méretdobozokat és elforgatást. Ezen információk segítségével most személyre szabhatja a PDF-fájlok kezelését tulajdonságaik alapján.

Feltétlenül tekintse meg a hivatalos Aspose.PDF for .NET dokumentációt, ha további információra van szüksége a speciális funkciókról és a testreszabási lehetőségekről.

### GYIK

#### K: Hogyan szerezhetem meg a PDF tulajdonságait az Aspose.PDF for .NET használatával?

V: Az Aspose.PDF for .NET használatával PDF tulajdonságainak lekéréséhez kövesse az alábbi lépéseket:

1. Állítsa be a dokumentumkönyvtárat a lekérni kívánt PDF-fájl elérési útjának megadásával.
2.  Nyissa meg a PDF dokumentumot a`Document` osztályú Aspose.PDF, amely megadja a PDF-fájl helyes elérési útját.
3.  A dokumentum oldalgyűjteményének eléréséhez használja a`Pages` tulajdona a`pdfDocument` objektum.
4. Ugrás egy adott oldalra a gyűjteményben lévő oldal indexével (az indexelés 1-től kezdődik).
5.  Szerezze meg a PDF-oldal különböző tulajdonságait, például ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Oldalszám és Rotation, a megfelelő tulajdonságok használatával`pdfPage` objektum.

#### K: Melyek a PDF-oldalak különböző tulajdonságai, amelyeket az Aspose.PDF for .NET használatával tölthetek le?

V: A PDF-oldalak különféle tulajdonságait lekérheti az Aspose.PDF for .NET használatával, például:

- ArtBox: Az oldal grafikájának méreteit jeleníti meg.
- BleedBox: Az oldal kifutójának méreteit jelöli.
- CropBox: Az oldal körbevágás után látható tartalmának méreteit jeleníti meg.
- MediaBox: Az oldal fizikai adathordozójának méreteit jeleníti meg.
- Vágódoboz: Az oldal levágott tartalmának méreteit jelöli.
- Rect: Az oldal határolókeretének méreteit jelöli.
- Oldalszám: A dokumentum oldalszámát jelöli.
- Elforgatás: Az oldal elforgatási szögét jelöli.

#### K: Hogyan érhetek el egy adott oldalt a PDF-dokumentumban a tulajdonságainak lekéréséhez?

 V: A PDF-dokumentum egy adott oldalának eléréséhez és tulajdonságainak lekéréséhez használja a`Pages` tulajdona a`pdfDocument` objektumot a dokumentum oldalgyűjteményének eléréséhez. Ezután a gyűjteményben lévő oldal indexével a kívánt oldalra ugorhat. Például a második oldal eléréséhez használhatja`pdfDocument.Pages[1]` (az indexelés 1-től kezdődik).

#### K: Végezhetek-e műveleteket a visszakeresett tulajdonságokon, például módosíthatom vagy átméretezhetem az oldaldobozokat?

V: Igen, miután lekérte egy PDF-oldal tulajdonságait az Aspose.PDF for .NET használatával, különféle műveleteket hajthat végre rajtuk. Módosíthatja például az oldaldobozok méreteit, elforgathatja az oldalt, vagy felhasználhatja a letöltött információkat a PDF-dokumentum egyéni feldolgozásához és kezeléséhez.

#### K: Az Aspose.PDF for .NET támogatja a tulajdonságok kinyerését titkosított vagy jelszóval védett PDF-fájlokból?

V: Igen, az Aspose.PDF for .NET támogatja a tulajdonságok kinyerését titkosított vagy jelszóval védett PDF-fájlokból. Mindaddig, amíg megadja a megfelelő jelszót a PDF-dokumentum megnyitásához, az oktatóanyagban bemutatott megközelítéssel hozzáférhet és visszakeresheti a tulajdonságait.