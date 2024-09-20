---
title: Render táblázat PDF dokumentumban
linktitle: Render táblázat PDF dokumentumban
second_title: Aspose.PDF for .NET API Reference
description: Hozzon létre egyszerűen professzionális PDF-eket az Aspose.PDF for .NET segítségével táblázatok renderelésével. Kövesse lépésenkénti útmutatónkat a dokumentumgenerálás elsajátításához.
type: docs
weight: 170
url: /hu/net/programming-with-tables/render-table/
---
## Bevezetés

A professzionális megjelenésű PDF-fájlok programozott készítése ijesztő feladatnak tűnhet, de az Aspose.PDF for .NET használatával ez gyerekjáték lesz. Függetlenül attól, hogy jelentéseket, számlákat vagy bármilyen más, táblázatos adatokat igénylő dokumentumtípust készít, az Aspose.PDF kínálja a szükséges eszközöket. Ebben az oktatóanyagban lépésről lépésre megvizsgáljuk, hogyan lehet táblázatokat megjeleníteni egy PDF-dokumentumban. A végére alapos ismerete lesz a táblázatok kezeléséről, az oldaltulajdonságok kezeléséről és a PDF-fájlok egyszerű mentéséről.

## Előfeltételek

Mielőtt belemerülnénk a kódba, a következőkre van szüksége:

-  Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Letöltheti[itt](https://visualstudio.microsoft.com/downloads/).
-  Aspose.PDF for .NET: Könnyen letöltheti az Aspose.PDF könyvtárat a[Az Aspose kiadási oldala](https://releases.aspose.com/pdf/net/).
- Alapvető C# ismerete: A C# alapjainak megértése segít jobban követni.
- .NET-keretrendszer: Ideális esetben győződjön meg arról, hogy kompatibilis .NET-környezetben dolgozik.

Miután beállította ezeket az előfeltételeket, készen áll a PDF-dokumentumok létrehozására!

## Csomagok importálása

A C# fájl elején importálnia kell a szükséges Aspose.PDF névtereket. Ez lehetővé teszi a könyvtári funkciók hasznosítását projektünkben.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

 Győződjön meg arról, hogy a projektben hozzáadta a szükséges hivatkozásokat az Aspose.PDF könyvtárhoz. Ha NuGetet használ, egyszerűen hozzáadhatja a következő kereséssel`Aspose.PDF`.

Most, hogy mindent beállítottunk, bontsuk le a folyamatot kezelhető lépésekre a táblázat PDF-dokumentumban történő megjelenítéséhez. Ne aggódj; Világos utasításokkal végigvezetem minden lépésen!

## 1. lépés: Állítsa be a dokumentum- és oldalinformációkat

Először is létre kell hoznunk egy új dokumentumot, és konfigurálni kell az oldalbeállításokat. Ezt a következőképpen teheti meg:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

Magyarázat: 
- Kezdjük azzal, hogy meghatározzuk, hova kerüljön a dokumentumunk (`dataDir`). 
-  Ezután létrehozunk egy új példányt a`Document` osztály. 
- Az oldalmargókat úgy állítjuk be, hogy némi lélegzetvételnyi helyet biztosítsunk az asztalunk körül.
- Végül a dokumentumot fekvő tájolásra állítottuk, ami segít a szélesebb táblázatok megjelenítésénél.

## 2. lépés: Hozza létre az első táblázatot

Ezután hozzuk létre az első táblázatunkat, és töltsük fel néhány mintaadattal:

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100"; // Határozza meg az oszlopszélességeket
```

 Magyarázat: Itt példányosítjuk a`Table` osztályt, és állítsa be az oszlopszélességeket. Az első oszlop 50 egység, a második oszlop pedig 100 egység széles lesz.

## 3. lépés: Töltse fel a táblázatot sorokkal

Most adjunk hozzá sorokat a táblázatunkhoz ciklusban:

```csharp
Page curPage = doc.Pages.Add(); // Új oldal hozzáadása
for (int i = 1; i <= 120; i++)
{
    Aspose.Pdf.Row row = table.Rows.Add();
    row.FixedRowHeight = 15; // Állítson be egy fix magasságot a sorokhoz
    
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("Content 1"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

Magyarázat: 
- Itt létrehozunk egy új oldalt a táblázatunk hozzáadásához.
-  Használjuk a`for` hurok hozzáadásához 120 sort a táblázatunkhoz. Minden sor fix magassága 15 egység.
- Minden sorba hozzáadunk két cellát, és feltöltjük őket szöveggel.

## 4. lépés: Adja hozzá az első táblázatot az oldalhoz

Miután feltöltöttük a táblázatot, hozzáadjuk az aktuális oldalhoz:

```csharp
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
```

Magyarázat: Ez a lépés egyszerűen hozzáadja az általunk létrehozott táblázatot az aktuális oldal bekezdéseihez, és láthatóvá teszi a táblázatot a PDF-dokumentumban.

## 5. lépés: Hozzon létre egy második táblázatot

Most készítsünk egy második táblázatot eltérő tartalommal, és adjuk hozzá egy új oldalhoz:

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
    Aspose.Pdf.Row row = table1.Rows.Add();
    Aspose.Pdf.Cell cell1 = row.Cells.Add();
    cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
    
    Aspose.Pdf.Cell cell2 = row.Cells.Add();
    cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true; // A második táblázat beállítása új oldalon való megjelenésre
paragraphs.Add(table1);
```

Magyarázat: 
- Ez a kódrészlet egy új, két oszlopból álló táblázatot hoz létre, mindkettő 100 egység széles.
-  A`for` ciklus 10 sort ad hozzá mintatartalommal.
-  Beállítás által`table1.IsInNewPage` igaz, gondoskodunk arról, hogy ez a táblázat egy új oldalon jelenjen meg, így a dolgok rendezetten és rendezetlenül maradnak.

## 6. lépés: Mentse el a dokumentumot

Most, hogy elkészültek a táblázataink, mentsük el a dokumentumunkat:

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);
```

 Magyarázat: Megadjuk a fájlnevet, és elmentjük a dokumentumot a megadott könyvtárba. Amikor futtatja ezt a kódot, egy PDF-fájl címe`IsNewPageProperty_Test_out.pdf` a megadott helyen jön létre.

## 7. lépés: Megerősítő üzenet

Végül, hogy a felhasználó tudja, hogy minden zökkenőmentesen működött, hozzáadhatunk egy barátságos konzolüzenetet:

```csharp
Console.WriteLine("\nTable rendered successfully on a page.\nFile saved at " + dataDir);
```

Magyarázat: Ez egy egyszerű módja annak, hogy megbizonyosodjon arról, hogy a művelet sikeres volt, és hol találja meg a felhasználó az új PDF-fájlt.

## Következtetés

És megvan! Sikeresen renderelt táblázatokat egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Néhány sornyi kóddal nagy mennyiségű adatot kezelhet és jeleníthet meg szervezett formátumban, így dokumentumai informatívak és látványosak. Akár leltárlistákkal, pénzügyi jelentésekkel vagy oktatási dokumentumokkal dolgozik, a táblázatok kiváló lehetőséget nyújtanak összetett információk egy pillantással történő közvetítésére.

## GYIK

### Testreszabhatom a táblázatok megjelenését az Aspose.PDF-ben?  
Teljesen! Beállíthatja a színeket, a szegélyeket, a betűstílusokat és egyéb tulajdonságokat a táblázatok megjelenésének javítása érdekében.

### Ingyenesen használható az Aspose.PDF?  
 Az Aspose.PDF ingyenes próbaverziót kínál, de kereskedelmi használatra vásárlás szükséges. Az árakat ellenőrizheti[itt](https://purchase.aspose.com/buy).

### Hogyan kaphatok támogatást az Aspose.PDF-problémákhoz?  
 Segítséget kérhet az Aspose támogatási fórumától[itt](https://forum.aspose.com/c/pdf/10).

### Vannak korlátozások az ingyenes próbaverzióra?  
 Igen, a próbaverziónak lehetnek bizonyos korlátai, például vízjelekkel a generált dokumentumokon. A teljes funkcionalitás érdekében fontolja meg egy ideiglenes licenc beszerzését[itt](https://purchase.aspose.com/temporary-license/).

### Hol találhatok további információt az Aspose.PDF funkcióiról?  
 Megtekintheti a rendelkezésre álló átfogó dokumentációt[itt](https://reference.aspose.com/pdf/net/).