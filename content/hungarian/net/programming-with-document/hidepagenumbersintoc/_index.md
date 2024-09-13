---
title: Oldalszámok elrejtése a TOC-ban
linktitle: Oldalszámok elrejtése a TOC-ban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan rejtheti el az oldalszámokat a tartalomjegyzékben az Aspose.PDF for .NET használatával. Kövesse ezt a részletes útmutatót a kódpéldákkal a professzionális PDF-ek létrehozásához.
type: docs
weight: 220
url: /hu/net/programming-with-document/hidepagenumbersintoc/
---
## Bevezetés

Amikor PDF-ekkel dolgozik, előfordulhat, hogy érdemes létrehozni egy tartalomjegyzéket (TOC), de az oldalszámok elrejtésével a dolgokat karcsúsíthatja. Lehet, hogy a dokumentum jobban megy nélkülük, vagy talán esztétikai választás. Bármi legyen is az oka, ha az Aspose.PDF for .NET-hez dolgozik, ez az oktatóanyag pontosan megmutatja, hogyan rejtheti el az oldalszámokat a tartalomjegyzékben.

## Előfeltételek

Mielőtt elkezdenénk, néhány dolgot meg kell tennie. Íme egy gyors ellenőrző lista:

- Visual Studio telepítve: A kódoláshoz szüksége lesz a Visual Studio működő verziójára.
- Aspose.PDF for .NET Library: Győződjön meg arról, hogy telepítette az Aspose.PDF for .NET könyvtárat.
  -  Letöltési link:[Aspose.PDF .NET-hez](https://releases.aspose.com/pdf/net/)
- Ideiglenes licenc: Ha teszteli a szolgáltatásokat, hasznos, ha rendelkezik ideiglenes licenccel.
  -  Ideiglenes jogosítvány:[Szerezd meg itt](https://purchase.aspose.com/temporary-license/)

## Csomagok importálása

Mielőtt belevágna a kódba, győződjön meg róla, hogy importálja a következő névtereket a C# projektbe. Ezek biztosítják a szükséges osztályokat és módszereket a PDF-dokumentumokkal való munkához és a tartalomjegyzék (TOC) létrehozásához.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Most, hogy a környezet készen áll, és a csomagok importálva vannak, bontsuk le a folyamat egyes lépéseit. Az egyértelműség érdekében a kód minden részét lefedjük, így könnyen követheti a lépést.

## 1. lépés: Inicializálja a PDF-dokumentumot

Először is létre kell hoznunk egy új PDF-dokumentumot, és hozzá kell adni egy oldalt a tartalomjegyzékhez (TOC).


```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir: Ez az a könyvtár, ahová a kimeneti fájl mentésre kerül.
- Document(): Új PDF dokumentum inicializálása.
- Pages.Add(): Új üres oldalt ad a dokumentumhoz, amely később tartalmazza a tartalomjegyzékét.

## 2. lépés: Állítsa be a TOC-adatokat és a címet

Ezután meghatározzuk a tartalomjegyzék-információkat, beleértve a tartalomjegyzék tetején megjelenő cím beállítását.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo: Ez az objektum tartalmazza a tartalomjegyzékről szóló összes információt.
- TextFragment: A tartalomjegyzék címének szövegét képviseli, itt "Tartalomjegyzék"-ként állítjuk be.
- FontStyle: A TOC címet úgy alakítjuk ki, hogy a méretét 20-ra állítjuk, és félkövérre szedjük.
- tocPage.TocInfo: A tartalomjegyzék-információt hozzárendeljük ahhoz az oldalhoz, amelyen megjelenik a tartalomjegyzék.

## 3. lépés: Az oldalszámok elrejtése a TOC-ban

Most jöjjön a szórakoztató rész! Itt állítjuk be a TOC-t az oldalszámok elrejtésére.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers: Ez a varázskapcsoló, amely elrejti az oldalszámokat. Állítsa be`false`, és az oldalszámok nem jelennek meg a tartalomjegyzékben.
- FormatArrayLength: Ezt 4-re állítjuk, jelezve, hogy a TOC címsorok négy szintjéhez szeretnénk formázást definiálni.

## 4. lépés: A TOC formázásának testreszabása

A TOC stílusosabbá tétele érdekében a címsorok különböző szintjeihez formázást határozunk meg.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray: Ez a tömb szabályozza a TOC bejegyzések formázását. Minden index más-más címsorszintet jelöl.
- Margó és szövegstílus: Minden címsorszinthez margókat állítunk be, és betűstílusokat alkalmazunk, például félkövér, dőlt és aláhúzott.

## 5. lépés: Adjon hozzá címeket a dokumentumhoz

Végül adjuk hozzá a tényleges címsorokat, amelyek a TOC részét képezik.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Címsor és szövegszegmens: Ezek a tartalomjegyzékben megjelenő címsorok. Minden szintnek megvan a maga címe.
- IsAutoSequence: Automatikusan számozza a címsorokat.
- IsInList: Biztosítja, hogy minden címsor megjelenjen a tartalomjegyzékben.

## 6. lépés: Mentse el a dokumentumot

Ha mindent beállított, mentse a PDF-dokumentumot a megadott kimeneti fájlba.

```csharp
doc.Save(outFile);
```

És ennyi! Sikeresen létrehozott egy PDF-t tartalomjegyzékkel, és az oldalszámok el vannak rejtve!

## Következtetés

tartalomjegyzék létrehozása PDF-ben és az oldalszámok elrejtése bonyolultnak tűnhet, de a .NET-hez készült Aspose.PDF használatával ez gyerekjáték. A lépésenkénti útmutató követésével megtanulta, hogyan szabhatja testre a tartalomjegyzék formátumát, hogyan rejtheti el az oldalszámokat, és hogyan alkalmazhat különböző stílusokat a címsorokhoz. Mostantól professzionális PDF-fájlokat készíthet, amelyek pontosan az Ön igényeihez vannak szabva.

## GYIK

### Megmutathatok oldalszámokat a tartalomjegyzékben bizonyos címsorokhoz?
Nem, az Aspose.PDF elrejti vagy megjeleníti a teljes tartalomjegyzék oldalszámait. Ezeket nem lehet szelektíven elrejteni bizonyos bejegyzéseknél.

### Lehetséges több szintet hozzáadni a TOC-hoz?
 Igen, növelheti a`FormatArrayLength` a TOC címsorok több szintjének meghatározásához.

### Hogyan változtathatom meg az összes TOC-bejegyzés betűtípusát?
 A betűtípust módosíthatja a`TextState.Font` tulajdonság minden szinten a`FormatArray`.

### Beilleszthetek hiperhivatkozásokat a tartalomjegyzékbe?
 Igen, az egyes TOC bejegyzéseket a dokumentum egy adott szakaszához kapcsolhatja a következővel`Heading.TocPage` ingatlan.

### Szükségem van licencre az Aspose.PDF fájlhoz?
Igen, a termelési felhasználáshoz érvényes engedély szükséges. Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/) a funkciók tesztelésére.