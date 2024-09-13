---
title: Oldalszám bélyegzők PDF fájlban
linktitle: Oldalszám bélyegzők PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Könnyen követhető, kódpéldával kiegészített útmutatónkból megtudhatja, hogyan adhat hozzá oldalszámbélyegzőket PDF-fájlokhoz az Aspose.PDF for .NET használatával.
type: docs
weight: 160
url: /hu/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## Bevezetés

Előfordult már, hogy egy PDF-dokumentummal birkózik, és azt kívánta, bárcsak oldalszámok szerepelnének a könnyebb navigáció érdekében? Legyen szó jegyzeteket megosztó diákról, jelentéseket prezentáló szakemberről vagy bárki, aki többoldalas dokumentumokat kezel, az oldalszámok hozzáadásával valóban javíthatja a PDF-fájlok tisztaságát. Szerencsére a hatékony Aspose.PDF for .NET könyvtárral könnyedén hozzáadhat oldalszámbélyegzőket PDF-dokumentumaihoz. Ebben az útmutatóban lépésről lépésre végigvezetjük a teljes folyamaton, biztosítva, hogy minden szükséges tudással rendelkezzen. Merüljünk el!

## Előfeltételek

Mielőtt elkezdené az oldalszámbélyegzőket PDF-dokumentumaihoz adni, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a rendszeren. Itt fogja írni és végrehajtani a kódját.
2. .NET-keretrendszer: A C#-programozás és a .NET-keretrendszer ismerete elengedhetetlen, mivel az Aspose.PDF-et .NET-alkalmazásokhoz tervezték.
3.  Aspose.PDF könyvtár: Az Aspose.PDF könyvtárat letöltheti a[Aspose PDF kiadások](https://releases.aspose.com/pdf/net/). 
4. A PDF-ek alapvető ismerete: Bár nem kell szakértőnek lenned, a PDF-fájlok működésének alapvető ismerete segít az oktatóanyag jobb megértésében.

Miután beállította ezeket az előfeltételeket, készen áll az oldalszámok bélyegzésére!

## Csomagok importálása

Mielőtt belemerülne a kódolásba, meg kell győződnie arról, hogy a szükséges Aspose.PDF csomagok importálva vannak a projektbe. Ez elengedhetetlen a könyvtári funkciók zökkenőmentes kihasználásához. Íme, hogyan kell csinálni:

### Hozzon létre egy új projektet

1. Nyissa meg a Visual Studio-t.
2.  Kattintson rá`File` >`New` >`Project`.
3.  Válasszon ki egy C#-nak megfelelő sablont (pl. konzolalkalmazás), nevezze el, és kattintson rá`Create`.

### Adja hozzá az Aspose.PDF hivatkozást

1. Kattintson a jobb gombbal a projekt nevére a Solution Explorerben.
2.  Kattintson rá`Manage NuGet Packages`.
3.  Keressen rá`Aspose.PDF` és telepítse a legújabb verziót.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ha a könyvtár készen áll, ugorjunk bele a kódolásba!

Most, hogy a környezetünk be van állítva, itt az ideje, hogy oldalszám-bélyegzőket adjunk egy PDF-fájlhoz. Ezt a folyamatot világos lépésekre bontjuk a jobb megértés érdekében.

## 1. lépés: Adja meg a dokumentumkönyvtárat

A kezdéshez meg kell adnia a könyvtárat, ahol a PDF-fájl található. Ez a projekt kiindulópontja.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Frissítse ezt az útvonalat
```

 Magyarázat: Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a PDF-fájlt tartalmazó könyvtár elérési útjával. Ez kritikus fontosságú, mivel megmondja a kódnak, hogy hol találja meg a módosítani kívánt fájlt.

## 2. lépés: Nyissa meg a dokumentumot

Ezután megnyitjuk a meglévő PDF-dokumentumot, amelyhez az oldalszám bélyegzőit hozzá szeretnénk adni.

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

 Magyarázat: Itt a`Document` Az Aspose.PDF által biztosított osztály az adott PDF fájl megnyitásához. Győződjön meg arról, hogy a fájlnév megegyezik a könyvtárában lévő tényleges fájllal.

## 3. lépés: Hozzon létre egy oldalszám bélyeget

Most jön a szórakoztató rész! Hozzon létre egy oldalszám bélyeget, amelyet hozzáadhat a PDF-hez.

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

 Magyarázat: A`PageNumberStamp`osztály lehetővé teszi számunkra, hogy bélyegzőt hozzunk létre, amely megjeleníti az aktuális oldalszámot a dokumentum teljes oldalszámához viszonyítva.

## 4. lépés: Konfigurálja a bélyegzőt

Most konfigurálnia kell a bélyegző beállításait. Itt lehet megtervezni a bélyegző megjelenését és viselkedését.

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

Magyarázat:
- `Background = false`: Ez azt jelenti, hogy a bélyegző az előtérben fog megjelenni.
- `Format`: Itt úgy állítja be a formátumot, hogy az „Y/X oldal” jelenjen meg, ahol dinamikusan lekéri a dokumentum összes oldalát.
- `BottomMargin`: Beállítja a távolságot az oldal aljától.
- `HorizontalAlignment`: A bélyegzőt vízszintesen középre állítja.
- `StartingNumber`: Beállítja, hogy mi legyen a kezdőoldal száma, általában 1-től.

## 5. lépés: Állítsa be a szöveg tulajdonságait

Ezután testreszabhatja a bélyegző szövegének megjelenését.

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

Magyarázat: Ezek az attribútumok beállítják a betűtípust, a betűméretet, a stílust (félkövér és dőlt) és a bélyegzőn belüli szöveg színét, hogy az vizuálisan vonzó legyen.

## 6. lépés: Adja hozzá a bélyegzőt egy adott oldalhoz

Ha beállította a bélyegzőt, itt az ideje, hogy hozzáadja azt a dokumentum egy adott oldalához.

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

 Magyarázat: Ez a sor hozzáadja a bélyeget a PDF első oldalához. Beállíthatja a`Pages[1]` szükség szerint további oldalak indexét.

## 7. lépés: Mentse el a kimeneti dokumentumot

Végül mentse el a módosított PDF-dokumentumot, hogy a változtatások véglegesek legyenek.

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

Magyarázat: Ön határozza meg a kimeneti fájl elérési útját, és menti a dokumentumot. A konzol tudatja Önnel, hogy a bélyegző sikeresen hozzáadásra került, és hová menti a fájlt.

## Következtetés

Az oldalszámbélyegzők hozzáadása a PDF-fájlokhoz az Aspose.PDF for .NET segítségével nem csak egyszerű, hanem nagymértékben testreszabható is. Lépésről lépésre végigjártuk az oldalszámbélyegző létrehozását, biztosítva, hogy egyértelmű útmutatást kapjon az út során. Most már rendelkezik a PDF-dokumentumok fejlesztéséhez szükséges ismeretekkel, amelyek felhasználóbarátabbá és professzionálisabbá teszik azokat. 

## GYIK

### Testreszabhatom az oldalszámok megjelenését?  
Igen! Az útmutatóban bemutatott módon módosíthatja az oldalszámok betűtípusát, méretét, színét és formázását.

### Ingyenesen használható az Aspose.PDF?  
 Az Aspose.PDF ingyenes próbaverziót kínál, de a széleskörű használathoz licenc szükséges. Nézze meg a[oldal vásárlása](https://purchase.aspose.com/buy) további információért.

### Mi van, ha problémákkal szembesülök a megvalósítás során?  
 Meglátogathatja a[Aspose támogatási fórum](https://forum.aspose.com/c/pdf/10) segítségért.

### Hogyan generálhatok automatikusan oldalszámokat több oldalhoz?  
Az útmutató kódja automatikusan kiszámítja az oldalak teljes számát, megkönnyítve a testreszabást több oldalhoz.

### Használhatom az Aspose.PDF-et más programozási nyelveken?  
Míg ez az útmutató a .NET-re összpontosít, az Aspose könyvtárakat tartalmaz Java, Python és sok más számára.