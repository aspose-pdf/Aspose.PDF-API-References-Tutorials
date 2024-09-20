---
title: Szöveg keresése és téglalap rajzolása
linktitle: Szöveg keresése és téglalap rajzolása
second_title: Aspose.PDF for .NET API Reference
description: Tanuljon meg szöveget keresni PDF-ben, és téglalapokkal kiemelje az Aspose.PDF for .NET segítségével! Könnyű, lépésről lépésre bemutató oktatóanyag a továbbfejlesztett PDF-kezelési készségekhez.
type: docs
weight: 460
url: /hu/net/programming-with-text/search-text-and-draw-rectangle/
---
## Bevezetés

Szeretné fejleszteni PDF-kezelési készségeit? Szeretné megtanulni, hogyan kereshet konkrét szöveget PDF-fájlokban, és hogyan emelheti ki téglalappal? A tökéletes útmutatóhoz jutottál! Ma végigvezetem Önt, hogyan használhatja az Aspose.PDF for .NET fájlt szövegek keresésére egy PDF-dokumentumban, és téglalapokat rajzolhat köré. Ez a cikk lépésről lépésre bemutatja az egyértelműséget és a hasznosságot szem előtt tartó oktatóanyagot, amely biztosítja, hogy követni tudja és alkalmazni tudja ezeket a technikákat projektjeinél. 

## Előfeltételek

Mielőtt belevágna az oktatóanyagba, készítsük elő, mire van szüksége a zökkenőmentes munkafolyamat biztosításához:

1. A .NET alapjai: ismernie kell a C# programozást és a .NET keretrendszert, hogy hatékonyan kövesse ezt az oktatóanyagot.
   
2. A Visual Studio telepítve: A kód írásához és teszteléséhez integrált fejlesztői környezetre (IDE) lesz szüksége. A Visual Studio Community nagyszerű lehetőség, és ingyenes.
   
3. Aspose.PDF for .NET: Telepíteni kell az Aspose.PDF könyvtárat a projektben. Letöltheti[itt](https://releases.aspose.com/pdf/net/) vagy fontolja meg a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) kiterjesztett funkciókhoz.
   
4.  Minta PDF-dokumentum: Ehhez az oktatóanyaghoz szüksége lesz egy PDF-mintafájlra`SearchAndGetTextFromAll.pdf` a projektkönyvtárban tárolva. 

## Csomagok importálása

A kezdéshez először importálnia kell a szükséges csomagokat a .NET-projektbe. Kövesse az alábbi lépéseket:

### Nyissa meg a Visual Studio-t

Indítsa el a Visual Studio alkalmazást, és hozzon létre egy új konzolalkalmazást, vagy használjon egy meglévőt, ahol a PDF-funkciókat szeretné megvalósítani.

### Adja hozzá az Aspose.PDF fájlt projektjéhez

1. Kattintson a jobb gombbal a projektre a Solution Explorerben.
2. Válassza a "NuGet-csomagok kezelése" lehetőséget.
3.  Keressen rá`Aspose.PDF` és telepítse a legújabb verziót.

Ezzel megteremti az alapot minden elképesztő PDF-manipulációhoz, amelyet éppen végrehajtani készül.

## Névterek importálása

A programfájl tetején érdemes importálni a vonatkozó névtereket az Aspose könyvtárból:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Ez megkönnyíti az osztályok és metódusok elérését az Aspose.PDF könyvtáron belül a feladatokhoz.


Most, hogy mindent beállított, bontsuk fel kezelhető lépésekre a PDF-ben található szöveg keresésének folyamatát, és rajzoljunk köré egy téglalapot.

## 1. lépés: Állítsa be a dokumentum elérési útját

 Először állítsa be a PDF-fájl elérési útját. Ügyeljen arra, hogy cserélje ki`YOUR DOCUMENT DIRECTORY` a tényleges útvonallal, ahol az Ön`SearchAndGetTextFromAll.pdf` tárolva van.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF-dokumentumot

 Ezután hozzon létre egy példányt a`Document` osztály a PDF betöltéséhez:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Ez a kódsor megnyitja a megadott PDF-fájlt, lehetővé téve annak további manipulálását.

## 3. lépés: Hozzon létre egy szövegelnyelőt

 Most szüksége lesz egy módra, hogy szöveget keressen a dokumentumban. Ehhez használjuk a`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 A reguláris kifejezés`@"[\S]+"` úgy lett kialakítva, hogy illeszkedjen a PDF-ben található nem szóközökhöz. 

## 4. lépés: Konfigurálja a szöveges keresési beállításokat

Ezután be kell állítania a szöveges keresési beállításokat:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Itt, a`true` paraméter azt jelenti, hogy a keresés megkülönbözteti a kis- és nagybetűket. Beállíthatja`false` ha kis- és nagybetűket nem érző keresést szeretne.

## 5. lépés: Fogadja el a szövegelnyelőt a dokumentumban

 A tiéddel`TextFragmentAbsorber` és a keresési lehetőségek készen állnak, itt az ideje, hogy szöveget vegyen fel a dokumentumból:

```csharp
document.Pages.Accept(textAbsorber);
```

Ez a módszer megvizsgálja a PDF minden oldalát, hogy megtalálja a megadott mintának megfelelő szövegrészleteket.

## 6. lépés: Hozzon létre egy PdfContentEditort

 Ha alakzatokat szeretne rajzolni a dokumentumra, szüksége lesz a`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Ez a szerkesztő lehetővé teszi a PDF-tartalom egyszerű kezelését és szerkesztését.

## 7. lépés: Ismételje meg a talált szövegtöredékeket

Most érdemes végigpörgetni a talált szövegrészleteket, és téglalapokat rajzolni köréjük:

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Ez a ciklus minden szövegtöredéken és szegmensükön iterál, és meghívja a`DrawBox` módszer a téglalap rajzolására.

## 8. lépés: Határozza meg a DrawBox módszert

 Meg kell határoznia a`DrawBox` metódust, amely kezeli a téglalap rajzolási logikát. Íme egy egyszerű megvalósítás:

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Számítsa ki a téglalap méreteit a szövegszegmens alapján
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Rajzoljon egy téglalapot a számított értékek felhasználásával
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Ez a módszer a szegmens határoló téglalapja alapján határozza meg a téglalap helyzetét és méretét, és a szerkesztő segítségével rajzolja meg.

## 9. lépés: Mentse el a módosított dokumentumot

Miután a talált szöveg köré rajzolta a téglalapokat, elmentheti a módosított dokumentumot:

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Győződjön meg arról, hogy az új fájlt más néven menti, hogy elkerülje az eredeti dokumentum felülírását.

## 10. lépés: Megerősítő üzenet

Végül nyomtasson egy megerősítő üzenetet a konzolra, hogy tudassa a művelet sikerességéről:

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

És megvan! Sikeresen létrehozott egy szkriptet, amellyel szöveget kereshet a PDF-ben, és téglalapokkal kiemelheti.

## Következtetés

Gratulálok! Ön most egy olyan hatékony készségre tett szert, amely nagymértékben javíthatja PDF-kezelési képességeit az Aspose.PDF for .NET használatával. Néhány egyszerű lépéssel megkereshet bármilyen szöveget a dokumentumban, és vizuálisan kiemelheti, így PDF-dokumentumait interaktívabbá és kezelhetőbbé teheti. Ne habozzon kísérletezni a különböző regex mintákkal és színválasztékkal, hogy valóban a magáévá tegye ezt az eszközt!

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy olyan könyvtár, amely átfogó módot biztosít PDF-dokumentumok programozott létrehozására, kezelésére és konvertálására.

### Használhatom ingyenesen az Aspose.PDF-et?
Igen, az Aspose ingyenes próbaverziót kínál, amellyel tesztelheti a könyvtár funkcióit. Nézd meg[itt](https://releases.aspose.com/).

### Milyen programozási nyelvet kell használnom az Aspose.PDF for .NET-hez?
Az Aspose.PDF for .NET a C# és más .NET nyelvekkel való használatra készült.

### Hogyan kaphatok segítséget az Aspose.PDF-hez?
 Bármilyen problémával vagy kérdéssel kapcsolatban felkeresheti az Aspose támogatási fórumát. Keressen támogatást[itt](https://forum.aspose.com/c/pdf/10).

### Honnan tölthetem le az Aspose.PDF-et .NET-hez?
 A könyvtár letölthető az Aspose weboldaláról,[itt](https://releases.aspose.com/pdf/net/).