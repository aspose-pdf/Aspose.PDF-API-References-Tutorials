---
title: Űrlapmező lekérése lapok sorrendjében
linktitle: Űrlapmező lekérése lapok sorrendjében
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan kérheti le az űrlapmezőket tabulátorok sorrendjében az Aspose.PDF for .NET használatával.
type: docs
weight: 240
url: /hu/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Ha PDF dokumentumokkal dolgozik C# nyelven az Aspose.PDF for .NET használatával, akkor előfordulhat, hogy egy adott lapozási sorrendben kell lekérnie az űrlapmezőket. Ez akkor lehet hasznos, ha műveleteket szeretne végrehajtani az űrlapmezőkön a tabulátorok sorrendje alapján. Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan kérheti le az űrlapmezőket tabulátorok sorrendjében az Aspose.PDF for .NET használatával.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- A Visual Studio telepítve van a rendszerére
- Aspose.PDF for .NET könyvtár telepítve

Most pedig nézzük meg az űrlapmezők tabulátoros sorrendben történő lekérésének lépéseit.

## 1. lépés: A dokumentumkönyvtár beállítása

 Először be kell állítania azt a dokumentumkönyvtárat, amelyben a PDF-dokumentum található. Ezt úgy teheti meg, hogy megadja a könyvtár elérési útját a`dataDir` változó.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 2. lépés: A PDF-dokumentum betöltése

 Ebben a lépésben az Aspose.PDF for .NET használatával töltjük be a PDF-dokumentumot. A`Document` osztály lehetővé teszi a PDF dokumentumok betöltését és kezelését.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Itt,`"Test2.pdf"` betölteni kívánt PDF dokumentum neve. Győződjön meg arról, hogy a dokumentum megtalálható a megadott dokumentumkönyvtárban.

## 3. lépés: Űrlapmezők lekérése lapok sorrendjében

 Az űrlapmezők tabulátor sorrendben történő lekéréséhez el kell érnünk a`FieldsInTabOrder` tulajdona a`Page` osztály. Ez a tulajdonság az űrlapmezők listáját adja vissza a tabulátorok sorrendje szerint rendezve.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

A fenti kódrészletben lekérjük az űrlapmezőket a második oldalról (`doc.Pages[1]` ).`s` változó. Ezt a kódrészletet saját igényei szerint módosíthatja.

## 4. lépés: A lapok sorrendjének módosítása

 Ha módosítani kívánja az űrlapmezők tabulátorsorrendjét, ezt a menüpontban teheti meg`TabOrder` minden mező tulajdonságát, és új tabulátorsorrend-értéket rendel hozzá. Íme egy példa:

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

A fenti kódrészletben új tabulátorsorrendi értékeket rendelünk három űrlapmezőhöz (`doc.Form[3]`, `doc.Form[1]` , és`doc.Form[2]`). Állítsa be a mezőindexeket és a tabulátorok sorrendjének értékeit sajátos igényei szerint.

## 5. lépés: Mentse el a módosított dokumentumot

 Az űrlapmezők tabulátorsorrendjének módosítása után el kell mentenie a módosított dokumentumot. Ezt megteheti a`Save` módszere a`Document` osztály.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Itt,`"39522_out.pdf"` annak a kimeneti fájlnak a neve, amelybe a módosított dokumentum mentésre kerül. Adja meg a kimeneti fájl kívánt nevét és helyét.

### Minta forráskód a Retrieve Form Field In Tab Order (Aspose.PDF for .NET) használatával. 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet lekérni az űrlapmezőket tabulátorok sorrendjében az Aspose.PDF for .NET használatával. Áttekintettük a PDF dokumentum betöltésének lépéseit, az űrlapmezők tabulátor sorrendben történő lekérését, a tabulátorok sorrendjének módosítását és a módosított dokumentum mentését. Ha követi ezeket a lépéseket, hatékonyan dolgozhat az űrlapmezőkkel, és igényei szerint testreszabhatja a tabulátorok sorrendjét.


### GYIK

#### K: Hogyan használhatom fel a C# kódomban található űrlapmezőket további feldolgozáshoz?

 V: A letöltött űrlapmezőket a C#-kódban használhatja, ha hozzáfér a tulajdonságaikhoz, például`Value`, `Name`, `Rect`stb. Ezek a tulajdonságok lehetővé teszik az űrlapmező adatainak igény szerinti olvasását és módosítását.

#### K: Lekérhetem az űrlapmezőket a PDF-dokumentum összes oldaláról tabulátoros sorrendben?

 V: Igen, lekérheti az űrlapmezőket a PDF-dokumentum összes oldaláról az egyes oldalak iterációjával és a`FieldsInTabOrder` tulajdonság az oktatóanyagban látható módon. Ez az űrlapmezőket a tabulátorok sorrendje szerint rendezi az összes oldalon.

#### K: Lehetséges-e csak bizonyos típusú űrlapmezőket, például szövegmezőket vagy jelölőnégyzeteket lekérni tabulátorok sorrendjében?

V: Igen, az űrlapmezőket típusuk, például szövegmezők vagy jelölőnégyzetek alapján szűrheti, miután lekérte őket tabulátorok sorrendjében. Feltételes utasításokkal ellenőrizheti az egyes űrlapmezők típusát, és ennek megfelelően dolgozhatja fel azokat.

#### K: Lekérhetem az űrlapmezőket a nevük alapján a tabulátorok sorrendje helyett?

 V: Igen, a nevük alapján lekérheti az űrlapmezőket a`doc.Form` gyűjtése és a mező nevének indexként való megadása. Például,`doc.Form["fieldName"]`lekéri az űrlapmezőt a megadott névvel.

#### K: Az Aspose.PDF for .NET támogatja a titkosított PDF-dokumentumokkal való munkát?

V: Igen, az Aspose.PDF for .NET támogatja a titkosított PDF dokumentumok kezelését. A megfelelő jelszóparaméterek használatával titkosított PDF-fájlokat tölthet be és kezelhet.