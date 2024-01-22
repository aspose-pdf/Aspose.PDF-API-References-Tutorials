---
title: lnk Annotation Line Width
linktitle: lnk Annotation Line Width
second_title: Aspose.PDF for .NET API Reference
description: Ez a cikk lépésről lépésre nyújt útmutatót az lnk-annotáció vonalszélességének beállításához az Aspose.PDF for .NET használatával.
type: docs
weight: 110
url: /hu/net/annotations/lnkannotationlinewidth/
---
Az Aspose.PDF egy hatékony és széles körben használt eszköz a PDF-fájlokkal való munkavégzéshez .NET-alkalmazásokban. Számos funkciót biztosít PDF-fájlok létrehozásához, szerkesztéséhez és kezeléséhez, beleértve a megjegyzések hozzáadását az oldalakhoz. Ebben az oktatóanyagban elmagyarázzuk, hogyan lehet beállítani egy hivatkozási megjegyzés vonalszélességét az Aspose.PDF for .NET használatával.

Ha megvannak ezek az előfeltételek, hozzon létre egy új konzolalkalmazás-projektet a Visual Studióban. Ezután adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz. Ehhez kattintson a jobb gombbal a projektre a Solution Explorerben, válassza ki a „NuGet-csomagok kezelése” lehetőséget, és keresse meg az „Aspose.PDF” kifejezést a NuGet Package Managerben.

Ha lnk-jegyzetet szeretne hozzáadni egy PDF-dokumentumhoz, kövesse az alábbi lépéseket:

##  1. lépés: Hozzon létre egy újat`Document` object.
```csharp
Document doc = new Document();
```
## 2. lépés: Új oldal hozzáadása a dokumentumhoz.
```csharp
doc.Pages.Add();
```
##  3. lépés: Hozzon létre egy listát`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  4. lépés: Hozzon létre egy újat`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  5. lépés: Hozzon létre egy újat`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## 6. lépés: Adja hozzá a mozdulatot a tintamozdulatok listájához.
```csharp
inkList.Add(gesture);
```
##  7. lépés: Hozzon létre egy újat`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## 8. lépés: Állítsa be a megjegyzés tárgyát és címét.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## 9. lépés: Állítsa be a megjegyzés színét.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  10. lépés: Hozzon létre egy újat`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## 11. lépés: Adja hozzá a megjegyzést az oldalhoz.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## 12. lépés: Mentse el a dokumentumot fájlba.
```csharp
// Mentse a kimeneti fájlt
doc.Save(dataDir);


```
### A példa az lnk Annotation Line Width-et mutatja Aspose.PDF-el .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Mentse a kimeneti fájlt
doc.Save(dataDir);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet beállítani egy hivatkozási megjegyzés vonalszélességét egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Az Aspose.PDF for .NET eszközök és szolgáltatások széles skáláját kínálja a PDF-dokumentumokkal való munkavégzéshez, beleértve a hivatkozási megjegyzések létrehozásának és testreszabásának lehetőségét. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával a fejlesztők könnyen hozzáadhatnak interaktív hivatkozásokat PDF dokumentumaikhoz, javítva ezzel a felhasználói élményt és alkalmazásaik interaktivitását. Az Aspose.PDF for .NET egy sokoldalú könyvtár, amely képessé teszi a .NET fejlesztőket arra, hogy hatékonyan és eredményesen dolgozzanak PDF fájlokkal.

### GYIK

#### K: Mi az a hivatkozási megjegyzés a PDF-dokumentumban?

V: A PDF-dokumentumban található hivatkozási megjegyzés olyan interaktív elem, amely lehetővé teszi olyan hiperhivatkozások vagy műveletek létrehozását, amelyek a felhasználót ugyanazon a dokumentumon belül, egy külső webhelyen vagy egy másik PDF-dokumentumban egy másik helyre irányítják.

#### K: Hogyan állíthatom be egy hivatkozási megjegyzés vonalszélességét az Aspose.PDF for .NET használatával?

V: A hivatkozási megjegyzés vonalszélességének beállításához az Aspose.PDF for .NET használatával, létrehozhat egy`InkAnnotation` objektumot, és adja meg a vonalszélesség tulajdonságot.

#### K: Milyen tulajdonságok szabhatók testre egy hivatkozási megjegyzéshez az Aspose.PDF for .NET-ben?

V: Az Aspose.PDF for .NET-ben található hivatkozási megjegyzések különféle tulajdonságait testreszabhatja, például helyét, méretét, színét, szegély tulajdonságait (szélesség, stílus, szaggatott minta és hatás), tárgyat, címet és láthatóságot.

#### K: Létrehozhatok több tintamozdulatot tartalmazó hivatkozási megjegyzést?

 V: Igen, több tintamozdulatot tartalmazó hivatkozási megjegyzést is létrehozhat több hozzáadásával`Point` tömbök a`InkAnnotation` tárgy.

#### K: Hogyan adhatok hivatkozás megjegyzést a PDF-dokumentum egy adott oldalához?

 V: Ha hivatkozás megjegyzést szeretne hozzáadni a PDF dokumentum egy adott oldalához, meg kell adnia az oldalszámot a dokumentum létrehozásakor.`InkAnnotation` tárgy. Például,`new InkAnnotation(doc.Pages[1], ...)` hozzáadja a hivatkozás megjegyzését az első oldalhoz.