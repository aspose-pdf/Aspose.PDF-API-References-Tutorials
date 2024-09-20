---
title: Illusztráció szerkezeti elemek
linktitle: Illusztráció szerkezeti elemek
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET fájlban strukturált PDF-fájlokat hozhat létre illusztrációs elemekkel a lépésenkénti oktatóanyagunk követésével.
type: docs
weight: 100
url: /hu/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## Bevezetés

Készen áll arra, hogy lenyűgöző, strukturált PDF-eket készítsen .NET-alkalmazásaiban? Akár egy tartalom címkézését igénylő projekten dolgozik, akár egyszerűen csak a következő szintre szeretné emelni PDF-fájljait, az Aspose.PDF for .NET minden olyan eszközzel rendelkezik, amelyre szüksége van az illusztrációs szerkezeti elemekkel való munkához. Ebben az oktatóanyagban lépésről lépésre végigvezetem a folyamaton, biztosítva, hogy még a legösszetettebb részek is kristálytiszták legyenek.

## Előfeltételek

Mielőtt belemerülnénk a részletekbe, győződjünk meg arról, hogy mindennel rendelkezünk, ami a zökkenőmentes követéshez szükséges.

1.  Aspose.PDF for .NET – telepítenie kell az Aspose.PDF könyvtárat. Még nincs meg? Megteheti[töltse le itt](https://releases.aspose.com/pdf/net/) . Ha először szeretné kipróbálni, megragadhat a[ingyenes próbaverzió](https://releases.aspose.com/).
2. Visual Studio – C#-ban fogunk kódolni, ezért győződjön meg róla, hogy a Visual Studio vagy bármely kompatibilis IDE telepítve van.
3. .NET-keretrendszer – Győződjön meg arról, hogy az Aspose.PDF for .NET-hez kompatibilis verziója van.
4.  Ideiglenes licenc – Az Aspose.PDF próbaüzemmódban bizonyos korlátozásokkal jár, ezért szerezze be a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) a teljes funkciók feloldásához.

Ez minden! Most importáljuk a szükséges névtereket, és folytassuk a kódolást.

## Névterek importálása

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ez az alap – e névterek importálása nélkül nem tudunk kölcsönhatásba lépni az Aspose.PDF szolgáltatásaival, és nem kezelhetjük a címkézett PDF-tartalmakat. Most bontsuk le részletesen a lépéseket.

## 1. lépés: A dokumentumkönyvtár beállítása

A PDF létrehozásának megkezdése előtt meg kell adnia annak a dokumentumkönyvtárnak az elérési útját, ahová a fájl mentésre kerül. Ez az a mappa a rendszeren, ahol a képei vagy egyéb eszközei tárolódnak.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ez a lépés egyszerű, de elengedhetetlen. Megmondja a programnak, hogy hol találja meg és tárolja a fájlokat, amelyekkel dolgozni fog. Ez olyan, mintha otthoni bázisa lenne a PDF-fájlok számára. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal a gépen.

## 2. lépés: Új PDF-dokumentum létrehozása

Itt az ideje a PDF dokumentum létrehozásának. Ebben a lépésben egy üres PDF dokumentumot indítunk el, amelyet a következő lépésekben módosítunk és javítunk.
 Hozd létre a dokumentumot

```csharp
Document document = new Document();
```

Ez a vonal minden varázslatot végrehajt. Létrehoz egy új PDF-fájlt, amely teljesen üres, és arra vár, hogy tartalmat adjon hozzá. Tekintsd úgy, mint egy friss vászon megnyitását.

## 3. lépés: A címkézett PDF-tartalom elérése

Az illusztrációs szerkezeti elemek használatához meg kell érintenünk a dokumentum címkézett tartalmát. Ez lehetővé teszi számunkra, hogy meghatározott címkéket határozzunk meg, így a PDF strukturáltabbá és hozzáférhetőbbé válik.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 Itt történik a varázslat! A`TaggedContent` Az objektum segítségével meghatározhatjuk, hogyan értelmezzük a PDF elemeit. Ha akadálymentesítéssel vagy struktúrával dolgozik, ez a lépés kulcsfontosságú.

## 4. lépés: A dokumentum címének és nyelvének beállítása

Strukturált PDF-et készítünk, ezért elengedhetetlen a cím és a nyelv meghatározása. Ez nem csak a hozzáférhetőségben segít, hanem professzionálisabbá és kereshetőbbé is teszi a dokumentumot.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

cím és a nyelv megadásával lényegében egyéniséget ad a PDF-nek. A cím megjelenik a dokumentum tulajdonságai között, és a nyelv beállítása biztosítja a kompatibilitást a képernyőolvasókkal és más kisegítő eszközökkel.

## 5. lépés: Illusztráció (ábra) elem létrehozása

Most jön az izgalmas rész – egy illusztráció hozzáadása! Ebben az esetben létrehozunk egy ábra elemet, amely egy képet, egy alternatív szöveges leírást és egy címet tartalmaz.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

Ez a kód egy új ábraelemet hoz létre, és hozzáfűzi a dokumentum gyökéreleméhez. Tekintse ezt úgy, mint egy kép-helyőrző hozzáadását a dokumentumhoz.

## 6. lépés: Alternatív szöveg, cím és kép hozzáadása

A PDF hozzáférhetőségének biztosítása érdekében érdemes alternatív szöveget és egy címet megadni az illusztrációhoz. Csatolunk képet is.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 Ez az utolsó simítás. Képünknek egy leíró alternatív szöveget adunk (ami a képernyőolvasók számára hasznos), egy címet és beállítjuk a tényleges képfájlt. A`SetTag`metódus címkézi az ábrát, megkönnyítve a későbbi hivatkozást.

 Fontos megjegyzés: Győződjön meg arról, hogy a kép elérési útja be`SetImage` egy érvényes képfájlra mutat a gépén.

## 7. lépés: Mentse el a címkézett PDF-dokumentumot

Az összes tartalom hozzáadása és strukturálása után ideje elmenteni a PDF-fájlt. Ez a lépés mindent véglegesít, és létrehozza a tényleges fájlt.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

Egyszerű, igaz? Ez a parancs elvégzi az összes elvégzett munkát, és létrehoz egy új PDF-fájlt a korábban megadott könyvtárban. Most ellenőrizze a mappát, és íme – van egy strukturált PDF-je illusztrációs elemekkel!

## Következtetés

Gratulálok! Most tanulta meg, hogyan hozhat létre címkézett PDF-et illusztrációs szerkezeti elemekkel az Aspose.PDF for .NET használatával. Ez a megközelítés biztosítja, hogy a PDF-fájlok ne csak látványosak legyenek, hanem strukturáltak és hozzáférhetőek is. A tartalom címkézésével és alternatív szövegek hozzáadásával biztosíthatja, hogy mindenki, beleértve a kisegítő technológiákat használókat is, élvezhesse dokumentumait.

## GYIK

### Mi az a címkézett PDF-tartalom?
címkézett PDF olyan PDF, amely címkéket vagy címkéket tartalmaz a különböző elemek, például címsorok, bekezdések és ábrák azonosítására, így a dokumentum könnyebben hozzáférhető.

### Hogyan segít az alternatív szöveg beállítása?
Az alternatív szöveg leírásokat ad a képekhez, amelyeket a képernyőolvasók is elolvashatnak, javítva a látássérült felhasználók hozzáférését.

### Hozzáadhatok több képet egy címkézett PDF-hez?
 Igen! Többet is létrehozhat`FigureElement` objektumokat, és mindegyiket hozzáfűzi a dokumentumhoz, ugyanúgy, mint az egyetlen kép esetében.

### Szükségem van licencre az Aspose.PDF for .NET használatához?
 Igen, az Aspose.PDF egy fizetős könyvtár, de beszerezheti a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) vagy kezdje a-val[ingyenes próbaverzió](https://releases.aspose.com/).

### Lehetséges az ábraelem módosítása a PDF elkészítése után?
A PDF mentése után nem módosíthatja közvetlenül, de újra megnyithatja a dokumentumot, módosíthatja, majd újra elmentheti az Aspose.PDF használatával.