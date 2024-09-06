---
title: Szövegdoboz
linktitle: Szövegdoboz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre szövegmezőt PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 290
url: /hu/net/programming-with-forms/text-box/
---
Ebben az útmutatóban lépésről lépésre elmagyarázzuk, hogyan használhatja az Aspose.PDF könyvtárat .NET-hez szövegmező létrehozásához PDF-dokumentumban. Megmutatjuk, hogyan lehet megnyitni a dokumentumot, létrehozni a szövegmezőt, testreszabni a tulajdonságait, és elmenteni a szerkesztett PDF-et.

## 1. lépés: A dokumentumkönyvtár konfigurálása

 Az első lépés annak a dokumentumkönyvtárnak a konfigurálása, amelyben a dolgozni kívánt PDF-fájl található. Használhatja a`dataDir` változót a könyvtár elérési útjának megadásához.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 2. lépés: Nyissa meg a PDF dokumentumot

 Ebben a lépésben megnyitjuk a PDF dokumentumot a`Document` osztályú Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Győződjön meg arról, hogy a PDF fájl megtalálható a megadott dokumentumok könyvtárában.

## 3. lépés: A szövegmező létrehozása

 Létrehozunk egy szövegmezőt a`TextBoxField` osztály. A pozíció koordinátáit és a mező méretét a segítségével adhatja meg`Rectangle` osztály.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Igény szerint testreszabhatja a koordinátákat, a méretet, a részleges nevet és a szövegmező értékét.

## 4. lépés: A szövegmező tulajdonságainak testreszabása

Ebben a lépésben testre szabjuk a szövegmező tulajdonságait, például keret, szín stb.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Szabja testre a szövegmező tulajdonságait preferenciái szerint.

## 5. lépés: A mező hozzáadása a dokumentumhoz

Most, hogy létrehoztuk és konfiguráltuk a szövegmezőt, hozzáadhatjuk a PDF dokumentumhoz.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## 6. lépés: A módosított PDF mentése

 Végül a módosított PDF-et a`Save` módszere a`Document` osztály.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Feltétlenül adja meg a szerkesztett PDF teljes elérési útját és fájlnevét.

### Minta forráskód a Text Box számára az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//Hozzon létre egy mezőt
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = new Border(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Mező hozzáadása a dokumentumhoz
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Módosított PDF mentése
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az útmutatóban megtanultuk, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez szövegmező létrehozásához PDF-dokumentumban. A leírt lépéseket követve testreszabhatja a szövegmező tulajdonságait, és szükség szerint hozzáadhatja a dokumentumhoz. Nyugodtan fedezze fel az Aspose.PDF for .NET szolgáltatásait a PDF-fájlok kezelésének lehetőségeinek bővítése érdekében.

### GYIK

#### K: Használhatom az Aspose.PDF for .NET fájlt több szövegmező létrehozására egyetlen PDF dokumentumban?

V: Igen, több szövegmezőt is létrehozhat egyetlen PDF-dokumentumban az Aspose.PDF for .NET használatával. Egyszerűen ismételje meg a szövegmezők létrehozásának és testreszabásának folyamatát a dokumentum minden kívánt helyéhez.

#### K: Hogyan szabhatom testre a szövegmező megjelenését, például a betűméretet és a színt?

V: Testreszabhatja a szövegmező megjelenését a tulajdonságainak, például a betűméret, a betűstílus, a szín, a szegélystílus, a háttérszín és egyebek módosításával. A minta forráskódban a szegély szélessége, a szegélyvonal mintázata és a szöveg színe testreszabott.

#### K: Kibontható a felhasználó által beírt szöveg a létrehozott szövegmezőből?

V: Igen, kibonthatja a felhasználó által beírt szöveget a létrehozott szövegmezőből. Miután a felhasználók kitöltötték a szövegmezőt a PDF-dokumentumban, programozottan lekérheti a mező értékét az Aspose.PDF for .NET használatával.

#### K: Hozzáadhatok szövegmezőket egy meglévő PDF-dokumentumhoz új létrehozása nélkül?

V: Igen, hozzáadhat szövegmezőket egy meglévő PDF-dokumentumhoz anélkül, hogy újat hozna létre. Az Aspose.PDF for .NET lehetővé teszi a meglévő PDF-dokumentumok módosítását, beleértve a szövegmezők, jelölőnégyzetek és egyéb űrlapelemek hozzáadását.

#### K: Az Aspose.PDF for .NET támogat más típusú űrlapmezőket, például jelölőnégyzeteket és rádiógombokat?

V: Igen, az Aspose.PDF for .NET különféle típusú űrlapmezőket támogat, beleértve a jelölőnégyzeteket, választógombokat, legördülő listákat stb. A könyvtár segítségével különféle típusú űrlapelemekkel dolgozhat a PDF dokumentumokban.