---
title: Állítsa be a szabad szöveges megjegyzések formázását
linktitle: Állítsa be a szabad szöveges megjegyzések formázását
second_title: Aspose.PDF for .NET API Reference
description: Ez a cikk lépésről lépésre bemutatja, hogyan hozhat létre szabad szöveges kommentárokat és határozhatja meg annak tartalmát az Aspose.PDF for .NET használatával
type: docs
weight: 140
url: /hu/net/annotations/setfreetextannotationformatting/
---
Az Aspose.PDF for .NET egy hatékony és könnyen használható PDF-dokumentum-manipulációs API, amely lehetővé teszi a PDF-fájlok programozott kezelését .NET-alkalmazásaiban. Az Aspose.PDF for .NET egyik szolgáltatása a szabad szöveges megjegyzések formázásának lehetősége a PDF dokumentumokban. Ebben a cikkben lépésről lépésre végigvezetjük az Aspose.PDF for .NET használatával történő szabad szöveges kommentárformázásának beállításán.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Microsoft Visual Studio 2010 vagy újabb
- Aspose.PDF .NET-hez
- C# alapismeretek



## 1. lépés: Hozzon létre egy új C# konzolalkalmazást

Először hozzon létre egy új C#-konzolalkalmazást a Microsoft Visual Studio-ban. Új konzolalkalmazás létrehozásához válassza a "Fájl" > "Új" > "Projekt" > "Visual C#" > "Konzolalkalmazás" lehetőséget a főmenüben.

## 2. lépés: Adjon hozzá hivatkozást az Aspose.PDF fájlhoz a .NET-hez

Ezután adjon hozzá hivatkozást az Aspose.PDF for .NET fájlhoz a projektben. Ehhez kattintson a jobb gombbal a projektre a "Solution Explorer" ablaktáblában, válassza a "Hozzáadás" > "Referencia" lehetőséget, majd tallózással keresse meg azt a helyet, ahová az Aspose.PDF for .NET DLL fájlt mentette. Válassza ki a DLL fájlt, és kattintson az "OK" gombra a hivatkozás hozzáadásához a projekthez.

## 3. lépés: Állítsa be a környezetet

Miután hozzáadta a hivatkozást az Aspose.PDF for .NET-hez, be kell állítania a környezetet. Ehhez hozzon létre egy új "dataDir" karakterlánc-változót, és állítsa be annak a könyvtárnak az elérési útjára, ahol a PDF-dokumentum található. Cserélje le a "DOKUMENTUMKÖNYVTÁR" kifejezést az alábbi kódban a dokumentumkönyvtár tényleges elérési útjával:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. lépés: Nyissa meg a PDF dokumentumot

A környezet beállítása után a következő kóddal nyithatja meg a PDF-dokumentumot:

```csharp
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Cserélje le a „SetFreeTextAnnotationFormatting.pdf” fájlt a PDF-dokumentum tényleges nevével.

## 5. lépés: Állítsa be az alapértelmezett megjelenést

A szabad szöveges megjegyzés alapértelmezett megjelenésének beállításához példányosítania kell a DefaultAppearance objektumot a kívánt betűtípussal, betűmérettel és színnel. Ebben az oktatóanyagban a betűtípust "Arial"-ra, a betűméretet 28-ra, a színt pedig pirosra állítjuk.

```csharp
// Példányosítása DefaultAppearance objektum
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. lépés: Hozzon létre egy szabad szöveges megjegyzést

Most, hogy beállította az alapértelmezett megjelenést, létrehozhat egy szabad szöveges megjegyzést a következő kóddal:

```csharp
// Jegyzet létrehozása
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

A fenti kód egy új szabad szöveges megjegyzést hoz létre a PDF dokumentum második oldalán. A kommentár (200, 400) helyen lesz, szélessége 400, magassága pedig 600 lesz.

## 7. lépés: Adja meg a megjegyzés tartalmát

A szabad szöveges kommentár létrehozása után a következő kóddal adhatja meg a kommentár tartalmát:

```csharp
// Adja meg a megjegyzés tartalmát
freetext.Contents = "Free Text
```

### Példa forráskódra a Set Free Text Annotation Formatting programhoz az Aspose.PDF segítségével .NET-hez
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Példányosítása DefaultAppearance objektum
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Jegyzet létrehozása
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Adja meg a megjegyzés tartalmát
freetext.Contents = "Free Text";
// Annotáció hozzáadása az oldal kommentárgyűjteményéhez
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Mentse el a frissített dokumentumot
pdfDocument.Save(dataDir);            
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan állíthat be szabad szöveges megjegyzés formázást egy PDF-dokumentumban az Aspose.PDF for .NET használatával. A könyvtár egyszerű és hatékony módszert biztosít a PDF-dokumentumokkal való programozott munkavégzéshez, lehetővé téve a fejlesztők számára, hogy különféle típusú megjegyzéseket hozzanak létre és testreszabjanak, beleértve a szabad szöveges kommentárokat is. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával egyszerűen beállíthatja a környezetet, megnyithat egy PDF-dokumentumot, és szabad szöveges megjegyzést készíthet egyéni formázással. Az Aspose.PDF for .NET egy robusztus és megbízható API, amely leegyszerűsíti a PDF-dokumentumkezelési feladatokat, így értékes eszköz a PDF-fájlokkal dolgozó .NET-fejlesztők számára.

### GYIK

#### K: Mi az a szabad szöveges megjegyzés egy PDF-dokumentumban?

V: A PDF-dokumentumban lévő szabad szöveges kommentárok olyan típusú megjegyzések, amelyek lehetővé teszik szöveg hozzáadását a dokumentumhoz anélkül, hogy egy adott helyhez vagy szerkezethez kötődnének. Általában megjegyzések, megjegyzések vagy egyéb kiegészítő információk megadására használják a dokumentumban.

#### K: Testreszabhatom a szabad szöveges kommentár megjelenését az Aspose.PDF for .NET használatával?

V: Igen, testreszabhatja a szabad szöveges megjegyzés különféle tulajdonságait, például a betűtípust, a betűméretet, a színt, a pozíciót és egyebeket.

#### K: Hogyan határozhatom meg a szabad szöveges kommentár tartalmát?

 V: A szabad szöveges megjegyzés tartalmának megadásához beállíthatja a`Contents` tulajdona a`FreeTextAnnotation` objektumot a kívánt szövegre.

#### K: Hozzáadhatok több szabad szöveges megjegyzést egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával?

 V: Igen, több szabad szöveges megjegyzést is létrehozhat egy PDF-dokumentumban, ha több példányt hoz létre a`FreeTextAnnotation`objektumot, és hozzáadhatja azokat a dokumentum különböző oldalaihoz vagy helyeihez.