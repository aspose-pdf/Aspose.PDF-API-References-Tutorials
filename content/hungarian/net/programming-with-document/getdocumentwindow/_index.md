---
title: Dokumentum beszerzése ablak
linktitle: Dokumentum beszerzése ablak
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan használhatja az Aspose.PDF for .NET GetDocumentWindow funkcióját a PDF-dokumentum ablaktulajdonságaival kapcsolatos információk lekéréséhez.
type: docs
weight: 170
url: /hu/net/programming-with-document/getdocumentwindow/
---
# Bevezetés

PDF-ekkel dolgozik, és jobban szeretné szabályozni, hogyan jelenjenek meg megnyitáskor? Legyen szó a menüsor elrejtéséről vagy az ablak átméretezéséről, hogy illeszkedjen az első oldalhoz, az Aspose.PDF for .NET minden olyan eszközt kínál, amelyre szüksége van a PDF megjelenítőben való megnyitásakor történő testreszabásához. Ebben az oktatóanyagban bemutatjuk, hogyan lehet lekérni és módosítani a dokumentumablak beállításait az Aspose.PDF for .NET-ben.


# Előfeltételek

Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Aspose.PDF for .NET telepítve a fejlesztői környezetre.
  - [Töltse le az Aspose.PDF-et .NET-hez](https://releases.aspose.com/pdf/net/)
-  Érvényes licenc az Aspose.PDF fájlhoz, vagy beszerezheti a[ingyenes próbaverzió](https://releases.aspose.com/) vagy[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).
- A .NET és a C# alapvető ismerete.
- Visual Studio vagy más megfelelő IDE.

# Csomagok importálása

Mielőtt bármilyen kódot írni kezdene, importálnia kell a szükséges csomagokat. Nyissa meg a projektet, és adja hozzá a következő névteret a C# fájl tetejéhez:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ez hozzáférést biztosít az összes osztályhoz és módszerhez, amely a PDF-dokumentumok Aspose.PDF for .NET használatával történő kezeléséhez szükséges.

 Most bontsuk le a különböző dokumentumablak-beállítások lekérésének folyamatát. Ebben a példában egy minta PDF-fájlt fogunk használni, melynek neve`GetDocumentWindow.pdf`.

## 1. lépés: Állítsa be a dokumentumkönyvtár elérési útját

Először is meg kell határoznunk a PDF-fájlunk elérési útját. Rendkívül fontos, hogy a megfelelő fájl elérési úttal rendelkezzen, hogy elkerülje a hibákat a végrehajtás során.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Tessék, cserélje ki`"YOUR DOCUMENT DIRECTORY"` azzal a könyvtárral, ahol a PDF-fájl található. Ez az Ön munkakönyvtára, ahonnan betöltheti a PDF dokumentumot.

## 2. lépés: Nyissa meg a PDF-dokumentumot

Most, hogy a fájl elérési útja be van állítva, a következő lépés a PDF-dokumentum megnyitása az Aspose.PDF használatával. Ez betölti a dokumentumot a memóriába, lehetővé téve a tulajdonságainak lekérését.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

Ezzel az egyszerű kódsorral sikeresen betöltötte a PDF-fájlt a`pdfDocument` objektum, amely most lehetővé teszi az összes tulajdonság elérését.

## 3. lépés: Az ablak központosítási állapotának lekérése

 Ezután nézzük meg, hogy a dokumentumablakot középre kell-e helyezni megnyitáskor. Ennek alapértelmezett értéke`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 Ha a kimenet az`true`, a dokumentum ablaka megnyílik a képernyő közepén. Ellenkező esetben az alapértelmezett pozíciójában nyílik meg.

## 4. lépés: Ellenőrizze a szöveg irányát

A PDF megjelenésének másik döntő szempontja a szöveg iránya, amely meghatározza, hogy a szöveg balról jobbra (L2R) vagy jobbról balra (R2L) kerül-e beolvasásra. Ezeket az információkat a következő kóddal kérheti le:

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 A kimenet az lesz`L2R` balról jobbra haladó szöveghez és`R2L` jobbról balra haladó szöveghez. Ez a beállítás különösen hasznos olyan nyelvű dokumentumok esetén, mint az arab vagy a héber.

## 5. lépés: Jelenítse meg a dokumentum címét az ablakban

 következő tulajdonság lehetővé teszi annak szabályozását, hogy a dokumentum címe vagy a fájl neve jelenjen-e meg az ablak címsorában. Alapértelmezés szerint ez be van állítva`false`, ami azt jelenti, hogy megjelenik a fájl neve.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

Ha azt szeretné, hogy a fájl neve helyett a dokumentum címe jelenjen meg, ezt a beállítást engedélyezni kell.

## 6. lépés: Méretezze át az ablakot az első oldalhoz

Néha előfordulhat, hogy a dokumentumablak automatikusan átméretezi magát, hogy a megnyitáskor illeszkedjen a PDF első oldalához. A következőképpen ellenőrizheti, hogy a funkció engedélyezve van-e:

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 Alapértelmezés szerint ez be van állítva`false`, ami azt jelenti, hogy az ablak mérete változatlan marad, függetlenül az első oldal méretétől.

## 7. lépés: A menüsor elrejtése

A fókuszáltabb olvasási élmény érdekében érdemes lehet elrejteni a megjelenítő alkalmazás menüsorát. Ezt a beállítást a következő sor segítségével kérheti le:

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 Ez vissza fog térni`true` ha a menüsor rejtett, és`false` egyébként.

## 8. lépés: Az Eszköztár elrejtése

Hasonlóképpen, érdemes lehet elrejteni az eszköztárat a PDF-megtekintőben a tisztább felhasználói felület érdekében. Ezt a beállítást a következőképpen lehet visszakeresni:

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

Ha ez a beállítás engedélyezve van, az eszköztár el lesz rejtve a PDF megnyitásakor.

## 9. lépés: A görgetősávok és a felhasználói felület elemeinek elrejtése

Ha csak az oldal tartalmát szeretné megjeleníteni további UI-elemek, például görgetősávok nélkül, ez a beállítás szabályozza ezt a viselkedést:

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 Amikor be van állítva`true`, a PDF-megjelenítő elrejti a görgetősávokat és a felhasználói felület egyéb elemeit, így csak a dokumentum tartalma marad meg.

## 10. lépés: Állítsa be a nem teljes képernyős oldal módot

 A teljes képernyős módból való kilépéskor a dokumentum megjelenítését a gombbal szabályozhatja`NonFullScreenPageMode` ingatlan. Ez a beállítás hasznos annak meghatározásában, hogy a felhasználó hogyan kezelje a dokumentumot nem teljes képernyős módban.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

A kimenet különböző módokba állítható, például miniatűrökre, körvonalakra vagy mellékletek panelre.

## 11. lépés: Határozza meg az oldalelrendezést

Ezzel a beállítással szabályozhatja a dokumentum oldalainak elrendezését. Választhat például egyoldalas vagy folyamatos oszlopnézetet:

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

Ez rugalmasságot biztosít a felhasználóknak a dokumentum tartalmának olvasásában vagy megtekintésében.

## 12. lépés: Adja meg az oldalmódot

 Végül a`PageMode` tulajdonság határozza meg, hogy a dokumentum hogyan jelenjen meg megnyitáskor. A lehetőségek közé tartozik a bélyegképek megjelenítése, a teljes képernyős módba való belépés vagy a mellékletek panel megjelenítése.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

Igényeitől függően bármilyen módot beállíthat, amely megfelel a PDF-fájl céljának.

## Következtetés

Amint láthatja, az Aspose.PDF for .NET átfogó eszközöket biztosít a PDF-dokumentumok különböző PDF-megjelenítőkben való megjelenítésének kezeléséhez. Függetlenül attól, hogy el szeretné rejteni az eszköztárat, középre akarja helyezni az ablakot, vagy szabályozni szeretné a szöveg irányát, az Aspose.PDF rugalmasságot kínál a felhasználó megtekintési élményének javításához.

# GYIK

### Testreszabhatom a PDF kezdeti nagyítási szintjét?
Igen, az Aspose.PDF lehetővé teszi a nagyítási szint beállítását a dokumentum megnyitásakor.

### Hogyan zárolhatom a PDF ablak méretét?
 Beállíthatja a`FitWindow` tulajdonság, hogy megakadályozza az ablak átméretezését.

### Az Aspose.PDF támogatja a különböző olvasási módokat?
Igen, támogatja a különböző módokat, például a teljes képernyőt, az indexképeket és a mellékleteket.

### Lehetséges a görgetősávok elrejtése a PDF-nézőben?
 Egyáltalán elrejtheti a görgetősávokat a`HideWindowUI` tulajdonát`true`.

### Középre tudom helyezni a dokumentumablakot megnyitáskor?
 Igen, ezt a beállításával szabályozhatja`CenterWindow` ingatlan.