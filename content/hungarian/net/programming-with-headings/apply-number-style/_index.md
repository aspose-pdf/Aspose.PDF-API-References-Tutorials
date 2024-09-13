---
title: Számstílus alkalmazása PDF-fájlban
linktitle: Számstílus alkalmazása PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan alkalmazhat különböző számstílusokat (római számok, ábécé) a PDF-fájlok címsoraira az Aspose.PDF for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-headings/apply-number-style/
---
## Bevezetés

Volt már olyan, hogy gyönyörűen számozott listákat kell hozzáadnia PDF-dokumentumaihoz? Akár jogi dokumentumokat, jelentéseket vagy prezentációkat formáz, a megfelelő számozási stílusok elengedhetetlenek az információk rendszerezéséhez. Az Aspose.PDF for .NET segítségével különféle számozási stílusokat alkalmazhat PDF-fájljai fejlécére, így jól strukturált és professzionális dokumentumokat hozhat létre. 

## Előfeltételek

Mielőtt belevágna a kódolásba, nézzük meg, mire lesz szüksége:

1. Aspose.PDF for .NET: Töltse le az Aspose.PDF legújabb verzióját innen[itt](https://releases.aspose.com/pdf/net/).
2. Fejlesztési környezet: Győződjön meg arról, hogy rendelkezik Visual Studio vagy bármely más .NET-kompatibilis IDE-vel.
3. .NET-keretrendszer: Győződjön meg arról, hogy telepítve van a .NET-keretrendszer 4.0-s vagy újabb verziója.
4.  Licenc: Ideiglenes licencet használhat[itt](https://purchase.aspose.com/temporary-license/) vagy fedezze fel a[ingyenes próbaverzió](https://releases.aspose.com/) opciók.

## Csomagok importálása

A kezdéshez győződjön meg arról, hogy a következő névtereket importálta a projektbe:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 1. lépés: A dokumentum beállítása

Kezdjük egy új PDF dokumentum létrehozásával és az oldalbeállítások konfigurálásával. Beállítjuk az oldalméretet és a margókat, hogy szabályozzuk a tartalom elrendezését.

Magyarázat: Ebben a lépésben a PDF alapstruktúráját állítjuk be, amely magában foglalja az oldalméret, a magasság és a margók meghatározását a következetes formázás érdekében.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Állítsa be az oldalméreteket és a margókat
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

Ezzel a dokumentum szabványos oldalmérettel rendelkezik, amely egy 8,5 x 11 hüvelykes oldalnak felel meg, és minden oldalán 72 pontos (1 hüvelyk) margó lesz.

## 2. lépés: Oldal hozzáadása a PDF-hez

Ezután hozzáadunk egy új oldalt a PDF dokumentumhoz, ahol később alkalmazzuk a számozási stílusokat.

Magyarázat: Minden PDF-hez oldalakra van szükség! Ez a lépés egy üres oldalt ad a PDF-hez, és beállítja a margókat a dokumentumszintű beállításoknak megfelelően.

```csharp
// Új oldal hozzáadása a PDF-dokumentumhoz
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## 3. lépés: Hozzon létre egy úszó dobozt

A FloatingBox lehetővé teszi, hogy tartalmat (például szöveget vagy címsorokat) helyezzen el egy olyan dobozban, amely az oldal áramlásától függetlenül működik. Ez akkor hasznos, ha teljes irányítást szeretne a tartalom elrendezése felett.

Magyarázat: Itt egy FloatingBox-ot állítunk be, amely tartalmazza azokat a címsorokat, amelyekre számstílusok vonatkoznak.

```csharp
// Hozzon létre egy FloatingBoxot a strukturált tartalomhoz
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## 4. lépés: Adja hozzá az első címsort római számokkal

Most jön az izgalmas rész! Adjuk hozzá az első címsort kisbetűs római számozással.

Magyarázat: A NumberingStyle.NumeralsRomanLowercase stílust alkalmazzuk a címsorra, amely a számozást római számokkal (i, ii, iii stb.) jeleníti meg.

```csharp
// Hozza létre az első címsort római számokkal
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## 5. lépés: Adjon hozzá egy második római számfejlécet

Szemléltetés céljából adjunk hozzá egy második római számfejlécet, de ezúttal 13-tól kezdjük.

Magyarázat: A StartNumber tulajdonság lehetővé teszi, hogy egyéni számról kezdje el a számozást – ebben az esetben 13-tól indulunk.

```csharp
// Hozzon létre egy második címsort, amely a 13-as római számmal kezdődik
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## 6. lépés: Adjon hozzá egy címsort alfabetikus számozással

A változatosság kedvéért adjunk hozzá egy harmadik címsort is, de ezúttal az alfabetikus számozást használjuk kisbetűkkel (a, b, c stb.).

Magyarázat: Ha a NumberingStyle-t LettersLowercase-re változtatjuk, akkor a címsorainkon alfabetikus számozást alkalmazhatunk.

```csharp
// Hozzon létre egy címsort alfabetikus számozással
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## 7. lépés: A PDF mentése

Végül az összes címsor és számstílus alkalmazása után mentsük el a PDF fájlt a kívánt könyvtárba.

Magyarázat: Ez a lépés elmenti az összes formázott fejlécet tartalmazó PDF-fájlt az alkalmazott számozási stílusokkal.

```csharp
// Mentse el a PDF dokumentumot
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Következtetés

És megvan! Sikeresen alkalmazta a számozási stílusokat – római számokat és ábécé sorrendet – a PDF-fájlok címsoraiban az Aspose.PDF for .NET használatával. Az Aspose.PDF által biztosított rugalmasság az oldalelrendezés, a számozási stílusok és a tartalompozícionálás szabályozásához hatékony eszközkészletet biztosít a jól szervezett, professzionális PDF-dokumentumok létrehozásához.

## GYIK

### Alkalmazhatok különböző számstílusokat ugyanarra a PDF dokumentumra?  
Igen, az Aspose.PDF for .NET lehetővé teszi különböző számozási stílusok, például római számok, arab számok és alfabetikus számozás keverését ugyanazon a dokumentumon belül.

### Hogyan szabhatom testre a címsorok kezdőszámát?  
 Bármely címsor kezdőszámát beállíthatja a gombbal`StartNumber` ingatlan.

### Van mód a számozási sorrend visszaállítására?  
Igen, visszaállíthatja a számozást a`StartNumber` tulajdonság minden címsorhoz.

### Alkalmazhatok félkövér vagy dőlt stílust a címsorokon a számozáson kívül?  
 Teljesen! Testreszabhatja a címsorstílusokat a tulajdonságok, például a betűtípus, a méret, a félkövér és a dőlt betűk használatával történő módosításával`TextState` objektum.

### Hogyan szerezhetek ideiglenes licencet az Aspose.PDF fájlhoz?  
 Ideiglenes jogosítványt szerezhet be[itt](https://purchase.aspose.com/temporary-license/) az Aspose.PDF korlátozások nélküli teszteléséhez.