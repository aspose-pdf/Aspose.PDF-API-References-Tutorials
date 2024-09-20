---
title: Szöveg és kép Bekezdésként PDF-fájlban
linktitle: Szöveg és kép Bekezdésként PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Hozzon létre PDF-eket szöveggel és képekkel az Aspose.PDF for .NET segítségével. Lépésről lépésre megtudhatja, hogyan adhat hozzá szöveget és szövegközi képeket.
type: docs
weight: 530
url: /hu/net/programming-with-text/text-and-image-as-paragraph/
---
## Bevezetés

A mai digitális világban a PDF univerzális dokumentumformátum, amellyel a legtöbben naponta találkozunk. Legyen szó jelentésről, e-könyvről vagy üzleti számláról, a PDF-fájlok megkönnyítik az információk megosztását különböző platformokon. De mi van akkor, ha programozottan szeretne személyre szabni egy PDF-fájlt? Itt lép be az Aspose.PDF for .NET. Ebben az oktatóanyagban végigvezetjük Önt, hogyan szúrhat be szöveget és képeket sorközi bekezdésként egy PDF-fájlba az Aspose.PDF for .NET segítségével.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjünk meg arról, hogy minden megvan, ami a zökkenőmentes követéshez szükséges:

-  Aspose.PDF for .NET Library: Telepítenie kell az Aspose.PDF for .NET-et. Letöltheti[itt](https://releases.aspose.com/pdf/net/).
- Visual Studio: Bármelyik verzió, amely támogatja a .NET-et, tökéletesen működik.
- A C# alapismeretei: Hasznos lesz a C# ismerete, de ne aggódjon – minden lépésen végigvezetem Önt!
- PDF dokumentum kész: Ha egyéni képet szeretne hozzáadni, készítse elő.

 A könyvtár ingyenes próbaverzióját is igénybe veheti[itt](https://releases.aspose.com/) , vagy ha nagyszabású projekten dolgozik, fontolja meg annak megvásárlását[itt](https://purchase.aspose.com/buy) . További részletekre van szüksége? Tekintse meg a dokumentációt[itt](https://reference.aspose.com/pdf/net/).

## Csomagok importálása

Az Aspose.PDF for .NET használatának megkezdéséhez importálnia kell a szükséges névtereket. Ezek a névterek lehetővé teszik, hogy a C# kód kölcsönhatásba lépjen az Aspose.PDF funkcióival.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

Egyszerű, igaz? Most pedig térjünk rá a szórakoztató részre – saját PDF-fájl létrehozására.

## Útmutató lépésről lépésre: PDF készítése szöveggel és beágyazott képpel

Bontsuk ezt emészthető, könnyen követhető lépésekre. Képzeld el, hogy összeállítasz egy puzzle-t; minden lépés olyan, mint a megfelelő darab megtalálása és elhelyezése.

## 1. lépés: Inicializálja a PDF-dokumentumot

Az első lépés egy új PDF-dokumentum inicializálása az Aspose.PDF használatával. Ez a dokumentum a szöveg és a képek hozzáadásának alapjául szolgál.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Példányos dokumentum példány
Document doc = new Document();
```

 Mi történik itt? Egyszerűen létrehozunk egy új dokumentumot a`Document`osztályt, és meghatározza azt a könyvtárat, ahová menteni szeretné a PDF-fájlt. Ez olyan, mintha egy friss vásznat nyitna meg remekművéhez!

## 2. lépés: Adjon hozzá egy oldalt a PDF-hez

Nem sok haszna van egy dokumentumnak oldalak nélkül, igaz? Adjunk hozzá egy üres oldalt a dokumentumhoz.

```csharp
// Oldal hozzáadása a Dokumentumpéldány oldalgyűjteményéhez
Page page = doc.Pages.Add();
```

Ez a kódrészlet új oldalt ad a dokumentum oldalgyűjteményéhez. Tekintsd úgy, mintha egy üres oldalt nyissz fel egy jegyzetfüzetben.

## 3. lépés: Szöveg hozzáadása bekezdésként

Ezután egy szöveges bekezdést adunk hozzá. Ide szúrhatja be üzenetét vagy fejlécét.

```csharp
// Szövegtöredék létrehozása
TextFragment text = new TextFragment("Hello World.. ");
// Szövegrészlet hozzáadása az Oldal objektum bekezdésgyűjteményéhez
page.Paragraphs.Add(text);
```

 Itt létrehozunk a`TextFragment` objektumot a „Hello World…” szöveg megtartásához, amely aztán bekezdésként hozzáadódik az oldalhoz. Ez olyan, mintha az első mondatot írná a PDF-dokumentumába.

## 4. lépés: Adjon hozzá egy képet sorközi bekezdésként

Most, hogy megvan a szöveg, fűszerezzük a dolgokat egy kép hozzáadásával soron belüli bekezdésként. A szövegközi bekezdés egyszerűen azt jelenti, hogy a kép közvetlenül a szöveg után jelenik meg, hasonlóan ahhoz, ahogy a Word dokumentumokban a képek megjelennek.

```csharp
// Hozzon létre egy képpéldányt
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// Állítsa be a képet sorközi bekezdésként, hogy közvetlenül utána jelenjen meg
// Az előző bekezdés objektum (TextFragment)
image.IsInLineParagraph = true;
// Adja meg a képfájl elérési útját
image.File = dataDir + "aspose-logo.jpg";
```

 Ebben a részletben létrehozunk egy`Image` objektumot, mondja meg neki, hogy igazítsa a szöveghez, és adja meg a képfájl elérési útját. Ez egyenértékű azzal, hogy egy képet közvetlenül egy mondat mögé illesztenek be a dokumentumban. Lecserélheti az "aspose-logo.jpg" fájlt a kívánt képre.

## 5. lépés: Állítsa be a képméretet (opcionális)

Szeretné átméretezni a képet? Nem probléma. Az Aspose.PDF lehetőséget ad a kép magasságának és szélességének beállítására, mielőtt hozzáadná a dokumentumhoz.

```csharp
// Kép magasságának beállítása (opcionális)
image.FixHeight = 30;
// Képszélesség beállítása (opcionális)
image.FixWidth = 100;
```

Ez a rész nem kötelező, de segít szabályozni, hogy a kép milyen nagy vagy kicsi legyen a PDF-ben. Ez olyan, mint egy fénykép átméretezése, mielőtt kinyomtatná.

## 6. lépés: Kép hozzáadása a bekezdésgyűjteményhez

Elkészítettük a képet. Most illesszük be a dokumentumba sorközi bekezdésként.

```csharp
// Kép hozzáadása az oldalobjektum bekezdésgyűjteményéhez
page.Paragraphs.Add(image);
```

Ez a sor közvetlenül a szöveg után adja hozzá a képet a bekezdésgyűjteményben. Ez olyan, mintha a „Kép beszúrása” gombot nyomná meg egy szövegszerkesztőben.

## 7. lépés: Adjon hozzá egy másik szövegközi bekezdést

Mi a teendő, ha több szöveget szeretne hozzáadni közvetlenül a kép után? Tegyük ezt meg úgy, hogy beillesztünk egy másik szövegrészletet.

```csharp
// Inicializálja újra a TextFragment objektumot különböző tartalommal
text = new TextFragment(" Hello Again..");
// A TextFragment beállítása sorközi bekezdésként
text.IsInLineParagraph = true;
// Újonnan létrehozott TextFragment hozzáadása az oldal bekezdésgyűjteményéhez
page.Paragraphs.Add(text);
```

 Újra használjuk a`TextFragment`objektumot ide új szöveggel ("Hello Again..."), és beilleszti a szövegbe, közvetlenül a kép után. Ez gördülékeny, összefüggő megjelenést kölcsönöz a PDF-nek.

## 8. lépés: Mentse el a PDF-dokumentumot

Már majdnem készen vagyunk! Most mentsük a dokumentumot a megadott könyvtárba.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

Ez az utolsó lépés elmenti a fájlt a könyvtárába "TextAndImageAsParagraph_out.pdf" néven. Gratulálunk – elkészített egy PDF-et, amely szöveget és képsorokat is tartalmaz!

## Következtetés

És kész is – szöveget és képeket tartalmazó PDF-fájl létrehozása soron belüli bekezdések formájában az Aspose.PDF for .NET segítségével egyszerűen csak követheti ezeket a lépéseket. Mindössze néhány sornyi kóddal dinamikus tartalmat adhat PDF-fájljaihoz, így látványosabbá és professzionálisabbá teheti azokat. Legyen szó üzleti jelentésről vagy e-könyvről, a PDF-fájlok elrendezésének ellenőrzése a világot megváltoztathatja.

## GYIK

### Hozzáadhatok több képet sorközi bekezdésként?  
 Igen, több képet is hozzáadhat külön létrehozásával`Image` objektumokat, és hozzáadjuk őket a bekezdésgyűjteményhez.

### Szabályozhatom a szöveg és a kép helyzetét a PDF-ben?  
Igen, az olyan tulajdonságok használatával, mint a margók, szabályozhatja a szöveg és a képek pontos elhelyezését.

### Ingyenes az Aspose.PDF for .NET?  
 Nem, ez egy licencelt termék, de beszerezheti a[ingyenes próbaverzió](https://releases.aspose.com/) vagy vásároljon licencet[itt](https://purchase.aspose.com/buy).

### Hozzáadhatok hiperhivatkozásokat a szöveghez?  
 Igen, az Aspose.PDF lehetővé teszi hiperhivatkozások hozzáadását a szövegrészletekhez. Ellenőrizze a[dokumentáció](https://reference.aspose.com/pdf/net/) további részletekért.

### Testreszabhatom a szöveg betűtípusát és stílusát?  
Teljesen! Könnyedén testreszabhatja a szövegrészletek betűtípusait, színeit és egyéb stílustulajdonságait.