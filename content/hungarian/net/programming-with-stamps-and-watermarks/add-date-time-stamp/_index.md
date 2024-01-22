---
title: Dátum és időbélyeg hozzáadása PDF-fájlhoz
linktitle: Dátum és időbélyeg hozzáadása PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá egyszerűen dátum- és időbélyegzőt PDF-fájlhoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Ebben a cikkben lépésről lépésre bemutatjuk, hogyan adhat hozzá dátum- és időbélyegzőt PDF-fájlhoz az Aspose.PDF for .NET használatával. Megmutatjuk, hogyan használhatja a megadott C# forráskódot dátum- és időbélyegző hozzáadásához egy meglévő PDF-fájlhoz.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 1. lépés: A környezet beállítása

Mielőtt dátum- és időbélyeget adhatna egy PDF-dokumentumhoz, be kell állítania a fejlesztői környezetet. Íme a követendő lépések:

1. Nyissa meg kedvenc IDE-jét (Integrated Development Environment).
2. Hozzon létre egy új C# projektet.
3. Győződjön meg arról, hogy hozzáadott egy hivatkozást a .NET Aspose.PDF könyvtárára.

## 2. lépés: Az Aspose.PDF könyvtár hozzáadása

A .NET-hez készült Aspose.PDF könyvtár szükséges a PDF dokumentumokkal való együttműködéshez a projektben.

## 3. lépés: A PDF dokumentum betöltése

A dátum- és időbélyeg hozzáadásának első lépése a meglévő PDF-dokumentum betöltése a projektbe. Itt van, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a PDF-dokumentum könyvtárának tényleges elérési útjára.

## 4. lépés: Dátum- és időbélyegző létrehozása

Most, hogy feltöltötte a dokumentumot

  PDF, létrehozhatja a hozzáadandó dátum- és időbélyegzőt. Íme, hogyan kell csinálni:

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Hozzon létre egy szöveges puffert
TextStamp textStamp = new TextStamp(annotationText);
```

A fenti kód egy új szöveges puffert hoz létre, amely tartalmazza az aktuális dátumot és időt.

## 5. lépés: A bélyegző tulajdonságainak konfigurálása

Mielőtt hozzáadná a bélyegzőt a PDF-dokumentumhoz, beállíthatja a bélyegző különféle tulajdonságait, például margót, vízszintes és függőleges igazítást stb. A következőképpen teheti meg:

```csharp
// Állítsa be a puffer tulajdonságait
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Ezeket a tulajdonságokat igényei szerint módosíthatja.

## 6. lépés: Bélyegző hozzáadása a PDF-hez

Most, hogy a dátum- és időbélyeg készen áll, hozzáadhatja a PDF-dokumentum egy adott oldalához. Itt van, hogyan:

```csharp
// Adja hozzá a bélyeget az oldal bélyeggyűjteményéhez
pdfDocument.Pages[1].AddStamp(textStamp);
```

fenti kód hozzáadja a pecsétet a PDF-dokumentum első oldalához. Szükség esetén megadhat másik oldalt is.

## 7. lépés: Mentse el a kimeneti dokumentumot

A dátum- és időbélyegző hozzáadása után mentheti a módosított PDF-dokumentumot. Itt van, hogyan:

```csharp
// Mentse el a kimeneti dokumentumot
pdfDocument.Save(dataDir);
```

A fenti kód a szerkesztett PDF dokumentumot a megadott könyvtárba menti.

### Forráskód minta a Dátum és időbélyeg hozzáadása az Aspose.PDF for .NET segítségével fájlhoz 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Szöveges bélyegző létrehozása
TextStamp textStamp = new TextStamp(annotationText);

// Állítsa be a bélyegző tulajdonságait
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Bélyegző hozzáadása a bélyeggyűjteményhez
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Mentse a kimeneti dokumentumot
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat hozzá dátum- és időbélyegzőt az Aspose.PDF for .NET használatával. Mostantól ezt a tudást saját projektjeire is alkalmazhatja, hogy dátum- és időbélyegzőket adjon a PDF-dokumentumokhoz.

### GYIK a dátum és időbélyeg hozzáadásához PDF-fájlban

#### K: Mi a célja a dátum- és időbélyegző hozzáadásának egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával?

V: Dátum- és időbélyegző hozzáadása a PDF-dokumentumhoz növeli annak információs értékét azáltal, hogy jelzi a dokumentum módosításának vagy létrehozásának időpontját. Ez a funkció hasznos a dokumentumok változásainak nyomon követéséhez, és referenciapontként szolgál a dokumentumelőzményekhez.

#### K: Testreszabhatom a dátum- és időbélyegző formátumát a konkrét követelményeknek megfelelően?

 V: Igen, testreszabhatja a dátum- és időbélyegző formátumát saját igényei szerint. A megadott C# forráskód a`DateTime.Now.ToString()` módszer az időbélyeg meghatározott formátumban történő generálására. Ezt a kódot szükség szerint módosíthatja az időbélyegző formázásához.

#### K: Lehetséges-e dátum- és időbélyegző hozzáadása egy adott helyhez egy PDF-oldalon?

 V: Természetesen módosíthatja a dátum- és időbélyegző elhelyezését a PDF-oldalon a fájl tulajdonságainak módosításával.`TextStamp` tárgy. Az oktatóanyagban található kód bemutatja, hogyan állíthat be olyan tulajdonságokat, mint a margó, az igazítás és a függőleges pozicionálás.

#### K: Hozzáadhatok több dátum- és időbélyeget ugyanazon PDF-dokumentum különböző oldalaihoz?

 V: Igen, több dátum- és időbélyeget is hozzáadhat ugyanazon PDF-dokumentum különböző oldalaihoz. Egyszerűen ismételje meg a létrehozási folyamatot a`TextStamp` objektumot, és konfigurálja tulajdonságait minden egyes kívánt oldalhoz.

#### K: Hogyan módosíthatom a dátum- és időbélyegző szövegének betűtípusát, méretét vagy színét?

 V: A dátum- és időbélyegzőszöveg betűtípusának, méretének vagy színének módosításához testreszabhatja a`DefaultAppearance` létrehozásához használt objektum`TextStamp`. Módosítsa a betűtípus nevét, méretét és színértékeit a kívánt megjelenés eléréséhez.

#### K: Lehetséges más típusú megjegyzések vagy bélyegzők hozzáadása egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával?

V: Igen, az Aspose.PDF for .NET a megjegyzéstípusok széles skáláját kínálja, amelyeket PDF-dokumentumokhoz adhat hozzá, beleértve a szöveges megjegyzéseket, bélyegzőket, vonalakat, alakzatokat és egyebeket. Az Aspose.PDF dokumentációban talál további részleteket a megjegyzésekkel való munkáról.

#### K: Vannak korlátozások vagy szempontok, amikor dátum- és időbélyegzőt ad hozzá egy PDF-dokumentumhoz?

V: Bár a dátum- és időbélyegző hozzáadása egyszerű, vegye figyelembe az olyan tényezőket, mint a dokumentum elrendezése és a meglévő tartalom. Ügyeljen arra, hogy a bélyegző elhelyezése ne takarjon el fontos információkat, és ne befolyásolja a dokumentum olvashatóságát.

#### K: Hogyan integrálhatom ezt a módszert a saját projektjeimbe, hogy dátum- és időbélyegzőket adjak a PDF-dokumentumokhoz?

V: A módszer integrálásához kövesse a megadott lépéseket, és állítsa be a kódot, hogy illeszkedjen a projekt szerkezetéhez. Dátum- és időbélyegzőket adhat a meglévő PDF-dokumentumokhoz, hogy fokozza azok hasznosságát, és egyértelmű ütemezést biztosítson a változásokhoz.

#### K: Automatizálhatom a dátum- és időbélyegzők több PDF-dokumentumhoz való hozzáadásának folyamatát?

V: Igen, automatizálhatja a dátum- és időbélyegzők több PDF-dokumentumhoz való hozzáadásának folyamatát egy olyan szkript vagy program létrehozásával, amely egy dokumentumlistán keresztül ismétlődik, és mindegyikre ugyanazt a bélyegzési folyamatot alkalmazza.