---
title: Állítsa be a kiemelés tulajdonságát a PDF-fájlban
linktitle: Állítsa be a kiemelés tulajdonságát a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthatja be a Kiemelés tulajdonságait PDF-fájlban az Aspose.PDF for .NET használatával. Testreszabhatja a kommentárokat kiemelő sorokkal, szövegszínnel és befejezési stílusokkal.
type: docs
weight: 130
url: /hu/net/annotations/setcalloutproperty/
---
 Az Aspose.PDF for .NET egy hatékony könyvtár PDF-dokumentumok létrehozásához, kezeléséhez és konvertálásához C# nyelven. Ennek a könyvtárnak az egyik szolgáltatása a PDF-dokumentumok szabad szöveges megjegyzéseinek kiemelési tulajdonságainak megadása. Ezt a`FreeTextAnnotation` osztály, amely lehetővé teszi feliratok létrehozását kiemelésekkel.

Ebben az oktatóanyagban végigvezetjük Önt egy szabad szöveges annotáció kiemelési tulajdonságainak beállításán az Aspose.PDF for .NET segítségével C# nyelven. A kezdéshez kövesse az alábbi lépéseket.

## Telepítse az Aspose.PDF fájlt .NET-hez

 Ha még nem tette meg, akkor meg kell tennie[Letöltés](https://releases.aspose.com/pdf/net/) és telepítse az Aspose.PDF for .NET fájlt az Aspose Releasesből vagy a NuGet csomagkezelőn keresztül.

## 1. lépés: Hozzon létre egy új PDF-dokumentumot

 Hozzon létre egy új PDF dokumentumot a`Document`osztályt az Aspose.PDF biztosítja a .NET számára.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2. lépés: Új oldal hozzáadása a dokumentumhoz

 Új oldal hozzáadása a dokumentumhoz a gombbal`Pages` gyűjteménye a`Document` osztály.

```csharp
Page page = doc.Pages.Add();
```

## 3. lépés: Állítsa be az alapértelmezett megjelenést

 Állítsa be a szabad szöveges kommentár alapértelmezett megjelenését egy új létrehozásával`DefaultAppearance` objektum és tulajdonságainak beállítása, mint pl`TextColor` és`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## 4. lépés: Hozzon létre ingyenes szöveges megjegyzést kiemeléssel

 Hozzon létre egy új szabad szöveges kommentárt kiemeléssel a segítségével`FreeTextAnnotation` osztály. Állítsa be a`Intent` tulajdonát`FreeTextIntent.FreeTextCallout` annak megadásához, hogy ez egy kiemelő megjegyzés. Állítsa be a`EndingStyle` tulajdonát`LineEnding.OpenArrow` a kiemelés végén lévő nyíl stílusának megadásához. Állítsa be a`Callout` ingatlan egy tömbjéhez`Point` objektumok, amelyek az oldal azon pontjait képviselik, ahol a kiemelő vonalat meg kell húzni.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## 5. lépés: Adja hozzá a szabad szöveges megjegyzést az oldalhoz

 Adja hozzá a szabad szöveges kommentárt az oldalhoz a segítségével`Annotations` gyűjteménye a`Page` osztály.

```csharp
page.Annotations.Add(fta);
```

## 6. lépés: Adjon hozzá szöveget a megjegyzéshez

 Adjon hozzá szöveget a megjegyzéshez a`RichText`tulajdonság egy formázott XML karakterláncra. Ebben az oktatóanyagban a szöveg színét pirosra, a betűméretet pedig 9-re állítjuk.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF
```

## 7. lépés: mentse a dokumentumot

Most mentse a dokumentumot a következő kóddal:

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### Példa forráskódra a Set Callout Property fájlhoz az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">Ez egy minta</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan állíthatunk be kiemelési tulajdonságokat egy szabad szöveges megjegyzéshez PDF-dokumentumban az Aspose.PDF for .NET használatával. A kiemelő megjegyzések hasznosak a dokumentum bizonyos területeivel kapcsolatos további információk vagy magyarázatok biztosítására. Az Aspose.PDF for .NET a szolgáltatások és képességek széles skáláját kínálja a PDF-fájlokkal való munkavégzéshez, beleértve a megjegyzések, például feliratok létrehozását és testreszabását. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával a fejlesztők könnyedén implementálhatnak kiemelő megjegyzéseket PDF-dokumentumaikba, javítva dokumentumaik használhatóságát és átláthatóságát. Az Aspose.PDF for .NET egy sokoldalú és megbízható könyvtár a .NET-alkalmazások PDF-műveleteihez, amely hatékony eszközöket kínál különféle PDF-ekkel kapcsolatos feladatok hatékony kezelésére.

### GYIK a kiemelési tulajdonság beállításához PDF-fájlban

#### K: Mi az a feliratozás a PDF-dokumentumban?

V: A PDF-dokumentumban található kiemelő megjegyzés egy olyan megjegyzéstípus, amely lehetővé teszi egy szövegdoboz létrehozását, amelyben egy vezérvonal mutat a dokumentum egy adott területére. Általában a dokumentum egy adott szakaszához vagy eleméhez kapcsolódó további információk vagy megjegyzések biztosítására használják.

#### K: Testreszabhatom a kiemelő megjegyzés megjelenését az Aspose.PDF for .NET használatával?

V: Igen, testreszabhatja a kiemelő megjegyzés különféle tulajdonságait, például a színt, a betűméretet, a szövegigazítást, a vonalstílust, a nyílstílust stb.

#### K: Hogyan adhatok hozzá szöveget a kiemelő megjegyzéshez?

 V: Ha szöveget szeretne hozzáadni a kiemelő megjegyzéshez, beállíthatja a`RichText` tulajdona a`FreeTextAnnotation` tárgy. A`RichText` A tulajdonság egy formázott XML-karakterláncot vesz fel, amely a kiemelés megjegyzésében megjelenítendő szöveget képviseli.

#### K: Hozzáadhatok több kiemelő megjegyzést egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával?

 V: Igen, több kiemelő megjegyzést is létrehozhat egy PDF-dokumentumban, ha több példányt hoz létre a`FreeTextAnnotation`objektumot, és hozzáadhatja azokat a dokumentum különböző oldalaihoz vagy helyeihez.