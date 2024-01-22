---
title: Szövegbélyegző hozzáadása PDF-fájlhoz
linktitle: Szövegbélyegző hozzáadása PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá egyszerűen szövegbélyeget PDF-fájlhoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 50
url: /hu/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá szövegbélyeget PDF-fájlhoz az Aspose.PDF for .NET használatával. Megmutatjuk, hogyan használhatja a megadott C# forráskódot egyéni szövegbélyegző hozzáadásához a PDF-fájl adott oldalához.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A PDF dokumentum betöltése

Az első lépés a meglévő PDF dokumentum betöltése a projektbe. Itt van, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a PDF-dokumentum könyvtárának tényleges elérési útjára.

## 3. lépés: A szöveges puffer létrehozása

Most, hogy feltöltötte a PDF-dokumentumot, létrehozhatja a hozzáadandó szövegbélyeget. Íme, hogyan kell csinálni:

```csharp
// Hozza létre a szöveges puffert
TextStamp textStamp = new TextStamp("Example Stamp");
```

A fenti kód egy új szöveges puffert hoz létre, amely a megadott szöveget tartalmazza.

## 4. lépés: A szövegbélyegző tulajdonságainak konfigurálása

Mielőtt hozzáadná a szövegbélyeget a PDF-dokumentumhoz, beállíthatja a bélyegző különféle tulajdonságait, például a hátteret, a pozíciót, az elforgatást, a betűtípust, a méretet stb. Így teheti meg:

```csharp
// Konfigurálja a szöveges puffer tulajdonságait
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Ezeket a tulajdonságokat igényei szerint módosíthatja.

## 5. lépés: Adjon hozzá szövegbélyeget a PDF-hez

Most, hogy a szövegbélyegző készen áll, hozzáadhatja a PDF-dokumentum egy adott oldalához. Itt van, hogyan:

```csharp
//Szöveges puffer hozzáadása egy adott oldalhoz
pdfDocument.Pages[1].AddStamp(textStamp);
```

A fenti kód hozzáadja a szövegbélyeget a PDF-dokumentum első oldalához. Szükség esetén megadhat másik oldalt is.

## 6. lépés: Mentse el a kimeneti dokumentumot

A szövegbélyegző hozzáadása után elmentheti a szerkesztett PDF dokumentumot. Itt van, hogyan:

```csharp
// Mentse el a kimeneti dokumentumot
pdfDocument.Save(dataDir);
```

A fenti kód a módosított PDF dokumentumot a megadott könyvtárba menti.

### Minta forráskód a Szövegbélyegző hozzáadása az Aspose.PDF for .NET használatával fájlhoz 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Szöveges bélyegző létrehozása
TextStamp textStamp = new TextStamp("Sample Stamp");

// Állítsa be, hogy a bélyegző háttér legyen-e
textStamp.Background = true;

// Állítsa be az eredetet
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Bélyegző forgatása
textStamp.Rotate = Rotation.on90;

// Állítsa be a szöveg tulajdonságait
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Bélyegző hozzáadása az adott oldalhoz
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Mentse a kimeneti dokumentumot
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat hozzá szövegbélyeget az Aspose.PDF for .NET használatával. Mostantól ezt a tudást saját projektjeire is alkalmazhatja, hogy egyéni szövegbélyegzőket adjon a PDF-dokumentumokhoz.

### GYIK a szövegbélyegző PDF-fájlhoz való hozzáadásához

#### K: Mi a célja szövegbélyegző hozzáadásának egy PDF-fájlhoz az Aspose.PDF for .NET használatával?

V: Szövegbélyegző hozzáadásával egyéni szöveget helyezhet el a PDF-dokumentum egy adott oldalán. Ez a funkció hasznos címkék, megjegyzések, vízjelek vagy bármilyen más szöveges információ hozzáadásához, hogy javítsa a dokumentum tartalmát és további kontextust biztosítson.

#### K: Testreszabhatom a szövegbélyegző megjelenését, például a betűtípust, a méretet, a színt és az elforgatást?

 V: Igen, teljesen testreszabhatja a szövegbélyegző megjelenését. A mellékelt C# forráskód bemutatja, hogyan kell beállítani a különböző tulajdonságokat`TextStamp` objektum, beleértve a betűtípust, a betűméretet, a betűstílust, a szöveg színét, a háttérszínt és az elforgatást.

#### K: Lehetséges-e több szövegbélyeg hozzáadása ugyanazon PDF-dokumentum különböző oldalaihoz?

V: Természetesen több szövegbélyeget is hozzáadhat ugyanazon PDF-dokumentum különböző oldalaihoz. Az oktatóanyagban található kód lehetővé teszi, hogy megadja a céloldalt a szövegbélyegző hozzáadásához, így sokoldalúan használható a dokumentum különböző oldalaihoz.

#### K: Hogyan határozhatom meg a szövegbélyegző helyét a PDF-dokumentumban?

 V: Testreszabhatja a szövegbélyegző pozícióját a`XIndent` és`YIndent` tulajdonságai a`TextStamp` tárgy. Ezek a tulajdonságok határozzák meg a bélyegző bal felső sarkának koordinátáit az oldal eredetéhez képest.

#### K: Alkalmazhatom ezt a módszert meglévő PDF-dokumentumokra szövegbélyegzők hozzáadásához?

V: Igen, ezt a módszert alkalmazhatja meglévő PDF-dokumentumokhoz szövegbélyegzők hozzáadásához. Az oktatóanyagban található kód bemutatja, hogyan tölthet be egy meglévő PDF-dokumentumot, és hogyan adhat hozzá szövegbélyeget egy adott oldalhoz.

#### K: Hozzáadhatok háttér- és előtérszínt is a szövegbélyegzőhöz?

 V: Igen, háttér- és előtérszínt is hozzáadhat a szövegbélyegzőhöz. Beállításával a`Background` tulajdonát`true` , színes hátteret biztosíthat a szövegbélyegzőhöz. Ezenkívül beállíthatja a`TextState.ForegroundColor` tulajdonság megadásához magának a szövegnek a színét.

#### K: Hogyan biztosíthatom, hogy a szövegbélyegző ne takarja el a PDF-dokumentum mögöttes tartalmát?

 V: Szöveges bélyegző hozzáadásakor ügyeljen annak elhelyezésére, hogy ne akadályozza a kritikus információkat, és ne befolyásolja negatívan a dokumentum olvashatóságát. Beállíthatja a`XIndent` és`YIndent` tulajdonságokkal a szövegbélyegző megfelelő elhelyezéséhez.

#### K: Használhatom ezt a módszert szövegen kívüli bélyegzők, például képek vagy logók hozzáadására?

V: Ez a speciális oktatóanyag a szöveges bélyegek hozzáadására összpontosít, de ehhez hasonlóan más típusú bélyegzőket is hozzáadhat, például képeket vagy logókat az Aspose.PDF for .NET használatával. A folyamat magában foglalja a megfelelő bélyegző objektum létrehozását és tulajdonságainak konfigurálását.

#### K: Hogyan automatizálhatom a szövegbélyegzők több PDF-dokumentumhoz való hozzáadásának folyamatát?

V: Automatizálhatja a szövegbélyegzők több PDF-dokumentumhoz való hozzáadásának folyamatát, ha létrehoz egy szkriptet vagy programot, amely egy dokumentumlistán keresztül iterál, és mindegyikre ugyanazt a szövegbélyegzési folyamatot alkalmazza.