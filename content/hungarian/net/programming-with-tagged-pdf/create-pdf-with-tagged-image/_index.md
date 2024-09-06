---
title: PDF létrehozása címkézett képpel
linktitle: PDF létrehozása címkézett képpel
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre útmutató címkézett képet tartalmazó PDF létrehozásához az Aspose.PDF for .NET használatával.
type: docs
weight: 40
url: /hu/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan hozhat létre címkézett képet tartalmazó PDF-dokumentumot az Aspose.PDF for .NET használatával. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi PDF-dokumentumok programozott létrehozását, kezelését és konvertálását. Az Aspose.PDF címkézett tartalomszerkezeti funkcióival címkézett képeket adhat hozzá PDF-dokumentumához.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Visual Studio .NET keretrendszerrel telepítve.
2. Az Aspose.PDF könyvtár a .NET-hez.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új projektet a Visual Studióban, és adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz. Letöltheti a könyvtárat az Aspose hivatalos webhelyéről, és telepítheti a gépére.

## 2. lépés: Importálja a szükséges névtereket

A C# kódfájlba importálja az Aspose.PDF által biztosított osztályok és metódusok eléréséhez szükséges névtereket:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3. lépés: A PDF-dokumentum létrehozása címkézett képpel

A következő kóddal hozzon létre egy címkézett képet tartalmazó PDF-dokumentumot:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Ez a kód egy üres PDF-dokumentumot hoz létre, és hozzáad egy címkézett képet az Aspose.PDF által biztosított módszerekkel. A kép alternatív szöveggel, címmel és címkével van megadva.

## 4. lépés: Mentse el a PDF-dokumentumot

A PDF dokumentum mentéséhez használja a következő kódot:

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Ez a kód a címkézett képet tartalmazó PDF-dokumentumot egy megadott fájlba menti.

### Minta forráskód: Create PDF with Tagged Image with Aspose.PDF for .NET 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Kép hozzáadása 300 DPI felbontással (alapértelmezés szerint)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF dokumentum mentése
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan hozhat létre címkézett képet tartalmazó PDF-dokumentumot az Aspose.PDF for .NET használatával. A címkézett képek további, strukturált információkat adnak a PDF-dokumentumhoz.

### GYIK

#### K: Mi a célja egy címkézett képet tartalmazó PDF-dokumentum létrehozásának az Aspose.PDF for .NET használatával?

V: A címkézett képet tartalmazó PDF-dokumentum létrehozása az Aspose.PDF for .NET használatával lehetővé teszi címkézett képek hozzáadását a dokumentum tartalmához. A címkézett képek strukturált információkat nyújtanak, például alternatív szöveget és címeket, javítva a hozzáférhetőséget és a rendszerezést.

#### K: Hogyan segít az Aspose.PDF könyvtár címkézett képet tartalmazó PDF-dokumentum létrehozásában?

V: Az Aspose.PDF for .NET egy robusztus könyvtár, amely funkciókat biztosít PDF-dokumentumok programozott létrehozásához, kezeléséhez és konvertálásához. Ebben az oktatóanyagban a könyvtár címkézett tartalomszerkezeti funkcióit használjuk felcímkézett kép hozzáadására a PDF-dokumentumhoz.

#### K: Milyen előfeltételei vannak egy címkézett képet tartalmazó PDF-dokumentum létrehozásának az Aspose.PDF for .NET használatával?

V: Mielőtt elkezdené, győződjön meg arról, hogy a Visual Studio telepítve van a .NET-keretrendszerrel, és hivatkozott-e a projektben a .NET-hez készült Aspose.PDF könyvtárra.

#### K: Hogyan hoz létre a mellékelt C# kód címkézett képet tartalmazó PDF dokumentumot?

V: A kód bemutatja, hogyan hozhat létre PDF-dokumentumot, hogyan határozhat meg egy címkézett képelemet, és hogyan adhatja hozzá a dokumentum tartalmához. A címkézett kép alternatív szöveget, címet és címkét tartalmaz az Aspose.PDF által biztosított módszerekkel.

#### K: Használhatok különböző képformátumokat a címkézett képhez?

V: Igen, különböző képformátumokat használhat a címkézett képhez, például JPEG, PNG, GIF stb. Az oktatóanyagban található kódpélda JPEG képet használ, de lecserélheti egy képfájl elérési útjára a kívánt formátumot.

#### K: Hogyan használják az alternatív szöveget (alternatív szöveget) a címkézett képekben?

 V: Az alternatív szöveg szöveges leírást ad a képről, amelyet a képernyőolvasók felolvasnak a látássérült felhasználók számára. A megadott kódban az alternatív szöveg a következővel van beállítva`AlternativeText` tulajdona a`IllustrationElement` a címkézett képet reprezentálja.

####  K: Hogyan működik a`SetTitle` method contribute to the PDF document's tagged image?

 V: A`SetTitle` metódus beállítja a PDF-dokumentum címkézett tartalmának címét, további kontextust biztosítva a címkézett képhez. Ez a cím segíthet azonosítani a címkézett tartalom célját vagy tárgyát.

#### K: Testreszabhatom a címkézett kép címkéjét és címét?

 V: Igen, testreszabhatja a címkézett kép címkéjét és címét a`SetTag` és`Title` módszerei a`IllustrationElement`. A kódpélda bemutatja, hogyan kell a címkét „Fig”-re, a címet pedig „1. képre” állítani.

#### K: Hogyan biztosíthatom, hogy a megcímkézett kép hozzáférhető legyen, és megfeleljen a kisegítő lehetőségek szabványainak?

V: Az Aspose.PDF címkézett tartalomszerkezeti funkcióinak használatával, valamint alternatív szövegek és egyéb releváns információk megadásával hozzájárul a címkézett kép hozzáférhetőségéhez. Az akadálymentesítési szabványoknak való megfelelés biztosítása magában foglalja az alternatív szöveg és a dokumentumstruktúra bevált gyakorlatainak követését.

#### K: Lehetséges több címkézett képet hozzáadni ugyanahhoz a PDF-dokumentumhoz hasonló technikákkal?

 V: Igen, több címkézett képet is hozzáadhat ugyanahhoz a PDF-dokumentumhoz hasonló technikákkal. Létrehozna további`IllustrationElement` példányokat minden egyes címkézett képhez, és szükség szerint testreszabhatja tulajdonságaikat.