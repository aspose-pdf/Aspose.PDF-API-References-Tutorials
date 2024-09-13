---
title: Kép és oldalszám a Fejléc lábléc részben
linktitle: Kép és oldalszám a Fejléc lábléc részben
second_title: Aspose.PDF for .NET API Reference
description: Ebben a lépésenkénti oktatóanyagban megtudhatja, hogyan adhat hozzá képet és oldalszámokat a PDF-fájl fejlécéhez és láblécéhez az Aspose.PDF for .NET használatával.
type: docs
weight: 110
url: /hu/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
## Bevezetés

Ha professzionális minőségű PDF-dokumentumokról van szó, elengedhetetlen az apró részletek, például a fejlécek és láblécek ellenőrzése. Azt szeretné, hogy dokumentumai fényezettnek és jól rendezettnek tűnjenek, igaz? Nos, az Aspose.PDF for .NET segítségével zökkenőmentesen adhat hozzá képeket és oldalszámokat a dokumentum fejlécéhez és láblécéhez. Ebben az oktatóanyagban minden lépésen végigvezetjük Önt, így könnyen követhető.

## Előfeltételek

Mielőtt belevágna ennek az oktatóanyagnak a lényegébe, győződjön meg arról, hogy a következőket rendezte:

1. .NET-keretrendszer: A .NET-keretrendszer bármely verzióját telepítenie kell a számítógépére. Ha nem rendelkezik vele, egyszerűen letöltheti a Microsoft webhelyéről.
2.  Aspose.PDF .NET-hez: Mivel az Aspose.PDF-et fogjuk használni, győződjön meg arról, hogy telepítve van a projektben. Letöltheti a próbaverziót[itt](https://releases.aspose.com/pdf/net/).
3. Alapvető C# ismerete: Az alapvető C# programozás ismerete minden bizonnyal segít megérteni a kódot különösebb gond nélkül.
4. Képfájl: Szüksége lesz egy képre, amelyet el szeretne helyezni a PDF-dokumentum fejlécébe, például egy logóra. Mentse el egy hozzáférhető könyvtárba. 
5. IDE: Használjon tetszőleges integrált fejlesztői környezetet (IDE), például a Visual Studio-t, hogy működjön együtt a .NET-projektjével.

Ha elkészült az előfeltételekkel, készen áll egy csodálatos PDF-fájl létrehozására!

## Csomagok importálása

Az Aspose.PDF for .NET használatának megkezdéséhez importálnia kell a szükséges névtereket. A C# fájl tetején a következőket kell hozzáadnia:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Image;
```

Ezek a névterek hozzáférést biztosítanak a PDF-fájlok kezeléséhez szükséges osztályokhoz.

Most pedig térjünk rá az igazira! Kövesse az alábbi lépéseket a PDF-dokumentum létrehozásához, a fejlécben egy képet, a láblécben pedig az oldalszámokat.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Minden jó projekt a szervezéssel kezdődik. Határozza meg a dokumentumkönyvtárat, ahová menteni fogja a fájljait, és ahol a kép található. Íme, hogyan kell csinálni:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ne felejtse el cserélni`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahová menteni szeretné a PDF-fájlt, és ahol a kép található.

## 2. lépés: Hozzon létre egy új PDF-dokumentumot

Ezután létrehozunk egy új PDF-dokumentumot, amelyben minden varázslat megtörténik:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Ezen a ponton létrehozott egy üres PDF-dokumentumot. Izgalmas, nem?

## 3. lépés: Adjon hozzá egy oldalt a dokumentumhoz

A PDF az oldalakról szól. Adjunk hozzá egy új oldalt a dokumentumunkhoz a következő használatával:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Most van egy vászon, ahol elkezdheti a tervezést!

## 4. lépés: Hozza létre a Fejléc szakaszt

A fejléc tartalmazza a megjeleníteni kívánt képet (mint egy logót). Hozza létre a fejléc szakaszt a következő kóddal:

```csharp
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
page.Header = header;
```

Most már van egy fejléce, amelyet személyre szabhat!

## 5. lépés: Adjon hozzá egy képet a fejléchez

Most elérkeztünk a szórakoztató részhez! A képet hozzá kell adnia a fejléchez. Először hozzon létre egy képobjektumot:

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

Állítsa be a kép fájl elérési útját:

```csharp
image1.File = dataDir + "aspose-logo.jpg";
```

Végül add hozzá a képet a fejléchez:

```csharp
header.Paragraphs.Add(image1);
```

Gratulálok! Most hozzáadott egy képet a PDF fejlécéhez.

## 6. lépés: Hozza létre a lábléc szakaszt

Most dolgozzunk a láblécen. A fejléchez hasonlóan hozzon létre egy láblécobjektumot:

```csharp
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();
page.Footer = footer;
```

Itt kell elhelyezni az oldalszámot. 

## 7. lépés: Szöveg hozzáadása a lábléchez

Hozzon létre egy szövegrészletet, amely tartalmazza az oldalszámot:

```csharp
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");
```

Ezután adja hozzá ezt a szövegrészletet a lábléchez:

```csharp
footer.Paragraphs.Add(txt);
```

Látod milyen könnyű volt? Dinamikusan beállítottad az oldalszámodat!

## 8. lépés: Mentse el a PDF-dokumentumot

Kalandunk utolsó lépése a dokumentum mentése. Ezzel a paranccsal mentheti el az újonnan létrehozott PDF-fájlt:

```csharp
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

És éppen így, a PDF-fájl készen áll, és a láblécben be van töltve egy fejléckép és oldalszámok!

## Következtetés

És megvan! Létrehozott egy PDF-fájlt, amelynek fejlécében egy kép, a láblécben pedig dinamikus oldalszámok találhatók az Aspose.PDF for .NET használatával. Egészen hihetetlen, hogy néhány sornyi kód hogyan eredményezhet ilyen csiszolt kimenetet. Legyen szó vállalati jelentésről vagy személyre szabott dokumentumról, ezeknek az elemeknek a hozzáadása megváltoztatja a PDF-fájl hangnemét és professzionalizmusát.

## GYIK

### Használhatom az Aspose.PDF-et bármely .NET platformon?
Igen, az Aspose.PDF for .NET több .NET-platformot támogat, beleértve a .NET-keretrendszert, a .NET Core-t és egyebeket.

### Elérhető az Aspose.PDF ingyenes próbaverziója?
 Teljesen! Letölthet egy ingyenes próbaverziót[itt](https://releases.aspose.com/).

### Milyen képformátumok támogatottak a fejlécekhez?
Az Aspose.PDF támogatja a legelterjedtebb képformátumokat, például a JPG, PNG és BMP fejléceket és lábléceket.

### Testreszabhatom az oldalszámformátumot?
Igen, könnyen testreszabhatja a lábléc szövegét és formátumát igényei szerint.

### Műszaki támogatás elérhető?
 Igen, az Aspose dedikált támogatást nyújt a fórumán keresztül. Segítségért fordulhat[itt](https://forum.aspose.com/c/pdf/10).