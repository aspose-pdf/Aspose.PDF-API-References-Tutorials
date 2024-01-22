---
title: Töltse le a könyvjelző oldalszámát PDF-fájlban
linktitle: Töltse le a könyvjelző oldalszámát PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Könnyen megszerezheti a könyvjelző oldalszámát PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 60
url: /hu/net/programming-with-bookmarks/get-bookmark-page-number/
---
könyvjelzőkkel társított oldalszámok PDF-fájlban történő lekérése hasznos lehet a navigációhoz. Az Aspose.PDF for .NET segítségével könnyen lekérheti a könyvjelzők oldalszámát a következő forráskód követésével:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Itt van a szükséges import irányelv:

```csharp
using Aspose.Pdf.Facades;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia annak a PDF-fájlnak az elérési útját, amelyből ki szeretné bontani a könyvjelző oldalszámait. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. lépés: Hozza létre a könyvjelzőszerkesztőt

 Most létrehozzuk a`PdfBookmarkEditor` objektumot a dokumentum könyvjelzőinek manipulálására. Használja a következő kódot:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## 4. lépés: Nyissa meg a PDF-fájlt

 Ebben a lépésben megnyitjuk a PDF fájlt a`BindPdf` a könyvjelzőszerkesztő módszere. Itt van a megfelelő kód:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 5. lépés: Bontsa ki a könyvjelzőket

 Most kivonjuk a könyvjelzőket a dokumentumból a segítségével`ExtractBookmarks` a könyvjelzőszerkesztő módszere. Itt van a megfelelő kód:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 6. lépés: Böngésszen a könyvjelzők között, és szerezzen be oldalszámokat

 Végül végigpörgetjük a kibontott könyvjelzőket, és az a segítségével megkapjuk az egyes könyvjelzőkhöz tartozó oldalszámokat`foreach` hurok. Itt van a megfelelő kód:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Minta forráskód a Könyvjelző oldalszámának lekéréséhez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// PdfBookmarkEditor létrehozása
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Nyissa meg a PDF fájlt
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Könyvjelzők kibontása
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Következtetés

Gratulálok ! Most egy lépésről lépésre bemutatja a könyvjelzők oldalszámainak beszerzését az Aspose.PDF for .NET segítségével. Ezzel a kóddal lekérheti a PDF-dokumentumok egyes könyvjelzőihez tartozó navigációs információkat.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt a speciális könyvjelzőkezelési funkciókkal kapcsolatos további információkért.

### GYIK a könyvjelző oldalszámának PDF-fájlban történő lekéréséhez

#### K: Mik azok a könyvjelzők egy PDF-fájlban?

V: A PDF-fájlban található könyvjelzők olyan navigációs segédeszközök, amelyek segítségével a felhasználók gyorsan ugorhatnak a dokumentum adott szakaszaira vagy oldalaira. Javítják a felhasználói élményt azáltal, hogy hivatkozásokat biztosítanak a releváns tartalomhoz.

#### K: Miért szeretném lekérni a könyvjelzők oldalszámait egy PDF-fájlból?

V: A könyvjelzők oldalszámainak lekérése segít a felhasználóknak hatékonyabban navigálni a dokumentumban, és egyértelműen jelzi, hová vezet az egyes könyvjelzők. Ez különösen hasznos hosszabb, több szakaszt tartalmazó dokumentumok esetén.

#### K: Hogyan importálhatom a C# projektemhez szükséges könyvtárakat?

V: A C#-projekthez szükséges könyvtár importálásához használja a következő importálási direktívát:

```csharp
using Aspose.Pdf.Facades;
```

Ez az irányelv lehetővé teszi az Aspose.PDF for .NET által biztosított osztályok és metódusok használatát.

#### K: Hogyan adhatom meg a dokumentumok mappa elérési útját?

 V: A megadott forráskódban cserélje ki`"YOUR DOCUMENT DIRECTORY"`annak a PDF-fájlnak a tényleges elérési útjával, amelyből a könyvjelző oldalszámait ki szeretné bontani. Ez biztosítja, hogy a kód meg tudja találni a cél PDF-fájlt.

#### K: Hogyan hozhatok létre könyvjelzőszerkesztőt?

V: Könyvjelzőszerkesztő létrehozásához használja a következő kódot:

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### K: Hogyan nyithatok meg PDF-fájlt könyvjelző-manipuláció céljából?

V: PDF-fájl megnyitásához könyvjelző-információk kibontásához használja a következő kódot:

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Cserélje ki`"GetBookmarks.pdf"` a tényleges fájlnévvel.

#### K: Hogyan bonthatok ki könyvjelzőket a PDF-fájlból?

 V: Ha könyvjelzőket szeretne kivonni a PDF-fájlból, használja a`ExtractBookmarks` a könyvjelzőszerkesztő módszere:

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### K: Hogyan kérhetem le és jeleníthetem meg a könyvjelzők oldalszámait?

 V: Lapozzon át a kibontott könyvjelzők között a a`foreach` hurok, és elérje a`PageNumber` minden könyvjelző tulajdonsága a kapcsolódó oldalszámok lekéréséhez és megjelenítéséhez:

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### K: Módosíthatom a könyvjelző tulajdonságait ezzel a megközelítéssel?

 V: Bár ez az oktatóanyag a könyvjelzők oldalszámainak lekérésére összpontosít, a könyvjelzők más tulajdonságait is módosíthatja ugyanezzel`Bookmark`objektum és kapcsolódó tulajdonságok.

#### K: Hogyan menthetem el a frissített PDF-fájlt a könyvjelző információk kibontása után?

V: A könyvjelzők kibontása nem módosítja az eredeti PDF-fájlt. Ha el szeretné menteni a módosításokat, az Aspose.PDF for .NET által biztosított más módszerekkel is megteheti.