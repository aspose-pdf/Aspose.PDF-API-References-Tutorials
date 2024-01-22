---
title: Oldalszám a fejléc láblécében úszó doboz használatával
linktitle: Oldalszám a fejléc láblécében úszó doboz használatával
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhatja hozzá az oldalszámot egy PDF-dokumentum fejlécéhez és láblécéhez az Aspose.PDF for .NET segítségével.
type: docs
weight: 150
url: /hu/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá oldalszámot egy PDF-dokumentum fejlécéhez és láblécéhez a FloatingBox with Aspose.PDF for .NET használatával. A mellékelt C# forráskódot használjuk PDF dokumentum létrehozásához, oldal hozzáadásához, FloatingBox létrehozásához, beállítjuk a pozícióját és hozzáadjuk az oldalszámot, majd mentjük a módosított PDF dokumentumot.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A PDF dokumentum létrehozása és egy oldal hozzáadása

Az első lépés a PDF-dokumentum példányának létrehozása és egy oldal hozzáadása. Itt van, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Példányosítsa a PDF dokumentumot
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Adjon hozzá egy oldalt a PDF dokumentumhoz
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Feltétlenül cserélje ki a "DOKUMENTUMKÖNYVTÁR" elemet annak a könyvtárnak az elérési útjára, ahová a PDF-dokumentumot menteni szeretné.

## 3. lépés: A FloatingBox létrehozása és az oldalszám hozzáadása

Most, hogy az oldal hozzáadásra került a PDF dokumentumhoz, létrehozhatunk egy FloatingBox-ot, beállíthatjuk a pozícióját, és hozzáadhatjuk az oldalszámot. Itt van, hogyan:

```csharp
// Hozzon létre egy úszódobozt, amelynek szélessége 140 és magassága 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Állítsa be a bekezdés bal oldali pozícióját
box1. Left = 2;

// Állítsa be a bekezdés felső pozícióját
box1. Top = 10;

// Adja hozzá az oldalszámot a FloatingBoxhoz
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Adja hozzá a FloatingBoxot az oldalhoz
page.Paragraphs.Add(box1);
```

A fenti kód egy FloatingBoxot hoz létre, amelynek szélessége 140 és magassága 80. Ezután a bal és felső értékek megadásával állítjuk be a pozícióját. Végül a „($p/ $P )” szintaxist tartalmazó TextFragment segítségével hozzáadjuk az oldalszámot a FloatingBox-hoz, amely az aktuális oldalszámmal és az összes oldalszámmal lesz helyettesítve.

## 4. lépés: Mentse el a módosított PDF dokumentumot

Miután az oldalszámot hozzáadtuk a fejléchez vagy a lábléchez a FloatingBox segítségével, elmenthetjük a módosított PDF dokumentumot. Itt van, hogyan:

```csharp
// Mentse el a módosított PDF dokumentumot
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

A fenti kód a szerkesztett PDF dokumentumot a megadott könyvtárba menti.

### Minta forráskód az oldalszámfejléc láblécéhez a lebegő mező használatával az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Példányos dokumentum példány
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Adjon hozzá egy oldalt a pdf dokumentumhoz
Aspose.Pdf.Page page = pdf.Pages.Add();

//Inicializálja a FloatingBox osztály új példányát
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Lebegő érték, amely a bekezdés bal oldali pozícióját jelzi
box1.Left = 2;

// Lebegő érték, amely a bekezdés felső pozícióját jelzi
box1.Top = 10;

// Adja hozzá a makrókat a FloatingBox bekezdésgyűjteményéhez
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Adjon hozzá egy floatingBoxot az oldalhoz
page.Paragraphs.Add(box1);

// Mentse el a dokumentumot
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Következtetés

Gratulálok ! Megtanulta, hogyan adhat hozzá oldalszámot a PDF-dokumentum fejlécéhez és láblécéhez a FloatingBox és az Aspose.PDF for .NET használatával. Mostantól személyre szabhatja fejléceit és lábléceit dinamikus információk, például oldalszám hozzáadásával.

### GYIK

#### K: Mi az a FloatingBox, és hogyan lehet vele oldalszámokat hozzáadni egy PDF-dokumentum fejlécéhez vagy láblécéhez?

V: A FloatingBox egy sokoldalú elrendezési elem az Aspose.PDF-ben, amely különféle tartalmakat, például szöveget és képeket tartalmazhat. Ebben az oktatóanyagban egy tároló létrehozására szolgál az oldalszám számára, amely lehetővé teszi az aktuális oldalszám és a teljes oldalszám dinamikus beszúrását a fejlécbe vagy a láblécbe.

#### K: Hogyan teszi lehetővé a megadott C# forráskód oldalszámok hozzáadását a FloatingBox segítségével?

V: A kódrészlet bemutatja, hogyan kell PDF-dokumentumot létrehozni, oldalt hozzáadni, FloatingBox-ot létrehozni, beállítani az oldalon belüli pozícióját, és beilleszteni az oldalszámot TextFragment segítségével. A szövegrészletben a "($p/ $P )" szintaxis helyére az aktuális oldalszám és a teljes oldalszám kerül.

#### K: Testreszabhatom a FloatingBox segítségével hozzáadott oldalszám megjelenését és formázását?

V: Igen, testreszabhatja az oldalszám megjelenését a TextFragment tulajdonságainak módosításával a FloatingBoxon belül. Módosíthatja a betűméretet, színt, stílust, igazítást és egyéb formázási beállításokat.

#### K: Lehetséges különböző dinamikus elemeket, például dátumot és időt hozzáadni a fejléchez vagy lábléchez hasonló megközelítéssel?

V: Természetesen felvehet különféle dinamikus elemeket, például dátumot, időt, dokumentum metaadatokat vagy egyéni szöveget, ha módosítja a TextFragment tartalmát a FloatingBoxon belül. Használhat olyan makrókat, mint a "($p/ $P )" az oldalszámokhoz vagy a "($date)" az aktuális dátumhoz.

#### K: Hogyan határozhatom meg a FloatingBox pozícióját a fejlécben vagy láblécben?
 V: A megadott kód beállítja a FloatingBox pozícióját a`Left` és`Top` tulajdonságait. Ezeket az értékeket módosíthatja, hogy a FloatingBox tetszőlegesen helyezkedjen el a fejlécben vagy láblécben.

#### K: Használhatok más betűtípust vagy stílust az oldalszámhoz a fejlécben vagy láblécben?

V: Igen, testreszabhatja az oldalszám szövegének betűtípusát, stílusát és egyéb formázási tulajdonságait a TextFragment tulajdonságainak módosításával a FloatingBoxon belül.

#### K: Mi történik, ha a FloatingBoxban lévő tartalom meghaladja a méreteit?

V: Ha a FloatingBoxon belüli tartalom meghaladja a méreteit, akkor levágható, vagy elrendezési problémák léphetnek fel. Győződjön meg arról, hogy a FloatingBox méretei alkalmasak a tartalom befogadására, és szükség esetén fontolja meg az oldal elrendezésének módosítását.

#### K: Lehetséges több különböző tartalmú FloatingBoxot hozzáadni ugyanazon oldal fejlécéhez vagy láblécéhez?

V: Igen, több különböző tartalmú FloatingBoxot is hozzáadhat ugyanazon oldal fejlécéhez vagy láblécéhez úgy, hogy külön FloatingBox példányokat hoz létre, és hozzáadja azokat az oldal Bekezdések gyűjteményéhez.

#### K: Használhatom a FloatingBox megközelítést tartalom hozzáadására a PDF-dokumentum más részeihez, például a törzshöz vagy a margókhoz?

V: Míg a FloatingBoxokat általában fejlécekhez és láblécekhez használják, a PDF-dokumentum más részeihez, például a törzshöz vagy a margókhoz is hozzáadhat tartalmat, ha megfelelően helyezi el őket az oldalon.