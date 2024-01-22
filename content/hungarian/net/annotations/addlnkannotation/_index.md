---
title: Lnk megjegyzés hozzáadása
linktitle: Lnk megjegyzés hozzáadása
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá Ink Annotation funkciót PDF dokumentumokhoz C# nyelven az Aspose.PDF for .NET használatával, lépésről lépésre útmutatóval és teljes forráskóddal.
type: docs
weight: 20
url: /hu/net/annotations/addlnkannotation/
---
Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy különféle PDF-műveleteket hajtsanak végre. Az egyik ilyen művelet az Ink Annotation hozzáadása a PDF-dokumentumokhoz. Ebben a cikkben egy lépésről lépésre ismertetjük a C# forráskódot az Aspose.PDF for .NET használatával történő Ink Annotation hozzáadásához. Kezdjük el!

## Az Aspose.PDF tintajelölési funkciójának megismerése .NET-hez

Mielőtt belemerülnénk a C# forráskódba, először értsük meg, mi az az Ink Annotation, és mi a felhasználása.

Az Ink Annotation egy módja annak, hogy szabad formájú tintajelöléseket rajzoljon PDF dokumentumokra. Lehetővé teszi megjegyzések készítését érintőceruzával vagy egérrel. Ez a funkció olyan helyzetekben hasznos, amikor diagramokat, vázlatokat vagy más típusú megjegyzéseket kell rajzolnia.

## 1. lépés: Új dokumentum létrehozása

Az Ink Annotation PDF-dokumentumhoz való hozzáadásának első lépése a Dokumentum osztály új példányának létrehozása. Ez a következő kódrészlettel érhető el:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Itt létrehozzuk a Dokumentum osztály új példányát, és hozzáadunk egy új oldalt.

## 2. lépés: Tintajegyzet létrehozása

A következő lépés az InkAnnotation osztály példányának létrehozása. Ez a következő kódrészlettel történik:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Itt először létrehozunk egy téglalapot a System.Drawing.Rectangle osztály segítségével, és a FromRect metódussal Aspose.Pdf.Rectangle-re alakítjuk. Ezután létrehozzuk az InkAnnotation osztály egy példányát a téglalap, a pontok listája és az oldal, amelyhez a megjegyzés hozzáadódik, felhasználásával.

Ezután beállítjuk az InkAnnotation különféle tulajdonságait, például a címet, a színt, a sapka stílusát, a keretet és az átlátszatlanságot. Végül az Annotations.Add metódussal hozzáadjuk az annotációt az oldalhoz.

## 3. lépés: A dokumentum mentése

Az utolsó lépés a PDF-dokumentum mentése a tintajegyzet hozzáadásával. Ez a következő kódrészlettel érhető el:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Itt összefűzzük a kimeneti fájl nevét az adatkönyvtárba, és elmentjük a dokumentumot a Mentés módszerrel.

### Példa forráskódra az Aspose.PDF használatával való tintafeljegyzés hozzáadásához .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Mentse a kimeneti fájlt
doc.Save(dataDir);
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan adhatunk tintajegyzeteket egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. A lépésenkénti útmutató és a mellékelt C# forráskód követésével a fejlesztők könnyedén implementálhatják az Ink Annotation funkciót PDF-feldolgozó alkalmazásaikba.

### GYIK

#### K: Mi az a tinta megjegyzés a PDF-dokumentumban?

V: A PDF-dokumentumban található tintajegyzetek lehetővé teszik a felhasználók számára, hogy szabad formájú tintajegyzeteket rajzoljanak ceruzával vagy egérrel. Gyakran használják kézzel rajzolt vázlatok, diagramok vagy más szabadkézi megjegyzések PDF-hez való hozzáadására.

#### K: Testreszabhatom a tintajegyzet megjelenését?

V: Igen, az Aspose.PDF for .NET különféle tulajdonságokat biztosít a tintajegyzet megjelenésének testreszabásához, például színt, átlátszatlanságot, sapkastílust, szegélyszélességet stb. A fejlesztők beállíthatják ezeket a tulajdonságokat, hogy megfeleljenek sajátos követelményeiknek.

#### K: Lehetséges több tintajegyzet hozzáadása egyetlen PDF-oldalhoz?

V: Igen, egyetlen PDF-oldalhoz több tintajegyzetet is hozzáadhat az Aspose.PDF for .NET használatával. Minden Ink Annotation saját pontkészlettel és testreszabott megjelenéssel rendelkezhet.

#### K: Hozzáadhatok tintajegyzeteket a meglévő PDF dokumentumokhoz?

V: Igen, az Aspose.PDF for .NET lehetővé teszi tintajegyzetek hozzáadását mind az újonnan létrehozott PDF-dokumentumokhoz, mind a meglévő PDF-fájlokhoz. Megnyithat egy meglévő PDF-fájlt, hozzáadhat tintajegyzeteket, és mentheti a frissített dokumentumot.

#### K: Melyek a leggyakoribb esetek a PDF-dokumentumok tintajegyzeteinek használatához?

V: A tintajegyzetek sokféle alkalmazáshoz hasznosak, beleértve az aláírások vagy kézzel írt megjegyzések PDF-űrlapokhoz való hozzáadását, az építészeti tervrajzok vagy mérnöki rajzok megjegyzéseit, valamint a dokumentumok közös áttekintéshez való jelölését.