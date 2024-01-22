---
title: Űrlapmező mozgatása
linktitle: Űrlapmező mozgatása
second_title: Aspose.PDF for .NET API Reference
description: Könnyen mozgathatja az űrlapmezőket PDF-dokumentumaiban az Aspose.PDF for .NET segítségével.
type: docs
weight: 200
url: /hu/net/programming-with-forms/move-form-field/
---
Ebben az oktatóanyagban bemutatjuk, hogyan helyezhet át egy űrlapmezőt egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse be a dokumentumot

Töltse be a meglévő PDF dokumentumot:

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## 3. lépés: Szerezze be az űrlapmezőt

Szerezze meg az áthelyezni kívánt űrlapmezőt:

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 4. lépés: Mező helyének módosítása

Módosítsa az űrlapmező helyét egy új téglalap alakú terület meghatározásával:

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## 5. lépés: Mentse el a szerkesztett dokumentumot

Mentse el a módosított PDF dokumentumot:

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### Forráskód minta a Move Form Field-hez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Nyissa meg a dokumentumot
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
// Szerezz egy mezőt
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
// Módosítsa a mező helyét
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
// Módosított dokumentum mentése
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet áthelyezni egy űrlapmezőt egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Az alábbi lépések követésével könnyedén navigálhat egy adott mezőre, és szükség szerint módosíthatja a helyét.


### GYIK

#### K: Áthelyezhetek több űrlapmezőt egyetlen PDF-dokumentumban az Aspose.PDF for .NET használatával?

V: Igen, több űrlapmezőt is áthelyezhet egyetlen PDF-dokumentumon belül az Aspose.PDF for .NET használatával. Egyszerűen ismételje meg a folyamatot minden áthelyezni kívánt űrlapmezőnél.

#### K: Egy űrlapmező áthelyezése hatással lesz a hozzá tartozó adatokra vagy funkciókra?

V: Nem, egy űrlapmező áthelyezése nincs hatással a kapcsolódó adatokra vagy funkciókra. Az űrlapmező minden tulajdonságát és értékét megőrzi, miután új helyre került.

#### K: Hogyan határozhatom meg az űrlapmező új helyének pontos koordinátáit?

 V: Az új helyet a gombbal adhatja meg`Aspose.Pdf.Rectangle` osztályban, ahol megadja a téglalapterület bal felső sarkának X és Y koordinátáit, valamint a jobb alsó sarkának X és Y koordinátáit.

#### K: Az Aspose.PDF for .NET kompatibilis mind Windows, mind Linux környezettel?

V: Igen, az Aspose.PDF for .NET kompatibilis Windows és Linux környezetekkel is, így rugalmasságot biztosít a fejlesztők számára, hogy az általuk preferált operációs rendszerekkel dolgozhassanak.