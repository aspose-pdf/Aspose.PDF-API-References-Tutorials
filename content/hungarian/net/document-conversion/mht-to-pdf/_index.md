---
title: MHT PDF-be
linktitle: MHT PDF-be
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató az MHT PDF formátumba konvertálásához az Aspose.PDF for .NET használatával.
type: docs
weight: 70
url: /hu/net/document-conversion/mht-to-pdf/
---
Ebben az oktatóanyagban végigvezetjük az MHT-fájlok PDF formátumba konvertálásának folyamatán az Aspose.PDF for .NET használatával. Az MHT (MIME HTML) egy teljes weboldal mentésére szolgáló formátum, beleértve a képeket és a kapcsolódó tartalmakat. Az alábbi lépések követésével az MHT fájlokat PDF formátumba konvertálhatja.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: MHT-fájl betöltése
Ebben a lépésben betöltjük az MHT-fájlt az Aspose.PDF for .NET használatával. Kövesse az alábbi kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

// Töltse be a dokumentumot
Document document = new Document(dataDir + "test.mht", options);
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol az MHT fájl található.

## 2. lépés: MHT konvertálás PDF-be
Az MHT fájl betöltése után folytathatjuk a konvertálást PDF-be. Használja a következő kódot:

```csharp
// Mentse el a kimenetet PDF dokumentumként
document.Save(dataDir + "MHTToPDF_out.pdf");
```

 A fenti kód az MHT fájlt PDF formátumba konvertálja, és fájlnévként menti`"MHTToPDF_out.pdf"`.

### Példa forráskód MHT-hoz PDF-be az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
// Dokumentum betöltése
Document document = new Document(dataDir  + "test.mht", options);
// Mentse el a kimenetet PDF dokumentumként
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## Következtetés
Ebben az oktatóanyagban az Aspose.PDF for .NET használatával lépésről lépésre bemutatjuk az MHT-fájlok PDF-formátumba konvertálásának folyamatát. A fent vázolt utasításokat követve most már képesnek kell lennie az MHT-fájlok PDF formátumba konvertálására. Ez a funkció akkor lehet hasznos, ha teljes weboldalakat kell PDF dokumentumokká konvertálnia.

### GYIK

#### K: Az Aspose.PDF for .NET támogatja a beágyazott képeket tartalmazó MHT-fájlok PDF formátumba konvertálását?

V: Igen, az Aspose.PDF for .NET támogatja a beágyazott képekkel rendelkező MHT-fájlok PDF-formátumba konvertálását. A könyvtár képes kezelni a teljes weboldal tartalmát, beleértve a képeket és a kapcsolódó forrásokat, és PDF dokumentummá konvertálni.

#### K: Testreszabhatom a PDF kimenetet az MHT PDF konvertálási folyamat során?

V: Igen, az Aspose.PDF for .NET különféle lehetőségeket kínál a PDF-kimenet testreszabásához az MHT-fájl konvertálási folyamat során. Beállíthat olyan tulajdonságokat, mint például az oldalméret, a tájolás, a margók és egyebek az eredményül kapott PDF-dokumentum megjelenésének szabályozásához.

#### K: Az Aspose.PDF for .NET megőrzi a hiperhivatkozásokat és az eredeti MHT-fájl formázását a PDF-kimenetben?

V: Igen, az Aspose.PDF for .NET megőrzi az eredeti MHT-fájl hiperhivatkozásait és formázását a PDF-kimenetben. A könyvtár biztosítja, hogy a konvertált PDF ugyanazt az elrendezést és tartalmat tartsa meg, mint a forrás MHT-fájl.

#### K: Konvertálhatok több MHT-fájlt különálló PDF-dokumentummá az Aspose.PDF for .NET használatával?

V: Igen, az Aspose.PDF for .NET segítségével több MHT-fájlt is konvertálhat külön PDF-dokumentummá. Egyszerűen töltse be az egyes MHT-fájlokat, és mentse el külön PDF-dokumentumként, egyedi fájlnévvel.