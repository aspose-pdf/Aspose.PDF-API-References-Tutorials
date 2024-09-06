---
title: Fájlinformációk beszerzése PDF fájlban
linktitle: Fájlinformációk beszerzése PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg az Aspose.PDF for .NET GetFileInfo PDF fájlban funkciójának használatát a PDF-dokumentum metaadatainak lekéréséhez.
type: docs
weight: 180
url: /hu/net/programming-with-document/getfileinfo/
---
 Az Aspose.PDF for .NET egy népszerű PDF-manipulációs könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PDF-fájlokat hozzanak létre, szerkesszenek és konvertáljanak .NET-alkalmazásaikban. A könyvtár által kínált szolgáltatások egyike a PDF-dokumentumok metaadataival kapcsolatos információk lekérése. Ez az oktatóanyag végigvezeti Önt a használatának lépésein`GetFileInfo` Az Aspose.PDF for .NET szolgáltatása a PDF-dokumentum metaadataival kapcsolatos információk lekéréséhez.

## 1. lépés: Telepítse az Aspose.PDF for .NET fájlt

 Az Aspose.PDF for .NET használatához .NET-alkalmazásaiban először telepítenie kell a könyvtárat. A könyvtár legújabb verzióját letöltheti a[Aspose.PDF .NET letöltési oldalhoz](https://releases.aspose.com/pdf/net).

Miután letöltötte a könyvtárat, bontsa ki a ZIP-fájl tartalmát egy mappába a számítógépén. Ezután hozzá kell adnia egy hivatkozást az Aspose.PDF for .NET DLL-hez a .NET projektben.

## 2. lépés: Töltse be a PDF-dokumentumot

 Miután telepítette az Aspose.PDF for .NET fájlt, és hozzáadott egy hivatkozást a DLL-re a .NET projektben, elkezdheti használni a`GetFileInfo` funkció a PDF-dokumentum metaadataival kapcsolatos információk lekéréséhez.

A funkció használatának első lépése annak a PDF-dokumentumnak a betöltése, amelyről információkat szeretne lekérni. Ehhez a következő kódot használhatja:

```csharp
// A PDF dokumentum elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a PDF dokumentumot
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 A fenti kódban cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a PDF-dokumentum található. Ez a kód betölti a PDF dokumentumot a`Document` objektum, amelyet aztán a dokumentum metaadataival kapcsolatos információk lekérésére használhat.

## 3. lépés: A dokumentum metaadatainak lekérése

A PDF-dokumentum metaadataival kapcsolatos információk lekéréséhez a következő kódot használhatja:

```csharp
// Dokumentuminformációk beszerzése
DocumentInfo docInfo = pdfDocument.Info;

// Dokumentuminformációk megjelenítése
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

A fenti kódban minden sor lekéri a PDF-dokumentum eltérő metaadat-tulajdonságát, és kiadja azt a konzolnak. Ezt a kódot testreszabhatja úgy, hogy csak az Önt érdeklő tulajdonságokat kérje le.

### Példa a forráskódhoz PDF fájl információinak lekérése az Aspose.PDF for .NET használatával

 Itt található a teljes forráskód a PDF-dokumentum metaadatainak lekéréséhez a`GetFileInfo` Az Aspose.PDF .NET-hez funkciója:

```csharp
// A PDF dokumentum elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a PDF dokumentumot
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Dokumentuminformációk beszerzése
DocumentInfo docInfo = pdfDocument.Info;

// Dokumentuminformációk megjelenítése
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Következtetés

Ebben az oktatóanyagban megvitattuk, hogyan használható az Aspose.PDF for .NET a PDF-dokumentumok metaadataival kapcsolatos információk lekérésére. Egy PDF-dokumentum betöltésével és metaadat-tulajdonságaihoz való hozzáféréssel információkat gyűjthet a dokumentum jellemzőiről és tulajdonságairól. Az Aspose.PDF for .NET egy egyszerű és könnyen használható API-t biztosít a PDF-dokumentumokkal való munkavégzéshez, beleértve a metaadat-információk lekérését, így értékes eszköz a PDF-kezeléshez .NET-alkalmazásokban.

### GYIK

#### K: Mit jelent a metaadat egy PDF-dokumentumban?

V: A PDF-dokumentum metaadatai a dokumentum tulajdonságait és jellemzőit leíró információkra utalnak. Ezek az információk általában magukban foglalják a dokumentum címét, szerzőjét, tárgyát, kulcsszavait, létrehozásának dátumát, módosításának dátumát stb.

#### K: Hogyan telepíthetem az Aspose.PDF for .NET fájlt a .NET projektembe?

 V: Az Aspose.PDF for .NET telepítéséhez le kell töltenie a könyvtárat a[Aspose.PDF .NET letöltési oldalhoz](https://releases.aspose.com/pdf/net). A letöltés után bontsa ki a ZIP-fájl tartalmát, és adjon hozzá hivatkozást az Aspose.PDF for .NET DLL-hez a .NET-projektben.

#### K: Testreszabhatom a kódot úgy, hogy csak meghatározott metaadat-tulajdonságokat kérjen le?

V: Igen, testreszabhatja a kódot bizonyos metaadat-tulajdonságok lekéréséhez úgy, hogy kommentálja azokat a sorokat, amelyekre nincs szüksége. A kód minden sora egy adott metaadat-tulajdonságnak felel meg, így igénye szerint felvehet vagy kizárhat tulajdonságokat.

#### K: Milyen típusú metaadat-tulajdonságokat kérhetek le az Aspose.PDF for .NET használatával?

V: Az Aspose.PDF for .NET használatával lekérheti a PDF-dokumentumok különböző metaadat-tulajdonságait, beleértve a szerzőt, a címet, a tárgyat, a kulcsszavakat, a létrehozás dátumát és a módosítás dátumát.