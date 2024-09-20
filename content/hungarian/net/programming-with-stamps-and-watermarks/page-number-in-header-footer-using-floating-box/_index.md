---
title: Oldalszám a fejléc láblécében úszó doboz használatával
linktitle: Oldalszám a fejléc láblécében úszó doboz használatával
second_title: Aspose.PDF for .NET API Reference
description: Könnyen hozzáadhat oldalszámokat PDF fejlécéhez és láblécéhez a .NET-hez készült Aspose.PDF-et tartalmazó lebegő doboz segítségével ebben a lépésről lépésre bemutatott oktatóanyagban.
type: docs
weight: 150
url: /hu/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## Bevezetés

Ha a PDF-dokumentumok programozott kezeléséről van szó, az Aspose.PDF for .NET kivételes eszközként tűnik ki. Leegyszerűsíti a PDF-fájlok létrehozását, szerkesztését és kezelését a .NET-alkalmazásokban. Akár számlákat, jelentéseket vagy bármilyen dokumentumtípust állít elő, az oldalszámok elegáns hozzáadásával javíthatja a PDF-ek professzionalizmusát és rendszerezését. Ebben az oktatóanyagban belemerülünk abba, hogyan lehet oldalszámokat hozzáadni a PDF-fájl fejlécéhez és láblécéhez a Floating Box segítségével. Készen áll az indulásra? Menjünk!

## Előfeltételek

Mielőtt elkezdené ezt az izgalmas utazást a PDF-manipuláció birodalmába, néhány dologra szüksége van:

### .NET-környezet beállítása
Győződjön meg arról, hogy rendelkezik .NET fejlesztői környezettel. Használhatja a Visual Studio-t, amely népszerű választás a .NET-alkalmazások fejlesztői körében.

### Aspose.PDF Library
Telepítse az Aspose.PDF könyvtárat. Könnyen letöltheti a weboldalról:

- [Töltse le az Aspose.PDF-et .NET-hez](https://releases.aspose.com/pdf/net/)

### C# programozási alapismeretek
A C# alapvető ismerete segít megérteni az oktatóanyagban bemutatott fogalmakat és kódrészleteket.

### Hozzáférés a Dokumentációhoz
 Mindig előnyös, ha a[Aspose.PDF dokumentáció](https://reference.aspose.com/pdf/net/) hasznos referenciaként és minden további funkció mélyebb felfedezéséhez.

## Csomagok importálása

A kezdéshez importálnia kell a szükséges csomagokat a projektbe. Ez biztosítja, hogy az Aspose.PDF összeállítás elérhető legyen a kódban való használatra. Íme, hogyan kell csinálni:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Most bontsuk fel kezelhető lépésekre az oldalszámok lebegő doboz használatával történő hozzáadásának folyamatát. Kövesd, ahogy átsétálunk.

## 1. lépés: Állítsa be a dokumentumkörnyezetet

Kezdjük a PDF-dokumentum tárolási könyvtárának megadásával. Ez döntő fontosságú, mert ez határozza meg, hogy a kimeneti fájl hova kerüljön mentésre.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`YOUR DOCUMENT DIRECTORY` a választott elérési úttal, ahová menteni szeretné a kimeneti PDF-fájlt.

## 2. lépés: Példányosítsa a dokumentumot

 A következő lépés egy új PDF dokumentum létrehozása. Ez magában foglalja a`Document` osztály az Aspose.PDF könyvtárból.

```csharp
// Példányos dokumentum példány
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 Itt létrehozunk egy új példányt a`Document` osztály, amely a manipuláció vásznánkként szolgál.

## 3. lépés: Új oldal hozzáadása

Most adjunk hozzá egy oldalt a PDF dokumentumunkhoz. Minden PDF-nek legalább egy oldalra van szüksége, igaz?

```csharp
// Adjon hozzá egy oldalt a PDF dokumentumhoz
Aspose.Pdf.Page page = pdf.Pages.Add();
```
Ez a kódrészlet új oldalt ad a dokumentumunkhoz, így készen áll a tartalom fogadására, beleértve az oldalszámokat tartalmazó lebegő dobozunkat.

## 4. lépés: Hozzon létre egy úszó dobozt

 Ezután itt az ideje létrehozni a Lebegő dobozunkat, amely az oldalszámot fogja tárolni. A`FloatingBox`osztály lehetővé teszi számunkra, hogy a tartalmat szabadon helyezzük el az oldalon.

```csharp
// Inicializálja a FloatingBox osztály új példányát
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 Itt a paraméterek`(140, 80)` adja meg a Lebegő doboz szélességét és magasságát. Ezeket az értékeket az elrendezési preferenciái alapján módosíthatja.

## 5. lépés: Az úszó doboz elhelyezése

 A pozicionálás kulcsfontosságú! Meg akarja határozni, hogy az oldalon hol jelenjen meg az oldalszám. Együtt fogsz dolgozni a`Left` és`Top` tulajdonságok a pozíció megadásához.

```csharp
// Lebegő érték, amely a bekezdés bal oldali pozícióját jelzi
box1.Left = 2;
// Lebegő érték, amely a bekezdés felső pozícióját jelzi
box1.Top = 10;
```
Ezek az értékek határozzák meg a Lebegő doboz elhelyezését az oldalon. Nyugodtan kísérletezzen velük, hogy megtudja, mi áll a legjobban a dokumentumhoz.

## 6. lépés: Szöveg hozzáadása az oldalszámmakróval

Most hozzáadunk egy karakterláncot, amely dinamikusan mutatja az oldalszámot. Itt történik a varázslat!

```csharp
// Adja hozzá a makrókat a FloatingBox bekezdésgyűjteményéhez
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 Ebben az esetben`($p/ $P)`egy makró, amely megjeleníti az aktuális oldalszámot (`$p`) és az oldalak teljes száma (`$P`). Ennek eredményeként a szöveget úgy formázza, hogy az „Oldal: 1/5”-hez hasonló legyen.

## 7. lépés: Adja hozzá a Lebegő dobozt az oldalhoz

Ideje hozzáadni a Lebegő dobozt az oldalszám szövegével együtt az újonnan létrehozott oldalunkhoz.

```csharp
// Adjon hozzá egy floatingBoxot az oldalhoz
page.Paragraphs.Add(box1);
```
Ez a sor lényegében beágyazza a Lebegő dobozt az oldalba, így a dokumentum elrendezésének részévé válik. 

## 8. lépés: Mentse el a dokumentumot

Végül ne felejtse el menteni a munkáját! Az utolsó lépés a PDF-dokumentum megfelelő fájlnévvel történő mentése.

```csharp
// Mentse el a dokumentumot
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
Győződjön meg arról, hogy a megadott elérési út tartalmazza a kívánt fájlnevet. Most elkészült az oldalszámokkal ellátott csodálatos PDF-je! 

## Következtetés

És itt van, emberek! Az oldalszámok hozzáadása a PDF fejlécéhez és láblécéhez az Aspose.PDF for .NET használatával ilyen egyszerű. Csak néhány sornyi kóddal elindult a dokumentumfeldolgozás elsajátítása felé vezető úton. Ne habozzon kísérletezni a különböző elrendezésekkel és formázással – elvégre a kreativitás nem ismer határokat! Készen áll a professzionális dokumentum létrehozására? Fogja meg kódoló kalapját, és kezdjen el kísérletezni.

## GYIK

### Testreszabhatom az oldalszám szövegének megjelenését?  
 Igen, személyre szabhatja a szöveg tulajdonságait, például a betűméretet, a színt és a stílust a`TextFragment` tulajdonságait.

### Ingyenesen használható az Aspose.PDF?  
 Míg az Aspose.PDF ingyenes próbaverziót kínál, ez egy fizetős termék éles használatra. Megteheti[vásárold meg itt](https://purchase.aspose.com/buy).

### Hol találok részletesebb dokumentációt?  
 Részletes dokumentációt találhat a[Aspose.PDF dokumentációs oldal](https://reference.aspose.com/pdf/net/).

### Hogyan alkalmazhatok fejlécet és láblécet több oldalra?  
Végigpörgetheti a dokumentum összes oldalát, és mindegyikre hasonlóan alkalmazhatja a Lebegő dobozt.

### Mi a teendő, ha támogatásra van szükségem a további funkciókhoz?  
További kérdéseivel vagy támogatásával keresse fel a[Aspose fórum](https://forum.aspose.com/c/pdf/10).