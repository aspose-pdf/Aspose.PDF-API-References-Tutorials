---
title: Kép és oldalszám a Fejléc lábléc szakaszában soron belül
linktitle: Kép és oldalszám a Fejléc lábléc szakaszában soron belül
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá képet és oldalszámot a fejléchez és a lábléchez sorközi bekezdések használatával az Aspose.PDF for .NET segítségével.
type: docs
weight: 120
url: /hu/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá képet és oldalszámot a PDF-dokumentum fejléc- és láblécrészéhez az Aspose.PDF for .NET használatával. A mellékelt C# forráskódot használjuk oldal létrehozásához, fejléc és lábléc beállításához, kép és szöveg hozzáadásához a PDF dokumentum fejlécében lévő soron belüli bekezdések használatával.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A PDF-dokumentum és az oldal létrehozása

Az első lépés egy új dokumentum objektum és egy oldal létrehozása a PDF dokumentumban. Itt van, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Hozzon létre egy új dokumentum objektumot
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a dokumentumban
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

A fenti kód egy új dokumentum objektumot és egy üres oldalt hoz létre a PDF dokumentumban.

## 3. lépés: A fejléc hozzáadása képpel és szövegközi szöveggel

Most, hogy az oldal elkészült, soron belüli bekezdések segítségével hozzáadhatunk egy fejlécet képpel és szöveggel. Itt van, hogyan:

```csharp
// Hozzon létre egy fejléc szakaszt
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Állítsa be az oldal fejlécét
page. Header = header;

// Hozzon létre egy TextFragment objektumot az első soron belüli szöveghez
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Adja meg a szöveg színét
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Hozzon létre egy Image objektumot a képhez
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Állítsa be a kép elérési útját
image1.File = dataDir + "aspose-logo.jpg";

// Határozza meg a kép méreteit
image1.FixWidth = 50;
image1.FixHeight = 20;

// Jelezze, hogy az első soron belüli szöveg egy kép
image1.IsInLineParagraph = true;

// Hozzon létre egy második soron belüli szöveget
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Elemek hozzáadása a fejléchez
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

A fenti kód létrehoz egy fejléc szakaszt, beállítja az oldal fejlécét ezzel a szakasszal, hozzáad egy szövegtöredéket inline szöveggel és egy soron belüli kép objektumot.

## 4. lépés: Mentse el a módosított PDF dokumentumot

Miután hozzáadtuk a fejlécet a képpel és a szövegközi szöveggel, elmenthetjük a módosított PDF dokumentumot. Itt van, hogyan:

```csharp
// Mentse el a módosított PDF dokumentumot
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

A fenti kód a szerkesztett PDF dokumentumot a megadott könyvtárba menti.

### Minta forráskód a képhez és az oldalszám fejléc lábléc szakaszához, az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányosítson egy dokumentum objektumot az üres konstruktor meghívásával
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Hozzon létre egy oldalt a PDF objektumban
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Hozzon létre fejléc részt a dokumentumban
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Állítsa be a PDF-fájl fejlécét
page.Header = header;

// Hozzon létre egy szöveg objektumot
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Adja meg a színt
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Hozzon létre egy képobjektumot a szakaszban
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Állítsa be a képfájl elérési útját
image1.File = dataDir + "aspose-logo.jpg";

// Állítsa be a képszélesség információit
image1.FixWidth = 50;
image1.FixHeight = 20;

// Jelezze, hogy a seg1 InlineParagraphja egy kép.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Mentse el a PDF-et
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat hozzá képet és oldalszámot egy PDF-dokumentum fejléc- és láblécrészéhez sorközi bekezdések használatával az Aspose.PDF for .NET segítségével. Most már rugalmasan testreszabhatja PDF-dokumentumai fejlécét és láblécét.

### GYIK

#### K: Milyen előnyökkel jár a sorközi bekezdések használata kép és szöveg hozzáadásához egy PDF-dokumentum fejlécéhez?

V: A sorközi bekezdések használatával zökkenőmentesen integrálhatja a képeket és a szöveget ugyanabban a bekezdésben, így pontos szabályozást biztosít az elhelyezésük és a formázásuk felett. Ez a módszer különösen hasznos vizuális elemekkel rendelkező, testreszabott fejlécek létrehozásához.

#### K: Hogyan hoz létre a megadott C#-forráskód soron belüli bekezdéseket a fejléchez egy PDF-dokumentumban?

V: A mellékelt kód bemutatja, hogyan hozhat létre PDF-dokumentumot, hogyan adhat hozzá oldalt, és testreszabhatja a fejlécet sorközi bekezdések segítségével. Hozzáad egy szövegtöredéket soron belüli szöveggel, egy soron belüli képet és egy másik beágyazott szövegtöredéket.

#### K: Hogyan adhatom meg a fejlécben szereplő szöveg színét?

 V: A szövegközi szöveg színe a gombbal van megadva`ForegroundColor` tulajdona a`TextState` a`TextFragment` tárgy.

#### K: Beállíthatom a fejlécben lévő beágyazott kép méreteit?

 V: Igen, beállíthatja a beágyazott kép méreteit a`FixWidth` és`FixHeight` tulajdonságai a`Image` tárgy. Ez lehetővé teszi a kép szélességének és magasságának szabályozását a fejlécen belül.

#### K: Felvehetek-e további soron belüli elemeket, például hiperhivatkozásokat vagy különböző betűstílusokat a fejlécbe?

 V: Igen, további soron belüli elemeket is felvehet a fejlécbe, ha további elemeket hoz létre`TextFragment` vagy`Image` objektumok a kívánt tulajdonságokkal. Ez lehetővé teszi a fejléc további testreszabását, beleértve a hiperhivatkozásokat, a különböző betűstílusokat vagy más vizuális elemeket.

#### K: Hogyan biztosíthatom, hogy a szövegközi kép és szöveg megfelelően igazodva és formázott maradjon a különböző eszközökön és megjelenítőkön?

V: Az Aspose.PDF for .NET biztosítja, hogy a beágyazott képek és szövegek megfelelően legyenek igazítva és formázva, ami egységes megjelenést eredményez a különböző eszközökön és PDF-megtekintőkön.

#### K: Alkalmazhatok soron belüli bekezdéseket a láblécrészre is?

 V: Igen, a szövegközi bekezdések használatának technikáját alkalmazhatja a láblécszakaszban is az a. létrehozásával`Footer` objektumot, és belső elemeket, például szöveget és képeket ad hozzá.

#### K: Lehetséges-e kombinálni a sorközi bekezdéseket más fejléc- vagy lábléc-testreszabási módszerekkel?

V: Igen, kombinálhatja a sorközi bekezdéseket más, az Aspose.PDF for .NET által biztosított fejléc- vagy lábléc-testreszabási módszerekkel, hogy összetettebb és személyre szabott fej- vagy láblécterveket hozzon létre.

#### K: Eltávolíthatom vagy törölhetem a soron belüli elemeket a fejlécből, ha szükséges?

 V: Igen, eltávolíthatja vagy törölheti a soron belüli elemeket a tartalom módosításával`HeaderFooter` objektumot, és eltávolítja a megfelelő sorközi bekezdéseket.

#### K: Hogyan alkalmazhatok sorközi bekezdéseket a PDF-dokumentum egyes oldalaira?

 V: A sorközi bekezdések meghatározott oldalakra történő alkalmazásához külön létrehozhat`HeaderFooter` objektumokat az egyes oldalakhoz, és rendelje hozzá őket a`Header` az illető tulajdona`Aspose.Pdf.Page` tárgyakat.