---
title: Dátum és időbélyeg hozzáadása PDF-fájlhoz
linktitle: Dátum és időbélyeg hozzáadása PDF-fájlhoz
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan adhat hozzá dátum- és időbélyegzőt PDF-fájljaihoz az Aspose.PDF for .NET használatával. Tökéletes a dokumentumok hitelességének javítására.
type: docs
weight: 10
url: /hu/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## Bevezetés

Amikor a dokumentumok, különösen a PDF-ek kezeléséről van szó, a dátum- és időbélyegző hozzáadása komoly változást hozhat. Akár jogi dokumentumokon, projektjelentéseken vagy számlákon dolgozik, az időbélyeg nemcsak hitelességet ad, hanem egyértelműen rögzíti a dokumentum létrehozásának vagy módosításának időpontját is. Ebben az útmutatóban végigvezetjük a dátum- és időbélyegző PDF-fájlhoz való hozzáadásának folyamatán az Aspose.PDF .NET könyvtár használatával. 

Ez a cikk úgy lett megalkotva, hogy egyértelmű és könnyen követhető legyen, így még akkor is magabiztosan megvalósíthatja ezt a funkciót, ha még kezdő a programozásban vagy az Aspose.PDF könyvtárban. Merüljünk el!

## Előfeltételek

Mielőtt elkezdenénk, meg kell felelnie néhány előfeltételnek:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Itt kell írni és végrehajtani a kódot.
2. Aspose.PDF for .NET: Le kell töltenie és telepítenie kell az Aspose.PDF könyvtárat. Megtalálhatja a legújabb verziót[itt](https://releases.aspose.com/pdf/net/).
3. Alapvető C# ismeretek: A C# programozás ismerete segít jobban megérteni a példákat, de ne aggódjon, ha még csak most kezdi; mindent elmagyarázunk lépésről lépésre.
4.  PDF-fájl: Készítsen egy minta PDF-fájlt. Példánkban egy nevű fájlt fogunk használni`AddTextStamp.pdf`.

Ha ezekkel az előfeltételekkel rendelkezik, készen áll arra, hogy dátum- és időbélyegzőket adjon PDF-fájljaihoz!

## Csomagok importálása

A kezdéshez importálnia kell a szükséges névtereket a C# projektbe. Íme, hogyan kell csinálni:

### Hozzon létre egy új projektet

1. A Visual Studio megnyitása: Indítsa el a Visual Studio alkalmazást.
2. Új projekt létrehozása: A kezdőképernyőn válassza az „Új projekt létrehozása” lehetőséget.
3. Válassza a Konzolalkalmazást: Válassza a „Konzolalkalmazás (.NET-keretrendszer)” lehetőséget a projektsablonok listájából.
4.  Nevezze el projektjét: Adjon nevet a projektnek, például`PDFDateTimeStamp`.

### Adja hozzá az Aspose.PDF hivatkozást

1. Kattintson a jobb gombbal a Referenciákra: A Solution Explorerben kattintson jobb gombbal a projekt „References” mappájára.
2. Válassza a „Referencia hozzáadása” lehetőséget: Válassza a „Hivatkozás hozzáadása” lehetőséget a helyi menüből.
3. Keresse meg az Aspose.PDF fájlt: Navigáljon arra a helyre, ahonnan letöltötte az Aspose.PDF fájlt, és válassza ki. Kattintson az „OK” gombra, hogy hozzáadja a projekthez.

### Importálja a szükséges névtereket

 A te tetején`Program.cs` fájlt, importálnia kell a következő névtereket:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

Most, hogy mindent beállítottunk, bontsuk le a dátum- és időbélyegző PDF-fájlhoz adásának folyamatát egyértelmű, kezelhető lépésekre.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Először is meg kell adnia a könyvtárat, ahol a PDF-fájl található. Ez döntő fontosságú, mert a kód ebben a könyvtárban keresi a PDF-fájlt.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Cserélje ki a tényleges útvonalat
```

 Ügyeljen arra, hogy cserélje ki`YOUR DOCUMENT DIRECTORY` a PDF-fájl tényleges elérési útjával.

## 2. lépés: Nyissa meg a PDF-dokumentumot

Ezután nyissa meg azt a PDF-dokumentumot, amelyhez hozzá szeretné adni az időbélyeget. 

```csharp
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Ez a kódsor inicializálja a`Document` osztályba, és betölti a PDF-fájlt a`pdfDocument` objektum.

## 3. lépés: Hozza létre a dátum-időbélyeget

Most itt az ideje létrehozni a dátum- és időbélyegzőt. Meg kell formázni, hogy meghatározott módon jelenjen meg. 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

 Itt,`DateTime.Now` lekéri az aktuális dátumot és időt, és`ToString` formázza a kívánt formátumra.

## 4. lépés: Hozzon létre egy szövegbélyeget

Ha készen áll a dátum- és időkarakterlánc, létrehozhat egy szövegbélyeget, amely hozzáadódik a PDF-hez.

```csharp
// Szöveges bélyegző létrehozása
TextStamp textStamp = new TextStamp(annotationText);
```

 Ez a sor új példányt hoz létre a`TextStamp` a formázott dátum és idő karakterlánc használatával.

## 5. lépés: Állítsa be a bélyegző tulajdonságait

Testreszabhatja a bélyegző megjelenését és helyzetét. A következőképpen állíthatja be a tulajdonságait:

```csharp
// Állítsa be a bélyegző tulajdonságait
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Ebben a lépésben beállítjuk a margókat, és a bélyegzőt a PDF-oldal jobb alsó sarkához igazítjuk.

## 6. lépés: Adja hozzá a bélyegzőt a PDF-hez

Itt az ideje, hogy hozzáadja a szövegbélyeget a PDF-dokumentumhoz. 

```csharp
// Bélyegző hozzáadása a bélyeggyűjteményhez
pdfDocument.Pages[1].AddStamp(textStamp);
```

Ez a sor hozzáadja a bélyeget a PDF első oldalához. Megváltoztathatja az oldalszámot, ha másik oldalra szeretné helyezni.

## 7. lépés: Hozzon létre egy szabad szöveges megjegyzést (opcionális)

Ha megjegyzést szeretne adni a bélyegzőhöz, létrehozhat egy`FreeTextAnnotation` alábbiak szerint:

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

Ez az opcionális lépés egy szabad szöveges megjegyzést hoz létre, amely további kontextust vagy információkat nyújthat a bélyegzőről.

## 8. lépés: Állítsa be a megjegyzésszegélyt

Ha testre szeretné szabni a kommentár szegélyét, ezt is megteheti:

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Ez a kódrészlet 0-ra állítja a szegély szélességét, így láthatatlanná teszi, és hozzáadja a megjegyzést a PDF-hez.

## 9. lépés: Mentse el a PDF-dokumentumot

Végül el kell mentenie a módosított PDF dokumentumot. 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; // Adja meg a kimeneti fájl nevét
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

Ez a sor új fájlba menti a hozzáadott időbélyeggel ellátott PDF-fájlt. A kimenet megtekintéséhez ellenőrizheti a megadott könyvtárat.

## Következtetés

Gratulálok! Sikeresen hozzáadott egy dátum- és időbélyeget egy PDF-fájlhoz az Aspose.PDF for .NET használatával. Ezzel az egyszerű, de hatékony funkcióval javíthatja dokumentumait, professzionálisabbá teheti azokat, és egyértelműen rögzítheti, mikor készültek vagy módosítottak. 

## GYIK

### Testreszabhatom a dátumformátumot az időbélyegzőben?
 Igen, módosíthatja a`ToString`módszert a dátumformátum tetszés szerinti módosításához.

### Ingyenesen használható az Aspose.PDF?
 Az Aspose.PDF ingyenes próbaverziót kínál, de a teljes funkciók használatához licencet kell vásárolnia. Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).

### Hozzáadhatok több időbélyeget egy PDF-hez?
 Teljesen! Többet is létrehozhat`TextStamp` példányokat, és adja hozzá őket a PDF különböző oldalaihoz vagy pozícióihoz.

### Mi van, ha nincs Visual Studio?
Bármilyen C# IDE-t vagy szövegszerkesztőt használhat, de a projekt futtatásához és hibakereséséhez a Visual Studio ajánlott.

### Hol találok további példákat az Aspose.PDF használatára?
 További példákat és oktatóanyagokat fedezhet fel a[Aspose.PDF dokumentáció](https://reference.aspose.com/pdf/net/).