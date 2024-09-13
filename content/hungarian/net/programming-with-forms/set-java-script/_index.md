---
title: Állítsa be a Java Scriptet
linktitle: Állítsa be a Java Scriptet
second_title: Aspose.PDF for .NET API Reference
description: Fedezze fel az Aspose.PDF for .NET erejét. Lépésről lépésre szóló útmutatónk segítségével megtudhatja, hogyan állíthat be JavaScriptet űrlapmezőkön.
type: docs
weight: 270
url: /hu/net/programming-with-forms/set-java-script/
---
## Bevezetés

A dinamikus és interaktív PDF-ek létrehozása jelentősen javíthatja a felhasználói élményt, különösen akkor, ha űrlapokat és mezőket integrál egy dokumentumba. Az egyik hatékony könyvtár, amely ezt lehetővé teszi, az Aspose.PDF for .NET. Ebben a cikkben részletesen bemutatjuk a JavaScript beállítását az űrlapmezők számára az Aspose.PDF használatával, biztosítva ezzel, hogy a PDF-fájlok ne csak jól nézzenek ki, hanem szépen működjenek is.

## Előfeltételek

Mielőtt belevágnánk a kódolásba, győződjünk meg arról, hogy mindennel rendelkezünk, ami a zökkenőmentes követéshez szükséges:

- Visual Studio (vagy bármely .NET IDE): Győződjön meg arról, hogy megfelelően telepítette és beállította.
  
-  Aspose.PDF Library: Szüksége lesz a könyvtár legújabb verziójára. Letöltheti[itt](https://releases.aspose.com/pdf/net/).

- Alapvető C# ismerete: A C# programozás ismerete segít jobban megérteni a kódrészleteket.

-  PDF-fájlok: rendelkeznie kell egy PDF-fájllal, amely készen áll a tesztelésre. Példánkban egy nevű fájlt fogunk használni`SetJavaScript.pdf`.

- Az Ön dokumentumkönyvtára: Tudja, hol tárolja dokumentumfájljait. Erre az útvonalra hivatkozunk a kódunkban.

Ha készen vannak ezek az előfeltételek, milyen eszközöket fogunk használni? Vizsgáljuk meg, mire képes az Aspose.PDF.

## Csomagok importálása

A kezdéshez fel kell vennie a szükséges névtereket a C# projektbe. Nyissa meg a fő C# fájlt, és adja hozzá a következő importálási utasításokat:

```csharp
using System;
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Ezek a névterek hozzáférést biztosítanak a PDF-hez és az űrlapokhoz kapcsolódó funkciókhoz az Aspose.PDF könyvtárban.

Készen áll a PDF interaktívvá tételére? Fogja meg a kódoló sapkát, és bontsa le ezt lépésről lépésre!

## 1. lépés: Határozza meg a dokumentum elérési útját

Először is meg kell adnunk a PDF-fájlunk helyét. Ez megadja a terepet mindennek, ami ezután következik. Íme, hogyan kell csinálni:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a PDF-fájl tényleges elérési útjával. Tekintsd ezt úgy, mint egy kincses térkép koordinátáit – tudnod kell, hol jelöli az „X” a pontot!

## 2. lépés: Töltse be a PDF-dokumentumot

Miután meghatároztuk a könyvtárat, betöltjük a PDF fájlunkat. 

```csharp
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Ez a sor megnyitja a megadott PDF-fájlt, és előkészíti a manipulációra. 

## 3. lépés: Nyissa meg az Űrlapmezőt

Ezután szeretnénk elérni az űrlapmezőt, ahol alkalmazni fogjuk a JavaScriptünket. 

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

 Itt feltételezzük, hogy a PDF-ben van egy elnevezésű szövegdoboz`textbox1`. Ha nincs ilyen nevű mezője, átnevezheti, vagy ennek megfelelően módosíthatja a kódot. 

## 4. lépés: Állítsa be a JavaScript-műveleteket

Most pedig adjunk hozzá néhány funkciót a szövegdobozunkhoz! Beállítunk JavaScript-műveleteket, amelyek bizonyos eseményeknél aktiválódnak. 

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Íme, mi történik:
- OnModifyCharacter: Ez a JavaScript-függvény határozza meg, hogy a mező hogyan viselkedjen egy karakter módosításakor. Ebben az esetben két tizedesvesszőt engedélyez a szám után elválasztó nélkül.
- OnFormat: Ez biztosítja, hogy amikor a felhasználó formázza a számot, az ugyanazt a szabályt tartja be.

E műveletek beállításával lényegében személyiséget adunk a szövegdobozunknak – mintha táncmozdulatot tanítanánk neki!

## 5. lépés: Inicializálja a mező értékét

Ezután adjunk kiindulási pontot a szövegdobozunknak egy kezdőérték beállításával. 

```csharp
field.Value = "123";
```

Ez a sor "123"-at állít be előre kitöltött értékként a szövegmezőben. Olyan ez, mint egy színpadot előkészíteni egy előadásra.

## 6. lépés: Mentse el a módosított PDF fájlt

Végül el kell mentenünk a dokumentumunkat az összes módosítás után.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
doc.Save(dataDir);
```

 Ez frissíti az eredeti fájlt a változtatásokkal, és más néven menti`Restricted_out.pdf`. Tekintsd ezt úgy, mint a PDF-ünk sorsának megpecsételését – a mentés után készen áll a világra!

## 7. lépés: Erősítse meg a sikert

Végül nézzük meg, hogy minden rendben ment-e. 

```csharp
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

Ennek az üzenetnek a futtatása megnyugtatja Önt arról, hogy a művelet sikeresen befejeződött, akárcsak a közönség tapsa egy nagyszerű előadás után.

## Következtetés

Gratulálok! Sikeresen beállította a JavaScriptet a PDF-fájl űrlapmezőihez az Aspose.PDF for .NET használatával. Ez az oktatóanyag nemcsak eszközöket adott a felhasználói interakció javításához, hanem arra is lehetőséget adott, hogy profi módon személyre szabja dokumentumait. Akár számlákban, felmérésekben vagy más interaktív PDF-dokumentumokban lévő űrlapokkal dolgozik, a lehetőségek valóban végtelenek.

### GYIK

### Mi az Aspose.PDF for .NET?  
Az Aspose.PDF egy olyan könyvtár, amelyet PDF-fájlok létrehozására, szerkesztésére és manipulálására terveztek .NET-alkalmazásokon belül, és hatékony PDF-funkciókat biztosít.

### Szükségem van engedélyre az Aspose.PDF használatához?  
 Bár ingyenes próbaverzió áll rendelkezésre, a korlátozások nélküli teljes használathoz licenc szükséges. Vásárolhat licencet[itt](https://purchase.aspose.com/buy).

### Beállíthatom a JavaScriptet más típusú űrlapmezőkre?  
Teljesen! Az Aspose.PDF lehetővé teszi a JavaScript-műveleteket különféle űrlapmezőkön, például jelölőnégyzeteken, választógombokon és legördülő listákon.

### Hogyan kaphatok támogatást az Aspose.PDF-problémákhoz?  
 A támogatást rajtuk keresztül érheti el[fórum](https://forum.aspose.com/c/pdf/10) bármilyen kérdés vagy probléma esetén.

### Van mód az Aspose.PDF tesztelésére vásárlás nélkül?  
Igen! Az Aspose biztosít a[ingyenes próbaverzió](https://releases.aspose.com/) hogy tesztelje a könyvtár funkcióit a vásárlás előtt.