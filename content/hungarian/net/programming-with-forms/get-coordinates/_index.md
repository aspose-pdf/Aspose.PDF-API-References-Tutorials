---
title: PDF űrlapmezőkoordináták beszerzése
linktitle: PDF űrlapmezőkoordináták beszerzése
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET segítségével könnyedén beszerezheti a PDF űrlapmezők koordinátáit PDF-dokumentumaiban.
type: docs
weight: 120
url: /hu/net/programming-with-forms/get-coordinates/
---
Ebben az oktatóanyagban bemutatjuk, hogyan szerezhet be PDF űrlapmezőkoordinátákat az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumok könyvtárának elérési útját:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a kimeneti dokumentumot

Töltse be a kimeneti PDF dokumentumot:

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 3. lépés: Keresse meg a hozzáadott mezőket

Keresse meg a hozzáadott űrlapmezőket (ebben a példában az „1. tétel”, „2. tétel” és „3. tétel” mezőket használjuk):

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 4. lépés: Jelenítse meg az egyes mezők altételeinek pozícióit

Válogassa végig az egyes mezők beállításait, és tekintse meg az egyes alelemek koordinátáit:

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Minta forráskód a Koordináták lekéréséhez az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Töltse be a kimeneti dokumentumot
	Document doc1 = new Document( dataDir + "input.pdf");
	// Keresse meg a hozzáadott mezőket
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// És mutassa meg mindegyik alelem pozícióját.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan szerezhet be űrlapmezők koordinátáit az Aspose.PDF for .NET használatával. Ha követi ezeket a lépéseket, az Aspose.PDF segítségével könnyedén lekérheti az űrlapmezők alelemeinek koordinátáit a PDF-dokumentumokban.

### GYIK

#### K: Használhatom ezt a módszert bármilyen típusú űrlapmező koordinátáinak lekérésére az Aspose.PDF for .NET-ben?

V: Igen, ezt a módszert használhatja különböző típusú űrlapmezők koordinátáinak lekérésére az Aspose.PDF for .NET fájlban. A mellékelt C# forráskód bemutatja, hogyan lehet koordinátákat szerezni a RadioButton mezőkhöz, de ugyanezt a megközelítést alkalmazhatja más űrlapmezőtípusokhoz is, például TextBox, CheckBox, ListBox stb.

#### K: Hogyan módosíthatom vagy módosíthatom az űrlapmező koordinátáit?

V: Az űrlapmező koordinátái a PDF dokumentum koordinátarendszerén alapulnak, ahol az origó (0,0) az oldal bal alsó sarkában található. Az űrlapmező koordinátáinak módosításához vagy módosításához frissítheti a`Rect` a megfelelő űrlapmező vagy annak alelemei, például a RadioButtonOptionField tulajdonsága.

#### K: Hozzáadhatom az űrlapmezők koordinátáit programozottan egy PDF-dokumentumhoz?

V: Igen, lekérheti azon űrlapmezők koordinátáit, amelyeket programozottan adtak hozzá egy PDF-dokumentumhoz. Az Aspose.PDF for .NET lehetővé teszi az űrlapmezők dinamikus hozzáadását, és a hozzáadást követően lekérheti a koordinátáikat az ebben az oktatóanyagban bemutatott megközelítéssel.

#### K: Mi a célja az űrlapmező koordinátáinak lekérésének?

V: Az űrlapmezők koordinátáinak lekérése hasznos lehet, ha meghatározott elrendezéssel kapcsolatos műveleteket vagy ellenőrzéseket kell végrehajtania egy PDF-dokumentum űrlapmezőin. Lehetővé teszi az űrlapmezők pontos pozicionálását és igazítását koordinátáik alapján, így biztosítva, hogy helyesen jelenjenek meg a dokumentumban, és zökkenőmentes felhasználói élményt nyújtson.

#### K: Az űrlapmező koordinátái pontokban vagy más egységekben vannak kifejezve?

V: Az Aspose.PDF űrlapmező koordinátái .NET esetén pontokban vannak kifejezve. Egy pont 1/72 hüvelyknek felel meg, így szabványos mértékegység a PDF formátumban.