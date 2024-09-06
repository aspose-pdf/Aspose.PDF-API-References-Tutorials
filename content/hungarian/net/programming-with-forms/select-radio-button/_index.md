---
title: Válassza a rádiógombot a PDF-dokumentumban
linktitle: Válassza a rádiógombot a PDF-dokumentumban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan választhat ki választógombot PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 250
url: /hu/net/programming-with-forms/select-radio-button/
---
Itt található egy részletes oktatóanyag a választógomb kiválasztásához az Aspose.PDF for .NET használatával. Kövesse az alábbi lépéseket:

##  1. lépés: Kezdje a dokumentumok könyvtárának meghatározásával az elérési út megadásával a`dataDir` variable.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

##  2. lépés: Nyissa meg a PDF dokumentumot a`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## 3. lépés: Szerezze be a választógomb mezőt a dokumentuműrlapból.

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## 4. lépés: Adja meg a csoportból kiválasztandó választógomb indexét.

```csharp
radioField. Selected = 2;
```

## 5. lépés: Állítsa be a szerkesztett PDF-fájl kimeneti útvonalát.

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## 6. lépés: Mentse el a módosított PDF-fájlt.

```csharp
pdfDocument.Save(dataDir);
```

## 7. lépés: Jelenítsen meg egy megerősítő üzenetet és a mentett fájl helyét.

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### Select Radio Button minta forráskódja az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Nyissa meg a dokumentumot
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	// Szerezz egy mezőt
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	// Adja meg a csoport rádiógombjának indexét
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	// Mentse el a PDF fájlt
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan válasszunk rádiógombot az Aspose.PDF for .NET használatával. A fent vázolt lépések követésével az Aspose.PDF for .NET segítségével manipulálhatja és módosíthatja a PDF-dokumentumokban lévő választógombokat.


### GYIK

#### K: Kijelölhetek több választógombot egy csoportban az Aspose.PDF for .NET használatával?

V: Nem, a csoport rádiógombjait úgy tervezték, hogy kizárják egymást. Egy csoporton belül egyszerre csak egy választógombot jelölhet ki, és ha egyet választ, akkor az ugyanabban a csoportban korábban kiválasztott választógombok kijelölése automatikusan megszűnik.

#### K: Hogyan kérhetem le a kiválasztott rádiógombot egy csoportban az Aspose.PDF for .NET használatával?

 V: A kiválasztott választógomb csoportban történő lekéréséhez használja a`Selected` tulajdona a`RadioButtonField` osztály. Visszaadja a kiválasztott rádiógomb indexét a csoporton belül.

#### K: Testreszabhatom a kiválasztott választógomb megjelenését a PDF dokumentumban?

V: Igen, testreszabhatja a kiválasztott választógomb megjelenését az Aspose.PDF for .NET használatával. Módosíthatja színét, méretét, szegélystílusát és egyéb vizuális attribútumait, hogy megfeleljen a kívánt megjelenésnek.

#### K: Lehetséges új választógomb-csoportok programozott létrehozása az Aspose.PDF for .NET használatával?

V: Igen, programozottan is létrehozhat új választógomb-csoportokat az Aspose.PDF for .NET használatával. Új választógombokat adhat a dokumentum űrlapjához, és minden választógombhoz ugyanazt a csoportnevet adhatja meg új csoport létrehozásához.

#### K: Az Aspose.PDF for .NET támogatja az interaktív PDF-űrlapokkal való munkát?

V: Igen, az Aspose.PDF for .NET teljes mértékben támogatja az interaktív PDF-űrlapokkal való munkát, beleértve a választógombokat, szövegmezőket, jelölőnégyzeteket és egyéb űrlapelemeket. A könyvtár segítségével könnyen olvashat, módosíthat és hozhat létre interaktív PDF-űrlapokat.