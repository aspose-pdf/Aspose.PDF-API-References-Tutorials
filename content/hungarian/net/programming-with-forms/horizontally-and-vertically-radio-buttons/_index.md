---
title: Vízszintesen és függőlegesen Rádiógombok
linktitle: Vízszintesen és függőlegesen Rádiógombok
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET segítségével könnyedén hozhat létre vízszintes és függőleges választógombokat PDF-dokumentumaiban.
type: docs
weight: 180
url: /hu/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
Ebben az oktatóanyagban bemutatjuk, hogyan hozhat létre vízszintesen és függőlegesen elrendezett rádiógombokat egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot

Töltse be a meglévő PDF dokumentumot:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 3. lépés: A választógomb opcióinak testreszabása

Testreszabhatja a választógomb opcióit a következő tulajdonságok beállításával:

```csharp
formEditor. RadioGap = 4; // Két választógomb közötti távolság
formEditor. RadioHoriz = true; // rádiógombok vízszintes elrendezése
formEditor.RadioButtonItemSize = 20; // A rádiógombok mérete
formEditor.Facade.BorderWidth = 1; // A választógomb szegélyének szélessége
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Rádiógomb szegélyszíne
```

## 4. lépés: Adjon hozzá vízszintes rádiógombokat

Adjon hozzá vízszintesen elhelyezett választógombokat a mező opcióinak és helyzetének megadásával:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## 5. lépés: Adjon hozzá függőleges rádiógombokat

Függőlegesen elhelyezett választógombok hozzáadása a mező opcióinak és helyzetének megadásával:

```csharp
formEditor. RadioHoriz = false; // A rádiógombok függőleges elrendezése
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 6. lépés: Mentse el a dokumentumot

Mentse el a módosított PDF dokumentumot:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Minta forráskód vízszintesen és függőlegesen rádiógombokhoz az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Töltse be a korábban mentett dokumentumot
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// A RadioGap a két választógomb közötti távolság.
	formEditor.RadioGap = 4;
	// Vízszintes választógomb hozzáadása
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize, ha a választógomb elem mérete.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Másik, függőlegesen elhelyezett rádiógomb hozzáadása
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Mentse el a PDF dokumentumot
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet vízszintesen és függőlegesen elrendezett rádiógombokat létrehozni egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Az alábbi lépések követésével egyszerűen testreszabhatja a választógombok elrendezését, és hozzáadhatja őket PDF-dokumentumaihoz az Aspose.PDF használatával.

### GYIK

#### K: Mik azok a vízszintesen és függőlegesen elhelyezett rádiógombok egy PDF-dokumentumban?

V: A vízszintesen és függőlegesen elhelyezett választógombok egy PDF-dokumentumban a választógomb-beállítások elrendezési tájolására vonatkoznak. A vízszintes elrendezés egymás mellé helyezi a választógomb opcióit, így a felhasználók balról jobbra választhatnak. A függőleges elrendezés viszont egymásra rakja a választógomb opcióit, lehetővé téve a felhasználók számára, hogy felülről lefelé válasszanak.

#### K: Hogyan szabhatom testre a választógomb-beállítások megjelenését az Aspose.PDF for .NET-ben?

V: Testreszabhatja a választógomb-beállítások megjelenését az Aspose.PDF for .NET fájlban több tulajdonság beállításával. Az API lehetőséget biztosít két választógomb közötti távolság beállítására (`RadioGap`), az elrendezés tájolása (`RadioHoriz`), a választógomb elemeinek mérete (`RadioButtonItemSize`), a választógombok szegélyszélessége és színe stb.

#### K: Hozzáadhatok vízszintes és függőleges rádiógombokat is ugyanahhoz a PDF dokumentumhoz?

V: Igen, vízszintes és függőleges választógombokat is hozzáadhat ugyanahhoz a PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Az oktatóanyagban található mintaforráskód bemutatja, hogyan lehet először vízszintesen elhelyezett választógombokat, majd függőlegesen elhelyezett választógombokat hozzáadni ugyanahhoz a PDF-dokumentumhoz.

#### K: Beállíthatok különböző választógomb-beállításokat az egyes választógomb-csoportokhoz?

 V: Igen, minden rádiógomb-csoporthoz különböző választógomb-beállításokat állíthat be. Minden csoportnak egyedinek kell lennie`RadioButtonField` objektum, és a`RadioButtonOptionField` Az egyes csoportokon belüli objektumok ugyanazon az oldalon osztoznak, és egyedi neveket kell megadniuk a beállításokhoz. Ez biztosítja, hogy az egyes csoportokon belüli rádiógombok megfelelően működjenek, és a kijelölések kölcsönösen kizárják egymást.

#### K: Minden PDF-megjelenítő és alkalmazás támogatja a választógombok elrendezését és megjelenési beállításait?

V: Igen, a választógombok elrendezése és megjelenése minden szabványnak megfelelő PDF-megtekintőben és alkalmazásban támogatott. A PDF specifikáció meghatározza a választógombokat és azok különféle attribútumait, így általánosan felismerhetőek a PDF formátumban. Mindazonáltal elengedhetetlen, hogy teszteljük a választógombok megjelenését és viselkedését a különböző PDF-megtekintőkben, hogy biztosítsuk a konzisztens megjelenítést a különböző platformokon.