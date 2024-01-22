---
title: Bontsa ki a Könyvjelzőket PDF-fájlban
linktitle: Bontsa ki a Könyvjelzőket PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Könnyen bővítheti a könyvjelzőket PDF-fájlban a jobb navigáció érdekében az Aspose.PDF for .NET segítségével.
type: docs
weight: 50
url: /hu/net/programming-with-bookmarks/expand-bookmarks/
---
A PDF-fájl könyvjelzőinek kibontása alapértelmezés szerint megjeleníti az összes nyitott könyvjelzőt. Az Aspose.PDF for .NET segítségével egyszerűen bővítheti a könyvjelzőket a következő forráskód követésével:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Itt van a szükséges import irányelv:

```csharp
using Aspose.Pdf;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia annak a PDF-fájlnak az elérési útját, amelynek könyvjelzőit ki szeretné bontani. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. lépés: Nyissa meg a PDF dokumentumot

Most megnyitjuk azt a PDF dokumentumot, amelynek könyvjelzőit ki akarjuk bontani a következő kóddal:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. lépés: Állítsa be az oldalmegjelenítési módot

Ebben a lépésben az oldalmegjelenítési módot úgy állítjuk be, hogy alapértelmezés szerint megjelenjenek a könyvjelzők. Használjuk a`PageMode` tulajdona a`doc` objektumot a kívánt oldalmód beállításához. Itt van a megfelelő kód:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 5. lépés: Böngésszen a könyvjelzők között, és bontsa ki őket

 Most végigpörgetjük a dokumentum könyvjelzőgyűjteményében lévő minden könyvjelzőelemet, és beállítjuk az egyes elemek nyitott állapotát`true` hogy alapértelmezés szerint kibontsa őket. Itt van a megfelelő kód:

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 6. lépés: Mentse el a frissített fájlt

 Végül a frissített PDF fájlt a`Save` módszere a`doc` tárgy. Itt van a megfelelő kód:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Minta forráskód a Könyvjelzők kibontásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document doc = new Document(dataDir + "input.pdf");
// Állítsa be az oldalnézeti módot, azaz mutasson miniatűröket, teljes képernyőt, mutasson mellékleteket
doc.PageMode = PageMode.UseOutlines;
// Lapozzon végig minden Ouline-elemen a PDF-fájl körvonalgyűjteményében
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Nyitott állapot beállítása a vázlatelemhez
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Mentse a kimenetet
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálok ! Most egy lépésről-lépésre szóló útmutatóval rendelkezik a könyvjelzők fejlesztéséhez az Aspose.PDF for .NET segítségével. Ezzel a kóddal megjelenítheti az összes alapértelmezett könyvjelzőt a PDF-dokumentumokban.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt a speciális könyvjelzőkezelési funkciókkal kapcsolatos további információkért.

### GYIK a könyvjelzők kibontásához PDF-fájlban

#### K: Mik azok a könyvjelzők egy PDF-fájlban?

V: A PDF-fájlban található könyvjelzők olyan navigációs segédeszközök, amelyek segítségével a felhasználók gyorsan ugorhatnak a dokumentum adott szakaszaira vagy oldalaira. Kényelmes módot biztosítanak a dokumentum különböző részei elérésére.

#### K: Miért szeretném kibontani a könyvjelzőket egy PDF-fájlban?

V: A könyvjelzők kibontása javíthatja a felhasználói élményt azáltal, hogy alapértelmezés szerint az összes könyvjelzőt kibontott állapotban jeleníti meg. Ez világos áttekintést ad a felhasználóknak a dokumentum szerkezetéről, és lehetővé teszi számukra, hogy könnyen navigáljanak a különböző szakaszokhoz.

#### K: Hogyan importálhatom a C# projektemhez szükséges könyvtárakat?

V: A C#-projekthez szükséges könyvtár importálásához használja a következő importálási direktívát:

```csharp
using Aspose.Pdf;
```

Ez az irányelv lehetővé teszi az Aspose.PDF for .NET által biztosított osztályok és metódusok használatát.

#### K: Hogyan adhatom meg a dokumentumok mappa elérési útját?

 V: A megadott forráskódban cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kezelni kívánt PDF-fájlt tartalmazó mappa tényleges elérési útjával. Ez biztosítja, hogy a kód meg tudja találni a cél PDF-fájlt.

#### K: Hogyan nyithatok meg egy PDF-dokumentumot a könyvjelzők bővítéséhez?

V: PDF-dokumentum megnyitásához a könyvjelzők kibontásához használja a következő kódot:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Cserélje ki`"input.pdf"` a tényleges fájlnévvel.

#### K: Hogyan állíthatom be az oldalmegjelenítési módot, hogy a könyvjelzők alapértelmezés szerint megjelenjenek?

V: Ha az oldalmegjelenítési módot úgy szeretné beállítani, hogy a könyvjelzők alapértelmezés szerint megjelenjenek, használja a`PageMode` tulajdona a`doc` tárgy:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### K: Hogyan bővíthetem ki az összes könyvjelzőt a PDF-dokumentumban?

 V: Az összes könyvjelző kibontásához görgessen végig a dokumentum körvonalgyűjteményében található könyvjelzőelemeken, és állítsa be a`Open` tulajdonát`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### K: Mi történik, ha egy könyvjelzőbe beágyazott gyermekkönyvjelzők vannak?

V: Ha egy könyvjelzőben vannak beágyazott alárendelt könyvjelzők, a szülő könyvjelző kibontása az alárendelt könyvjelzőket is kiterjeszti, így átfogó képet ad a dokumentum szerkezetéről.

#### K: Hogyan menthetem el a frissített PDF-fájlt a könyvjelzők kibontása után?

V: A frissített PDF-fájl mentéséhez a könyvjelzők kibontása után használja a következő kódot:

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### K: Testreszabhatom a kiterjesztett könyvjelzők megjelenését?

V: Bár ez az oktatóanyag alapértelmezés szerint a könyvjelzők kibontására összpontosít, az Aspose.PDF egyéb funkcióival és tulajdonságaival testreszabhatja a könyvjelzők megjelenését.