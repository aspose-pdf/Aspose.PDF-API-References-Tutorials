---
title: Gyermek könyvjelző hozzáadása PDF-fájlhoz
linktitle: Gyermek könyvjelző hozzáadása PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Könnyen hozzáadhat gyermekkönyvjelzőt PDF-fájlhoz a rendezettebb böngészés érdekében az Aspose.PDF for .NET segítségével.
type: docs
weight: 20
url: /hu/net/programming-with-bookmarks/add-child-bookmark/
---
A gyermekkönyvjelzők PDF-fájlba történő hozzáadása strukturáltabb rendszerezést és navigációt tesz lehetővé. Az Aspose.PDF for .NET segítségével könnyen hozzáadhat alkönyvjelzőket a következő forráskód követésével:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Itt van a szükséges import irányelv:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia az alkönyvjelzőt hozzáadni kívánt PDF-fájlt tartalmazó mappa elérési útját. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. lépés: Nyissa meg a PDF dokumentumot

Most megnyitjuk a PDF dokumentumot, amelyhez alkönyvjelzőt szeretnénk hozzáadni a következő kóddal:

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## 4. lépés: Szülő könyvjelző objektum létrehozása

 Ebben a lépésben létrehozunk egy szülő könyvjelző objektumot a`OutlineItemCollection` osztályt, és állítsa be a tulajdonságait, például a címet, a dőlt attribútumot és a félkövér attribútumot. Itt van a megfelelő kód:

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## 5. lépés: Hozzon létre gyermekkönyvjelző objektumot

Ebben a lépésben újra létrehozunk egy alkönyvjelző objektumot a`OutlineItemCollection` osztályt, és állítsa be a tulajdonságait. Itt van a megfelelő kód:

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## 6. lépés: Adja hozzá az alkönyvjelzőt a szülő könyvjelzőhöz

 Végül hozzáadjuk a létrehozott alkönyvjelzőt a szülő könyvjelző alkönyvjelző gyűjteményéhez a segítségével`Add` a szülőobjektum metódusa. Itt van a megfelelő kód:

```csharp
pdfOutline.Add(pdfChildOutline);
```

## 7. lépés: Adja hozzá a szülő könyvjelzőt a dokumentum könyvjelzőgyűjteményéhez

 Végül hozzáadjuk a szülő könyvjelzőt a dokumentum könyvjelzőgyűjteményéhez a segítségével`Add` módszere a`Outlines` ingatlan. Itt van a megfelelő kód:

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Minta forráskód a Gyermekkönyvjelző hozzáadása funkcióhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Hozzon létre egy szülő könyvjelző objektumot
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Hozzon létre egy gyermek könyvjelző objektumot
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Gyermekkönyvjelző hozzáadása a szülő könyvjelző gyűjteményéhez
pdfOutline.Add(pdfChildOutline);
// Szülő könyvjelző hozzáadása a dokumentum vázlatgyűjteményéhez.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Mentse a kimenetet
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálok ! Most lépésről lépésre van útmutatója egy alkönyvjelző hozzáadásához az Aspose.PDF .NET-hez. Ezzel a kóddal rendezheti és strukturálhatja könyvjelzőit a PDF-dokumentumokban.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt a speciális könyvjelzőkezelési funkciókkal kapcsolatos további információkért.

### GYIK gyermekkönyvjelzők hozzáadásához PDF-fájlban

#### K: Mik azok a gyermekkönyvjelzők egy PDF-fájlban?

V: Az alárendelt könyvjelzők, más néven alkönyvjelzők, a PDF-dokumentumban található navigációs elemek, amelyek hierarchikusan egy szülő könyvjelző alatt vannak felszerelve. Módot biztosítanak a dokumentum rendezettebb és részletesebb tartalomjegyzékének létrehozására.

#### K: Hogyan importálhatom a C# projektemhez szükséges könyvtárakat?

V: A C#-projekthez szükséges könyvtárak importálásához a következő importálási direktívát használhatja:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ezek a könyvtárak biztosítják a szükséges osztályokat és funkciókat a PDF-dokumentumokkal és interaktív szolgáltatásokkal való munkához.

#### K: Hogyan adhatom meg a dokumentumok mappa elérési útját?

 V: A megadott forráskódban ki kell cserélni`"YOUR DOCUMENT DIRECTORY"` a dolgozni kívánt PDF-fájlt tartalmazó mappa tényleges elérési útjával. Ez biztosítja, hogy a kód helyesen találja meg a cél PDF-fájlt.

#### K: Létrehozhatok többszintű gyermekkönyvjelzőket?

V: Igen, az oktatóanyagban vázolt folyamat kiterjesztésével többszintű gyermekkönyvjelzőket is létrehozhat. Szülő könyvjelzők alkönyvjelzőkkel történő létrehozásával és további egymásba ágyazásával létrehozhatja a könyvjelzők hierarchikus struktúráját az összetett PDF-dokumentumok számára.

####  K: Mi a célja a`OutlineItemCollection` class?

 V: A`OutlineItemCollection` osztályt az Aspose.PDF for .NET-ben a körvonalak létrehozására és kezelésére használják, amelyek lényegében könyvjelzők egy PDF-dokumentumban. Ez az osztály lehetővé teszi olyan tulajdonságok beállítását, mint a cím, a betűstílus és a könyvjelzők műveletei.

#### K: Hogyan adhatok hozzá alkönyvjelzőt egy szülő könyvjelzőhöz?

 V: Ha alkönyvjelzőt szeretne hozzáadni egy szülő könyvjelzőhöz, hozzon létre egy újat`OutlineItemCollection` objektumot az alkönyvjelzőhöz, és állítsa be a tulajdonságait. Ezután használja a`Add` a szülő könyvjelző módszere`OutlineItemCollection` az alkönyvjelző hozzáadásához a szülő gyűjteményéhez.

#### K: Testreszabhatom a gyermekkönyvjelzők megjelenését?

V: Igen, a szülő könyvjelzőkhöz hasonlóan testreszabhatja az alárendelt könyvjelzők megjelenését olyan tulajdonságok beállításával, mint a cím, a betűstílus és egyéb attribútumok. Ez lehetővé teszi vizuálisan megkülönböztető és informatív könyvjelzők létrehozását.

#### K: Az Aspose.PDF for .NET kompatibilis más programozási nyelvekkel?

V: Az Aspose.PDF for .NET kifejezetten C# és .NET környezetekhez készült. Az Aspose azonban hasonló könyvtárakat kínál más programozási nyelvekhez, például a Java-hoz és az Android-hoz, amelyek mindegyike a megfelelő platformra szabott.

#### K: Hogyan javítják a gyermekkönyvjelzők a PDF navigációt?

V: A gyermekkönyvjelzők strukturáltabb és rendezettebb tartalomjegyzéket biztosítva javítják a PDF navigációt. A felhasználók gyorsan elérhetik a dokumentum egyes részeit a hierarchikus könyvjelzőszerkezeten keresztül.