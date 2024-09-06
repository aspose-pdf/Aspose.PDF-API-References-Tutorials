---
title: Betűtípusok beágyazása és PDF-fájlok optimalizálása
linktitle: Betűtípusok beágyazása és PDF-fájlok optimalizálása
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg az Aspose.PDF for .NET használatát az Unembed Fonts letöltéséhez és a PDF-fájlok optimalizálásához. Lépésről lépésre szóló útmutató.
type: docs
weight: 370
url: /hu/net/programming-with-document/unembedfonts/
---
Az Aspose.PDF for .NET egy hatékony könyvtár, amely szolgáltatások széles skáláját kínálja a PDF dokumentumok kezeléséhez. Egyik funkciója a beágyazott betűtípusok beszerzése egy PDF-dokumentumból. Ez akkor lehet hasznos, ha fontokat kell kivonnia egy PDF-dokumentumból, és más alkalmazásokban kell használnia.

lépésről lépésre bemutatjuk az Aspose.PDF for .NET C# forráskódját.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

Mielőtt elkezdenénk, be kell állítanunk annak a könyvtárnak az elérési útját, ahol a PDF dokumentumunk található. Ezt az elérési utat egy "dataDir" nevű változóban tároljuk.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Cserélje le a „DOKUMENTUMKÖNYVTÁR” elemet a PDF-dokumentum könyvtárának tényleges elérési útjával.

## 2. lépés: Nyissa meg a PDF-dokumentumot

 Az első lépés az, hogy betöltse a PDF dokumentumot, amelyet meg szeretne tenni, használja a`Document` osztályú Aspose.PDF .NET-hez. A következő kódrészlet bemutatja a PDF dokumentum betöltését:

```csharp
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3. lépés: Állítsa be az UnembedFonts opciót

 A nem beágyazott betűtípusok PDF-dokumentumból való lekéréséhez be kell állítania a`UnembedFonts` opciót`true` . Ez az opció elérhető a`OptimizationOptions` osztály. A következő kódrészlet bemutatja, hogyan kell beállítani a`UnembedFonts` opció:

```csharp
// Állítsa be az UnembedFonts opciót
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 4. lépés: Optimalizálja a PDF-dokumentumot

 Miután beállította a`UnembedFonts` opcióval optimalizálhatja a PDF-dokumentumot a`OptimizeResources` módszere a`Document` osztály. A következő kódrészlet bemutatja, hogyan optimalizálhatja a PDF-dokumentumot:

```csharp
// Optimalizálja a PDF-dokumentumot az OptimizationOptions segítségével
pdfDocument.OptimizeResources(optimizeOptions);
```

## 5. lépés: Mentse el a frissített dokumentumot

 A PDF-dokumentum optimalizálása után a frissített dokumentumot elmentheti a`Save` módszere a`Document`osztály. A következő kódrészlet bemutatja, hogyan kell menteni a frissített dokumentumot:

```csharp
// Mentse el a frissített dokumentumot
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 6. lépés: Szerezze be az eredeti és csökkentett fájlméretet

 Végül a PDF-dokumentum eredeti és csökkentett fájlméretét a`FileInfo` osztályú System.IO. A következő kódrészlet bemutatja, hogyan szerezheti be az eredeti és csökkentett fájlméretet:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### Példa forráskódra a Get Unembed Fonts használatához az Aspose.PDF for .NET használatával

Íme a teljes példaforráskód a beágyazott betűtípusok PDF-dokumentumból való lekéréséhez az Aspose.PDF for .NET használatával:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Állítsa be az UnembedFonts opciót
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// Optimalizálja a PDF-dokumentumot az OptimizationOptions segítségével
pdfDocument.OptimizeResources(optimizeOptions);
// Mentse el a frissített dokumentumot
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan használható az Aspose.PDF for .NET a beágyazott betűtípusok PDF-dokumentumból való lekéréséhez. A lépésenkénti útmutató követésével könnyedén megvalósíthatja ezt a funkciót C# alkalmazásaiban. A betűtípusok beágyazásának megszüntetése előnyös lehet, ha külön kell dolgoznia a kibontott betűtípusokkal, vagy konzisztens betűtípus-használatot kell biztosítania a különböző platformokon.

## GYIK

#### K: Mi a célja a betűtípusok PDF-dokumentumból való eltávolításának?

V: A betűtípusok beágyazásának megszüntetése PDF-dokumentumból lehetővé teszi a beágyazott betűtípusok kibontását és más alkalmazásokban való felhasználását. Ez hasznos lehet a konzisztens betűtípus-megjelenítés biztosításához és a dokumentum vizuális megjelenésének megőrzéséhez.

#### K: Hogyan adhatom meg a dokumentumkönyvtár elérési útját a C# kódban?

 V: A dokumentumkönyvtár elérési útjának megadásához cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban annak a könyvtárnak az elérési útjával, ahol a PDF-dokumentum található.

####  K: Mit jelent a`UnembedFonts` option do, and where is it set?

 V: A`UnembedFonts` opció, elérhető a`OptimizationOptions` osztály, engedélyezi vagy letiltja a fontok beágyazásának feloldását a PDF dokumentumból. Ennek az opciónak a beállításához`true`, használja a következő kódot:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### K: Visszaállíthatom az optimalizálási folyamat során végrehajtott változtatásokat?

V: Az Aspose.PDF for .NET nem módosítja az eredeti PDF-dokumentumot az optimalizálás során. Az optimalizálási folyamatot a dokumentum másolatán hajtják végre, az eredetit érintetlenül hagyva.

#### K: Hogyan ellenőrizhetem az eredeti és a csökkentett fájlméretet az optimalizálás után?

 V: Használhatja a`FileInfo` osztálya`System.IO` hogy megkapja az eredeti és csökkentett fájlméretet. Íme egy példa kódrészlet ennek eléréséhez:

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```