---
title: Csoportosított jelölőnégyzetek a PDF-dokumentumban
linktitle: Csoportosított jelölőnégyzetek a PDF-dokumentumban
second_title: Aspose.PDF for .NET API Reference
description: Könnyen hozhat létre csoportosított jelölőnégyzeteket PDF-dokumentumban az Aspose.PDF for .NET segítségével.
type: docs
weight: 170
url: /hu/net/programming-with-forms/grouped-check-boxes/
---
Ebben az oktatóanyagban bemutatjuk, hogyan hozhat létre csoportosított jelölőnégyzeteket egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Példányosítson egy dokumentumobjektumot

Dokumentum objektum példányosítása:

```csharp
Document pdfDocument = new Document();
```

## 3. lépés: Oldal hozzáadása a PDF dokumentumhoz

Oldal hozzáadása a PDF dokumentumhoz:

```csharp
Page page = pdfDocument.Pages.Add();
```

## 4. lépés: Példányosítson egy RadioButtonField objektumot

Példányosítson egy RadioButtonField objektumot az oldalszámmal argumentumként:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 5. lépés: Adja meg a választógomb opcióit

Adjon hozzá választógomb-beállításokat a RadioButtonOptionField objektum segítségével, és adja meg helyzetüket a Rectangle objektum segítségével:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## 6. lépés: A választógomb opcióinak testreszabása

Testreszabhatja a választógomb opcióit stílusuk, szegélyük és megjelenésük beállításával:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## 7. lépés: Adja hozzá a rádiógombokat az űrlaphoz

Adja hozzá a választógombokat a dokumentum űrlap objektumhoz:

```csharp
pdfDocument.Form.Add(radio);
```

## 8. lépés: Mentse el a dokumentumot

Mentse el a PDF dokumentumot:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Minta forráskód csoportos jelölőnégyzetekhez az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dokumentum objektum példányosítása
	Document pdfDocument = new Document();
	// Oldal hozzáadása a PDF-fájlhoz
	Page page = pdfDocument.Pages.Add();
	// Állítsa be a RadioButtonField objektumot oldalszámmal argumentumként
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Adja hozzá az első választógombot, és adja meg annak eredetét is a Rectangle objektum segítségével
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Rádiógomb hozzáadása a Dokumentumobjektum objektumának létrehozásához
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Mentse el a PDF dokumentumot
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre csoportosított jelölőnégyzeteket egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ezeket a lépéseket követve egyszerűen hozzáadhat egyéni választógomb-beállításokat, és az Aspose.PDF segítségével PDF-dokumentumaiba kötegelheti őket.

### GYIK

#### K: Mik azok a csoportosított jelölőnégyzetek egy PDF-dokumentumban?

V: A PDF-dokumentumban lévő csoportosított jelölőnégyzetek egy csoportba sorolt választógomb-beállításokra utalnak. A választógombok lehetővé teszik a felhasználók számára, hogy csak egy opciót válasszanak ki az egymást kölcsönösen kizáró lehetőségek közül. Ha valamelyik választógombot kiválasztja, az ugyanabban a csoportban lévő többi választógomb kijelölése automatikusan megszűnik. Ez a csoportosítási viselkedés akkor hasznos, ha több lehetőséget szeretne felkínálni a felhasználóknak, de csak egy lehetőségre korlátozza a választást.

#### K: Testreszabhatom a csoportosított jelölőnégyzetek megjelenését az Aspose.PDF for .NET fájlban?

V: Igen, testreszabhatja a csoportosított jelölőnégyzetek megjelenését az Aspose.PDF for .NET fájlban. Az API különféle lehetőségeket kínál a választógomb-beállítások stílusának, szegélyének és megjelenésének beállítására. Meghatározhatja az egyes opciók helyzetét, választhat a különböző dobozstílusok közül (pl. négyzet, kör, kereszt), és módosíthatja a szegély tulajdonságait a kívánt vizuális megjelenítés eléréséhez.

#### K: Hogyan adhatok csoportosított jelölőnégyzeteket egy PDF-dokumentum egy adott oldalához?

V: Ha csoportosított jelölőnégyzeteket szeretne hozzáadni egy PDF-dokumentum egy adott oldalához, példányosítania kell a`RadioButtonField` objektum a kívánt oldalszámmal argumentumként. Ezután hozzon létre`RadioButtonOptionField` az egyes választógomb opciókat képviselő objektumokat, és adjuk meg pozíciójukat a gombbal`Rectangle` tárgy. Végül adja hozzá ezeket a lehetőségeket a`RadioButtonField` és szükség szerint testreszabhatja megjelenésüket, mielőtt hozzáadná a`RadioButtonField` a dokumentum űrlapra.

#### K: Hozzáadhatok több jelölőnégyzetcsoportot egyetlen PDF-dokumentumhoz?

 V: Igen, több jelölőnégyzetcsoportot is hozzáadhat egyetlen PDF-dokumentumhoz. Minden csoportnak egyedinek kell lennie`RadioButtonField` objektum, és a`RadioButtonOptionField` Az egyes csoportokon belüli objektumok ugyanazon az oldalon osztoznak, és egyedi neveket kell megadniuk a beállításokhoz. Ez biztosítja, hogy az egyes csoportokon belüli rádiógombok megfelelően működjenek, és a kijelölések kölcsönösen kizárják egymást.

#### K: Minden PDF-megjelenítő és alkalmazás támogatja a csoportosított jelölőnégyzeteket?

V: Igen, a csoportosított jelölőnégyzetek minden szabványnak megfelelő PDF-megtekintőben és alkalmazásban támogatottak. A PDF specifikáció meghatározza a választógombokat és csoportosítási viselkedésüket, így általánosan felismerhetőek a PDF formátumban. Mindazonáltal elengedhetetlen a funkcionalitás tesztelése a különböző PDF-megtekintőkben, hogy a különböző platformokon egységes viselkedést biztosítsunk.