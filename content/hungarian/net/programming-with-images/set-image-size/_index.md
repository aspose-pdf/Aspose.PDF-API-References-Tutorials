---
title: Állítsa be a képméretet a PDF-fájlban
linktitle: Állítsa be a képméretet a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a kép méretének beállításához PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 270
url: /hu/net/programming-with-images/set-image-size/
---
Ebben az oktatóanyagban végigvezetjük, hogyan állíthatja be a kép méretét PDF-fájlban az Aspose.PDF for .NET használatával. Kövesse ezeket a lépéseket a művelet egyszerű végrehajtásához.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más fejlesztői környezet telepítve és konfigurálva.
- Alapszintű C# programozási nyelv ismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve. Letöltheti az Aspose hivatalos webhelyéről.

## 1. lépés: A PDF dokumentum létrehozása

A kezdéshez használja a következő kódot új PDF-dokumentum létrehozásához:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Példányosítson egy dokumentum objektumot
Document doc = new Document();

// Adjon hozzá egy oldalt a PDF-fájl oldalainak gyűjteményéhez
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 2. lépés: Kép hozzáadva

Ezután egy képet adunk a PDF-dokumentum oldalához. Használja a következő kódot:

```csharp
// Hozzon létre egy képpéldányt
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// Állítsa be a kép szélességét és magasságát pontokban
img. FixWidth = 100;
img. FixHeight = 100;

//Képtípus beállítása ismeretlenre (Ismeretlen)
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

// A kép forrásfájljának elérési útja
img.File = dataDir + "aspose-logo.jpg";

// Adja hozzá a képet az oldal bekezdésgyűjteményéhez
page.Paragraphs.Add(img);
```

Ügyeljen arra, hogy a képforrásfájl helyes elérési útját adja meg.

## 3. lépés: Az oldal tulajdonságainak beállítása

Végül beállítjuk az oldal tulajdonságait, beleértve a szélességét és magasságát. Használja a következő kódot:

```csharp
// Állítsa be az oldal tulajdonságait
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### Minta forráskód a Set Image Size-hez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentum objektum példányosítása
Document doc = new Document();
// oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
Aspose.Pdf.Page page = doc.Pages.Add();
// Hozzon létre egy képpéldányt
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Állítsa be a kép szélességét és magasságát pontokban
img.FixWidth = 100;
img.FixHeight = 100;
// Állítsa be a képtípust SVG-re
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// A forrásfájl elérési útja
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//Állítsa be az oldal tulajdonságait
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// mentse az eredményül kapott PDF fájlt
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálok ! Sikeresen beállította a PDF-dokumentumban lévő kép méretét az Aspose.PDF for .NET segítségével. Most már alkalmazhatja ezt a módszert saját projektjeire a PDF-fájlokban lévő képek méretének beállításához.

### GYIK a képméret beállításához PDF-fájlban

#### K: Mi a célja egy PDF-dokumentumban lévő kép méretének beállításának az Aspose.PDF for .NET használatával?

V: A PDF-dokumentumban lévő kép méretének beállításának célja a kép méreteinek szabályozása a PDF-hez való hozzáadásakor. Ez lehetővé teszi a PDF-fájlokon belüli képek megjelenésének és elrendezésének beállítását.

#### K: Hogyan működik a kép méretének beállítása PDF dokumentumban?

 V: A folyamat magában foglalja egy`Aspose.Pdf.Image` például a szélességét és magasságát a`FixWidth` és`FixHeight` tulajdonságait, majd adja hozzá a képet a PDF dokumentumhoz. Ezenkívül beállíthatja magának az oldalnak a méreteit, hogy illeszkedjen a képhez.

#### K: Beállíthatom a kép méretét az oldal méretének egy bizonyos százalékára?

V: A mellékelt kód beállítja a kép abszolút szélességét és magasságát pontokban. Ha egy kép méretét az oldalméretek százaléka alapján szeretné beállítani, akkor ennek megfelelően kell kiszámítania a méreteket, és ennek megfelelően módosítania kell a kódot.

####  K: Mi a jelentősége a`FileType` property when adding an image to the PDF document?

 V: A`FileType`tulajdonság határozza meg a PDF dokumentumhoz hozzáadandó kép típusát. A megadott kódban az érték`Unknown` azt jelzi, hogy a kép típusa ismeretlen, és az Aspose.PDF megpróbálja meghatározni a kép típusát a fájlkiterjesztés alapján.

#### K: Hozzáadhatok több képet egyetlen oldalhoz ezzel a módszerrel?

 V: Igen, több képet is hozzáadhat egyetlen oldalhoz, ha több képet hoz létre`Aspose.Pdf.Image` példányokat, és hozzáadjuk őket az oldal bekezdésgyűjteményéhez. Szükség szerint állítsa be a képek elhelyezését és elrendezését.

#### K: Hogyan szabályozhatom a hozzáadott kép elhelyezését és igazítását az oldalon?

 V: A hozzáadott kép elhelyezése és igazítása szabályozható a kép koordinátáinak és elrendezésének beállításával olyan tulajdonságok segítségével, mint pl.`img.Left`, `img.Top`, és a bekezdés formázási tulajdonságai.

####  K: Mi a célja az oldaltulajdonságok beállításának`page.PageInfo.Width` and `page.PageInfo.Height`?

V: Az oldal tulajdonságainak beállítása lehetővé teszi magának az oldalnak a méreteinek meghatározását. Ez biztosítja, hogy az oldal méretei megfeleljenek a hozzáadott képnek és az oldalon esetlegesen található egyéb tartalomnak.

#### K: Beállíthatok különböző méreteket a különböző képekhez ugyanazon a PDF dokumentumon belül?

 V: Igen, különböző méreteket állíthat be a különböző képekhez külön létrehozásával`Aspose.Pdf.Image` példányok és a`FixWidth`, `FixHeight`, és az egyes képek elhelyezési tulajdonságait.

#### K: Hogyan integrálhatom ezt a módszert a saját projektjeimbe a képméretek beállításához PDF-fájlokban?

V: Ennek a módszernek a projektekbe való integrálásához kövesse a vázolt lépéseket, és szükség szerint módosítsa a kódot. Ezzel a módszerrel az alkalmazás követelményei alapján meghatározott méretű képeket adhat hozzá PDF-dokumentumaihoz.