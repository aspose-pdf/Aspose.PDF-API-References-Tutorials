---
title: Szöveg elhelyezése a kép körül a PDF-fájlban
linktitle: Szöveg elhelyezése a kép körül a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan helyezhet el szöveget a képek köré a PDF-fájlokban az Aspose.PDF for .NET segítségével. Kövesse lépésenkénti útmutatónkat, hogy professzionális PDF-eket készítsen képekkel és szövegekkel egymás mellett.
type: docs
weight: 260
url: /hu/net/programming-with-text/placing-text-around-image/
---
## Bevezetés

Próbáltál már szöveget elhelyezni egy kép körül egy PDF-fájlban, de kihívást jelentett? Ha igen, akkor jó helyen jársz! Az Aspose.PDF for .NET leegyszerűsíti ezt a folyamatot, lehetővé téve, hogy szöveget helyezzen el a képek mellett, mindössze néhány sornyi kóddal. Akár jelentéseket, dokumentumokat vagy prezentációkat hoz létre, ez a funkció fantasztikus módja annak, hogy javítsa tartalmai elrendezését és vizuálisan vonzóbbá tegye. Ma bemutatjuk, hogyan használhatja az Aspose.PDF for .NET fájlt a képek köré szöveg elhelyezésére egy PDF-dokumentumban.

## Előfeltételek

Mielőtt belevágnánk a kódba, győződjünk meg arról, hogy mindent beállítottunk. Íme, amire szüksége lesz:

-  Aspose.PDF for .NET: Letöltheti innen[itt](https://releases.aspose.com/pdf/net/).
- Visual Studio: Győződjön meg róla, hogy a legújabb verzió van telepítve, hogy zökkenőmentesen kövesse a munkát.
- .NET-keretrendszer: Ez a példa .NET-et használ, ezért győződjön meg arról, hogy a környezete be van állítva a .NET-fejlesztéshez.
-  Ideiglenes licenc: Kérhet ideiglenes licencet[itt](https://purchase.aspose.com/temporary-license/) ha értékeli a terméket.

Ha még nem állította be az Aspose.PDF-et .NET-hez, kövesse a telepítési utasításokat a[dokumentáció](https://reference.aspose.com/pdf/net/).

## Névterek importálása

A kódolás megkezdése előtt importálni kell a szükséges névtereket. Íme a kódrészlet ehhez:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Ezek a névterek elengedhetetlenek, mivel hozzáférést biztosítanak olyan osztályokhoz, mint pl`Document`, `Page`, `Image` , és`HtmlFragment`, amelyet a PDF létrehozásához és kezeléséhez fogunk használni.

Most, hogy készen állunk, részletezzük, hogyan helyezhet el szöveget egy kép körül a PDF-fájlban az Aspose.PDF for .NET használatával. Lépésről lépésre végigvezetjük ezen.

## 1. lépés: Példányosítsa a dokumentumobjektumot

 Először is létre kell hoznia egy PDF dokumentumot. Az Aspose.PDF-ben ez a példányosítással történik`Document` objektum. Ez az objektum szolgál majd az összes hozzáadott tartalom alapjául.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Itt létrehoztunk egy üres PDF dokumentumot. Még nincs oldala, de ne aggódjon, a következő lépésben hozzáadunk egyet.

## 2. lépés: Adjon hozzá egy oldalt a dokumentumhoz

Most, hogy megvan a dokumentumunk, ideje hozzáadni egy oldalt. Tekintsd ezt úgy, mint egy üres papírlapot, amelyen hozzáadhatod a tartalmat.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Ez a kód egy új oldalt ad a dokumentumhoz. Alapértelmezés szerint az oldal üres, de ezen változtatni fogunk.

## 3. lépés: Hozzon létre egy táblázatot a tartalom rendszerezéséhez

Ahhoz, hogy képünk és szövegünk megfelelően igazodjon, egy táblázatot használunk. A PDF-fájlokban található táblázatok segíthetnek az elrendezés felépítésében, hasonlóan a Word-dokumentumokhoz vagy a HTML-hez.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Ez a kódrészlet létrehoz egy táblázatot, és hozzáadja az oldalhoz. Gondoljon a táblázatra a kép és a szöveg összehangolásának keretére.

## 4. lépés: Állítsa be a táblázat oszlopszélességét

Most, hogy hozzáadtunk egy táblázatot, meg kell határoznunk, hogy milyen szélesek legyenek az oszlopok. Ez biztosítja, hogy a kép és a szöveg megfelelő méretű legyen az oldalon.

```csharp
table1.ColumnWidths = "120 270";
```

Ez a sor két oszlop szélességét állítja be – egyet a képhez, egyet pedig a szöveghez. Módosítsa ezeket az értékeket, ha képének vagy szövegének több vagy kevesebb helyre van szüksége.

## 5. lépés: A margók és a kitöltés meghatározása

Annak érdekében, hogy minden rendben legyen, adjunk hozzá néhány margót és párnázást a táblázathoz.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Ezek a beállítások biztosítják, hogy a táblázat egyenletes térközzel rendelkezzen, így a tartalom látványos legyen.

## 6. lépés: Szúrjon be egy képet a táblázatba

Most pedig térjünk rá a szórakoztató részre – egy kép hozzáadására. Ebben az esetben hozzáadjuk az Aspose logót, de nyugodtan használhat bármilyen képet.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Íme, mi történik:
- A képet a megadott könyvtárból töltjük be.
- Beállítjuk a kép magasságát és szélességét.
- Végül hozzáadjuk a képet a táblázat első cellájához.

## 7. lépés: Adjon hozzá szöveget a kép mellé

Most, hogy a kép a helyén van, tegyünk mellé szöveget. Ebben a példában HTML-formátumú szöveget fogunk használni a tartalom stílusának meghatározásához.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Ez a blokk stílusos címet és leírást ad a kép melletti cellába. A szöveget HTML-címkékkel formázhatja a testreszabhatóság érdekében.

## 8. lépés: Állítsa be a függőleges igazítást

Alapértelmezés szerint előfordulhat, hogy a táblázatcellák tartalma nem igazodik a kívánt módon. Ebben az esetben meg akarunk győződni arról, hogy a szöveg a cella tetejéhez igazodik.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Ez biztosítja, hogy a szöveg a cella tetején üljön, így az elrendezés tiszta és professzionális marad.

## 9. lépés: További szöveg hozzáadása a kép és a leírás alá

Érdemes több tartalmat is elhelyezni a kép és a szöveg alatt. Ehhez adjunk még egy sort a táblázathoz.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Itt hozzáadtunk egy másik sort további szöveggel, amely mindkét oszlopot átfogja az elrendezés egyensúlyának megőrzése érdekében.

## 10. lépés: Mentse el a PDF-dokumentumot

Végül el kell mentenünk a dokumentumot, hogy megtekinthesse a módosításokat.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Ezzel elmenti a PDF-fájlt a kívánt képpel és szöveggel.

## Következtetés

Szöveg elhelyezése a képek körül a PDF-ben ijesztő feladatnak tűnhet, de az Aspose.PDF for .NET leegyszerűsíti a folyamatot. A táblázatok, képek és stílusos szövegek felhasználásával minimális erőfeszítéssel professzionális megjelenésű PDF-fájlokat hozhat létre. Csak néhány sornyi kóddal pontosan oda helyezheti el a tartalmat, ahová szeretné, így a dokumentumok csiszolt és jól szervezett megjelenést kölcsönöznek.

## GYIK

### Használhatom ezt a módszert több szöveges kép elhelyezésére?
Igen, egyszerűen adjon hozzá további sorokat és cellákat a táblázathoz, hogy további képeket és szöveget tartalmazzon.

### Meg tudom változtatni a kép igazítását?
Teljesen! A kép igazítását a cella igazítási tulajdonságainak módosításával módosíthatja.

### Hogyan alakíthatom tovább a szöveget?
 A HTML-címkéket használhatja a`HtmlFragment` objektum különböző stílusok, például félkövér, dőlt vagy különböző betűtípusok alkalmazásához.

### Szabályozhatom a szöveg és a kép közötti távolságot?
 Igen, a`MarginInfo` Az objektum lehetővé teszi az elemek közötti kitöltés és margók szabályozását.

### Lehet-e linkeket hozzáadni a szöveghez?
 Határozottan! A HTML-formátumú szövegbe a hivatkozások segítségével ágyazhat be`<a>` címke.