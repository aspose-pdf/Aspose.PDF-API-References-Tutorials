---
title: Állítsa be a Java Scriptet
linktitle: Állítsa be a Java Scriptet
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan használhatja az Aspose.PDF for .NET fájlt a JavaScript beállításához PDF-fájlok űrlapmezőiben.
type: docs
weight: 270
url: /hu/net/programming-with-forms/set-java-script/
---
Ebben az útmutatóban lépésről lépésre elmagyarázzuk, hogyan használhatjuk az Aspose.PDF könyvtárat .NET-hez JavaScript definiálására egy PDF-dokumentum űrlapmezőjében. Megmutatjuk, hogyan konfigurálhat JavaScript-műveleteket, hogy bizonyos műveleteket hajtsanak végre a szövegmezőben.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- A rendszerére telepített .NET fejlesztői környezet.
- Az Aspose.PDF könyvtár a .NET-hez. Letöltheti az Aspose hivatalos webhelyéről.

## 1. lépés: A dokumentumkönyvtár konfigurálása

 Az első lépés annak a dokumentumkönyvtárnak a konfigurálása, amelyben a dolgozni kívánt PDF-fájl található. Használhatja a`dataDir` változót a könyvtár elérési útjának megadásához.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 2. lépés: A bemeneti PDF fájl betöltése

Ebben a lépésben betöltjük a bemeneti PDF-fájlt a`Document` osztályú Aspose.PDF.

```csharp
// Bemeneti PDF fájl betöltése
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Győződjön meg arról, hogy a bemeneti PDF-fájl megtalálható a megadott dokumentumok könyvtárában.

## 3. lépés: A TextBox mező elérése

 Ahhoz, hogy a JavaScriptet egy adott szövegmezőre alkalmazzuk, először el kell érnünk azt a mezőt. Ebben a példában feltételezzük, hogy a szövegmező neve "textbox1". Használja a`doc.Form["textbox1"]` módszer a megfelelő beszerzéséhez`TextBoxField` tárgy.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Győződjön meg arról, hogy a megadott szövegmező létezik a bemeneti PDF-fájlban.

## 4. lépés: Konfigurálja a JavaScript-műveleteket

 Most, hogy elértük a szövegmezőt, konfigurálhatjuk a mezőhöz tartozó JavaScript-műveleteket. Ebben a példában két műveletet fogunk használni:`OnModifyCharacter` és`OnFormat` . Ezeket a műveleteket a segítségével határozzuk meg`JavascriptAction` tárgyakat.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Ügyeljen arra, hogy a JavaScript-műveleteket igényei szerint szabja testre.

## 5. lépés: A mező kezdeti értékének beállítása

Az így kapott PDF mentése előtt beállíthatunk egy kezdőértéket a szövegmezőnek. Ebben a példában a "123" értéket fogjuk beállítani a mezőben.

```csharp
field.Value = "123";
```

Szabja testre ezt az értéket igényei szerint.

## 6. lépés: Az eredményül kapott PDF mentése

 Most, hogy befejeztük a szövegmező és a JavaScript műveletek beállítását, elmenthetjük a kapott PDF-et a`Save` módszere a`Document` osztály.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Az eredményül kapott PDF mentése
doc.Save(dataDir);
```

Feltétlenül adja meg a kapott PDF teljes elérési útját és fájlnevét.


### Minta forráskód a Set Java Scripthez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Bemeneti PDF fájl betöltése
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 számjegy a pont után
// Nincs elválasztó
// Neg stílus = mínusz
// Nincs valuta
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Állítsa be a mező kezdeti értékét
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Az eredményül kapott PDF mentése
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Következtetés

Ebben az útmutatóban megtanultuk, hogyan használhatja az Aspose.PDF könyvtárat a .NET-hez a JavaScript beállításához egy PDF-dokumentum űrlapmezőjében. A vázolt lépések követésével testreszabhatja a JavaScript-műveleteket, hogy különféle műveleteket hajtson végre a szövegmezőkön. Nyugodtan fedezze fel az Aspose.PDF for .NET szolgáltatásait a PDF-fájlok kezelésének lehetőségeinek bővítése érdekében.


### GYIK

#### K: Használhatom az Aspose.PDF for .NET fájlt a JavaScript hozzáadásához más űrlapelemekhez, például jelölőnégyzetekhez és választógombokhoz?

 V: Igen, az Aspose.PDF for .NET lehetővé teszi JavaScript hozzáadását különböző űrlapelemekhez, beleértve a jelölőnégyzeteket, választógombokat és legördülő listákat. Használhatja a`JavascriptAction` osztály JavaScript-műveletek meghatározásához különböző űrlapelemekhez.

#### K: Lehetséges a felhasználói bevitel érvényesítése JavaScript használatával az űrlapmezőkben?

 V: Igen, használhatja a JavaScriptet a felhasználói bevitel érvényesítésére az űrlapmezőkben. JavaScript-műveletek meghatározásával, mint pl`OnBlur` vagy`OnKeystroke` űrlapmezőnél a bevitt adatokat érvényesíteni tudja, és szükség esetén hibaüzeneteket is megjeleníthet.

#### K: Végrehajthatok összetett JavaScript-függvényeket az Aspose.PDF for .NET használatával?

 V: Igen, végrehajthat összetett JavaScript-függvényeket az Aspose.PDF for .NET használatával. Rugalmasan definiálhat egyéni JavaScript-függvényeket, és meghívhatja őket a`JavascriptAction`.

#### K: Az Aspose.PDF for .NET támogatja az oktatóanyagban említettektől eltérő JavaScript-eseményeket?

 V: Igen, az Aspose.PDF for .NET támogatja a JavaScript-események széles skáláját, beleértve`OnMouseEnter`, `OnMouseExit`, `OnMouseDown` , és`OnMouseUp`, többek között. Ezekkel az eseményekkel JavaScript-műveleteket indíthat el a felhasználói interakciók alapján.

#### K: Használhatom az Aspose.PDF for .NET fájlt JavaScript-kód kinyerésére a meglévő PDF dokumentumokból?

 V: Az Aspose.PDF for .NET lehetőséget biztosít JavaScript-kód kinyerésére a meglévő PDF dokumentumokból. Használhatja a`JavascriptAction` osztályt és más releváns módszereket a JavaScript-műveletek eléréséhez és elemzéséhez PDF-formátumban.