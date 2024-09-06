---
title: Állítsa be a kiemelés tulajdonságát a PDF-fájlban
linktitle: Állítsa be a kiemelés tulajdonságát a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a részletes, lépésenkénti oktatóanyagból megtudhatja, hogyan állíthatja be a kiemelési tulajdonságot PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 130
url: /hu/net/annotations/setcalloutproperty/
---
## Bevezetés

professzionális és tetszetős PDF-dokumentumok létrehozásához gyakran olyan megjegyzések hozzáadása szükséges, amelyek konkrét tartalomra hívják fel a figyelmet. Az egyik ilyen megjegyzés a felirat, amely olyan, mint a képregényekben látható szövegbuborékok. Segítenek tisztázni vagy kiemelni a szöveget a PDF-ben. Az Aspose.PDF for .NET hihetetlenül egyszerűvé teszi az ilyen megjegyzések hozzáadását a dokumentumokhoz, és ebben az oktatóanyagban végigvezetjük, hogyan állíthatja be a kiemelés tulajdonságát egy PDF-fájlban ezzel a hatékony könyvtárral. Akár tapasztalt fejlesztő, akár csak most kezdő, ennek az útmutatónak a végére világosan megérti, hogyan kell dolgozni a PDF-fájlokban található feliratokkal.

## Előfeltételek

Mielőtt belemerülnénk a kódba, tekintsük át az induláshoz szükséges alapvető tudnivalókat.

1.  Aspose.PDF for .NET: Győződjön meg arról, hogy telepítve van az Aspose.PDF for .NET könyvtár. Letöltheti innen[itt](https://releases.aspose.com/pdf/net/).
2. IDE: Fejlesztői környezet, például a Visual Studio.
3. .NET-keretrendszer: Győződjön meg arról, hogy a .NET telepítve van a gépen.
4. Ideiglenes licenc: Ha korlátozások nélkül szeretné kipróbálni az Aspose.PDF teljes funkcióját, szerezzen be egy[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).

## Csomagok importálása

Mielőtt elkezdené írni a kódot, importálnia kell a szükséges csomagokat, amelyek lehetővé teszik a PDF-fájlok és megjegyzések kezelését.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Ezek az importálások minden szükséges osztályt és módszert biztosítanak a PDF-dokumentumok kezeléséhez és a megjegyzésekhez hasonló megjegyzések létrehozásához.

## 1. lépés: Inicializálja a PDF-dokumentumot

Utunk első lépése egy új PDF-dokumentum inicializálása, amelyhez hozzáadjuk a feliratozásunkat. Tekintsd ezt úgy, mint egy üres vászon létrehozását, ahol elkezdheted az elemek hozzáadását.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Új PDF dokumentum inicializálása
Document doc = new Document();
```
 Itt egy újat hozunk létre`Document` objektum, amely PDF fájlként fog szolgálni. A`dataDir` változó arra a könyvtárra van állítva, ahová menteni szeretné a PDF-fájlt, miután végeztünk.

## 2. lépés: Új oldal hozzáadása a dokumentumhoz

Egy PDF-dokumentum több oldalas is lehet, és ebben a lépésben egy új oldalt adunk hozzá a dokumentumunkhoz. Ezen az oldalon helyezzük el a kiemelő megjegyzésünket.

```csharp
//Új oldal hozzáadása a dokumentumhoz
Page page = doc.Pages.Add();
```
 A`Pages.Add()`módszerrel új oldalt adunk hozzá a`doc` objektum. Az új oldal a`page` változót, amelyet később a megjegyzés hozzáadásakor használunk.

## 3. lépés: Határozza meg az alapértelmezett megjelenést

A kommentároknak, akárcsak a kiemelésnek, vizuális megjelenésük van, amelyet személyre szabhat. Ebben a lépésben meghatározzuk, hogyan nézzen ki a feliraton belüli szöveg.

```csharp
// Határozza meg a megjegyzés alapértelmezett megjelenését
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 Létrehozunk a`DefaultAppearance` objektum, amely meghatározza a szöveg színét és betűméretét. Itt a szöveg piros lesz, a betűméret pedig 10-re van állítva. Ez a megjelenés lesz alkalmazva a kiemelés megjegyzésénél.

## 4. lépés: Készítse el a szabad szöveges megjegyzést

Most itt az ideje létrehozni a tényleges megjegyzést. A szabad szöveges annotáció lehetővé teszi, hogy konkrét szöveget és stílust tartalmazó kiemelést adjunk hozzá.

```csharp
// Hozzon létre egy FreeTextAnnotation feliratot
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 Létrehozunk a`FreeTextAnnotation` objektumot adott koordinátákkal, meghatározva a pozícióját az oldalon. A`Intent` be van állítva`FreeTextCallout` , jelezve, hogy ez egy feliratozás. A`EndingStyle` be van állítva`OpenArrow`vagyis a kiemelő sor egy nyitott nyíllal fog végződni.

## 5. lépés: Határozza meg a kiemelés vonalpontjait

A kiemelő megjegyzésnek van egy vonala, amely az érdeklődési területre mutat. Itt meghatározzuk azokat a pontokat, amelyek ezt a vonalat alkotják.

```csharp
// Határozza meg a kiemelő sor pontjait
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 A`Callout` tulajdonság egy tömb`Point` objektumok, amelyek mindegyike egy-egy koordinátát képvisel az oldalon. Ezek a pontok határozzák meg a kiemelő vonal útvonalát, és a klasszikus beszédbuborék megjelenését kölcsönzik neki.

## 6. lépés: Adja hozzá a megjegyzést az oldalhoz

A kommentárunk létrehozása és konfigurálása után a következő lépés az, hogy hozzáadjuk az oldalhoz.

```csharp
// Adja hozzá a megjegyzést az oldalhoz
page.Annotations.Add(fta);
```
 A`Annotations.Add()` módszerrel helyezzük el a megjegyzést a korábban létrehozott oldalon. Ez a lépés hatékonyan „megrajzolja” a feliratot a PDF-oldalon.

## 7. lépés: Állítsa be a Rich Text tartalmat

A kiemelő megjegyzések tartalmazhatnak formázott szöveget, lehetővé téve a formázott tartalmat a buborékon belül. Adjunk hozzá néhány minta szöveget.

```csharp
// Állítsa be a formázott szöveget a kommentárhoz
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Ez egy minta</span></p></body>";
```
 A`RichText` tulajdonság HTML tartalommal van beállítva. Ez lehetővé teszi a feliraton belüli részletes formázást, például a betűméret, a szín és a stílus megadását.

## 8. lépés: Mentse el a PDF-dokumentumot

Végül, miután mindent beállítottunk, el kell mentenünk a dokumentumot. Ez a lépés véglegesíti a PDF-fájl létrehozását a feliratozással.

```csharp
// Mentse el a dokumentumot
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 A`Save()` metódus elmenti a dokumentumot a megadott könyvtárba "SetCalloutProperty.pdf" fájlnévvel. Ezzel a lépéssel lezárjuk a PDF létrehozási folyamatot.

## Következtetés

És megvan! Létrehozott egy PDF-dokumentumot kiemelő megjegyzéssel az Aspose.PDF for .NET használatával. Ez a megjegyzés rendkívül hasznos lehet a dokumentum egyes részeinek kiemeléséhez vagy magyarázatához. Az Aspose.PDF egy hatékony API-t kínál, amely egyszerűvé és rugalmassá teszi a PDF-kezelést. Akár megjegyzéseket ad hozzá, akár dokumentumokat konvertál, akár összetett PDF-feladatokat kezel, az Aspose.PDF mindent megtesz.

## GYIK

### Testreszabhatom a kiemelés megjelenését?

Teljesen! Testreszabhatja a különböző szempontokat, például a vonal színét, vastagságát, valamint a szöveg betűtípus-családját és stílusát.

### Lehetséges több kiemelést hozzáadni egyetlen oldalon?

Igen, tetszőleges számú kiemelést adhat hozzá az egyes megjegyzések lépéseinek megismétlésével.

### Hogyan változtathatom meg a felirat pozícióját?

 Egyszerűen módosítsa a koordinátákat a`Rectangle` és`Callout` tulajdonságokkal a megjegyzés áthelyezéséhez.

### Hozzáadhatok más típusú megjegyzéseket az Aspose.PDF használatával?

Igen, az Aspose.PDF különféle megjegyzéstípusokat támogat, beleértve a kiemeléseket, bélyegzőket és fájlmellékleteket.

### A rich text tartalom HTML-re korlátozódik?

 A`RichText` tulajdonság támogatja a HTML egy részhalmazát, amely lehetővé teszi stílusos szöveg és alapvető formázások hozzáadását.