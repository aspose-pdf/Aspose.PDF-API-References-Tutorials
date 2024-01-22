---
title: PDF-jegyzet hozzáadása
linktitle: Megjegyzés hozzáadása
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá szöveges PDF-annotációkat az Aspose.PDF for .NET segítségével ezzel a C#-forráskóddal. Testreszabhatja kommentárjait konkrét részletekkel és ikonokkal.
type: docs
weight: 10
url: /hu/net/annotations/addannotation/
---
A megjegyzések hozzáadása a PDF-dokumentumokhoz hatékony funkció, amely javíthatja az együttműködést és az ellenőrzési folyamatokat. Az Aspose.PDF for .NET megkönnyíti a megjegyzések programozott hozzáadását PDF-dokumentumokhoz C# használatával. Ebben az útmutatóban lépésről lépésre elmagyarázzuk, hogyan használhatja az Aspose.PDF-et .NET-hez megjegyzések hozzáadásához egy PDF-dokumentumhoz.

## 1. lépés: Hozzon létre egy új projektet, és telepítse az Aspose.PDF fájlt a .NET számára

Mielőtt elkezdené írni a megjegyzések hozzáadásához szükséges kódot, létre kell hoznunk egy új projektet, és telepítenünk kell az Aspose.PDF-et .NET-hez. Az Aspose.PDF for .NET telepítéséhez kövesse az alábbi lépéseket:

1. Nyissa meg a Visual Studio-t, és hozzon létre egy új C#-projektet.
2. Kattintson a jobb gombbal a projektre a Solution Explorerben, és válassza a "NuGet-csomagok kezelése" lehetőséget.
3. Keresse meg az "Aspose.PDF" elemet, és válassza az "Install" lehetőséget.

telepítés befejezése után elkezdhetjük a kód írását.

## 2. lépés: Nyissa meg a PDF-dokumentumot

A megjegyzések hozzáadásának első lépése a PDF-dokumentum megnyitása. A dokumentum megnyitásához a következő kódot használhatjuk:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Ebben a kódban adjuk meg a megnyitni kívánt PDF dokumentum elérési útját. Ügyeljen arra, hogy az „ADATKÖNYVTÁR” szöveget az adatkönyvtár tényleges elérési útjára cserélje.

## 3. lépés: Hozza létre a megjegyzést

 Annotáció hozzáadásához létre kell hoznunk egy új példányt a`TextAnnotation` osztály. A következő kóddal új szöveges megjegyzést hozhatunk létre:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Ebben a kódban egy új szöveges megjegyzést hozunk létre a PDF dokumentum második oldalán. Beállítjuk a kommentár címét, tárgyát, állapotát, tartalmát, megnyitását és ikonjait is.

## 4. lépés: A kommentár testreszabása

 Az annotáció megjelenését testreszabhatjuk a`Border` osztály. A következő kóddal testreszabhatjuk a kommentár szegélyét:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Ebben a kódban létrehozunk egy újat`Border`objektumot, és állítsa be a szélesség és a kötőjel tulajdonságait. Ezután beállítottuk a`Border` a megjegyzés tulajdonsága az újhoz`Border` tárgy. Végül beállítottuk a`Rect` az annotáció tulajdonsága, hogy megadja a pozícióját és méretét.

## 5. lépés: Adja hozzá a megjegyzést a PDF-dokumentumhoz

Miután elkészítettük és testreszabtuk a megjegyzést, hozzá kell adnunk a PDF dokumentumhoz. A következő kóddal hozzáadhatjuk a megjegyzést a PDF dokumentumhoz:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Ebben a kódban hozzáadjuk a megjegyzést a PDF dokumentum második oldalának megjegyzésgyűjteményéhez.

## 6. lépés: Mentse el a kimeneti fájlt

Végül el kell mentenünk a PDF dokumentumot a hozzáadott megjegyzéssel. A kimeneti fájl mentéséhez a következő kódot használhatjuk:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Példa forráskód a megjegyzések hozzáadásához az Aspose.PDF használatával .NET-hez


```csharp   
 // A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DATA DIRECTORY";

// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Jegyzet létrehozása
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Adjon hozzá megjegyzést az oldal kommentárgyűjteményéhez
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Mentse a kimeneti fájlt
pdfDocument.Save(dataDir);
```
Ez a kód bemutatja, hogyan adhat hozzá szöveges megjegyzést meghatározott címmel, témával, állapottal, tartalommal és ikonnal egy PDF-oldalhoz az Aspose.PDF for .NET használatával. Ezt a kódot módosíthatja a PDF-dokumentumokhoz való megjegyzésekkel kapcsolatos igényei szerint. Csak ne felejtse el lecserélni AZ ADATKÖNYVTÁRA a tényleges könyvtár elérési útját, ahol a PDF-fájl található, és ahová menteni szeretné a kimeneti fájlt.

## Következtetés

Megjegyzések hozzáadása PDF-dokumentumokhoz az Aspose.PDF for .NET használatával értékes eszközt kínál a dokumentumokkal való együttműködés és a felülvizsgálati folyamatok javítására. Az ebben a cikkben található, lépésenkénti útmutatót követve a fejlesztők zökkenőmentesen integrálhatják a jegyzetelési képességeket C# alkalmazásaikba.

### GYIK

#### K: Milyen típusú megjegyzések adhatók hozzá az Aspose.PDF for .NET használatával?

V: Az Aspose.PDF for .NET különféle típusú megjegyzéseket támogat, beleértve a szöveges megjegyzéseket, bélyegzőket, hivatkozásokat, alakzatokat és egyebeket. A fejlesztők saját igényeiknek megfelelően testreszabhatják ezeknek a megjegyzéseknek a megjelenését és tulajdonságait.

#### K: Hozzáadhatok megjegyzéseket egy többoldalas PDF-dokumentum bizonyos oldalaihoz?

V: Igen, az Aspose.PDF for .NET lehetővé teszi, hogy meghatározza azt az oldalt, amelyhez a megjegyzést hozzá kívánja adni. Igény szerint kiválaszthat egy adott oldalt, vagy több oldalhoz is hozzáadhat megjegyzéseket.

#### K: Hogyan szabhatom testre a kommentárok megjelenését?

V: A megjegyzések testreszabhatók olyan tulajdonságokkal, mint a szegély szélessége, színe, kötőjelstílusa, szövegstílusa stb. Az Aspose.PDF for .NET opciók gazdag készletét kínálja a megjegyzések megjelenésének testreszabásához.

#### K: Lehetséges-e hiperhivatkozásokat annotációként hozzáadni az Aspose.PDF for .NET használatával?

V: Igen, az Aspose.PDF for .NET használatával hiperhivatkozásokat annotációként adhat hozzá PDF-dokumentumokhoz. A hiperhivatkozás-jegyzetek külső URL-ekre vagy ugyanazon a dokumentumon belüli meghatározott helyekre hivatkozhatnak.

#### K: Lehet-e megjegyzéseket hozzáadni a meglévő PDF-dokumentumokhoz az eredeti tartalom megváltoztatása nélkül?

V: Igen, az Aspose.PDF for .NET megjegyzéseket ad hozzá további elemként anélkül, hogy megváltoztatná a PDF-dokumentum eredeti tartalmát. Az eredeti PDF-tartalom érintetlen marad.