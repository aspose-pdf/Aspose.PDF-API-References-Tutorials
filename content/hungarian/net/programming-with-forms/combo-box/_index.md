---
title: Kombinált doboz
linktitle: Kombinált doboz
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET segítségével egyszerűen hozhat létre kombinált listát PDF-dokumentumaiban.
type: docs
weight: 30
url: /hu/net/programming-with-forms/combo-box/
---
Ebben az oktatóanyagban bemutatjuk, hogyan hozhat létre kombinált listát az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Először győződjön meg arról, hogy importálta a szükséges könyvtárakat, és állítsa be a dokumentumok könyvtárának elérési útját:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumobjektumot

Hozzon létre egy dokumentum objektumot a PDF űrlap tárolására:

```csharp
Document doc = new Document();
```

## 3. lépés: Adjon hozzá egy oldalt

Oldal hozzáadása a dokumentumhoz:

```csharp
doc.Pages.Add();
```

## 4. lépés: Példányosítson egy ComboBoxField objektumot

Példányosítson egy ComboBoxField objektumot a kívánt méretekkel:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 5. lépés: Adjon hozzá lehetőségeket a legördülő listához

Adja hozzá a kívánt beállításokat a legördülő listához:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## 6. lépés: Adja hozzá a kombinált listát az űrlaphoz

Adja hozzá a ComboBoxField objektumot a Dokumentuműrlap mezők gyűjteményéhez:

```csharp
doc.Form.Add(combo);
```

## 7. lépés: Mentse el a dokumentumot

Mentse el a PDF dokumentumot:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Példa a Combo Box forráskódjához az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentumobjektum létrehozása
	Document doc = new Document();
	// Oldal hozzáadása a dokumentumobjektumhoz
	doc.Pages.Add();
	// ComboBox Field objektum példányosítása
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Opció hozzáadása a ComboBoxhoz
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Vegyes doboz objektum hozzáadása a dokumentumobjektum mezőgyűjteményéhez
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Mentse el a PDF dokumentumot
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre kombinált listát az Aspose.PDF for .NET használatával. Ha követi ezeket a lépéseket, az Aspose.PDF használatával egyszerűen hozzáadhat egy kombinált listát PDF-dokumentumaihoz.

### GYIK

#### K: Testreszabhatom a kombinált lista megjelenését az Aspose.PDF for .NET használatával?

V: Igen, testreszabhatja a kombinált lista megjelenését az Aspose.PDF for .NET használatával. Beállíthat olyan tulajdonságokat, mint például a betűméret, a szín, a háttérszín, a szegélystílus és még sok más, hogy megfeleljenek a kívánt megjelenésnek.

#### K: Beállíthatom az alapértelmezett kiválasztott beállításokat a kombinált listában?

 V: Igen, beállíthatja az alapértelmezett kiválasztott beállításokat a kombinált listában az Aspose.PDF for .NET használatával. Használhatja a`Selected` tulajdona a`ComboBoxField` objektumot, hogy egy vagy több opciót alapértelmezés szerint kiválasztottként jelöljön meg.

#### K: Hogyan kérhetem le a kiválasztott értéket a kombinált listából, miután a felhasználó kiválasztott?

 V: A kiválasztott értéket lekérheti a kombinált listából az Aspose.PDF for .NET használatával. Miután a felhasználó kiválasztott, elérheti a`Value` tulajdona a`ComboBoxField`objektumot, hogy megkapja a kiválasztott értéket.

#### K: Lehetséges eseménykezelőket vagy műveleteket hozzáadni a kombinált listához?

 V: Igen, az Aspose.PDF for .NET lehetővé teszi eseménykezelők vagy műveletek hozzáadását a kombinált listához. JavaScript-műveleteket társíthat, mint pl`OnValueChanged`, a kombinált listába, hogy konkrét műveleteket hajtson végre, amikor a felhasználó kiválaszt egy lehetőséget.

#### K: Hozzáadhatok eszköztippeket vagy leírásokat a kombinált lista opcióihoz?

 V: Igen, az Aspose.PDF for .NET használatával eszköztippeket vagy leírásokat adhat a kombinált lista opcióihoz. Beállíthatja a`AlternateName` az egyes opciók tulajdonsága, hogy eszközleírást vagy leírást adjon, amely akkor jelenik meg, amikor a felhasználó az opció fölé viszi az egérmutatót.