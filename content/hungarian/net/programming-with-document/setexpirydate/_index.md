---
title: Állítsa be a lejárati dátumot a PDF-fájlban
linktitle: Állítsa be a lejárati dátumot a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthat be lejárati dátumot a PDF-fájlokban az Aspose.PDF for .NET használatával. Növelje a dokumentumok biztonságát ezzel a lépésenkénti útmutatóval.
type: docs
weight: 300
url: /hu/net/programming-with-document/setexpirydate/
---
## Bevezetés

mai digitális korban a dokumentumok kezelése és védelme fontosabb, mint valaha. Képzelje el, hogy kiküld egy PDF-fájlt, amely egy bizonyos dátum után automatikusan elérhetetlenné válik. Varázslatnak hangzik, igaz? Nos, az Aspose.PDF for .NET segítségével egyszerűen beállíthat egy lejárati dátumot a PDF-fájlokhoz. Ez a funkció különösen hasznos olyan bizalmas dokumentumok esetében, amelyeket bizonyos idő elteltével korlátozni kell. Ebben az oktatóanyagban lépésről lépésre végigvezetjük a lejárati dátum PDF-fájlban történő beállításának folyamatán. Szóval, fogd a kódoló kalapot, és merüljünk bele!

## Előfeltételek

Mielőtt elkezdenénk, néhány dolgot meg kell tennie:

1. Fejlesztői környezet: Győződjön meg arról, hogy be van állítva egy .NET fejlesztői környezet. Ez lehet a Visual Studio vagy bármely más IDE, amely támogatja a .NET-et.
2.  Aspose.PDF for .NET: telepítenie kell az Aspose.PDF könyvtárat. Ha még nem tette meg, letöltheti innen[itt](https://releases.aspose.com/pdf/net/).
3. Alapvető C# ismeretek: Ez az oktatóanyag feltételezi, hogy rendelkezik alapvető ismeretekkel a C# programozásról. Ha még nem ismeri a C#-t, ne aggódjon! Legyen egyszerű és egyértelmű.

## Csomagok importálása

Az Aspose.PDF használatának megkezdéséhez importálnia kell a szükséges névtereket a C# projektbe. Így teheti meg:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Ezek a névterek hozzáférést biztosítanak az Aspose.PDF PDF-dokumentumainak kezeléséhez szükséges alapvető funkciókhoz.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Először is meg kell adnia a dokumentumkönyvtár elérési útját. Ez az a hely, ahol a kimeneti PDF mentésre kerül. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahová a PDF-fájlt menteni szeretné. Ez olyan, mintha azt mondaná a programnak: "Hé, itt tartom a fájljaimat!"

## 2. lépés: Példányosítsa a dokumentumobjektumot

 Ezután létre kell hoznia egy új példányt a`Document` osztály. Ez a vászon, ahol elkészítheti PDF-jét.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Gondolj a`Document` tárgyat üres papírlapként. Tetszés szerint hozzáadhat tartalmat!

## 3. lépés: Adjon hozzá egy oldalt a PDF-hez

Most, hogy beállította a dokumentumot, ideje hozzáadni egy oldalt. Ide kerül a tartalom.

```csharp
doc.Pages.Add();
```

Most hozott létre egy új oldalt a PDF-ben. Ez olyan, mintha új oldalt adna a jegyzetfüzetéhez, ahol feljegyezheti gondolatait.

## 4. lépés: Szöveg hozzáadása az oldalhoz

Tegyük érdekesebbé ezt az oldalt egy kis szöveg hozzáadásával. Hozzáadunk egy egyszerű „Hello World” üzenetet.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Ez a kódsor egy szövegrészletet ad a PDF-fájl első oldalához. Mintha címet írnál az oldalad tetejére!

## 5. lépés: Hozzon létre JavaScriptet a lejárati dátumhoz

Most jön a szórakoztató rész! Létrehoz egy JavaScript-műveletet, amely ellenőrzi a PDF lejárati dátumát. Ha az aktuális dátum meghaladja a lejárati dátumot, egy üzenet figyelmezteti a felhasználót.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Íme, mi történik:
- Ön határozza meg a lejárati évet és hónapot.
- Megkapod a mai dátumot.
- Összehasonlítja a mai dátumot a lejárati dátummal.
- Ha a mai dátum lejárt a lejárati dátumon, megjelenik egy üzenet!

## 6. lépés: Állítsa be a JavaScriptet PDF megnyitási műveletként

Most be kell állítania a JavaScript-műveletet a PDF-dokumentum megnyitási műveleteként. Ez azt jelenti, hogy a JavaScript a PDF megnyitásakor azonnal lefut.

```csharp
doc.OpenAction = javaScript;
```

Ez a sor arra utasítja a PDF-fájlt, hogy hajtsa végre a JavaScriptet, amikor valaki megnyitja. Ez olyan, mintha egy emlékeztetőt állítana be, amely azonnal felkapcsol, amint kinyitja a naptárát!

## 7. lépés: Mentse el a PDF-dokumentumot

Végül itt az ideje, hogy elmentse PDF-dokumentumát a lejárati dátum funkcióval. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Ez a sor menti a PDF-fájlt a megadott könyvtárba "SetExpiryDate_out.pdf" néven. Ez olyan, mintha az elkészült alkotásodat keretbe helyeznéd!

## Következtetés

És megvan! Sikeresen létrehozott egy lejárati dátumú PDF-fájlt az Aspose.PDF for .NET használatával. Ez a funkció nemcsak a biztonságot növeli, hanem azt is biztosítja, hogy az érzékeny információk ellenőrzés alatt maradjanak. Akár szerződéseket, jelentéseket vagy egyéb fontos dokumentumokat küld ki, a lejárati dátum beállítása megváltoztathatja a játékot.

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok létrehozását, kezelését és konvertálását .NET-alkalmazásokban.

### Használhatom ingyenesen az Aspose.PDF-et?
 Igen, használhatja az Aspose.PDF ingyenes próbaverzióját. Letöltheti[itt](https://releases.aspose.com/).

### Hogyan vásárolhatom meg az Aspose.PDF-et?
Megvásárolhatja az Aspose.PDF-et a weboldalon[vásárlási oldal](https://purchase.aspose.com/buy).

### Mi van, ha támogatásra van szükségem?
Ha bármilyen kérdése van, vagy segítségre van szüksége, keresse fel a[Aspose támogatási fórum](https://forum.aspose.com/c/pdf/10).

### Kaphatok ideiglenes licencet az Aspose.PDF fájlhoz?
 Igen, kérhet ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).