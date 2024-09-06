---
title: Kép és oldalszám a Fejléc lábléc részben
linktitle: Kép és oldalszám a Fejléc lábléc részben
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá képet és oldalszámot egy PDF-dokumentum fejlécéhez és láblécéhez az Aspose segítségével.
type: docs
weight: 110
url: /hu/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá képet és oldalszámot egy PDF-dokumentum fejléc- és láblécrészéhez az Aspose.PDF for .NET használatával. Megmutatjuk, hogyan használhatja a megadott C# forráskódot oldal létrehozásához, fejléc és lábléc beállításához, kép hozzáadásához a fejléchez és szöveg oldalszámmal történő hozzáadásához a dokumentum láblécéhez.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A PDF-dokumentum és az oldal létrehozása

Az első lépés egy új dokumentum objektum és egy oldal létrehozása a PDF dokumentumban. Íme, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy új dokumentum objektumot
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a dokumentumban
Aspose.Pdf.Page page = doc.Pages.Add();
```

A fenti kód egy új dokumentum objektumot és egy üres oldalt hoz létre a PDF dokumentumban.

## 3. lépés: A fejléc hozzáadása képpel

Most, hogy az oldal elkészült, hozzáadhatunk egy fejléc részt egy képpel. Íme, hogyan:

```csharp
// Hozzon létre egy fejléc szakaszt
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Állítsa be az oldal fejlécét
page. Header = header;

// Hozzon létre egy Image objektumot
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Állítsa be a kép elérési útját
image1.File = dataDir + "aspose-logo.jpg";

// Adja hozzá a képet a PDF-dokumentum oldalfejlécéhez
header.Paragraphs.Add(image1);
```

A fenti kód létrehoz egy fejlécet, beállítja az oldal fejlécét ezzel a szakaszsal, és képet ad a fejléchez.

## 4. lépés: A lábléc hozzáadása az oldalszámmal

Most, hogy a fejléc hozzáadva van, hozzáadhatunk egy lábléc részt oldalszámmal. Íme, hogyan:

```csharp
// Hozzon létre egy lábléc szakaszt
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Határozza meg a PDF dokumentum láblécét
page. Footer = footer;

// Hozzon létre egy TextFragment objektumot
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Adja hozzá a szöveget az oldalszámmal a PDF-dokumentum láblécéhez
footer.Paragraphs.Add(txt);
```

A fenti kód létrehoz egy lábléc szakaszt, beállítja az oldal láblécét ezzel a szakaszsal, és hozzáad egy szövegtöredéket, amely a következő szöveget tartalmazza: "Oldal: ($p $P )"

  amely megjeleníti az oldalszámot.

## 5. lépés: Mentse el a módosított PDF dokumentumot

A fejléc és a lábléc hozzáadása után elmenthetjük a módosított PDF dokumentumot. Íme, hogyan:

```csharp
// Mentse el a módosított PDF dokumentumot
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

A fenti kód a szerkesztett PDF dokumentumot a megadott könyvtárba menti.

### Minta forráskód a kép és az oldalszám fejléc lábléc szakaszához az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a dokumentumobjektumban
Aspose.Pdf.Page page = doc.Pages.Add();

// Hozzon létre fejléc részt a dokumentumban
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Állítsa be a PDF-fájl fejlécét
page.Header = header;

// Hozzon létre egy képobjektumot az oldalon
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Állítsa be a képfájl elérési útját
image1.File = dataDir + "aspose-logo.jpg";

// Kép hozzáadása a PDF fájl fejléc oldalához
header.Paragraphs.Add(image1);

//Hozzon létre egy lábléc szakaszt a dokumentumban
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Állítsa be a PDF-fájl láblécét
page.Footer = footer;

// Hozzon létre egy szöveg objektumot
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Szöveg hozzáadása a PDF-fájl Fejléc részéhez
footer.Paragraphs.Add(txt);

// Mentse el a Pdf fájlt
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat hozzá képet és oldalszámot egy PDF-dokumentum fejléc- és láblécrészéhez az Aspose.PDF for .NET használatával. Most már használhatja ezt a módszert a fejléc és a lábléc testreszabására a PDF-dokumentumokban.

### GYIK

#### K: Mi a célja egy kép és oldalszám hozzáadásának a PDF-dokumentum fej- és láblécrészéhez?

V: Ha egy PDF-dokumentum fej- és láblécrészéhez képet és oldalszámot ad hozzá, javíthatja annak vizuális vonzerejét, márkajelzését és navigációs elemeit. A kép emblémát, vízjelet vagy bármilyen grafikus elemet képviselhet, míg az oldalszám segít a felhasználóknak nyomon követni a folyamatot és megtalálni az egyes oldalakat.

#### K: Hogyan segít a mellékelt C# forráskód kép és oldalszám hozzáadása a PDF-dokumentum fejlécéhez és láblécéhez?

V: A mellékelt kód bemutatja, hogyan hozzon létre PDF-dokumentumot, adjon hozzá egy oldalt, majd szabja testre a fejléc és lábléc szakaszokat. Megmutatja, hogyan lehet képet hozzáadni a fejléchez és szövegrészletet oldalszámozással a lábléchez.

#### K: Használhatok bármilyen képformátumot a fejléchez, és hogyan adhatom meg az elérési utat?

 V: Igen, különféle képformátumokat (például JPEG, PNG, GIF stb.) használhat a fejlécképhez. A kép elérési útja a`File` tulajdona a`Aspose.Pdf.Image` objektum.

#### K: Hogyan szabhatom testre a kép megjelenését és elhelyezését a fejléc részben?

 V: Testreszabhatja a kép megjelenését és elhelyezkedését a tulajdonságok beállításával`Aspose.Pdf.Image` objektumot, mielőtt hozzáadná a fejléc részhez. Például beállíthatja a kép méreteit, igazítását, elforgatását, átlátszatlanságát stb.

####  K: Mi a célja a`TextFragment` object used for the footer?

 V: A`TextFragment` Az objektum a lábléc részben megjelenő szöveg létrehozására és formázására szolgál. A megadott kódban az oldalszám és a teljes oldalszám megjelenítésére szolgál.

#### K: Módosíthatom a lábléc szövegét, hogy további információkat vagy formázást tartalmazzon?

 V: Igen, módosíthatja a lábléc szövegét a tartalmának módosításával`TextFragment` objektum. Igényeinek megfelelően további szöveget adhat hozzá, módosíthatja a betűtípusokat, színeket és formázást.

#### K: Alkalmazhatok eltérő fejléc- és lábléctartalmat a PDF-dokumentum különböző oldalaira?

 V: Igen, különböző fejléc- és lábléc-tartalmakat alkalmazhat a különböző oldalakon külön létrehozva`HeaderFooter` objektumok és hozzárendelésük adott oldalakhoz a segítségével`Header` és`Footer` tulajdonságai a`Aspose.Pdf.Page` objektum.

#### K: Hogyan szabhatom tovább a fejlécet és a láblécet, például módosíthatom a betűstílusokat vagy adhatok hozzá további elemeket?

V: A fejléc és a lábléc testreszabható az Aspose.PDF for .NET által biztosított különféle osztályok és tulajdonságok használatával. Használhat például különböző szövegformázási beállításokat, további bekezdéseket, képeket vagy akár táblázatokat is hozzáadhat a fejléc- és láblécrészekhez.

#### K: Eltávolíthatom vagy törölhetem a fejléc és lábléc szakaszokat, ha szükséges?

V: Igen, eltávolíthatja vagy törölheti a fejléc és lábléc szakaszokat a`Header` és`Footer` tulajdonságai a`Aspose.Pdf.Page` tiltakozik`null`.

#### K: Hogyan biztosíthatom, hogy a hozzáadott kép és oldalszám egységes maradjon a különböző eszközökön és nézők között?

V: Az Aspose.PDF for .NET szabványos és konzisztens PDF-dokumentumok létrehozását biztosítja, biztosítva, hogy a hozzáadott kép és oldalszám következetesen megjelenjen a különböző eszközökön és PDF-megtekintőkön.