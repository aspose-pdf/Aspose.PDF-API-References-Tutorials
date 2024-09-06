---
title: Dokumentum létrehozása
linktitle: Dokumentum létrehozása
second_title: Aspose.PDF for .NET API Reference
description: Könnyen létrehozhat dokumentumot rádiógombokkal az Aspose.PDF for .NET segítségével.
type: docs
weight: 40
url: /hu/net/programming-with-forms/create-doc/
---
Ebben az oktatóanyagban bemutatjuk, hogyan hozhat létre dokumentumot rádiógombokkal az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

##1. lépés: Előkészítés

Először győződjön meg arról, hogy importálta a szükséges könyvtárakat, és állítsa be a dokumentumok könyvtárának elérési útját:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy új dokumentumot

Hozzon létre egy új dokumentumobjektumot a PDF-dokumentum tárolására:

```csharp
Document doc = new Document();
```

## 3. lépés: Adjon hozzá egy oldalt

Új oldal hozzáadása a dokumentumhoz:

```csharp
Page page = doc.Pages.Add();
```

## 4. lépés: Adjon hozzá egy választógomb mezőt

Hozzon létre egy választógomb mezőt, és állítsa be a helyét és méretét:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## 5. lépés: Adja hozzá a választógomb opcióit

Adja hozzá a kívánt beállításokat a választógomb mezőhöz. Igény szerint beállíthatja az egyes opciók koordinátáit és méretét:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## 6. lépés: Adja hozzá a választógomb mezőt az űrlaphoz

Adja hozzá a választógomb mezőt a Dokumentuműrlap-mezők gyűjteményhez:

```csharp
doc.Form.Add(field);
```

## 7. lépés: Mentse el a dokumentumot

Mentse el a PDF dokumentumot:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Forráskód minta a Create Doc használatához Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Hozzon létre egy új dokumentumot
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Rádiógomb mező hozzáadása
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Adja hozzá a választógomb opcióit. kérjük, vegye figyelembe, hogy ezek a lehetőségek vannak
	// Sem vízszintesen, sem függőlegesen.
	// Megpróbálhat bármilyen koordinátát (és akár méretet) beállítani nekik.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Mentse el a PDF dokumentumot
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre dokumentumot rádiógombokkal az Aspose.PDF for .NET használatával. Ha követi ezeket a lépéseket, az Aspose.PDF használatával egyszerűen hozzáadhat választógombokat PDF-dokumentumaihoz.

### GYIK

#### K: Testreszabhatom a választógombok megjelenését a dokumentumban az Aspose.PDF for .NET használatával?

V: Igen, testreszabhatja a választógombok megjelenését a dokumentumban az Aspose.PDF for .NET használatával. A választógombok megjelenésének testreszabásához beállíthat olyan tulajdonságokat, mint a méret, szín, szegélystílus és egyebek.

#### K: Hogyan adhatok hozzá egymást kölcsönösen kizáró opciókkal rendelkező választógomb-csoportokat?

V: Egymást kizáró opciók létrehozásához több azonos nevű választógomb mezőt is hozzáadhat. Ez biztosítja, hogy az egyik opció kiválasztásakor a többi azonos nevű opció kijelölése automatikusan megszűnjön.

#### K: Beállítható a rádiógombok alapértelmezett beállítása?

V: Igen, beállíthat egy alapértelmezett beállítást a választógombokhoz az Aspose.PDF for .NET használatával. Használhatja a`Selected` tulajdona a`RadioButtonOptionField` objektumot, hogy egy beállítást alapértelmezés szerint kiválasztottként jelöljön meg.

#### K: Hozzáadhatok eseménykezelőket a rádiógombokhoz?

 V: Igen, eseménykezelőket adhat hozzá a választógombokhoz az Aspose.PDF for .NET használatával. JavaScript-műveleteket társíthat, mint pl`OnValueChanged`, a rádiógombokra, hogy konkrét műveleteket hajtson végre, amikor a felhasználó kiválaszt egy lehetőséget.

#### K: Hogyan kérhetem le a kiválasztott opciót a választógomb-csoportból, miután a felhasználó kiválasztott?

 V: A kiválasztott beállítást lekérheti a választógomb-csoportból az Aspose.PDF for .NET használatával. Miután a felhasználó kiválasztott, elérheti a`Selected` tulajdona a`RadioButtonOptionField` objektumot, hogy ellenőrizze, melyik opció van kiválasztva.