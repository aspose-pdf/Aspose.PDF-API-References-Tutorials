---
title: Töltse ki a körvonal szövegét PDF-fájlban
linktitle: Töltse ki a körvonal szövegét PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a gyakorlati példákat tartalmazó, lépésenkénti útmutatóból megtudhatja, hogyan töltsön ki könnyedén PDF-fájlok körvonalas szövegét az Aspose.PDF for .NET segítségével.
type: docs
weight: 90
url: /hu/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
## Bevezetés

Szeretett volna már úgy módosítani egy PDF-fájlt, hogy kiemelkedjen? Lehet, hogy egy feltűnő vízjelet vagy egy félkövér bélyegzőt kell hozzáadnia, amely egy fontos dokumentumot összetéveszthetetlenül a magáévá tesz. A .NET-hez készült Aspose.PDF segítségével könnyedén kitöltheti a körvonalas szöveget egy PDF-fájlban, és művészi hangulatot ad hozzá, amely megragadja a figyelmet. A mai oktatóanyagban ennek a folyamatát mutatjuk be – a körvonalas szöveg kitöltését PDF-be C# használatával. A végére alaposan meg fogja tudni, hogyan kell profi módon kezelni a PDF-fájlokat.

## Előfeltételek

Mielőtt belemerülnénk a kódolásba, van néhány dolog, amit meg kell tennie, hogy ez az oktatóanyag gyerekjáték legyen:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépén, mivel mi fogunk C# kódot írni.
2.  Aspose.PDF könyvtár: Győződjön meg arról, hogy letöltötte az Aspose.PDF for .NET könyvtárat. Megfoghatod[itt](https://releases.aspose.com/pdf/net/).
3. A C# alapismeretei: A C# programozás ismerete segít az oktatóanyag könnyebb megértésében.
4. Minta PDF fájl: Szüksége lesz egy minta PDF fájlra (`input.pdf`tesztelési célból. Létrehozhat egy egyszerűt, vagy használhat bármilyen meglévő PDF-et.

Most, hogy minden a helyén van, kezdjük el a PDF-fájlban lévő körvonalas szövegek kitöltésének aprólékos dolgait.

## Csomagok importálása

A kezdéshez importálnunk kell a szükséges csomagokat. Íme egy rövid áttekintés a projektünkhöz szükséges legfontosabb importtermékekről:

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ezek a csomagok lehetővé teszik számunkra az Aspose.PDF könyvtár robusztus funkcióinak használatát.

Bontsuk le a fő feladatot egyértelmű lépésekre. Az alábbi lépések követésével könnyedén kitöltheti a körvonalas szöveget a PDF-fájlokba. 

## 1. lépés: Állítsa be környezetét

Először győződjön meg arról, hogy mindent megfelelően beállított a Visual Studio projektben. Hozzon létre egy új projektet, vagy válasszon egy meglévőt. Ha segítségre van szüksége, a következőképpen teheti meg:

1. Nyissa meg a Visual Studio-t.
2. Hozzon létre egy új C# projektet (pl. konzolalkalmazást).
3. Kattintson a jobb gombbal a projektre a Solution Explorerben, és válassza a „NuGet-csomagok kezelése” lehetőséget.
4.  Keressen rá`Aspose.PDF` és telepítse.

## 2. lépés: Határozza meg a dokumentumkönyvtárat

Minden útnak szüksége van egy kiindulási pontra, és esetünkben ez a dokumentumok könyvtára, ahol a bemeneti és kimeneti fájlok találhatók. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahol a bevitt PDF-fájl található. 

## 3. lépés: Hozza létre a TextState objektumot

Ebben a lépésben kezdheti meg a hozzáadni kívánt szöveg tulajdonságainak meghatározását. 

```csharp
TextState ts = new TextState();
```

 A`TextState` objektum fogja tartani a körvonal szövegének stílusbeállításait.

## 4. lépés: Állítsa be a Stroke színét

Ezután meg kell határoznia a szöveg körvonalának színét. 

```csharp
ts.StrokingColor = Color.Gray;
```

Ebben a kódban szürke színt használunk a körvonalhoz. Nyugodtan változtassa meg a színt igényeinek megfelelően!

## 5. lépés: A Rendering Mode konfigurálása

Annak érdekében, hogy a szöveg a kívánt módon jelenjen meg, állítsa be a megjelenítési módot:

```csharp
ts.RenderingMode = TextRenderingMode.StrokeText;
```

Ez arra utasítja az Aspose könyvtárat, hogy körvonalas szöveggel dolgozunk.

## 6. lépés: Töltse be a bevitt PDF-dokumentumot

Most itt az ideje, hogy betöltse a módosítani kívánt PDF-fájlt. 

```csharp
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

Győződjön meg arról, hogy a bevitt PDF-et (`input.pdf`a korábbi lépésekben meghatározott dokumentumok könyvtárában található.

## 7. lépés: Hozzon létre egy bélyegzőobjektumot

Ezután hozzon létre egy bélyeget, amely a körvonal szövegét fogja tárolni. 

```csharp
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
```

Ez a bélyegző a szöveg átfedésére szolgál a PDF-en.

## 8. lépés: Határozza meg a bélyegzendő szöveget

Meg kell adnia, hogy milyen szöveget kíván hozzáadni a PDF-hez:

```csharp
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));
```

Itt a „TELJES MEGFIZETÉS” az a szöveg, amelyet hozzáadunk a stílusjellemzőkkel együtt. Testreszabhatja igényei szerint!

## 9. lépés: Kösse össze a szövegállapotot

 Most kösse be a`TextState` korábban definiáltad a bélyegzőhöz. 

```csharp
stamp.BindTextState(ts);
```

Ez a lépés az összes stílust, például a színt és a renderelési módot alkalmazza a szövegre.

## 10. lépés: Állítsa be a bélyegző pozícióját

Határozza meg, hol jelenjen meg a bélyegzője a PDF-ben:

```csharp
stamp.SetOrigin(100, 100);
```

 Az érvek`(100, 100)` jelölje a szöveg eredetének X és Y koordinátáit (pontokban). Állítsa be ezeket az értékeket a szöveg tökéletes elhelyezéséhez!

## 11. lépés: Az átlátszatlanság és az elforgatás konfigurálása

Itt játszhat a szöveg megjelenésével:

```csharp
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
```

Ebben az esetben az átlátszatlanság érték és a 45 fokos elforgatási szög egyedi hangulatot ad a szövegnek. Nyugodtan módosítsa ezeket a beállításokat a különböző hatásokhoz.

## 12. lépés: Adja hozzá a bélyegzőt a PDF-hez

Ez az a döntő lépés, amikor végre hozzáadjuk a körvonal szövegét tartalmazó bélyegzőnket a PDF-hez:

```csharp
fileStamp.AddStamp(stamp);
```

És a szöveged készen áll a nyilatkozattételre!

## 13. lépés: Mentse el és zárja be a dokumentumot

Végül mentse el a változtatásokat, és győződjön meg róla, hogy minden megfelelően meg van tisztítva. 

```csharp
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

 A körvonal szövegét tartalmazó újonnan módosított PDF-fájl a következő néven lesz elmentve`output_out.pdf` dokumentumkönyvtárában. 

## Következtetés

És megvan! Ezeket az egyszerű lépéseket követve egyszerűen kitöltheti a körvonalas szöveget egy PDF-fájlban az Aspose.PDF for .NET segítségével. Legyen szó üzleti dokumentumokról vagy személyes projektekről, ez a technika lehetővé teszi, hogy egyedi árnyalatot adjon PDF-fájljaihoz, és minden papírkötegben kiemelkedjen.

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára PDF-fájlok programozott létrehozását, kezelését és konvertálását.

### Használhatom ingyenesen az Aspose.PDF-et?
Igen, az Aspose ingyenes próbaverziót kínál. Megkaphatod[itt](https://releases.aspose.com/).

### Fizetnem kell az engedélyért?
 Míg a könyvtár ingyenes próbaverzióval rendelkezik, ideiglenes licenc is vásárolható a címen[ezt a linket](https://purchase.aspose.com/temporary-license/).

### Hol találom a dokumentációt?
 Hozzáférhet a teljes dokumentációhoz[itt](https://reference.aspose.com/pdf/net/).

### Van-e támogatás, ha problémákba ütközöm?
 Teljesen! Támogatást kaphat az Aspose fórumon[itt](https://forum.aspose.com/c/pdf/10).