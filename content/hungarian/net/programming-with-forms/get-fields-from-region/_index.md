---
title: Mezők lekérése a régióból PDF-fájlban
linktitle: Mezők lekérése a régióból PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Könnyen beszerezheti a mezőket egy adott régióból PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 130
url: /hu/net/programming-with-forms/get-fields-from-region/
---
Ebben az oktatóanyagban bemutatjuk, hogyan töltheti le egy adott régió mezőit PDF-fájlban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Nyissa meg a PDF-fájlt

Nyissa meg a PDF fájlt:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## 3. lépés: Hozzon létre egy téglalap alakú objektumot a régió behatárolásához

Hozzon létre egy téglalap alakú objektumot, amely lehatárolja azt a régiót, ahol a mezőket szeretné lekérni:

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## 4. lépés: Szerezze meg a PDF űrlapot

Szerezze meg a dokumentum PDF formátumát:

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## 5. lépés: Szerezze be a mezőket a téglalap alakú területen

A megadott téglalap alakú régióban található mezők lekérése:

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## 6. lépés: A mezőnevek és értékek megjelenítése

Ismételje meg a kapott mezőket, és jelenítse meg a nevüket és értékeikat:

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### Minta forráskód a Mezők lekérése régióból fájlhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a pdf fájlt
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
// Hozzon létre téglalap objektumot, hogy mezőket kapjon az adott területen
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
// Szerezd meg a PDF űrlapot
Aspose.Pdf.Forms.Form form = doc.Form;
// Keressen mezőket a téglalap alakú területen
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
// Mezőnevek és értékek megjelenítése
foreach (Field field in fields)
{
	// Képelhelyezési tulajdonságok megjelenítése az összes elhelyezéshez
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet egy adott régió mezőit PDF-dokumentumban letölteni az Aspose.PDF for .NET használatával. Ha követi ezeket a lépéseket, az Aspose.PDF segítségével könnyedén kibonthatja a PDF-dokumentum adott négyszögletes területén található mezőket.

### GYIK

#### K: Használhatom ezt a módszert mezők lekérésére egy PDF-dokumentum nem téglalap alakú területéről?

 V: Nem, a megadott módszer`GetFieldsInRect` kifejezetten a PDF-dokumentum téglalap alakú területén belüli mezők lekérésére készült. Ha nem téglalap alakú régióból kell kivonnia a mezőket, akkor egyéni logikát kell alkalmaznia a mezők azonosításához és kibontásához más feltételek, például mezőkoordináták vagy -nevek alapján.

#### K: Hogyan módosíthatom a téglalap méretét vagy helyzetét, hogy a mezőket egy másik régióból kapja meg?

 V: Más régióból származó mezők lekéréséhez módosíthatja a`Aspose.Pdf.Rectangle` az objektum paraméterei, amelyek a határoló téglalap meghatározására szolgálnak. A`Rectangle` A konstruktor négy paramétert vesz fel:`x`, `y`, `width` , és`height`amelyek a bal felső sarok koordinátáit és a téglalap méreteit jelentik. Ezen paraméterek módosítása megváltoztatja azt a régiót, ahonnan a mezők kinyerhetők.

#### K: Mi a teendő, ha a megadott téglalap alakú területen belül nincsenek mezők?

 V: Ha nincs mező a megadott téglalap alakú területen belül, a`GetFieldsInRect` metódus üres tömböt ad vissza. Ellenőrizheti a tömb hosszát, hogy megállapítsa, vannak-e mezők a régión belül.

#### K: Kaphatok mezőket átfedő régiókból egy PDF-dokumentumban?

 V: Igen, egy PDF-dokumentum átfedő régióiból is beszerezhet mezőket, ha több példányt hoz létre`Aspose.Pdf.Rectangle` tárgyakat és a`GetFieldsInRect` módszer mindegyikére. Az átfedő régiókat a rendszer önállóan kezeli, és minden régióhoz külön mezőtömböket kap.

#### K: Lehetséges-e mezőket lekérni egy adott oldalról vagy több oldalról a PDF-dokumentumban?

V: Igen, a mezőket egy adott oldalról vagy egy PDF-dokumentum több oldaláról is lekérheti. Ennek eléréséhez betöltheti a PDF-dokumentumot, és a kívánt oldalakat a segítségével érheti el`doc.Pages` gyűjtemény, majd alkalmazza a`GetFieldsInRect` módszert az egyes oldalak adott régiójához.