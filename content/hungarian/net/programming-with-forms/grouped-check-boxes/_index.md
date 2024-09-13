---
title: Csoportosított jelölőnégyzetek a PDF-dokumentumban
linktitle: Csoportosított jelölőnégyzetek a PDF-dokumentumban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésenkénti oktatóanyagból megtudhatja, hogyan hozhat létre csoportosított jelölőnégyzeteket (választógombokat) PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 170
url: /hu/net/programming-with-forms/grouped-check-boxes/
---
## Bevezetés

Az interaktív PDF-fájlok létrehozása nem olyan nehéz, mint amilyennek hangzik, különösen akkor, ha olyan hatékony eszközök állnak rendelkezésére, mint az Aspose.PDF for .NET. Az egyik interaktív elem, amelyet hozzá kell adnia a PDF-dokumentumokhoz, a csoportos jelölőnégyzetek, pontosabban a választógombok, amelyek lehetővé teszik a felhasználók számára, hogy egy beállítást válasszanak a készletből. Ez az oktatóanyag végigvezeti a csoportosított jelölőnégyzetek (rádiógombok) PDF-dokumentumokhoz való hozzáadásának folyamatán az Aspose.PDF for .NET használatával. Akár kezdő, akár tapasztalt fejlesztő, ezt az útmutatót lebilincselőnek, részletesnek és könnyen követhetőnek találja.

## Előfeltételek

Mielőtt belemerülnénk a lépésről lépésre szóló útmutatóba, tekintsünk át néhány alapvető előfeltételt:

1.  Aspose.PDF for .NET: Győződjön meg arról, hogy telepítve van az Aspose.PDF könyvtár. Ha nem, akkor megteheti[töltse le itt](https://releases.aspose.com/pdf/net/).
2. IDE: Be kell állítania egy fejlesztői környezetet, például a Visual Studio-t.
3. .NET-keretrendszer: A projektnek meg kell céloznia a .NET-keretrendszer Aspose.PDF-fel kompatibilis verzióját.
4. Alapvető C# ismeretek: A zökkenőmentes követéshez a C# és a PDF-kezelés ismerete szükséges.
5.  Licenc: Az Aspose.PDF teljes funkcióihoz licenc szükséges. Tudod[ideiglenes engedélyt szerezni](https://purchase.aspose.com/temporary-license/) ha szükséges.

## Csomagok importálása

Mielőtt elkezdené, győződjön meg róla, hogy importálta a szükséges névtereket a projektbe:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Ezek a csomagok hozzáférést biztosítanak a PDF dokumentumok kezeléséhez szükséges összes osztályhoz és módszerhez, beleértve a választógombok létrehozását és tulajdonságaik meghatározását.

Ebben a részben a csoportosított jelölőnégyzetek (rádiógombok) létrehozásának folyamatát világos, könnyen követhető lépésekre bontjuk.

## 1. lépés: Hozzon létre egy új PDF-dokumentumot

 Az első lépés egy példány létrehozása a`Document` objektum, amely az Ön PDF-fájlját fogja képviselni. Ezután adjon hozzá egy üres oldalt a dokumentumhoz, ahol elhelyezheti a csoportosított jelölőnégyzeteket.

```csharp
// Dokumentum objektum példányosítása
Document pdfDocument = new Document();

// Adjon hozzá egy oldalt a PDF-fájlhoz
Page page = pdfDocument.Pages.Add();
```

Ez megteremti az alapot bármely elem, például rádiógombok PDF-hez való hozzáadásához.

## 2. lépés: Inicializálja a rádiógomb mezőt

Ezután létre kell hoznunk a`RadioButtonField` objektum, amely a csoportosított jelölőnégyzeteket (rádiógombokat) fogja tartalmazni. Ez a mező hozzáadódik ahhoz az oldalhoz, ahol a jelölőnégyzetek megjelennek.

```csharp
// Példányosítsa a RadioButtonField objektumot, és rendelje hozzá az első oldalhoz
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Tekintse ezt úgy, mint egy tárolót, amely csoportosítja az egyes választógomb-beállításokat.

## 3. lépés: Adja hozzá a választógomb opcióit

 Most adjuk hozzá az egyes választógomb-beállításokat a mezőhöz. Ebben a példában két választógombot adunk hozzá, és adjuk meg a pozíciójukat a gombbal`Rectangle` objektum.

```csharp
// Adja hozzá az első választógombot, és adja meg a pozícióját a Téglalap segítségével
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Állítsa be az azonosításhoz szükséges opcióneveket
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Itt, a`Rectangle` objektum határozza meg az oldalon lévő egyes rádiógombok koordinátáit és méretét.

## 4. lépés: A rádiógombok stílusának testreszabása

 Testreszabhatja a rádiógombok megjelenését azok beállításával`Style` ingatlan. Például érdemes lehet négyzet alakú jelölőnégyzeteket vagy kereszt alakúakat.

```csharp
// Állítsa be a rádiógombok stílusát
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Ez lehetővé teszi a jelölőnégyzetek megjelenésének szabályozását, felhasználóbarátabbá és látványosabbá téve azokat.

## 5. lépés: Állítsa be a szegély tulajdonságait

A szegélyek létfontosságú szerepet játszanak abban, hogy a jelölőnégyzetek könnyen azonosíthatók legyenek. Itt tömör kereteket adunk az egyes választógombok körül, és meghatározzuk a szélességet és a színt.

```csharp
// Állítsa be az első rádiógomb szegélyét
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Állítsa be a második rádiógomb szegélyét
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Ez a lépés biztosítja, hogy minden rádiógombnak jól meghatározott szegélye legyen, javítva a dokumentum olvashatóságát.

## 6. lépés: Adja hozzá a választógomb opciókat az űrlaphoz

Most hozzáadjuk a választógombokat a dokumentum űrlapjához. Ez az utolsó lépés a jelölőnégyzetek egyetlen mező alá történő csoportosításában.

```csharp
// Rádiógomb mező hozzáadása a dokumentum űrlapobjektumához
pdfDocument.Form.Add(radio);
```

Az űrlapobjektum az összes interaktív elem tárolójaként működik, beleértve a csoportosított jelölőnégyzeteinket is.

## 7. lépés: Mentse el a PDF-dokumentumot

Végül, miután mindent beállított, elmentheti a PDF dokumentumot a kívánt helyre.

```csharp
// Határozza meg a kimeneti fájl elérési útját
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Mentse el a PDF dokumentumot
pdfDocument.Save(dataDir);

// Erősítse meg a sikeres létrehozást
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

És ennyi! Sikeresen létrehozott egy PDF-et csoportosított jelölőnégyzetekkel az Aspose.PDF for .NET használatával.

## Következtetés

Interaktív elemek, például csoportos jelölőnégyzetek hozzáadása a PDF-dokumentumokhoz elsőre trükkösnek tűnhet, de az Aspose.PDF for .NET használatával gyerekjáték. Ennek a lépésenkénti útmutatónak a követésével megtanulta, hogyan állíthat be egy alapvető PDF-dokumentumot, hogyan adhat hozzá csoportosított választógombokat, hogyan szabhatja testre megjelenésüket, és hogyan mentheti el a végeredményt. Akár nyomtatványokat, felméréseket vagy bármilyen más interaktív PDF-t készít, ez az útmutató szilárd alapot ad a kezdéshez.

## GYIK

### Hozzáadhatok kettőnél több választógombot egy csoporthoz?
 Teljesen! Egyszerűen további példányosítás`RadioButtonOptionField` objektumokat, és add hozzá őket a`RadioButtonField` az oktatóanyagban látható módon.

### Hogyan kezelhetek több jelölőnégyzetcsoportot egy dokumentumban?
Több csoport létrehozásához példányosítsa el őket külön`RadioButtonField` objektumok minden csoporthoz.

### Korlátozott a hozzáadható jelölőnégyzetek száma?
Nem, az Aspose.PDF for .NET nem szab semmilyen korlátozást a PDF-hez hozzáadható jelölőnégyzetek számára.

### Módosíthatom a jelölőnégyzetek megjelenését a hozzáadása után?
Igen, a jelölőnégyzetek hozzáadása után módosíthatja a tulajdonságokat, például a szegély stílusát, szélességét és színét.

### Lehetséges a képeket rádiógombként használni?
 Igen, az Aspose.PDF lehetővé teszi egyéni képek rádiógombként történő használatát a`Appearance` az egyes választógomb opciók tulajdonsága.