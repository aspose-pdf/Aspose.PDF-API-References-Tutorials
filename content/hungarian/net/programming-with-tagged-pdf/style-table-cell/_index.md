---
title: Stílus táblázat Cell
linktitle: Stílus táblázat Cell
second_title: Aspose.PDF for .NET API Reference
description: Ebből a részletes oktatóanyagból megtudhatja, hogyan alakíthat stílust PDF-fájlban az Aspose.PDF for .NET használatával. Kövesse az utasításokat gyönyörű PDF-táblázatok létrehozásához és formázásához.
type: docs
weight: 160
url: /hu/net/programming-with-tagged-pdf/style-table-cell/
---
## Bevezetés

A professzionális megjelenésű PDF-táblázatok létrehozása bonyolult lehet, de az Aspose.PDF for .NET-hez ez meglepően egyszerű! Legyen szó fejlécek, láblécek vagy konkrét táblázatcellák stílusáról, ez a nagy teljesítményű könyvtár minden olyan eszközzel rendelkezik, amelyre szüksége van a gyönyörűen formázott PDF-dokumentumok létrehozásához. Ebben az oktatóanyagban végigvezetjük, hogyan lehet stílust formálni egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ne aggódjon – mindent egyszerűen követhető lépésekre bontunk.

## Előfeltételek

Mielőtt belemerülne a kódba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Aspose.PDF for .NET: Töltse le és telepítse az Aspose.PDF legújabb verzióját innen[itt](https://releases.aspose.com/pdf/net/).
2. IDE (mint a Visual Studio): .NET fejlesztői környezet beállítása.
3. C# programozási alapismeretek: Szükséges egy kis C# ismeret.
4.  Aspose.PDF Licenc: Szerezzen be egy ideiglenes vagy teljes licencet a könyvtár összes funkciójának feloldásához. Ingyenes próbaverziót kaphat[itt](https://purchase.aspose.com/temporary-license/).

## Csomagok importálása

Mielőtt elkezdené, feltétlenül importálja a szükséges névtereket. A projektben a következőkre lesz szüksége:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Most, hogy minden be van állítva, ugorjunk bele a lépésről lépésre szóló útmutatóba!

Létre fogunk hozni egy táblázatot egy PDF dokumentumban, és stílust fogunk alakítani a celláiban. Minden lépés részletesen elmagyarázza a folyamatot.

## 1. lépés: Hozzon létre egy új PDF-dokumentumot

 Az első lépés egy új PDF dokumentum létrehozása. Az Aspose.PDF-ben inicializálhat egy újat`Document` objektum, amely a PDF-fájlt képviseli.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Hozzon létre egy új PDF dokumentumot
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");
```

Itt inicializálunk egy PDF-dokumentumot, és beállítjuk a címét és a nyelvét. Ez megfelelő szerkezetet ad a dokumentumnak, ami elengedhetetlen a PDF/UA megfelelőséghez.

## 2. lépés: Állítsa be a táblázat szerkezetét

A PDF-fájlok táblázatai a szerkezeti elemeken belül vannak meghatározva. Hozzuk létre a táblázatot, és határozzuk meg a táblázat sorait és oszlopait.

```csharp
// Szerezd meg a gyökérstruktúra elemet
StructureElement rootElement = taggedContent.RootElement;

// Hozzon létre egy táblázat szerkezeti elemet
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Meghatároztuk az asztal fejét (`TableTHeadElement`), test (`TableTBodyElement`), és láb (`TableTFootElement`) szakaszok. Gondolhatod ezeket az asztalod vázának.

## 3. lépés: A fejléccellák stílusának kialakítása

A fejléccellák stílusa kiemeli őket. Itt háttérszíneket, szegélyeket és szövegigazítást alkalmazunk.

```csharp
int colCount = 4;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
    thElement.BackgroundColor = Color.GreenYellow;
    thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
    thElement.IsNoBorder = true;
    thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
    thElement.Alignment = HorizontalAlignment.Right;
}
```

Ebben a lépésben végigpörgetjük az egyes fejléccellákat, így zöld-sárga hátteret, szürke szegélyt és jobbra igazított szöveget kapunk. Ezeket a tulajdonságokat a kívánt kialakításhoz igazíthatja.

## 4. lépés: Töltse fel és alakítsa ki a táblázat törzsét

A táblázat törzse tartalmazza a tényleges adatokat. A következőképpen alakíthatja ki az egyes cellák stílusát meghatározott margókkal, szegélyekkel és szövegbeállításokkal.

```csharp
int rowCount = 4;

for (int rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = $"Row {rowIndex}";

    for (int colIndex = 0; colIndex < colCount; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
        tdElement.BackgroundColor = Color.Yellow;
        tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
        tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
        tdElement.Alignment = HorizontalAlignment.Center;
        
        TextState cellTextState = new TextState();
        cellTextState.ForegroundColor = Color.DarkBlue;
        cellTextState.FontSize = 7.5F;
        cellTextState.FontStyle = FontStyles.Bold;
        cellTextState.Font = FontRepository.FindFont("Arial");
        tdElement.DefaultCellTextState = cellTextState;
    }
}
```

 Ebben a lépésben kitöltjük a táblázat törzsét négy sorral, és az egyes cellákat sárga háttérrel és középen félkövér kék szöveggel díszítjük. Mi is használjuk a`MarginInfo`osztályban a szöveg körüli kitöltés meghatározásához.

## 5. lépés: A lábléc stílusának kialakítása

Ahhoz, hogy a táblázat teljes szerkezetű legyen, hozzáadjuk és stílusozzuk a lábléccellákat, ugyanúgy, mint a fejlécnél.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";

for (int colIndex = 0; colIndex < colCount; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText($"Foot {colIndex}");
}
```

A lábléc rész stílusa hasonló a fejléchez, így az olvasók könnyen követhetik a táblázat szerkezetét.

## 6. lépés: Mentse el és érvényesítse a PDF-dokumentumot

Végül elmentjük a PDF dokumentumot, és ellenőrizzük, hogy az PDF/UA kompatibilis-e.

```csharp
// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA megfelelőség ellenőrzése
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

 Mentjük a PDF-et és használjuk a`Validate` módszerrel biztosítja, hogy megfeleljen az akadálymentesítési szabványoknak (PDF/UA megfelelőség).

## Következtetés

A táblázatok formázása PDF-ben az Aspose.PDF for .NET használatával egyszerre hatékony és rugalmas. Néhány soros kóddal egyedi táblázatterveket hozhat létre, amelyekkel a PDF-dokumentumok kiemelkednek. A cellaszegélyek és hátterek testreszabásától a kisegítő lehetőségek megfelelőségéig az Aspose.PDF megkönnyíti a csiszolt PDF-fájlok létrehozását.

## GYIK

### Alkalmazhatok különböző stílusokat az egyes táblázatcellákra?  
Igen, stílusozhatja az egyes cellákat a`TableTDElement` tulajdonságait.

### Hogyan egyesíthetem a táblázat celláit?  
 Használhatja a`ColSpan` és`RowSpan` tulajdonságokkal egyesítheti a cellákat egy táblázatban.

### Létre lehet hozni PDF/UA-kompatibilis táblázatot?  
 Igen, amint az ebben az útmutatóban is látható, a PDF/UA megfelelőség biztosítható, ha a dokumentumot a következővel érvényesíti`Validate` módszer.

### Használhatok különböző betűtípusokat a táblázat celláiban?  
 Teljesen! Különféle betűtípusokat adhat meg a segítségével`TextState` objektum minden cellához.

### Hogyan tölthetem le az Aspose.PDF-et .NET-hez?  
 Letöltheti a[kiadások oldala](https://releases.aspose.com/pdf/net/).