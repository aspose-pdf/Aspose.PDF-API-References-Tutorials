---
title: Vízszintesen és függőlegesen Rádiógombok
linktitle: Vízszintesen és függőlegesen Rádiógombok
second_title: Aspose.PDF for .NET API Reference
description: Ebben a lépésenkénti oktatóanyagban megtudhatja, hogyan hozhat létre vízszintesen és függőlegesen igazított választógombokat PDF-ben az Aspose.PDF for .NET használatával.
type: docs
weight: 180
url: /hu/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Bevezetés

Az interaktív PDF-űrlapok létrehozása jelentősen javíthatja a felhasználói élményt, különösen, ha információgyűjtésről van szó. Az egyik legelterjedtebb űrlapelem a választógomb, amely lehetővé teszi a felhasználók számára, hogy egy beállítást válasszanak ki egy halmazból. Ebben az oktatóanyagban megvizsgáljuk, hogyan hozhatók létre vízszintesen és függőlegesen elhelyezett választógombok az Aspose.PDF for .NET használatával. Akár tapasztalt fejlesztő, akár csak kezdő, ez az útmutató lépésről lépésre végigvezeti Önt a folyamaton, biztosítva, hogy az egyes részeket egyértelműen megértse.

## Előfeltételek

Mielőtt belemerülne a kódba, meg kell felelnie néhány előfeltételnek:

1.  Aspose.PDF for .NET: Győződjön meg arról, hogy telepítve van az Aspose.PDF könyvtár. Letöltheti a[telek](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Egy fejlesztői környezet, ahol megírhatja és tesztelheti kódját.
3. Alapvető C# ismerete: A C# programozás ismerete segít jobban megérteni a kódrészleteket.

## Csomagok importálása

A kezdéshez importálnia kell a szükséges csomagokat a C# projektbe. A következőképpen teheti meg:

### Hozzon létre egy új projektet

Nyissa meg a Visual Studio-t, és hozzon létre egy új C#-projektet. Az egyszerűség kedvéért választhat egy konzolalkalmazást.

### Adja hozzá az Aspose.PDF hivatkozást

1. Kattintson a jobb gombbal a projektre a Solution Explorerben.
2. Válassza a "NuGet-csomagok kezelése" lehetőséget.
3. Keresse meg az "Aspose.PDF" kifejezést, és telepítse a legújabb verziót.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Most, hogy mindent beállított, bontsuk le a kódot vízszintesen és függőlegesen igazított rádiógombok létrehozásához.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Ebben a lépésben meghatározzuk annak a könyvtárnak az elérési útját, ahol a PDF-dokumentumok tárolásra kerülnek.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahová a PDF-fájlt menteni szeretné. Ez döntő fontosságú, mivel megmondja a programnak, hogy hol keresse a bemeneti fájlokat, és hova mentse a kimenetet.

## 2. lépés: Töltse be a meglévő PDF-dokumentumot

 Ezután be kell töltenünk a PDF dokumentumot, amellyel dolgozni fogunk. Ez a`FormEditor` osztály.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Itt létrehozunk egy példányt`FormEditor` és kösse össze egy létező nevű PDF fájlhoz`input.pdf`. Győződjön meg arról, hogy ez a fájl létezik a megadott könyvtárban.

## 3. lépés: Konfigurálja a rádiógomb tulajdonságait

Most állítsunk be néhány tulajdonságot a rádiógombokhoz. Ez magában foglalja a gombok közötti rést, a tájolásukat és a méretüket.

```csharp
formEditor.RadioGap = 4; // A rádiógomb opciói közötti távolság
formEditor.RadioHoriz = true; // Állítsa igazra a vízszintes igazításhoz
formEditor.RadioButtonItemSize = 20; // A rádiógomb mérete
formEditor.Facade.BorderWidth = 1; // Szegély szélessége
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Szegély színe
```

 Ezek a tulajdonságok segítenek meghatározni, hogy a választógombok hogyan jelenjenek meg a PDF-ben. A`RadioGap` tulajdonság szabályozza a gombok közötti teret, míg`RadioHoriz` meghatározza az elrendezésüket.

## 4. lépés: Adjon hozzá vízszintes rádiógombokat

Most adjuk hozzá a vízszintes választógombokat a PDF-hez.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 Ebben a kódban meghatározzuk a választógombok elemeit, és hozzáadjuk őket a PDF-hez. A`AddField`metódus számos paramétert vesz igénybe, beleértve a mező típusát, a mező nevét és az elhelyezés koordinátáit.

## 5. lépés: Adjon hozzá függőleges rádiógombokat

Ezután hozzáadjuk a függőleges rádiógombokat. Ehhez vissza kell állítanunk a tájolást függőlegesre.

```csharp
formEditor.RadioHoriz = false; // Állítsa false értékre a függőleges igazításhoz
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Csakúgy, mint korábban, itt is meghatározzuk az elemeket, és hozzáadjuk őket a PDF-hez, de ezúttal függőlegesen lesznek igazítva.

## 6. lépés: Mentse el a PDF-dokumentumot

Végül el kell mentenünk a módosított PDF dokumentumot.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Ez a kód elmenti a PDF-fájlt az újonnan hozzáadott választógombokkal. Ügyeljen arra, hogy ellenőrizze a kimeneti fájl megadott könyvtárát.

## Következtetés

A választógombok létrehozása PDF-ben az Aspose.PDF for .NET használatával egyszerű folyamat. Az oktatóanyagban ismertetett lépések követésével könnyedén hozzáadhat vízszintesen és függőlegesen igazított választógombokat PDF-űrlapjaihoz. Ez nemcsak a dokumentumok interaktivitását javítja, hanem az általános felhasználói élményt is. Szóval, hajrá, és próbáld ki!

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok programozott létrehozását, kezelését és konvertálását.

### Használhatom ingyenesen az Aspose.PDF-et?
 Igen, az Aspose ingyenes próbaverziót kínál, amellyel értékelheti a könyvtárat. Letöltheti[itt](https://releases.aspose.com/).

### Hogyan kaphatok támogatást az Aspose.PDF fájlhoz?
 Támogatást kaphat, ha ellátogat a[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Lehetséges más űrlapelemeket létrehozni az Aspose.PDF segítségével?
Teljesen! Az Aspose.PDF különféle űrlapelemeket támogat, beleértve a szövegmezőket, jelölőnégyzeteket és legördülő listákat.

### Hol vásárolhatom meg az Aspose.PDF-et .NET-hez?
 Az Aspose.PDF for .NET a következő webhelyről vásárolható meg[vásárlási oldal](https://purchase.aspose.com/buy).