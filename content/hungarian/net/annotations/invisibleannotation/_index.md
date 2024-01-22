---
title: Láthatatlan megjegyzés PDF fájlban
linktitle: Láthatatlan megjegyzés PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan készíthet láthatatlan megjegyzéseket PDF-fájlban C# forráskóddal az Aspose.PDF for .NET segítségével. Lépésről lépésre útmutató.
type: docs
weight: 100
url: /hu/net/annotations/invisibleannotation/
---
A PDF-fájlban található megjegyzések egy hatékony funkció, amely lehetővé teszi további információk vagy megjegyzések hozzáadását a dokumentumhoz a tényleges tartalom megváltoztatása nélkül. Használhatók szöveg kiemelésére, a figyelem felhívására a dokumentum bizonyos területeire, illetve megjegyzések vagy visszajelzések hozzáadására.

A PDF-dokumentumokban számos különböző típusú megjegyzés használható, többek között:

- Szöveges megjegyzések
- Link megjegyzések
- Bélyegjegyzetek
- Hangjegyzetek
- Fájlmelléklet megjegyzések
- és még sok más

## 1. lépés: Láthatatlan megjegyzés létrehozása PDF-dokumentumban az Aspose.PDF for .NET használatával

 Ha láthatatlan megjegyzést szeretne létrehozni egy PDF-dokumentumban az Aspose.PDF for .NET használatával, először létre kell hoznunk egy`FreeTextAnnotation` objektumot, és adja meg a megjegyzés helyét és méretét.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 A fenti kódban létrehozunk egy`FreeTextAnnotation`objektumot, és adja meg a megjegyzés helyét a PDF-dokumentum 2. oldalán. Meghatározzuk a megjegyzésben megjelenő szöveg betűtípusát, méretét és színét is.

## 2. lépés: Jellemzők hozzáadása a láthatatlan megjegyzéshez

Ezután hozzáadhatunk néhány jellemzőt a megjegyzéshez, például szegélyszínt, háttérszínt vagy átlátszatlanságot.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

A fenti kódban az annotáció szegélyszínét pirosra állítottuk.

## 3. lépés: A megjegyzésjelzők beállítása

Miután elkészítettük az annotációt és beállítottuk a jellemzőit, megadhatjuk a megjegyzésjelzőket. Ebben az oktatóanyagban azt szeretnénk, hogy a kommentár nyomtatható legyen, de ne legyen megtekinthető.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## 4. lépés: Mentse el a módosított PDF-dokumentumot

Végül elmenthetjük a módosított PDF dokumentumot az új láthatatlan annotációval.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Példa forráskódra a Hogyan készítsünk láthatatlan megjegyzéseket az Aspose.PDF segítségével .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Mentse a kimeneti fájlt
doc.Save(dataDir);
// ExEnd:InvisibleAnnotation
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan hozhatunk létre láthatatlan megjegyzéseket egy PDF-dokumentumban az Aspose.PDF for .NET használatával. A láthatatlan megjegyzések hasznos funkciót jelentenek, ha további információkat vagy megjegyzéseket szeretne hozzáadni egy dokumentumhoz anélkül, hogy azokat az olvasónak megjelenítené. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával a fejlesztők könnyen létrehozhatnak és testreszabhatnak láthatatlan megjegyzéseket PDF-dokumentumaikban. Az Aspose.PDF for .NET átfogó eszközkészletet kínál a megjegyzésekkel való munkához, lehetővé téve a PDF-fájlok interaktivitásának és használhatóságának fokozását.

### GYIK

#### K: Mit jelent a láthatatlan megjegyzés egy PDF-dokumentumban?

V: A PDF-dokumentumban lévő láthatatlan megjegyzés olyan megjegyzés, amely nem látható az oldalon, de további információkat vagy megjegyzéseket tartalmaz. Lehetővé teszi megjegyzések vagy visszajelzések hozzáadását anélkül, hogy azokat az olvasónak megjelenítené.

#### K: Milyen típusú jellemzőket lehet hozzáadni egy láthatatlan megjegyzéshez?

V: A láthatatlan megjegyzésekhez különféle jellemzők adhatók hozzá, például a szegélyszín, a háttérszín, az átlátszatlanság, a betűtípus, a méret és a megjelenítendő szöveg színe.

#### K: Beállíthatok különböző megjegyzésjelzőket egy láthatatlan annotációhoz?

V: Igen, az igényeitől függően különböző megjegyzésjelzőket állíthat be egy láthatatlan annotációhoz. Például beállíthatja a megjegyzést nyomtathatóvá, de nem megtekinthetővé.

#### K: Hogyan adhatok láthatatlan megjegyzést a PDF-dokumentum egy adott oldalához?

 V: Ha láthatatlan megjegyzést szeretne hozzáadni a PDF-dokumentum egy adott oldalához, létre kell hoznia a`FreeTextAnnotation` objektumot, és adja meg a megjegyzés helyét és méretét az oldalon.

#### K: Módosíthatom egy meglévő láthatatlan megjegyzés jellemzőit egy PDF-fájlban?

V: Igen, módosíthatja a PDF-fájlban található láthatatlan megjegyzések jellemzőit az Aspose.PDF for .NET segítségével. Módosíthatja a megjegyzés betűtípusát, méretét, színét, szegélyszínét, háttérszínét, átlátszatlanságát és egyéb tulajdonságait.