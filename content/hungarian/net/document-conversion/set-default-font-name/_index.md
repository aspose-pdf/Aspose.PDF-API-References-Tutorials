---
title: Állítsa be az alapértelmezett betűtípus nevét
linktitle: Állítsa be az alapértelmezett betűtípus nevét
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthat be alapértelmezett betűtípusnevet PDF-fájlok képekké történő renderelésekor az Aspose.PDF for .NET használatával. Ez az útmutató tartalmazza az előfeltételeket, a lépésenkénti utasításokat és a GYIK-et.
type: docs
weight: 270
url: /hu/net/document-conversion/set-default-font-name/
---
## Bevezetés

Próbált már PDF-dokumentumot képpé renderelni, de úgy találta, hogy a betűtípusok egyszerűen nem néznek ki jól? Lehet, hogy a szöveg torznak tűnik, vagy az eredeti betűtípus nem támogatott. Itt mentheti meg a napot az alapértelmezett betűtípus beállítása! Az Aspose.PDF for .NET használatával egyszerűen beállíthat egy alapértelmezett betűtípust a PDF-megjelenítéshez, így a dokumentum éles és professzionális megjelenésű. Ebben az oktatóanyagban végigvezetjük, hogyan állíthatja be az alapértelmezett betűtípusnevet PDF-fájl képpé történő renderelésekor. Ennek az útmutatónak a végére rendelkezni fog azzal a készségekkel, hogy megbirkózzon minden PDF-megjelenítési kihívással. Kész? Merüljünk el!

## Előfeltételek

Mielőtt belevágnánk a kódba, néhány dolgot meg kell határoznia:

- Aspose.PDF .NET-hez: Ezt a hatékony könyvtárat fogjuk használni PDF-dokumentumunk manipulálására. Letöltheti a[Aspose honlapja](https://releases.aspose.com/pdf/net/).
- Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Ez lesz a fejlesztési környezetünk.
- .NET-keretrendszer: Győződjön meg arról, hogy a .NET-keretrendszer telepítve van. Az Aspose.PDF for .NET különféle verziókat támogat, ezért ellenőrizze a dokumentációt, hogy megfeleljen az igényeinek.
- PDF-dokumentum: A munkához szüksége lesz egy minta PDF-dokumentumra. Ha nem rendelkezik ilyennel, hozzon létre egy egyszerű PDF-fájlt, vagy töltsön le egy mintát online.

Ha mindent beállított, készen állunk a kódolás megkezdésére!

## Csomagok importálása

Mielőtt belemerülnénk a kódba, elengedhetetlen a szükséges csomagok importálása. Ez biztosítja, hogy hozzáférjünk a projektünkhöz szükséges összes osztályhoz és metódushoz.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Ezek az importálások létfontosságúak, mivel behozzák a szükséges névtereket a PDF-kezeléshez, a képmegjelenítéshez és a fájlfolyam-műveletekhez.

## 1. lépés: Állítsa be a projektet és a dokumentum elérési utat

Először is állítsuk be a könyvtár elérési útját, ahol a PDF-dokumentum található. Ez lesz a kiindulópont a PDF-fájl kezeléséhez.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Itt,`dataDir` az a könyvtár, ahol a PDF-dokumentum található. Ügyeljen arra, hogy cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentum tényleges elérési útjával. Ez elengedhetetlen, mivel a kódnak tudnia kell, hogy honnan töltse le a PDF-fájlt.

## 2. lépés: Töltse be a PDF-dokumentumot

Most, hogy megvan a dokumentum elérési útja, a következő lépés a PDF dokumentum betöltése a memóriába, hogy elkezdhessük a munkát.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Használjuk a`Document` osztályt az Aspose.PDF könyvtárból a PDF fájl betöltéséhez. Ez az osztály különféle módszereket és tulajdonságokat biztosít a PDF-dokumentum kezeléséhez. A`"input.pdf"` le kell cserélni a PDF tényleges fájlnevére. Ez a fájl lesz a renderelés bemenete.

## 3. lépés: Hozzon létre egy képfolyamot a kimenethez

A dokumentum betöltése után be kell állítanunk egy adatfolyamot a renderelt kép mentéséhez. Ez az a hely, ahol a kimeneti kép tárolódik.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 A`FileStream`osztályt egy új fájl létrehozására használjuk, amelybe a renderelt kép mentésre kerül. Ebben a példában a képet másként mentjük`"SetDefaultFontName.png"` . A`FileMode.Create` biztosítja egy új fájl létrehozását, vagy egy meglévő fájl felülírását.

## 4. lépés: Állítsa be a kép felbontását

Mielőtt képpé renderelné a PDF-fájlt, nagyon fontos beállítani a felbontást. Ez határozza meg a kimeneti kép minőségét és tisztaságát.

```csharp
Resolution resolution = new Resolution(300);
```
 A`Resolution` osztály állítja be a kimeneti kép felbontását. Itt a 300 DPI (dots per inch) felbontást választottuk, ami a jó minőségű képek szabványa. Ez biztosítja, hogy a PDF szövege és grafikái tisztán jelenjenek meg a részletek elvesztése nélkül.

## 5. lépés: Konfigurálja a PNG-eszközt

Ezután konfigurálnunk kell azt az eszközt, amely kezeli a PDF PNG-képké történő megjelenítését.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 A`PngDevice` osztály felelős a PDF-dokumentum PNG-képpé történő leképezéséért. Áthaladva a`resolution` ellenőrzi, akkor biztosítjuk, hogy a kép a megadott DPI-vel készüljön.

## 6. lépés: Állítsa be az alapértelmezett betűtípus nevét

Itt van a kritikus rész – az alapértelmezett betűtípusnév beállítása. Ez lesz a tartalék betűtípus arra az esetre, ha a PDF eredeti betűtípusa nem érhető el.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Létrehozunk egy példányt`RenderingOptions` és állítsa be`DefaultFontName` tulajdonát`"Arial"`. Ez azt jelenti, hogy ha az eredeti betűtípus a PDF-ben nem található, akkor a rendszer az Arial-t használja helyette. Ez a lépés kulcsfontosságú a szöveg olvashatóságának és megjelenésének megőrzéséhez a renderelt képen.

## 7. lépés: Rendelje meg a PDF-oldalt képpé

Végül, miután mindent beállítottunk, a PDF-dokumentum első oldalát képpé renderelhetjük, és elmenthetjük a korábban létrehozott fájlfolyam segítségével.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 A`Process` módszere a`PngDevice` osztályt használjuk a megadott PDF-oldal (ebben az esetben az első oldal) képpé renderelésére. A kimenet ezután mentésre kerül a`imageStream`. Ez a lépés a PDF-oldalt PNG-képpé alakítja a megadott felbontással és alapértelmezett betűtípussal.

## 8. lépés: Zárja be a File Stream és a PDF-dokumentumot

A kép megjelenítése után feltétlenül zárja be a fájlfolyamot és a PDF-dokumentumot, hogy erőforrásokat szabadítson fel.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Bezárva a`imageStream` biztosítja a fájl megfelelő mentését és az adatok elvesztését. Ártalmatlanítása a`pdfDocument` memóriát és erőforrásokat szabadít fel, megelőzve az esetleges memóriaszivárgást.

## Következtetés

És megvan! Néhány sornyi kóddal megtanulta, hogyan állíthat be alapértelmezett betűtípusnevet, amikor PDF-et képpé renderel az Aspose.PDF for .NET használatával. Ez a készség hihetetlenül hasznos, különösen akkor, ha olyan PDF-fájlokkal foglalkozik, amelyek esetleg nem támogatott betűtípusokat tartalmaznak. Az alapértelmezett betűtípus beállításával biztosítja, hogy a megjelenített képek megőrizzék olvashatóságukat és professzionális megjelenésüket.

## GYIK

### Mi történik, ha a megadott alapértelmezett betűtípus nincs telepítve a rendszerre?
 Ha a megadott alapértelmezett betűtípus a`RenderingOptions` nincs telepítve a rendszerre, az Aspose.PDF egy rendszer által meghatározott tartalék betűtípust fog használni.

### Használhatok az Arialtól eltérő betűtípusokat alapértelmezett betűtípusként?
Teljesen! A rendszerre telepített bármely betűtípust beállíthatja alapértelmezett betűtípusként.

### Lehetséges egy PDF több oldalát képekké renderelni egy menetben?
Igen, végigpörgetheti a PDF-fájl oldalait, és ugyanazzal az eljárással minden oldalt külön-külön renderelhet.

### A nagy felbontás beállítása befolyásolja a PDF-megjelenítés teljesítményét?
Igen, a nagyobb felbontás nagyobb képfájlokat eredményez, és megnövelheti a renderelési időt, de tisztább képeket is eredményez.

### Renderelhetem a PDF-et a PNG-n kívül más képformátumokra is?
Igen, az Aspose.PDF támogatja a különböző képformátumok, például JPEG, BMP és TIFF megjelenítést.