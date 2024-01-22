---
title: Lekerekített saroktábla PDF dokumentumban
linktitle: Lekerekített saroktábla PDF dokumentumban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre lekerekített sarkú táblázatot PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 190
url: /hu/net/programming-with-tables/rounded-corner-table/
---
Ebben az oktatóanyagban lépésről lépésre elvezetjük Önt egy lekerekített saroktáblázat létrehozásához PDF-dokumentumban az Aspose.PDF for .NET használatával. Elmagyarázzuk a megadott C# forráskódot, és megmutatjuk, hogyan kell megvalósítani.

## 1. lépés: A táblázat létrehozása
Először létrehozzuk a táblázatot a következő kóddal:

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 2. lépés: Lekerekített sarokstílus beállítása
Ezután konfiguráljuk a táblázat lekerekített sarok stílusát:

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## 3. lépés: A táblázat szegélyének beállítása
Ahhoz, hogy a táblázatnak lekerekített sarokszegélyt adjunk, létre kell hoznunk egy BorderInfo objektumot, és be kell állítani a megfelelő paraméterekkel:

```csharp
// Hozzon létre egy GraphInfo objektumot a keret színének beállításához
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

// Hozzon létre egy üres BorderInfo objektumot
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

// Állítsa a lekerekített szegély sugarát 15-re
bInfo.RoundedBorderRadius = 15;

// Alkalmazza a szegélyinformációkat a táblázatra
tab1.Border = bInfo;
```

### Példa forráskód a Rounded Corner Table-hoz az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
// Hozzon létre egy üres BorderInfo objektumot
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
// Állítson be egy kerekebb szegélyt, ahol a kör sugara 15
bInfo.RoundedBorderRadius = 15;
// Állítsa az asztal Sarok stílusát Kerekre.
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
// Állítsa be a táblázat határának információit
tab1.Border = bInfo;
```

## Következtetés
Gratulálok ! Most megtanulta, hogyan hozhat létre lekerekített saroktáblázatot PDF-dokumentumban az Aspose.PDF for .NET használatával. Ez a lépésről lépésre bemutatja, hogyan állíthatja be a lekerekített sarkok stílusát és az asztal szegélyét. Most már alkalmazhatja ezt a tudást saját projektjeihez.

### GYIK a lekerekített sarkú táblázathoz PDF dokumentumban

#### K: Testreszabhatom az asztal lekerekített sarkainak sugarát?

V: Igen, testreszabhatja a táblázat lekerekített sarkainak sugarát az érték módosításával`bInfo.RoundedBorderRadius` tulajdonság a megadott C# forráskódban. Egyszerűen állítsa be a kívánt sugárértéket (pontokban), hogy elérje a kívánt lekerekített sarok megjelenést.

#### K: Alkalmazhatok lekerekített sarkokat a táblázat egyes celláira?

V: Nem, a lekerekített sarokstílus a teljes asztal egészére vonatkozik. Az Aspose.PDF for .NET jelenleg nem nyújt beépített támogatást a táblázat egyes celláinak lekerekített sarkainak alkalmazásához.

#### K: Meg tudom változtatni a lekerekített sarokszegély színét?

 V: Igen, megváltoztathatja a lekerekített sarokszegély színét az érték módosításával`graph.Color` tulajdonság a C# forráskódban. Egyszerűen adja meg a kívánt színt, mint pl`Aspose.Pdf.Color.Red` vagy bármely más érvényes színábrázolás.

#### K: Lehetséges-e különböző sarokstílusokat (pl. négyzetes és lekerekített) alkalmazni ugyanazon a PDF dokumentumon belüli különböző táblázatokhoz?

V: Igen, lehetséges különböző sarokstílusokat alkalmazni ugyanazon a PDF dokumentumon belüli különböző táblázatokhoz. Létrehozhat több asztalt, és egyedileg konfigurálhatja a sarokstílusukat az Ön igényei szerint.

#### K: Beállíthatom a lekerekített sarokszegély vastagságát?

 V: Igen, beállíthatja a lekerekített sarokszegély vastagságát a`BorderInfo` objektum tulajdonságait a C# forráskódban. Például beállíthatja a`bInfo.Width` tulajdonság a szegély vastagságának beállításához.