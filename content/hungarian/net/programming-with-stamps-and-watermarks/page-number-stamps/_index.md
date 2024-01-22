---
title: Oldalszám bélyegek PDF fájlban
linktitle: Oldalszám bélyegek PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá oldalszámbélyegzőket PDF-fájlhoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 160
url: /hu/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá oldalszámbélyegzőket PDF-fájlhoz az Aspose.PDF for .NET használatával. A mellékelt C# forráskód segítségével megnyitunk egy meglévő PDF-dokumentumot, létrehozunk egy oldalszámbélyeget, beállítjuk a tulajdonságait, és hozzáadjuk a PDF-fájl egy adott oldalához.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A meglévő PDF dokumentum betöltése

Az első lépés a meglévő PDF dokumentum betöltése a projektbe. Itt van, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Nyissa meg a meglévő PDF dokumentumot
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a PDF-dokumentum könyvtárának tényleges elérési útjára.

## 3. lépés: Az oldalszámozási bélyegző létrehozása és konfigurálása

Most, hogy a PDF dokumentum betöltődött, létrehozhatunk egy oldalszámozási puffert, és igényeink szerint konfigurálhatjuk. Itt van, hogyan:

```csharp
// Hozzon létre egy oldalszám puffert
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// Határozza meg, hogy a puffer a háttérben van-e vagy sem
pageNumberStamp.Background = false;

// Az oldalszámozási puffer formátuma
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// Az oldalszámozási puffer alsó margója
pageNumberStamp.BottomMargin = 10;

// Az oldalszámozási puffer vízszintes igazítása
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// Az oldalszámozás kezdő száma
pageNumberStamp.StartingNumber = 1;

// Állítsa be az oldalszám-puffer szöveg tulajdonságait
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

fenti kód oldalszámbélyeget hoz létre olyan tulajdonságokkal, mint az oldalszám formátuma, alsó margó, vízszintes igazítás, kezdőszám és szövegtulajdonságok.

## 4. lépés: Az oldalszámbélyegző hozzáadása egy adott oldalhoz

Az oldalszámbélyegző beállítása után hozzáadhatjuk a PDF dokumentum egy adott oldalához. Itt van, hogyan:

```csharp
// Adja hozzá az oldalszám puffert egy adott oldalhoz
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

A fenti kód hozzáadja az oldalszám bélyeget a PDF dokumentum első oldalához. Az oldalszámot szükség szerint módosíthatja.

## 5. lépés: Mentse el a módosított PDF dokumentumot

Miután az oldalszám bélyegzőt hozzáadtuk a PDF dokumentumhoz, elmenthetjük a módosított PDF dokumentumot. Itt van, hogyan:

```csharp
// Mentse el a módosított PDF dokumentumot
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

Feltétlenül cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet annak a könyvtárnak az elérési útjára, ahová a szerkesztett PDF-dokumentumot menteni szeretné.

### Minta forráskód oldalszámbélyegzőkhöz az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// Oldalszám bélyegző létrehozása
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// A bélyegző háttér-e
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// Állítsa be a szöveg tulajdonságait
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// Bélyegző hozzáadása az adott oldalhoz
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// Mentse a kimeneti dokumentumot
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat oldalszámbélyegzőket PDF-dokumentumokhoz az Aspose.PDF for .NET használatával. Most már személyre szabhatja PDF-dokumentumait egyértelmű és informatív oldalszámok hozzáadásával.

### GYIK oldalszámbélyegzőkkel kapcsolatban PDF-fájlban

#### K: Mi az az oldalszámbélyegző, és hogyan lehet vele oldalszámokat adni egy PDF-fájlhoz?

V: Az oldalszámbélyegző az Aspose.PDF olyan funkciója, amely lehetővé teszi dinamikus oldalszámok hozzáadását a PDF-dokumentum bizonyos oldalaihoz. Ebben az oktatóanyagban ez úgy érhető el, hogy létrehoz egy PageNumberStamp objektumot, konfigurálja a tulajdonságait, és hozzáadja egy kijelölt oldalhoz.

#### K: A mellékelt C# forráskód hogyan teszi lehetővé az oldalszám bélyegzők hozzáadását egy PDF-fájlhoz?

V: A kód bemutatja, hogyan kell betölteni egy meglévő PDF-dokumentumot, létrehozni egy PageNumberStamp-et, beállítani a különböző tulajdonságokat (például formátum, betűtípus, igazítás stb.), majd hozzáadni a bélyeget egy adott oldalhoz. A bélyegző automatikusan kiszámítja a teljes oldalszámot, és beilleszti a megfelelő oldalszámokat.

#### K: Testreszabhatom az oldalszám megjelenését, például betűstílust, színt és méretet?

V: Természetesen testreszabhatja az oldalszámbélyegző megjelenését a tulajdonságok, például a betűtípus, a betűméret, a betűstílus (félkövér, dőlt stb.) és a szöveg színének módosításával.

#### K: Lehetséges oldalszámbélyegzőket hozzáadni egy PDF-dokumentum több oldalához?

V: Igen, több oldalhoz is hozzáadhat oldalszámbélyegzőket, ha több PageNumberStamp objektumot hoz létre, és mindegyiket hozzáadja a kívánt oldalakhoz.

#### K: Kiválaszthatom, hogy az oldalszámbélyegző az oldal tartalmának részeként vagy háttérelemként jelenjen meg?

 V: Igen, beállíthatja, hogy az oldalszámbélyegző az oldal tartalmának részeként vagy háttérelemként jelenjen meg`Background` a PageNumberStamp tulajdonsága.

#### K: Hogyan adhatom meg az oldalszám formátumát, beleértve a teljes oldalszámot is?

 V: A kód a`Format` PageNumberStamp tulajdonsága az oldalszám formátumának megadásához. A „# of” makró a teljes oldalszámot jelöli.

#### K: Mi történik, ha ugyanazt az oldalszám bélyegzőt több oldalra adom?

V: Ha ugyanazt a PageNumberStamp példányt több oldalhoz is hozzáadja, akkor minden oldalhoz a megfelelő oldalszámok jelennek meg. A bélyegző automatikusan beállítja az oldalszámot és a teljes oldalszámot.

#### K: Hozzáadhatok oldalszám bélyegzőt a PDF-dokumentum fejléc- vagy láblécrészéhez?

V: Míg a PageNumberStamp-eket általában közvetlenül az oldal tartalmához adják hozzá, használhatja a FloatingBox-ot vagy más technikákat a fejléc- vagy lábléc-szakaszban való elhelyezésükhöz.

#### K: Hogyan határozhatom meg az oldalszámbélyegző helyét az oldalon?

 V: A`BottomMargin` és`HorizontalAlignment` a PageNumberStamp tulajdonságai lehetővé teszik a bélyegző pozíciójának szabályozását az oldalon.

#### K: Mi a teendő, ha az oldalszámozást egy másik számmal szeretném kezdeni, nem pedig 1-től?

 V: Beállíthatja a`StartingNumber` PageNumberStamp tulajdonsága a kezdőoldalszám megadásához.