---
title: Szegély kibontása PDF fájlból
linktitle: Szegély kibontása PDF fájlból
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan vonhat ki szegélyeket egy PDF-fájlból, és hogyan mentheti el őket képként az Aspose.PDF for .NET segítségével. Lépésről lépésre útmutató kódmintákkal és tippekkel a sikerhez.
type: docs
weight: 80
url: /hu/net/programming-with-tables/extract-border/
---
## Bevezetés

Amikor PDF-ekkel dolgozik, bizonyos elemek, például szegélyek vagy grafikus útvonalak kinyerése ijesztő feladatnak tűnhet. Az Aspose.PDF for .NET segítségével azonban könnyedén kivonhatja a szegélyeket vagy alakzatokat egy PDF-fájlból, és képként mentheti őket. Ebben az oktatóanyagban belevetjük magunkat a szegély PDF-ből való kivonásához és PNG-képként való mentéséhez. Készüljön fel arra, hogy átvegye PDF-je grafikus tartalmát!

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy mindent beállított:

1.  Aspose.PDF for .NET: Ha még nem telepítette az Aspose.PDF könyvtárat, megteheti[töltse le itt](https://releases.aspose.com/pdf/net/). A licencet is alkalmaznia kell, akár az ingyenes próbaverzióval, akár egy megvásárolt licenccel.
2. IDE beállítása: Állítson be egy C#-projektet a Visual Studióban vagy bármely más .NET IDE-ben. Győződjön meg arról, hogy hozzáadta a szükséges hivatkozásokat az Aspose.PDF könyvtárhoz.
3. PDF-fájl bevitele: Készítsen PDF-fájlt, amelyből kivonhatja a szegélyeket. Ez az oktatóanyag egy nevű fájlra hivatkozik`input.pdf`.

## A szükséges csomagok importálása

Kezdjük a szükséges névterek importálásával. Ezek a csomagok biztosítják a PDF-tartalom kezeléséhez szükséges eszközöket.

```csharp
using System.IO;
using System;
using System.Drawing.Drawing2D;
using System.Drawing.Imaging;
using System.Collections;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

Most, hogy az alapokkal foglalkoztunk, térjünk át a lépésről lépésre szóló útmutatóra, ahol a kód minden egyes részét lebontjuk, hogy részletesen elmagyarázzuk.


## 1. lépés: A PDF-dokumentum betöltése

Az első lépés a kibontandó szegélyt tartalmazó PDF dokumentum betöltése. Gondolj úgy, mintha kinyitnál egy könyvet, mielőtt elkezdesz olvasni – hozzá kell férned a tartalomhoz!

 Kezdjük azzal, hogy megadjuk a könyvtárat, ahol a PDF-fájl tárolva van, és betöltjük a dokumentumot a segítségével`Aspose.Pdf.Document` osztály.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

 Ez a kód betölti a`input.pdf` fájlt a megadott könyvtárból. Győződjön meg arról, hogy a fájl elérési útja helyes, különben a fájl nem található hibaüzenetet kaphat.

## 2. lépés: A grafika és a bitkép beállítása

Mielőtt elkezdené a kibontást, létre kell hoznunk egy vásznat, amelyre rajzolhatunk. A .NET világában ez egy Bitmap és Graphics objektumok beállítását jelenti. A Bitmap a képet ábrázolja, a Graphics objektum pedig lehetővé teszi a PDF-ből kinyert alakzatok, például szegélyek rajzolását.

```csharp
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);
```

Íme egy bontás:
- A PDF első oldalának megfelelő méretű bittérképes képet készítünk.
- A GraphicsPath alakzatok (ebben az esetben szegélyek) meghatározására szolgál.
- A mátrix meghatározza a grafika átalakításának módját; szükségünk van egy inverziós mátrixra, mert a PDF és a .NET eltérő koordinátarendszerrel rendelkezik.

## 3. lépés: A PDF-tartalom feldolgozása


A PDF-fájl rajzparancsok sorozata, és mindegyik parancsot fel kell dolgoznunk a határinformációk azonosításához és kibontásához.

```csharp
foreach (Operator op in doc.Pages[1].Contents)
{
    // Parancsok feldolgozása, például állapot mentése/visszaállítása, vonalak rajzolása, alakzatok kitöltése stb.
}
```

A kód végigfut minden rajzoperátoron a PDF tartalomfolyamában. Mindegyik operátor egy vonalat, téglalapot vagy más grafikus utasítást jelenthet.

## 4. lépés: PDF-kezelők kezelése

A PDF-fájl minden operátora egy-egy műveletet vezérel. A szegély kibontásához olyan parancsokat kell azonosítanunk, mint a „mozgatás ide”, „sor ide” és „téglalap rajzolása”. A következő operátorok kezelik ezeket a műveleteket:

- MoveTo: A kurzort egy kezdőpontra mozgatja.
- LineTo: vonalat húz az aktuális ponttól egy új pontig.
- Re: Rajzol egy téglalapot (ez lehet a szegély része).

```csharp
Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;

if (opMoveTo != null)
{
    lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
    System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
    graphicsPath.AddLine(lastPoint, linePoint);
    lastPoint = linePoint;
}
else if (opRe != null)
{
    System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
    graphicsPath.AddRectangle(re);
}
```

Ebben a lépésben:
- Minden megrajzolt vonalhoz vagy alakzathoz rögzítjük a pontokat.
- Téglalapokhoz (`opRe` ), közvetlenül hozzáadjuk őket a`graphicsPath`, amelyet később a határ meghúzásához használunk.

## 5. lépés: Rajzolja meg a határt

Miután azonosítottuk a szegélyt alkotó vonalakat és téglalapokat, ténylegesen rá kell rajzolnunk őket a Bitmap objektumra. Itt jön be a Graphics objektum.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
    gr.SmoothingMode = SmoothingMode.HighQuality;
    gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
}
```

- A bittérkép alapján létrehozunk egy grafikus objektumot.
- A SmoothingMode.HighQuality biztosítja, hogy szép sima képet kapjunk.
- Végül a DrawPath segítségével rajzoljuk meg a határt.

## 6. lépés: A kivont szegély mentése

Most, hogy kibontottuk a szegélyt, ideje elmenteni képfájlként. Ezzel a szegélyt PNG-ként menti el.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

- A bitkép PNG-képként kerül mentésre.
- Most megnyithatja ezt a képet a kivont szegély megtekintéséhez.

## Következtetés

A szegélyek kinyerése egy PDF-fájlból az Aspose.PDF for .NET használatával eleinte bonyolultnak tűnhet, de ha egyszer lebontja, ez egyszerűvé válik. A PDF-ben található rajzoperátorok megértésével és a hatékony .NET-könyvtárak használatával hatékonyan kezelheti és bonthatja ki a grafikus tartalmat. Ez az útmutató szilárd alapot nyújt a PDF-kezelés megkezdéséhez!

## GYIK

### Hogyan kezelhetek több oldalt a PDF-ben?  
 A dokumentum egyes oldalai között ismétléssel lépkedhet`doc.Pages` keménykódolás helyett`doc.Pages[1]`.

### Kivonhatok más elemeket, például szöveget, ugyanezzel a megközelítéssel?  
Igen, az Aspose.PDF gazdag API-kat biztosít a szövegek, képek és egyéb tartalmak PDF-fájlokból való kinyerésére.

### Hogyan kérhetek engedélyt a korlátozások elkerülése érdekében?  
 Megteheti[engedélyt alkalmazni](https://purchase.aspose.com/temporary-license/) keresztül töltve be`License` osztály által biztosított Aspose.

### Mi van, ha a PDF-emnek nincsenek határai?  
Ha a PDF-fájl nem tartalmaz látható szegélyeket, előfordulhat, hogy a grafikai kinyerési folyamat nem hoz eredményt. Győződjön meg arról, hogy a PDF-tartalom rajzolható szegélyeket tartalmaz.

### Elmenthetem a kimenetet nem PNG formátumban?  
 Igen, egyszerűen változtassa meg a`ImageFormat.Png` másik támogatott formátumra, mint pl`ImageFormat.Jpeg`.