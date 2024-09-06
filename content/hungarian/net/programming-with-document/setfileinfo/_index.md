---
title: Állítsa be a fájladatokat a PDF-fájlban
linktitle: Állítsa be a fájladatokat a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan használhatja az Aspose.PDF for .NET-et a fájladatok PDF-fájlban történő beállításához.
type: docs
weight: 310
url: /hu/net/programming-with-document/setfileinfo/
---
Ha olyan projekten dolgozik, amelyhez PDF-fájlok kezelését igényli az Aspose.PDF for .NET használatával, akkor az egyik hasznos funkció a PDF-dokumentum fájlinformációinak megadása. A fájlinformációk különféle részleteket tartalmaznak, például a szerzőt, a létrehozás dátumát, a kulcsszavakat, a módosítás dátumát, a tárgyat és a címet. Ez az útmutató végigvezeti Önt egy PDF-dokumentum fájlinformációinak beállításán C# forráskóddal az Aspose.PDF for .NET-hez.

## Lépésről lépésre a fájladatok beállításához az Aspose.PDF for .NET használatával

1. Hozzon létre egy új C#-projektet a Visual Studio IDE-ben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárra a projektben.
3. Hozzon létre egy új PDF-dokumentumobjektumot annak a PDF-fájlnak az elérési útjának megadásával, amelynek fájlinformációit módosítani szeretné.

## 1. lépés: Állítsa be a dokumentumok könyvtárának elérési útját.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF dokumentumot

```csharp
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## 3. lépés: Használja a DocumentInfo objektumot a PDF-dokumentum fájlinformációinak eléréséhez.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## 4. lépés: Állítsa be a kívánt fájlinformációs értékeket a DocumentInfo objektum tulajdonságainak használatával.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## 5. lépés: Mentse el a frissített PDF dokumentumot a megadott helyre.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## 6. lépés: Ellenőrizze, hogy a fájlinformációk frissítése sikeresen megtörtént.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Sikeresen beállította egy PDF-dokumentum fájlinformációit az Aspose.PDF for .NET használatával.

### Példa forráskódra a Set File Info-hoz az Aspose.PDF segítségével a .NET-hez


```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Adja meg a dokumentum adatait
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Mentse a kimeneti dokumentumot
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Következtetés

Összefoglalva, az Aspose.PDF for .NET egyszerű és hatékony módot kínál a PDF-dokumentumok fájlinformációinak beállítására. A fent említett lépések követésével könnyedén beállíthatja a kívánt fájlinformáció-értékeket PDF-dokumentumaihoz C# forráskód használatával.

### GYIK a beállított fájlinformációkhoz PDF fájlban

#### K: Beállíthatok további, a példában nem említett fájlinformációs tulajdonságokat?

 V: Igen, beállíthat további fájlinformációs tulajdonságokat a`DocumentInfo` objektum az Aspose.PDF-ben .NET-hez. A`DocumentInfo`osztály különféle tulajdonságokat biztosít, amelyek lehetővé teszik további információk, például a gyártó, a verzió és az egyéni tulajdonságok beállítását.

#### K: Lekérhető-e a fájlinformáció egy meglévő PDF-dokumentumból?

 V: Igen, lekérheti a fájlinformációkat egy meglévő PDF-dokumentumból az Aspose.PDF for .NET használatával. Ehhez használhatja a`DocumentInfo` objektumot, hogy hozzáférjen a fájlinformáció tulajdonságaihoz és elolvassa a PDF dokumentumban tárolt információkat.

#### K: A fájlinformációk beállítása módosítja az eredeti PDF dokumentumot?

V: Nem, a fájlinformációk Aspose.PDF for .NET használatával beállítása nem módosítja az eredeti PDF-dokumentumot. Ehelyett új PDF-dokumentumot hoz létre a frissített fájlinformációkkal. Az eredeti PDF dokumentum változatlan marad.