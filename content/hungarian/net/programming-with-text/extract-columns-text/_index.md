---
title: Oszlopok szövegének kibontása PDF-fájlban
linktitle: Oszlopok szövegének kibontása PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan bonthat ki szövegoszlopokat PDF-fájlokból az Aspose.PDF for .NET segítségével. Ez az útmutató az egyes lépéseket kódpéldákkal és magyarázatokkal részletezi.
type: docs
weight: 150
url: /hu/net/programming-with-text/extract-columns-text/
---
## Bevezetés

PDF fájlokkal dolgozik, és szöveget kell kivonnia egy adott oszlopformátumban? Függetlenül attól, hogy számlákat, jelentéseket vagy bármilyen strukturált dokumentumot dolgoz fel, a szöveg pontos kinyerése a PDF-ből bonyolult feladat lehet. Itt lép be az Aspose.PDF for .NET a folyamat egyszerűsítésére. Ebben az oktatóanyagban végigvezetjük, hogyan bonthat ki könnyedén szövegoszlopokat egy PDF-fájlból. 

## Előfeltételek

Mielőtt belemerülnénk a kódba, fedjük le azokat a lényeges dolgokat, amelyekre szüksége lesz:

-  Aspose.PDF for .NET: Győződjön meg arról, hogy az Aspose.PDF for .NET legújabb verziója telepítve van. Ha nem, akkor megteheti[töltse le itt](https://releases.aspose.com/pdf/net/).
- Fejlesztői környezet: A kóddal való együttműködéshez Visual Studio vagy más .NET fejlesztői környezet szükséges.
- PDF-dokumentum: Legyen kéznél egy minta PDF-dokumentum, lehetőleg egy szövegoszlopokkal, mivel abból fogunk szöveget kivonni.

 Ha még nem telepítette az Aspose.PDF for .NET fájlt, megragadhatja a[ingyenes próbaverzió](https://releases.aspose.com/) vagy[vásároljon licencet](https://purchase.aspose.com/buy) a teljes funkciókért. Jelentkezni is lehet a[ideiglenes engedély](https://purchase.aspose.com/temporary-license) ha szükséges.

## Névterek importálása

Az Aspose.PDF for .NET projektben való használatához a következő névtereket kell importálnia:

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Útmutató lépésről lépésre: Szövegoszlopok kibontása PDF-ből

Most bontsuk fel a kód minden részét, hogy jobban megértsük, hogyan működik. Kövesse lépésről lépésre, és magyarázza el a folyamat egyes szakaszait.

## 1. lépés: Töltse be a PDF-dokumentumot

 Az első dolog, amit meg kell tennie, hogy betöltse a PDF fájlt a`Document`objektum. Az Aspose.PDF így működik együtt a dokumentummal.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 Ebben a lépésben egyszerűen meghatározzuk azt a könyvtárat, ahol a PDF-dokumentumot tároljuk. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a helyi PDF-fájl elérési útjával. A`Document` objektum betölti a PDF-fájlt a memóriába, így elérhetővé teszi a további feldolgozáshoz.

## 2. lépés: Állítsa be a szövegtöredék-elnyelőt

 Ezután használjuk a`TextFragmentAbsorber` a PDF-fájl teljes szövegének befogadásához vagy rögzítéséhez. Ezt az elnyelő osztályt arra tervezték, hogy szövegtöredékeket vonjon ki a PDF-ben meghatározott területekről, ami ideálissá teszi szövegoszlopok kinyerésére.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Itt létrehozunk egy példányt`TextFragmentAbsorber` és alkalmazza a PDF összes oldalára a használatával`Accept()` . A`TextFragmentCollection` tárolja a kivont szöveget, és ebből a gyűjteményből szükség szerint módosíthatjuk vagy kivonhatjuk a szöveget.

## 3. lépés: Állítsa be a kivont szöveg betűméretét

A szövegrészletek rögzítése után érdemes lehet csökkenteni a betűméretüket, különösen akkor, ha az eredeti szöveg túl nagy. Ebben a példában a betűméretet 70%-kal csökkentjük.

```csharp
foreach (TextFragment tf in tfc)
{
    // Csökkentse a betűméretet 70%-kal
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Ez a kód mindegyiken áthalad`TextFragment` a gyűjteményben, és 70%-kal csökkenti a betűméretet. A betűméret módosítása megkönnyítheti a kivonatolt szöveg kezelését, különösen, ha különböző célokra formázza.

## 4. lépés: Mentse el a dokumentumot memóriafolyamba

 A szöveg módosítása után a PDF-et elmentjük a`MemoryStream`. Ez lehetővé teszi számunkra, hogy a dokumentumot a memóriában tartsuk további feldolgozáshoz anélkül, hogy vissza kellene írnia a lemezre.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Itt elmentjük a PDF-fájlt egy memóriafolyamba, majd újratöltjük a dokumentumot. Ez a módszer akkor hasznos, ha nagy fájlokkal dolgozik, és szeretné elkerülni a szükségtelen lemezműveleteket.

## 5. lépés: Az összes szöveg kibontása a szövegabszorber segítségével

 Most, hogy elkészítettük a PDF-fájlt, ideje kivonatolni a szöveget. Használjuk`TextAbsorber` hogy az összes szöveget megkapja a dokumentumból.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 Ebben a lépésben a`TextAbsorber` elnyeli az összes szöveget a PDF-ből, és a kivont szöveget a rendszer tárolja`extractedText` húr. Itt történik a varázslat – a szövegoszlopai mostantól egyszerű szöveges formátumban vannak!

## 6. lépés: Mentse el a kicsomagolt szöveget egy fájlba

 Végül a kinyert szöveget elmentjük a`.txt` fájl a könnyű hozzáférés és a további használat érdekében.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Ez a kód a kibontott szöveget egy újba írja`.txt` fájlt, és elmenti a megadott könyvtárba. Egy üzenet jelenik meg a konzolon, amely megerősíti, hogy a folyamat sikeres volt.

## Következtetés

Megvan! A szövegoszlopok kinyerése egy PDF-fájlból az Aspose.PDF for .NET segítségével egyszerűbb, mint gondolná. Mindössze néhány sornyi kóddal betölthet egy PDF-fájlt, kivonhat adott szöveget, módosíthatja a formázást, és az eredményeket szövegfájlba mentheti.

Ez a technika hihetetlenül hasznos strukturált dokumentumok, például táblázatok, jelentések vagy bármilyen oszlopokba rendezett tartalom feldolgozásához. Függetlenül attól, hogy automatizálnia kell az adatkinyerést vagy a tömeges dokumentumok feldolgozását, az Aspose.PDF biztosítja az eszközöket a hatékony megvalósításhoz.

## GYIK

### Kivonhatok szöveget a PDF adott oldalairól?  
 Igen! Módosíthatja a`TextFragmentAbsorber` adott oldalak megcélzásához a`pdfDocument.Pages[pageIndex].Accept(tfa);` módszer.

### Lehetséges-e csak egy oszlopból szöveget kivonni egy többoszlopos PDF-fájlból?  
 Igen, de a szövegrészletek koordinátáival kell dolgozni`TextFragment.Rectangle` a dokumentum meghatározott területeinek megcélzásához.

### Hogyan javíthatom a szövegkivonás pontosságát?  
 A nagyobb pontosság érdekében ügyeljen arra, hogy a PDF szerkezete jól meghatározott legyen, és kerülje az összetett elrendezésű dokumentumokat. Finomhangolhatja is a`TextFragmentAbsorber` szöveg kinyeréséhez betűstílusok, -méretek vagy régiók alapján.

### Támogatja az Aspose.PDF a beolvasott dokumentumokból a szöveg kinyerését?  
Igen, de OCR (optikai karakterfelismerő) technológiát kell használnia. Az Aspose ehhez is biztosít eszközöket.

### Hogyan kezelhetek nagy, több ezer oldalas PDF fájlokat?  
Nagyméretű PDF-fájlok esetén a nagy memóriahasználat elkerülése érdekében a dokumentumot darabokban dolgozza fel úgy, hogy egyszerre néhány oldalról bontja ki a szöveget.