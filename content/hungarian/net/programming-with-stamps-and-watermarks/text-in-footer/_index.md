---
title: Szöveg A PDF-fájl láblécében
linktitle: Szöveg A PDF-fájl láblécében
second_title: Aspose.PDF for .NET API Reference
description: Tanuljon meg szöveget hozzáadni a PDF-fájl láblécéhez az Aspose.PDF for .NET segítségével.
type: docs
weight: 180
url: /hu/net/programming-with-stamps-and-watermarks/text-in-footer/
---
Ebben az oktatóanyagban megtudjuk, hogyan lehet szöveget hozzáadni a PDF-fájl láblécéhez az Aspose.PDF for .NET használatával. Kövesse az alábbi lépéseket:

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
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a dokumentumkönyvtár tényleges elérési útjára.

## 4. lépés: Hozzon létre láblécszöveget

Hozzon létre egy új szövegbélyeget a láblécbe felvenni kívánt szöveggel:

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

Testreszabhatja a szöveget olyan tulajdonságainak módosításával, mint az alsó margó, a vízszintes igazítás és a függőleges igazítás.

## 5. lépés: Adjon hozzá láblécszöveget az összes oldalhoz

Menjen végig a PDF-dokumentum összes oldalán, és adja hozzá a szövegbélyeget a lábléchez:

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6. lépés: A PDF-dokumentum mentése

Miután a lábléc szövegét hozzáadta az összes oldalhoz, mentse el a frissített PDF-dokumentumot:

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

Feltétlenül cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet annak a könyvtárnak az elérési útjára, ahová a PDF-dokumentumot menteni szeretné.

### Minta forráskód a Textin Footerhez az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// Lábléc létrehozása
TextStamp textStamp = new TextStamp("Footer Text");

// Állítsa be a bélyegző tulajdonságait
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Adjon hozzá láblécet az összes oldalhoz
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// Mentse el a frissített PDF fájlt
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## Következtetés

Gratulálok ! Megtanulta, hogyan lehet szöveget hozzáadni egy PDF-dokumentum láblécéhez az Aspose.PDF for .NET használatával. Most már személyre szabhatja lábléceit, ha további szöveget ad PDF-dokumentumaihoz.

### GYIK a PDF-fájl láblécében található szöveghez

#### K: Mi a célja egy PDF-dokumentum láblécébe szöveg hozzáadásának?

V: Ha egy PDF-dokumentum láblécébe szöveget ad, fontos információk, például szerzői jogi megjegyzések, oldalszámok, dokumentumverzió vagy bármilyen más szöveg, amelyet konzisztensen szeretne megjelenni az egyes oldalak alján, hozzáadhat.

#### K: A megadott C# forráskód hogyan teszi lehetővé a szöveg hozzáadását a PDF-dokumentum láblécébe?

V: A kód bemutatja egy meglévő PDF-dokumentum megnyitásának folyamatát, szövegbélyegző létrehozását a kívánt láblécszöveggel, a szövegtulajdonságok testreszabását, a szövegbélyegző hozzáadását az összes oldalra, végül pedig a frissített PDF-dokumentum elmentését a hozzáadott láblécszöveggel.

#### K: Módosíthatom a lábléc szövegének megjelenését, például annak betűtípusát, méretét, színét és igazítását?

 V: Igen, testreszabhatja a lábléc szövegének megjelenését a tulajdonságok módosításával`TextStamp` tárgy. A kódpélda olyan beállítási tulajdonságokat tartalmaz, mint az alsó margó, a vízszintes igazítás és a függőleges igazítás. Beállíthatja a betűtípust, a méretet, a színt és a szöveggel kapcsolatos egyéb tulajdonságokat is.

#### K: Lehetséges-e különböző szöveget hozzáadni az egyes oldalak láblécéhez?

 V: Igen, az egyes oldalak láblécéhez más szöveget is hozzáadhat, ha külön létrehozza azt`TextStamp` különböző szövegtartalommal vagy tulajdonságokkal rendelkező objektumokat, majd szükség szerint hozzáadhatja azokat adott oldalakhoz.

#### K: Hogyan biztosíthatom, hogy a lábléc szövege következetesen megjelenjen a PDF-dokumentum minden oldalán?

V: Ha olyan ciklust használ, amely végighalad a PDF-dokumentum összes oldalán, és minden oldalhoz ugyanazt a szövegbélyeget adja, akkor biztosítja, hogy a lábléc szövege minden oldalon következetesen megjelenjen.

#### K: Hozzáadhatok több sornyi szöveget, vagy formázhatom a lábléc szövegét sortöréssel?

 V: Igen, több sornyi szöveget is hozzáadhat a lábléchez, ha sortörést ad a szöveges karakterláncban. Használhatja például az escape szekvenciát`\n` sortörés jelzésére a szövegben.

#### K: Mi történik, ha eltérő tartalmat akarok hozzáadni ugyanannak a PDF-dokumentumnak a fejlécéhez és láblécéhez?

V: Ha eltérő tartalmat szeretne hozzáadni a fejléchez és a lábléchez, akkor mindkét szakaszhoz hasonló lépéseket kell követnie. A kód bemutatja a szöveg hozzáadását a lábléchez; hasonló megközelítést alkalmazhat szöveg hozzáadásához a fejléchez.

#### K: Lehetséges képeket vagy más elemeket hozzáadni a lábléc szövegéhez ezzel a megközelítéssel?

V: Míg a mellékelt kód kifejezetten bemutatja, hogy szöveget kell hozzáadni a lábléchez, az Aspose.PDF könyvtár segítségével további elemeket, például képeket, vonalakat, alakzatokat vagy bármilyen más tartalmat is hozzáadhat a lábléchez.