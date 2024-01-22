---
title: Örökölni a nagyítást a PDF-fájlban
linktitle: Örökölni a nagyítást a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Könnyen örökölheti a könyvjelzők nagyítását PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 90
url: /hu/net/programming-with-bookmarks/inherit-zoom/
---
PDF-fájl nagyítási öröklése lehetővé teszi a könyvjelzők alapértelmezett nagyítási szintjének megadását. Az Aspose.PDF for .NET segítségével könnyedén örökölheti a nagyítást a következő forráskód követésével:

## 1. lépés: Importálja a szükséges könyvtárakat

Mielőtt elkezdené, importálnia kell a C#-projekthez szükséges könyvtárakat. Itt van a szükséges import irányelv:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2. lépés: Állítsa be a dokumentumok mappa elérési útját

 Ebben a lépésben meg kell adnia annak a PDF-fájlnak az elérési útját, amelyből a nagyítást örökölni szeretné. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` következő kódban a dokumentummappa tényleges elérési útjával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3. lépés: Nyissa meg a PDF dokumentumot

Most megnyitjuk azt a PDF dokumentumot, amelyen a nagyítást örökölni szeretnénk a következő kóddal:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4. lépés: Szerezze be a könyvjelzőgyűjteményt

 Ebben a lépésben megkapjuk a dokumentum könyvjelzőinek vagy tereptárgyainak gyűjteményét a`Outlines` tulajdona a`doc` tárgy. Itt van a megfelelő kód:

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## 5. lépés: Állítsa be a nagyítási szintet

 Most beállítjuk a nagyítási szintet egy`XYZExplicitDestination` objektum a megadott x, y és z koordinátákkal. Itt a koordinátákat (100, 100, 0) használjuk 2-es nagyítással. Íme a megfelelő kód:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## 6. lépés: Adja hozzá a nagyítási szintet a könyvjelzőkhöz

 Ebben a lépésben hozzáadjuk a`XYZExplicitDestination` objektumot műveletként a könyvjelzőihez`item` Gyűjtemény. Itt van a megfelelő kód:

```csharp
item. Action = new GoToAction(dest);
```

## 7. lépés: Adja hozzá a frissített könyvjelzőket a dokumentumhoz

 Végül hozzáadjuk a frissített könyvjelzőket a dokumentum könyvjelzőgyűjteményéhez a segítségével`Add` módszere a`doc.Outlines` tárgy. Itt van a megfelelő kód:

```csharp
doc. Outlines. Add(item);
```

## 8. lépés: Mentse el a frissített fájlt

 Most mentsük el a frissített PDF fájlt a`Save` módszere a`doc` tárgy. Itt van a megfelelő kód:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Minta forráskód az Inherit Zoomhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document doc = new Document(dataDir + "input.pdf");
// Szerezzen körvonalakat/könyvjelzőgyűjteményt PDF-fájlokból
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Állítsa be a nagyítási szintet 0-ra
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Adja hozzá az XYZExplicitDestination műveletet a PDF-gyűjtemény körvonalaihoz
item.Action = new GoToAction(dest);
// Elem hozzáadása a PDF-fájl körvonalgyűjteményéhez
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Mentse a kimenetet
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálok ! Most egy lépésről lépésre bemutatja a nagyítás öröklését az Aspose.PDF segítségével .NET-hez. Ezzel a kóddal megadhatja a PDF-dokumentumokban lévő könyvjelzők alapértelmezett nagyítási szintjét.

Feltétlenül tekintse meg a hivatalos Aspose.PDF dokumentációt a speciális könyvjelzőkezelési funkciókkal kapcsolatos további információkért.

### GYIK a PDF-fájl nagyításának örökléséhez

#### K: Mit jelent a nagyítás öröklése egy PDF-fájlban?

V: A nagyítás öröklődése a PDF-dokumentum könyvjelzőinek alapértelmezett nagyítási szintjének meghatározására utal. Ez lehetővé teszi a következetes és felhasználóbarát navigációt, amikor a felhasználók a könyvjelzőket használják.

#### K: Miért szeretném örökölni a könyvjelzők nagyítási szintjét?

V: A nagyítási szintek öröklése biztosítja, hogy a felhasználók egységes megtekintési élményben legyenek a PDF-dokumentum könyvjelzői között való navigálás során. Különösen hasznos lehet, ha egy adott nézetet szeretne biztosítani a dokumentum különböző szakaszaihoz.

#### K: Hogyan importálhatom a C# projektemhez szükséges könyvtárakat?

V: A C#-projekthez szükséges könyvtárak importálásához adja meg a következő importálási direktívákat:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ezek az utasítások lehetővé teszik a PDF dokumentumok és könyvjelzők kezeléséhez szükséges osztályok és módszerek elérését.

#### K: Hogyan adhatom meg a dokumentumok mappa elérési útját?

 V: A megadott forráskódban cserélje ki`"YOUR DOCUMENT DIRECTORY"` az örökölni kívánt PDF-fájlt tartalmazó mappa tényleges elérési útjával.

#### K: Hogyan nyithatok meg egy PDF-dokumentumot, hogy örököljem a nagyítási szinteket?

V: PDF-dokumentum megnyitásához a nagyítási szintek örökléséhez használja a következő kódot:

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Cserélje ki`"input.pdf"` a tényleges fájlnévvel.

#### K: Hogyan állíthatom be a könyvjelzők nagyítási szintjét?

 V: A nagyítási szint beállításához hozzon létre egy`XYZExplicitDestination` objektumot a kívánt koordinátákkal és nagyítási tényezővel. Íme egy példa:

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

Ez a nagyítási szintet 2-re állítja a koordinátákon (100, 100).

#### K: Hogyan adhatom hozzá a nagyítási szintet a könyvjelzőkhöz?

 V: Add hozzá a`XYZExplicitDestination` objektumot a könyvjelzőgyűjtemény műveleteként:

```csharp
item.Action = new GoToAction(dest);
```

 Ahol`item` egy`OutlineItemCollection` könyvjelzőt képvisel.

#### K: Hogyan menthetem el a frissített PDF fájlt?

 V: Mentse el a frissített PDF-fájlt a`Save` módszere a`doc` tárgy:

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

#### K: Testreszabhatom a nagyítási szinteket a különböző könyvjelzőkhöz?

 V: Igen, több könyvjelző létrehozásával testreszabhatja a nagyítási szinteket a különböző könyvjelzőkhöz`XYZExplicitDestination` különböző koordinátákkal és nagyítási tényezőkkel rendelkező objektumok.

#### K: Van-e korlát azoknak a könyvjelzőknek a száma, amelyekre nagyítási örökséget alkalmazhatok?

V: Általában nincs szigorú korlátozás a nagyítási öröklődést alkalmazó könyvjelzők számára. A túl sok könyvjelzővel rendelkező, nagyon nagy dokumentumok azonban hatékony memóriakezelést igényelhetnek.

#### K: Hogyan erősíthetem meg, hogy alkalmazták-e a zoom öröklődését?

V: Nyissa meg a létrehozott PDF-fájlt, és ellenőrizze, hogy a megadott nagyítási szinteket örökölték-e a könyvjelzők.