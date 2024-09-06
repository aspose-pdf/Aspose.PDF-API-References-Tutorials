---
title: Töltse ki a körvonal szövegét PDF-fájlban
linktitle: Töltse ki a körvonal szövegét PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan lehet egyszerűen kitölteni és körvonalazni szöveget PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 90
url: /hu/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan töltsön ki és vázoljon fel szöveget PDF-fájlban az Aspose.PDF for .NET használatával. Megmutatjuk, hogyan használhatja a mellékelt C# forráskódot a kitöltési és körvonali színek alkalmazására a PDF-fájl szövegére.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A TextState objektum létrehozása

Az első lépés egy TextState objektum létrehozása a speciális tulajdonságok átadásához. Íme, hogyan:

```csharp
// Hozzon létre TextState objektumot a speciális tulajdonságok átviteléhez
TextState ts = new TextState();

// Állítsa be a körvonal színét
ts.StrokingColor = Color.Gray;

// Határozza meg a szövegmegjelenítési módot
ts.RenderingMode = TextRenderingMode.StrokeText;
```

A fenti kód egy új TextState objektumot hoz létre, és beállítja a körvonal színét, valamint a szöveg megjelenítési módját.

## 3. lépés: A PDF dokumentum betöltése

Most, hogy a TextState objektum készen áll, betölthetjük azt a PDF dokumentumot, ahol alkalmazni szeretnénk a szövegkitöltést és a körvonalat. Íme, hogyan:

```csharp
// Töltse be a PDF dokumentumot bemenetként
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

A fenti kód betölti a meglévő PDF-dokumentumot az Aspose.PDF.Facades könyvtár PdfFileStamp osztályával.

## 4. lépés: Adja hozzá a kitöltést és a körvonalakat a szöveghez

Most, hogy a PDF dokumentum betöltődött, hozzáadhatjuk a kitöltést és a körvonalat a szöveghez. Íme, hogyan:

```csharp
// Hozzon létre egy bélyeget (Bélyegző) a meghatározott szöveggel és tulajdonságokkal
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Kösse össze a TextState objektumot
stamp.BindTextState(ts);

// Állítsa be az X, Y eredetet
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// Adja hozzá a bélyegzőt a dokumentumhoz
fileStamp.AddStamp(stamp);
```

A fenti kód létrehoz egy pecsétet a megadott szöveggel és meghatározott kitöltés és körvonal tulajdonságokkal.

## 5. lépés: Mentse el a kimeneti dokumentumot

A szövegbélyegző hozzáadása után elmenthetjük a módosított PDF dokumentumot. Íme, hogyan:

```csharp
// Mentse el a módosított dokumentumot
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

A fenti kód a szerkesztett PDF dokumentumot a megadott könyvtárba menti.

### Minta forráskód a Fill Stroke Texthez az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Hozzon létre TextState objektumot a speciális tulajdonságok átviteléhez
TextState ts = new TextState();

// Állítsa be a körvonal színét
ts.StrokingColor = Color.Gray;

// Állítsa be a szövegmegjelenítési módot
ts.RenderingMode = TextRenderingMode.StrokeText;

// Töltsön be egy bemeneti PDF dokumentumot
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// Bind TextState
stamp.BindTextState(ts);

// Állítsa be az X,Y origót
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// Bélyegző hozzáadása
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## Következtetés

Gratulálok ! Megtanulta, hogyan lehet PDF-dokumentumban szöveget kitölteni és felvázolni az Aspose.PDF for .NET használatával. Mostantól ezt a tudást alkalmazhatja PDF-dokumentumaiban a kitöltési és körvonali színek testreszabásához.

### GYIK a kitöltési körvonal szövegéhez PDF-fájlban

#### K: Mit jelent a szöveg kitöltése és körvonalazása egy PDF-dokumentumban, és mikor kell erre?

V: A PDF-dokumentum szövegének kitöltése és körvonalazása azt jelenti, hogy színeket alkalmaznak a szövegkarakterek belsejében (kitöltés) és a szöveg körüli szegélyeken (körvonal). Ez felhasználható a szöveg vizuális megjelenésének javítására, hangsúlyok létrehozására vagy konkrét tartalom kiemelésére a PDF-ben.

#### K: Hogyan végzi el a mellékelt C# forráskód a szöveg kitöltését és körvonalazását egy PDF-fájlban?

 V: A mellékelt forráskód bemutatja, hogyan kell létrehozni a`TextState` objektumot a speciális szövegtulajdonságok, például a körvonal színe és a megjelenítési mód meghatározásához. Ezután az Aspose.PDF.Facades segítségével betölt egy meglévő PDF-dokumentumot, létrehoz egy bélyeget, amely tartalmazza a megadott kitöltési és körvonal-tulajdonságokkal rendelkező szöveget, és hozzáadja a bélyeget a dokumentumhoz.

####  K: Mi a célja a`TextState` object in the code?

 V: A`TextState`Az objektum speciális szövegtulajdonságok meghatározására szolgál, beleértve a szöveg körvonalának színét (körvonal) és a megjelenítési módot. Lehetővé teszi a szöveg megjelenésének testreszabását a körvonal és a kitöltés szempontjából.

#### K: Alkalmazhatok különböző kitöltési és körvonali színeket ugyanannak a szövegnek különböző részein?

 V: Igen, módosíthatja a kódot, hogy mást hozzon létre`TextState` objektumokat különálló kitöltési és körvonali színekkel, és alkalmazza őket a szöveg meghatározott részeire külön használatával`Stamp` tárgyakat.

#### K: Alkalmazhatok kitöltési és körvonali színeket a PDF-dokumentumban már szereplő szövegekre?

 V: Igen, hasonló elvek alapján alkalmazhat kitöltési és körvonali színeket a PDF-dokumentum meglévő szövegére úgy, hogy kiválasztja a megfelelő szövegobjektumokat, és hozzáadja azokat bélyegzőként a kívánt értékkel.`TextState` tulajdonságait.

#### K: Hogyan állíthatom be a kitöltött és vázolt szöveg átlátszatlanságát és keverését?

 V: A mellékelt kód segítségével beállíthatja a bélyeg átlátszatlanságát és keverési tulajdonságait a`Opacity` és`BlendingSpace`tulajdonságait, ill. Ezeket az értékeket módosíthatja a kívánt vizuális hatás eléréséhez.

#### K: Hogyan alkalmazhatok különböző kitöltési és körvonali színeket több bélyegzőre ugyanazon a PDF dokumentumon belül?

 V: Többet is létrehozhat`TextState` objektumok különböző kitöltési és körvonali színekkel, majd hozzon létre külön`Stamp` objektumok minden egyes szövegkészlethez különböző színekkel. Adja hozzá ezeket a bélyegzőket ugyanahhoz a PDF-dokumentumhoz a`PdfFileStamp` osztály.

#### K: Használhatok az Arialtól eltérő betűtípusokat a vázolt és kitöltött szöveghez?

 V: Igen, módosíthatja a betűtípust a betűtípusnév paraméter módosításával a`FormattedText` konstruktor a bélyeg létrehozásakor. Bármilyen, a rendszeren elérhető betűtípust használhat.

#### K: Hogyan módosíthatom a körvonalazott és kitöltött szöveg elforgatási szögét?

 V: A mellékelt kód lehetővé teszi a bélyegző elforgatási szögének beállítását a`Rotation` ingatlan. Ezzel a tulajdonsággal módosíthatja a szöveg kívánt elforgatási szögét.

#### K: Hogyan szabályozhatom a vázolt és kitöltött szöveg helyzetét és méretét az oldalon?

 V: Használhatja a`SetOrigin` módszere a`Stamp` objektumot a bélyeg oldali pozíciójának X és Y koordinátáinak beállításához. Ezenkívül beállíthatja a betűméretet a`FormattedText` konstruktorral szabályozhatja a szöveg méretét.