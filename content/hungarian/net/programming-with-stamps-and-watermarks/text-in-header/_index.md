---
title: Szöveg a PDF-fájl fejlécében
linktitle: Szöveg a PDF-fájl fejlécében
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá szöveget a PDF-fájl fejlécéhez az Aspose.PDF for .NET segítségével.
type: docs
weight: 190
url: /hu/net/programming-with-stamps-and-watermarks/text-in-header/
---
Ebben az oktatóanyagban megtudjuk, hogyan lehet szöveget hozzáadni a PDF-fájl fejlécéhez az Aspose.PDF for .NET használatával. Kövesse az alábbi lépéseket:

## 1. lépés: Projekt előkészítés

Győződjön meg arról, hogy telepítette az Aspose.PDF for .NET fájlt, és létrehozott egy C# projektet.

## 2. lépés: Névterek importálása

Adja hozzá a következő névtereket a C# forrásfájlhoz:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. lépés: Nyissa meg a dokumentumot

Nyissa meg a meglévő PDF-dokumentumot a megadott útvonalon:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 4. lépés: Fejléc szövegének létrehozása

Hozzon létre egy új szövegbélyeget a fejlécbe felvenni kívánt szöveggel:

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

Testreszabhatja a szöveget olyan tulajdonságainak módosításával, mint a felső margó, a vízszintes igazítás és a függőleges igazítás.

## 5. lépés: Adjon hozzá fejlécet az összes oldalhoz

Menjen végig a PDF-dokumentum összes oldalán, és adja hozzá a szövegbélyeget a fejléchez:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6. lépés: A PDF-dokumentum mentése

Miután a fejléc szövegét hozzáadta az összes oldalhoz, mentse el a frissített PDF-dokumentumot:

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

Feltétlenül cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet annak a könyvtárnak az elérési útjára, ahová a PDF-dokumentumot menteni szeretné.

### Minta forráskód a Textin Headerhez az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

// Fejléc létrehozása
TextStamp textStamp = new TextStamp("Header Text");

// Állítsa be a bélyegző tulajdonságait
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

// Adjon hozzá fejlécet az összes oldalhoz
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

// Mentse el a frissített dokumentumot
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## Következtetés

Gratulálok ! Megtanulta, hogyan lehet szöveget hozzáadni egy PDF-dokumentum fejlécéhez az Aspose.PDF for .NET használatával. Mostantól személyre szabhatja fejléceit, ha további szöveget ad PDF-dokumentumaihoz.

### GYIK a PDF-fájl fejlécében található szöveghez

#### K: Mi a célja egy PDF-dokumentum fejlécébe szöveg hozzáadásának?

V: Ha egy PDF-dokumentum fejlécébe szöveget ad, fontos információk, például címek, dokumentumok nevei, dátumok vagy bármely más olyan szöveg szerepeltetése, amelyet konzisztensen kíván megjeleníteni az egyes oldalak tetején.

#### K: A megadott C# forráskód hogyan teszi lehetővé a szöveg hozzáadását egy PDF dokumentum fejlécéhez?

V: A kód bemutatja egy meglévő PDF dokumentum megnyitásának folyamatát, szövegbélyegző létrehozását a kívánt fejlécszöveggel, a szöveg tulajdonságainak testreszabását, a szövegbélyegző hozzáadását az összes oldalhoz, végül pedig a frissített PDF dokumentum mentését a hozzáadott fejlécszöveggel.

#### K: Módosíthatom a fejléc szövegének megjelenését, például annak betűtípusát, méretét, színét és igazítását?

 V: Igen, testreszabhatja a fejléc szövegének megjelenését a tulajdonságok módosításával`TextStamp`tárgy. A kódpélda olyan beállítási tulajdonságokat tartalmaz, mint a felső margó, a vízszintes igazítás és a függőleges igazítás. Beállíthatja a betűtípust, a méretet, a színt és a szöveggel kapcsolatos egyéb tulajdonságokat is.

#### K: Lehetséges-e különböző szöveget hozzáadni az egyes oldalak fejlécéhez?

 V: Igen, az egyes oldalak fejlécéhez más szöveget is hozzáadhat, ha külön létrehozza azokat`TextStamp` különböző szövegtartalommal vagy tulajdonságokkal rendelkező objektumokat, majd szükség szerint hozzáadhatja azokat adott oldalakhoz.

#### K: Hogyan biztosíthatom, hogy a fejléc szövege következetesen jelenjen meg a PDF-dokumentum minden oldalán?

V: Ha olyan ciklust használ, amely végighalad a PDF-dokumentum összes oldalán, és minden oldalhoz ugyanazt a szövegbélyeget adja, akkor biztosítja, hogy a fejléc szövege minden oldalon következetesen megjelenjen.

#### K: Hozzáadhatok több sornyi szöveget, vagy formázhatom a fejléc szövegét sortöréssel?

 V: Igen, több sornyi szöveget is hozzáadhat a fejléchez, ha sortörést ad a szöveges karakterláncban. Használhatja például az escape szekvenciát`\n` sortörés jelzésére a szövegben.

#### K: Mi történik, ha eltérő tartalmat akarok hozzáadni ugyanannak a PDF-dokumentumnak a fejlécéhez és láblécéhez?

V: Ha eltérő tartalmat szeretne hozzáadni a fejléchez és a lábléchez, akkor mindkét szakaszhoz hasonló lépéseket kell követnie. A kód bemutatja, hogy szöveget kell hozzáadni a fejléchez; hasonló megközelítést alkalmazhat szöveg hozzáadásához a lábléchez.

#### K: Lehetséges képeket vagy más elemeket hozzáadni a fejléc szövegéhez ezzel a megközelítéssel?

V: Míg a mellékelt kód kifejezetten bemutatja a szöveg fejléchez való hozzáadását, az Aspose.PDF könyvtár használatával kiterjesztheti a megközelítést más elemek, például képek, vonalak, alakzatok vagy bármilyen más tartalom hozzáadására a fejlécrészhez.
