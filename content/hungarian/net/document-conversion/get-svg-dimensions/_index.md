---
title: Szerezze be az SVG-méreteket
linktitle: Szerezze be az SVG-méreteket
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató az SVG-méretek megszerzéséhez az Aspose.PDF for .NET használatával.
type: docs
weight: 40
url: /hu/net/document-conversion/get-svg-dimensions/
---
## Bevezetés
Ebben az oktatóanyagban végigvezetjük az Aspose.PDF for .NET használatával SVG-fájlok méreteinek beszerzésének folyamatán. Az SVG (Scalable Vector Graphics) egy XML-alapú képformátum, amelyet vektorgrafikák ábrázolására használnak. Az alábbi lépésekkel lekérheti egy SVG-fájl méreteit, és elmentheti őket PDF-ként.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy megfelel a következő előfeltételeknek:

- C# programozási nyelv alapismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve a rendszerére.
- Fejlesztői környezet, például a Visual Studio.

## 1. lépés: SVG fájl betöltése
Ebben a lépésben betöltjük az SVG-fájlt az Aspose.PDF for .NET használatával. Kövesse az alábbi kódot:

```csharp
// A dokumentumok könyvtár elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` azzal a könyvtárral, ahol az SVG-fájl található.

## 2. lépés: Az oldalméret beállítása
Most, hogy betöltöttük az SVG-fájlt, beállíthatjuk az oldal méretét az SVG-tartalomhoz. Használja a következő kódot:

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

A fenti kód nullára állítja az oldalmargót, lehetővé téve az oldalméret beállítását az SVG-tartalom alapján.

## 3. lépés: Mentse el a kapott PDF fájlt
Az oldalméret beállítása után most már elmenthetjük az így létrejött PDF dokumentumot. Íme az utolsó lépés:

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a kívánt könyvtárral, ahová menteni szeretné a kimeneti PDF-fájlt.
  
### Példa forráskódra a Get SVG Dimensions használatához Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## Következtetés
Ebben az oktatóanyagban lépésről lépésre bemutatjuk az SVG-fájlok méreteinek meghatározását az Aspose.PDF for .NET használatával. A fent vázolt utasításokat követve most már képesnek kell lennie egy SVG-fájl méreteinek lekérésére és PDF formátumba mentésére. Ez a funkció akkor lehet hasznos, ha meg kell mérnie egy vektorgrafika méretét.

### GYIK

#### K: Mi az SVG?

V: Az SVG (Scalable Vector Graphics) egy XML-alapú képformátum, amelyet vektorgrafikák ábrázolására használnak. A raszteres képekkel ellentétben az SVG-fájlok felbontásfüggetlenek, és minőségromlás nélkül méretezhetők. Az SVG-t széles körben használják grafikák webes megjelenítésére, és könnyen szerkeszthető és kezelhető.

#### K: Miért használja az Aspose.PDF-et .NET-hez az SVG-ből PDF-be konvertálásához?

V: Az Aspose.PDF for .NET megbízható és hatékony módot biztosít az SVG-fájlok kezelésére és PDF formátumba konvertálására. Különféle lehetőségeket és beállításokat kínál az átalakítási folyamat testreszabásához, például az oldalméret, a margók és egyéb tulajdonságok módosítását a PDF-ben való pontos megjelenítés érdekében.

#### K: Átalakíthatom az összetett grafikát és szöveget tartalmazó SVG fájlokat?

V: Igen, az Aspose.PDF for .NET képes kezelni az összetett grafikát, szöveget és vektoros elemeket tartalmazó SVG fájlokat. Pontosan megőrzi az SVG tartalom részleteit és minőségét az átalakítási folyamat során, ami kiváló minőségű PDF dokumentumokat eredményez.

#### K: Kivonható-e szöveg az SVG-fájlokból az Aspose.PDF for .NET segítségével?

V: Igen, az Aspose.PDF for .NET lehetővé teszi az SVG-fájlok szövegének kinyerését. A könyvtár szövegkivonási funkcióival szöveges elemeket kinyerhet az SVG-ből, és külön mentheti el azokat további feldolgozás céljából.