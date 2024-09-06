---
title: Rejtett szövegblokk PDF-fájlban
linktitle: Rejtett szövegblokk PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre rejtett szövegblokkokat PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 230
url: /hu/net/programming-with-text/hidden-text-block/
---
Ebben az oktatóanyagban elmagyarázzuk, hogyan hozhat létre rejtett szövegblokkot PDF-fájlban az Aspose.PDF könyvtár segítségével a .NET-hez. A rejtett szövegblokk egy lebegő szöveg, amely akkor válik láthatóvá, amikor az egérmutatót egy adott terület fölé viszi. Lépésről lépésre végigvesszük a rejtett szövegblokk létrehozásának folyamatát a mellékelt C# forráskód használatával.

## Követelmények

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Az Aspose.PDF for .NET könyvtár telepítve van.
- A C# programozás alapvető ismerete.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

 Először is be kell állítania annak a könyvtárnak az elérési útját, ahová a létrehozott PDF-fájlt menteni szeretné. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változót a kívánt könyvtár elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy mintadokumentumot

Ebben a lépésben létrehozunk egy minta PDF dokumentumot, és hozzáadunk egy szövegrészletet. A szövegrészlet a rejtett szövegblokk megjelenítésének indítójaként fog szolgálni.

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 3. lépés: Nyissa meg a dokumentumot

 Most megnyitjuk a korábban létrehozott dokumentumot a`Document` osztály.

```csharp
Document document = new Document(outputFile);
```

## 4. lépés: Keresse meg a szövegrészletet

 Használjuk a`TextFragmentAbsorber`objektumot, hogy megtalálja azt a szövegrészletet, amely kiváltja a rejtett szövegblokk megjelenítését. Ebben az esetben pontosan a "Vigye ide az egérkurzort a lebegő szöveg megjelenítéséhez" szövegre keresünk.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 5. lépés: Hozza létre a rejtett szövegmezőt

 Létrehozunk a`TextBoxField` objektumot a rejtett szövegmező megjelenítéséhez. Ez a mező tartalmazza azt a szöveget, amely akkor válik láthatóvá, amikor az egérmutatót a trigger szövege fölé viszi.

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## 6. lépés: Adja hozzá a rejtett szövegmezőt a dokumentumhoz

A rejtett szövegmezőt hozzáadjuk a dokumentum űrlapgyűjteményéhez.

```csharp
document.Form.Add(floatingField);
```

## 7. lépés: Hozza létre a Láthatatlan gombot

Létrehozunk egy láthatatlan gombmezőt, amely a trigger szövegrészlet tetejére kerül. Ebben a gombmezőben az egér be- és kilépési eseményeivel kapcsolatos műveletek találhatók.

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 8. lépés: Mentse el a dokumentumot

Végül elmentjük a módosított dokumentumot a rejtett szövegtömbbel.

```csharp
document. Save(outputFile);
```

### Minta forráskód a rejtett szövegblokkhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
// Készítsen mintadokumentumot szöveggel
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
// Nyissa meg a dokumentumot szöveggel
Document document = new Document(outputFile);
// Hozzon létre TextAbsorber objektumot a reguláris kifejezésnek megfelelő kifejezések megtalálásához
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
// Fogadja el a dokumentumoldalak elnyelőjét
document.Pages.Accept(absorber);
// Szerezd meg az első kivont szövegrészletet
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//Rejtett szövegmező létrehozása a lebegő szöveghez az oldal megadott téglalapjában
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
// Állítsa be a mező értékeként megjelenítendő szöveget
floatingField.Value = "This is the \"floating text field\".";
// Javasoljuk, hogy ennél a forgatókönyvnél állítsa be a „csak olvasható” mezőt
floatingField.ReadOnly = true;
// Állítsa be a „rejtett” jelzőt, hogy a mező láthatatlan legyen a dokumentum megnyitásakor
floatingField.Flags |= AnnotationFlags.Hidden;
// Egyedi mezőnév beállítása nem szükséges, de megengedett
floatingField.PartialName = "FloatingField_1";
// A terepi megjelenés jellemzőinek beállítása nem szükséges, de jobbá teszi
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
// Szövegmező hozzáadása a dokumentumhoz
document.Form.Add(floatingField);
// Láthatatlan gomb létrehozása a szövegrészlet pozíciójában
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
// Hozzon létre új elrejtési műveletet a megadott mezőhöz (jegyzet) és láthatatlansági jelzőhöz.
// (A lebegő mezőt a névvel is hivatkozhat, ha fent megadta.)
// Adjon hozzá műveleteket az egér be-/kilépésekor a láthatatlan gombmezőben
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
// Gombmező hozzáadása a dokumentumhoz
document.Form.Add(buttonField);
// Dokumentum mentése
document.Save(outputFile);
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan hozhat létre rejtett szövegblokkot az Aspose.PDF for .NET könyvtár használatával. A lépésenkénti útmutatót követve PDF-dokumentumot hozhat létre rejtett szövegmezővel, amely akkor válik láthatóvá, amikor az egérmutatót egy adott terület fölé viszi. Igényeinek megfelelően testreszabhatja a rejtett szövegblokk megjelenését és viselkedését.

### GYIK

#### K: Mi a célja a „Rejtett szövegblokk PDF-fájlban” című oktatóanyagnak?

V: A „Rejtett szövegblokk PDF-fájlban” című oktatóanyag elmagyarázza, hogyan hozhat létre rejtett szövegblokkot PDF-fájlban az Aspose.PDF-könyvtár használatával a .NET-hez. A rejtett szövegblokk egy lebegő szöveg, amely akkor válik láthatóvá, amikor az egérmutatót egy adott terület fölé viszi. Ez az oktatóanyag lépésenkénti útmutatót nyújt a C# forráskód használatával.

#### K: Miért szeretnék rejtett szövegblokkot létrehozni egy PDF-fájlban?

V: A rejtett szövegblokk létrehozása hasznos lehet olyan interaktív PDF-dokumentumoknál, ahol további információkat vagy kontextust kíván megadni, amelyek csak akkor válnak láthatóvá, ha a felhasználó az egérmutatót egy kijelölt terület fölé viszi.

#### K: Hogyan állíthatom be a dokumentumkönyvtárat?

V: A dokumentumkönyvtár beállításához:

1.  Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a`dataDir` változó annak a könyvtárnak az elérési útjával, ahová a generált PDF fájlt menteni szeretné.

#### K: Hogyan készíthetek mintadokumentumot, és hogyan adhatok hozzá szövegrészletet?

 V: Az oktatóanyagban a`Document` osztályban PDF-minta létrehozásához és szövegrészlet hozzáadásához. Ez a szövegtöredék szolgál a rejtett szövegblokk megjelenítéséhez.

#### K: Hogyan találhatom meg azt a szövegrészletet, amely kiváltja a rejtett szövegblokkot?

 V: Az oktatóanyag bemutatja, hogyan kell használni a`TextFragmentAbsorber` objektumot, hogy megtalálja azt a szövegrészletet, amely kiváltja a rejtett szövegblokk megjelenítését. Egy adott szöveges karakterláncot keres a PDF-dokumentumban.

#### K: Hogyan hozhatom létre és szabhatom testre a rejtett szövegmezőt?

 V: Ön létrehoz egy`TextBoxField`objektumot a rejtett szövegmező megjelenítéséhez. Az oktatóanyag kódot tartalmaz a rejtett szövegmező különféle tulajdonságainak, például pozíciójának, értékének, megjelenésének és viselkedésének beállításához.

#### K: Hogyan hozhatok létre egy láthatatlan gombot a rejtett szövegblokkhoz társítva?

 V: Egy láthatatlan gombmező a gombbal jön létre`ButtonField` osztály. Ez a gombmező az indító szövegrészlet tetején helyezkedik el, és az egér be- és kilépési eseményeihez kapcsolódó műveleteket tartalmaz. Ezek a műveletek szabályozzák a rejtett szövegblokk láthatóságát.

#### K: Testreszabhatom a rejtett szövegblokk és az aktiválási terület megjelenését?

V: Igen, testreszabhatja a rejtett szövegmező és a láthatatlan gomb különféle tulajdonságait, beleértve a betűtípust, a színt, a méretet és az elhelyezést.

#### K: Hogyan menthetem el a módosított dokumentumot a rejtett szövegblokkkal?

 V: Az oktatóanyag bemutatja, hogyan mentheti el a módosított dokumentumot a`Save` módszere a`Document` osztály.