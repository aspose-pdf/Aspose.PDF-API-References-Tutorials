---
title: Szöveg kivonat a bélyegző megjegyzéséből
linktitle: Szöveg kivonat a bélyegző megjegyzéséből
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre bemutatott, részletes kódpéldával kiegészített oktatóanyagból megtudhatja, hogyan bonthat ki szöveget egy PDF-formátumú bélyegjegyzetből az Aspose.PDF for .NET használatával.
type: docs
weight: 80
url: /hu/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
## Bevezetés

Ha PDF fájlokkal dolgozik, nagyon hasznos lehet bizonyos adatok, például szöveg kinyerése a megjegyzésekből. Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan bonthat ki szöveget egy PDF-dokumentum bélyegző megjegyzéseiből az Aspose.PDF for .NET használatával. Ez a nagy teljesítményű könyvtár lehetővé teszi a fejlesztők számára a PDF-fájlok kezelését, lehetővé téve olyan feladatokat, mint a szövegkivonat, a kommentárkezelés és még sok más. Merüljünk el a részletekben, és bontsuk szét az egészet!

## Előfeltételek

Mielőtt belevágnánk az oktatóanyagba, van néhány dolog, amire szüksége lesz:

-  Aspose.PDF for .NET: telepítenie kell az Aspose.PDF for .NET fájlt. Tudod[töltse le a legújabb verziót innen](https://releases.aspose.com/pdf/net/).
- Visual Studio: Ez az útmutató feltételezi, hogy a Visual Studiot használja integrált fejlesztői környezetként (IDE).
- Alapvető C# ismerete: Alapvető ismeretekkel kell rendelkeznie a C# programozásról.

Győződjön meg arról, hogy beállította ezeket az eszközöket, hogy követhesse az oktatóanyagot.

## Csomagok importálása

Minden .NET-projekt első lépése a szükséges névterek importálása. Az Aspose.PDF használatával csak néhány kulcsfontosságú importálásra lesz szüksége a kezdéshez:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Ezek az importálások a PDF-dokumentumokkal, a megjegyzésekkel és a szövegkivonattal való munkához szükséges funkciókat biztosítják.

Nézzük végig a bélyegfeliratból szöveg kinyerésének folyamatát. Ez magában foglalja a PDF dokumentum betöltését, a bélyegző megjegyzés azonosítását és a szöveges tartalom kibontását.

## 1. lépés: Töltse be a PDF-dokumentumot

Az első dolog, amit meg kell tennie, hogy betöltse a PDF-fájlt, ahol a bélyegző megjegyzés található. Ebben a példában egy minta PDF-fájlt töltünk be a helyi könyvtárból.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
```

 Itt a`Document` Az Aspose.PDF által biztosított osztály a PDF-fájl megnyitásához és interakciójához. A`dataDir` változó a fájl elérési útját jelöli. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a PDF tárolási útvonalával.

## 2. lépés: Azonosítsa a bélyegző megjegyzést

PDF-annotációkat típusuk és a dokumentumon belüli elhelyezkedésük alapján azonosítjuk. Esetünkben egy bélyegző megjegyzést szeretnénk találni egy adott oldalon. Íme, hogyan kell csinálni:

```csharp
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
```

Ebben a kódsorban:
- `doc.Pages[1]`: A dokumentum első oldalának megnyitása.
- `Annotations[3]`: Az oldal negyedik megjegyzésére vonatkozik (mivel az indexelés 0-tól kezdődik).
- `as StampAnnotation` : A kommentárt a`StampAnnotation` objektum, amely az annotáció konkrét típusa, amellyel foglalkozunk.

## 3. lépés: Hozzon létre egy szövegelnyelőt

Ahhoz, hogy szöveget kinyerhessünk a bélyegző megjegyzéséből, szövegelnyelőt kell használnunk. Ez az eszköz segít abban, hogy elnyeljük vagy rögzítsük a szöveget a PDF egy adott területéről, ebben az esetben a megjegyzésről.

```csharp
TextAbsorber ta = new TextAbsorber();
```

 A`TextAbsorber` osztály célja a szöveg kinyerésére a dokumentum bármely részéből, és ezzel fogjuk megcélozni a kommentár megjelenését.

## 4. lépés: Bontsa ki a bélyegző megjegyzés megjelenését

PDF-fájlokban található bélyegjegyzeteknek van egy hozzárendelt megjelenése, általában XForm formájában tárolva. Ezt a megjelenést kell lekérnünk, hogy hozzáférhessünk a bélyegzőn belüli tényleges szöveghez.

```csharp
XForm ap = annot.Appearance["N"];
```

Itt:
- `annot.Appearance["N"]`: Lekéri az "N" nevű megjelenési adatfolyamot (amely a megjegyzés normál megjelenését jelenti).

## 5. lépés: Bontsa ki a szöveges tartalmat

 Most, hogy megvan a megjelenés, használhatjuk a`TextAbsorber` hogy látogassa meg a megjelenést és rögzítse a szöveget.

```csharp
ta.Visit(ap);
```

 A`Visit` módszer lehetővé teszi a`TextAbsorber` hogy elemezze a megjelenést és kivonja az abba beágyazott szöveges tartalmat.

## 6. lépés: Jelenítse meg a kivont szöveget

Végül a szöveg kibontása után kiírhatjuk a konzolra, vagy tárolhatjuk további felhasználás céljából.

```csharp
Console.WriteLine(ta.Text);
```

Ez az egyszerű kódsor megjeleníti a kivont szöveget a konzol ablakában. Igényei szerint fájlba is mentheti, vagy tovább manipulálhatja.

## Következtetés

PDF-dokumentumokban található megjegyzésekkel, különösen a bélyegzőkkel való munkavégzés jelentős funkciókkal bővítheti alkalmazásait. Az Aspose.PDF for .NET segítségével robusztus eszközkészlettel rendelkezik, amelyek megkönnyítik az adatok kinyerését, a megjegyzések kezelését és a PDF-ekkel való értelmes interakciót. Ebben az oktatóanyagban megmutattuk, hogyan lehet szöveget kinyerni a bélyegző megjegyzéseiből néhány egyszerű lépésben. Most Önön a sor, hogy kísérletezzen ezekkel a funkciókkal projektjei során!

## GYIK

### Kivonhatok szöveget más típusú megjegyzésekből az Aspose.PDF használatával?  
Igen, az Aspose.PDF lehetővé teszi a szöveg kinyerését különféle típusú megjegyzésekből, például szöveges megjegyzésekből, szabad szöveges megjegyzésekből és egyebekből, nem csak bélyegző megjegyzésekből.

### Az Aspose.PDF támogatja az egyéni megjegyzések hozzáadását?  
Teljesen! Az Aspose.PDF támogatja az egyéni megjegyzések létrehozását és hozzáadását PDF-dokumentumokhoz, így rugalmasságot biztosít az adatok kezelésében és bemutatásában.

### Kivonhatok képeket a bélyegjegyzetekből?  
Igen, hasonló módszerekkel kinyerhet képeket a bélyegjegyzetekből, ha hozzáfér a megjelenéshez és lekéri a képadatokat.

### Milyen egyéb funkciókat kínál az Aspose.PDF for .NET?  
Az Aspose.PDF for .NET funkciók széles skáláját kínálja, beleértve a szövegkezelést, az űrlapmezők kezelését, a dokumentumkonverziót és még sok mást.

### Ingyenes az Aspose.PDF for .NET?  
 Az Aspose.PDF for .NET ingyenes próbaverziót kínál, de a szolgáltatások teljes készletének eléréséhez licencet kell vásárolnia. Jelentkezni is lehet a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).