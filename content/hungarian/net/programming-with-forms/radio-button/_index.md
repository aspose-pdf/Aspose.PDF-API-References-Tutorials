---
title: Rádiógomb
linktitle: Rádiógomb
second_title: Aspose.PDF for .NET API Reference
description: Könnyen hozzáadhat rádiógombokat PDF-dokumentumaihoz az Aspose.PDF for .NET segítségével.
type: docs
weight: 220
url: /hu/net/programming-with-forms/radio-button/
---
Ebben az oktatóanyagban bemutatjuk, hogyan adhat hozzá választógombot egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Példányosítson egy dokumentumobjektumot

Példányosítson egy dokumentumobjektumot új PDF-dokumentum létrehozásához:

```csharp
Document pdfDocument = new Document();
```

## 3. lépés: Adjon hozzá egy oldalt

Oldal hozzáadása a PDF dokumentumhoz:

```csharp
pdfDocument.Pages.Add();
```

## 4. lépés: Példányosítson egy RadioButtonField objektumot

Példányosítson egy RadioButtonField objektumot, amely argumentumként adja meg az oldalszámot:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5. lépés: Adja meg a választógomb opcióit

Adjon hozzá rádiógomb-beállításokat a RadioButtonField objektumhoz úgy, hogy az egyes opciók koordinátáit egy Rectangle objektummal adja meg:

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## 6. lépés: Adja hozzá a választógombot az űrlaphoz

Adja hozzá a választógombot a dokumentum Form objektumához:

```csharp
pdfDocument.Form.Add(radio);
```

## 7. lépés: Mentse el a PDF-dokumentumot

Mentse el a létrehozott PDF dokumentumot:

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### Példa a Radio Button forráskódjához az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentum objektum példányosítása
	Document pdfDocument = new Document();
	// Oldal hozzáadása a PDF-fájlhoz
	pdfDocument.Pages.Add();
	// Állítsa be a RadioButtonField objektumot oldalszámmal argumentumként
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Adja hozzá az első választógombot, és adja meg annak eredetét is a Rectangle objektum segítségével
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	// Második választógomb opció hozzáadása
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	// Rádiógomb hozzáadása a Dokumentumobjektum objektumának létrehozásához
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	// Mentse el a PDF fájlt
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá választógombot egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Az alábbi lépések követésével egyszerűen létrehozhat választógombot, és elhelyezheti azt a PDF-dokumentum egy adott oldalán.


### GYIK

#### K: Testreszabhatom a választógomb megjelenését, például méretét és színét?

 V: Igen, testreszabhatja a rádiógomb megjelenését a`Rectangle` az objektum koordinátái a méretének és helyzetének meghatározásához. Az Aspose.PDF for .NET lehetővé teszi a választógomb megjelenésének igényeinek megfelelő beállítását.

#### K: Hozzáadhatok több választógombot különböző csoportokkal ugyanazon az oldalon?

V: Igen, ugyanazon az oldalon több választógombot is hozzáadhat különböző csoportokhoz. A rádiógombok minden csoportjának egyedi neve lehet, és az egyes csoportokon belül egyszerre csak egy opció választható ki.

#### K: Hogyan adhatok hozzá címkét vagy szöveges leírást a választógomb opcióihoz?

 V: Címke vagy szöveges leírás hozzáadásához a választógomb opcióihoz használja a`TextStamp`osztály az Aspose.PDF-ből .NET-hez, hogy meghatározott koordinátákon átfedje a PDF-dokumentum szövegét.

#### K: Az Aspose.PDF for .NET kompatibilis a .NET Framework összes verziójával?

V: Igen, az Aspose.PDF for .NET kompatibilis a .NET Framework összes verziójával, beleértve a .NET Core-t és a .NET Standardot is.

#### K: Szabályozhatom programozottan a választógombok beállítását a PDF-dokumentumban?

 V: Igen, programozottan vezérelheti egy választógomb opció kiválasztását a`IsSelected` tulajdona a`RadioButtonOption` osztály. Ez a tulajdonság lehetővé teszi egy adott beállítás kiválasztását.