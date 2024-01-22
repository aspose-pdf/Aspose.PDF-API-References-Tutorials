---
title: Űrlapmező 14. betűtípusa
linktitle: Űrlapmező 14. betűtípusa
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET segítségével könnyedén beállíthatja a PDF-dokumentumok űrlapmezőinek betűtípusát.
type: docs
weight: 110
url: /hu/net/programming-with-forms/form-field-font-14/
---
Ebben az oktatóanyagban bemutatjuk, hogyan konfigurálhatja egy űrlapmező betűtípusát az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Először győződjön meg arról, hogy importálta a szükséges könyvtárakat, és állítsa be a dokumentumok könyvtárának elérési útját:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Nyissa meg a dokumentumot

Nyissa meg a meglévő PDF dokumentumot:

```csharp
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
```

## 3. lépés: Szerezzen be egy adott űrlapmezőt

Szerezze be a kívánt űrlapmezőt (ebben a példában a "textbox1" mezőt használjuk):

```csharp
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
```

## 4. lépés: Hozzon létre egy font objektumot

Hozzon létre egy betűtípus objektumot a használni kívánt új betűtípushoz (például "ComicSansMS"):

```csharp
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
```

## 5. lépés: Konfigurálja a betűtípus-információkat az űrlapmezőhöz

Állítsa be az űrlapmező fontinformációit a korábban létrehozott betűtípus használatával:

```csharp
field.DefaultAppearance = new Aspose.Pdf.Forms.DefaultAppearance(font, 14, System.Drawing.Color.Black);
```

## 6. lépés: Mentse el a frissített dokumentumot

Mentse el a frissített PDF dokumentumot:

```csharp
dataDir = dataDir + "FormFieldFont14_out.pdf";
pdfDocument.Save(dataDir);
```


### Minta forráskód a Form Field Font 14-hez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "FormFieldFont14.pdf");
// Adott űrlapmező lekérése a dokumentumból
Aspose.Pdf.Forms.Field field = pdfDocument.Form["textbox1"] as Aspose.Pdf.Forms.Field;
// Hozzon létre font objektumot
Aspose.Pdf.Text.Font font = FontRepository.FindFont("ComicSansMS");
// Állítsa be az űrlapmező betűtípus-információit
// Field.DefaultAppearance = new Aspose.Pdf.Forms.in.DefaultAppearance(font, 10, System.Drawing.Color.Black);
dataDir = dataDir + "FormFieldFont14_out.pdf";
// Mentse el a frissített dokumentumot
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field font setup successfully.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan kell beállítani egy űrlapmező betűtípusát az Aspose.PDF for .NET használatával. Az alábbi lépések követésével az Aspose.PDF használatával egyszerűen megadhatja a PDF-dokumentumok űrlapmezőinek betűtípusát és betűméretét.

### GYIK

#### K: Használhatok bármilyen betűtípust az Aspose.PDF for .NET űrlapmezőihez?

V: Igen, bármilyen TrueType vagy OpenType betűtípust használhat az Aspose.PDF for .NET űrlapmezőihez. Mindaddig, amíg a betűtípus elérhető és telepítve van a rendszeren, vagy elérhető a FontRepository-n keresztül, használhatja az űrlapmező szövegének megjelenését testreszabhatja.

#### K: Hogyan találhatom meg az elérhető betűtípusokat az Aspose.PDF for .NET fájlban?

 V: Az elérhető betűtípusok megkereséséhez az Aspose.PDF for .NET fájlban, használja a`FontRepository.GetAvailableFonts()`módszer. Ez a módszer a rendelkezésre álló betűtípusok tömbjét adja vissza, amelyeket űrlapmezőkhöz vagy bármely más, szöveggel kapcsolatos művelethez használhat a PDF-dokumentumban.

#### K: Módosíthatom az űrlapmezők betűméretét bármilyen értékre?

V: Igen, az űrlapmezők betűméretét bármilyen pozitív számértékre módosíthatja az Aspose.PDF for .NET használatával. Azonban elengedhetetlen annak biztosítása, hogy a betűméret megfeleljen az adott űrlapmezőnek, és ne vezessen a szöveg csonkolásához vagy a dokumentum más elemeivel való átfedéshez.

#### K: Módosíthatom az űrlapmezők betűszínét?

V: Igen, módosíthatja az űrlapmezők betűszínét az Aspose.PDF for .NET segítségével. A mellékelt C# forráskódban a betűszín feketere van állítva (`System.Drawing.Color.Black`), de testreszabhatja bármely más érvényes színértékre.

#### K: Hogyan igazíthatom a szöveget az űrlapmezőn belül?

 V: Az űrlapmezőn belüli szöveg igazításához használja a`Multiline`az űrlapmező tulajdonságát, és állítsa igazra. Ez a tulajdonság többsoros szöveget tesz lehetővé az űrlapmezőn belül, lehetővé téve a szövegigazítás szabályozását sortörésekkel és kocsivisszaadásokkal.