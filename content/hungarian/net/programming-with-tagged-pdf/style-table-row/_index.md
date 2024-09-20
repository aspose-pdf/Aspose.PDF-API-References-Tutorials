---
title: Stílus táblázat sor
linktitle: Stílus táblázat sor
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan stílusozhat táblázatsorokat PDF-ben az Aspose.PDF for .NET használatával egy lépésről lépésre szóló útmutatóval, amellyel könnyedén javíthatja a dokumentumformázást.
type: docs
weight: 180
url: /hu/net/programming-with-tagged-pdf/style-table-row/
---
## Bevezetés

Ha jól strukturált és szépen formázott PDF-dokumentumokról van szó, az Aspose.PDF for .NET kiváló megoldás. Függetlenül attól, hogy automatizálja a jelentéseket, számlákat vagy dinamikus táblázatokat hoz létre, a táblázatok különféle stílusokkal történő formázása kulcsfontosságú a csiszolt dokumentumhoz. Ebben az oktatóanyagban részletesen elmerülünk a táblázatsorok stílusában az Aspose.PDF for .NET használatával. És ne aggódj, lépésről lépésre elvezetlek, akárcsak egy jó beszélgetés egy kávé mellett!

## Előfeltételek

Mielőtt belevágnánk a kacsikba, győződjünk meg arról, hogy az összes kacsa sorban van. Szükséged lesz:

1. Aspose.PDF for .NET Library  
    Ha még nem rendelkezik vele, akkor előveheti[itt](https://releases.aspose.com/pdf/net/) . Azt is kaphat a[ingyenes próbaverzió](https://releases.aspose.com/) kezdeni.
2. Fejlesztési környezet  
   Állítsa be a Visual Studio-t vagy bármely tetszőleges C# IDE-t. Szükséged lesz a .NET-re is, de gondolom ezt már ismered.
3. C# és .NET alapszintű ismerete  
   A C# jó ismerete gyerekjáték lesz ez az oktatóanyag. De ne aggódj, minden lépést részletesen elmagyarázok!

## Csomagok importálása

Mielőtt elkezdhetnénk dolgozni az Aspose.PDF-fel, importálnunk kell a szükséges névtereket. A C# projektben győződjön meg róla, hogy tartalmazza a következőket:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ezek elengedhetetlenek a táblázat létrehozásához és stílusához, és természetesen a címkézett tartalommal való együttműködéshez a megfelelőség érdekében.

Most bontsuk le a feladatot lépésről lépésre, hogy profi stílusban formázhassa táblázatsorait!

## 1. lépés: Hozzon létre egy új PDF-dokumentumot

Először is: hozzunk létre egy vadonatúj PDF-dokumentumot. Ez a dokumentum tartalmazza az összes stílusos táblázatsort.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Dokumentum létrehozása
Document document = new Document();
```

 Itt egyszerűen inicializálunk egy újat`Document` objektum, amely a PDF-fájlunkat fogja képviselni. Ügyeljen arra, hogy beállítsa a könyvtár elérési útját, ahová a kimeneti fájlokat menteni fogja.

## 2. lépés: Munkavégzés a címkézett tartalommal

A PDF-fájl akadálymentesítésének kialakítása érdekében címkézett tartalommal dolgozunk. Ez segít strukturált elemek, például táblázatok létrehozásában, biztosítva, hogy azok megfeleljenek az akadálymentesítési szabványoknak, például a PDF/UA.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

Itt beállítjuk a PDF címkézett tartalmának címét és nyelvét. Ez olyan, mintha nevet adna a PDF-nek, és megmondaná, milyen nyelven beszéljen!

## 3. lépés: Határozza meg a táblázat szerkezetét

Ezután határozzuk meg a létrehozandó táblázat szerkezetét. Minden táblázatnak szüksége van fejlécre, törzsre és láblécre – hasonlóan egy jól szervezett blogbejegyzéshez!

```csharp
// Gyökérstruktúra elem lekérése
StructureElement rootElement = taggedContent.RootElement;

// Táblázatstruktúra elem létrehozása
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

Itt egy táblázatot készítünk fejléccel (`THead`), test (`TBody`), és lábléc (`TFoot`). Ezek az elemek fogják tartani a sorainkat.

## 4. lépés: Adja hozzá a táblázat fejlécét

A fejléc nélküli táblázatok olyanok, mint a cím nélküli könyvek. Először hozzuk létre a fejléc sort, hogy kontextust biztosítsunk az adatokhoz.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

Itt áthurkoljuk és hozzáadunk három fejlécet (`TableTHElement`), mindegyiknek egy-egy leíró szöveget adva. Egyszerű, igaz?

## 5. lépés: Adjon hozzá stílusos törzssorokat

Most jön a szórakoztató rész – a sorok formázása! Hozzon létre hét sort egyéni stílusokkal. Beállítjuk a háttérszíneket, a szegélyeket, a kitöltést és a szövegigazítást.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- Háttérszín: Világos aranyvesszősárgát használtunk a professzionális, mégis meleg érintéshez.
- Szegélyek: Minden sor sötétszürke külső szegélyt és kék cellaszegélyt kap az éles megjelenés érdekében.
- Magasság és párnázás: A sormagasság be van állítva, és párnázás kerül hozzáadásra a tiszta megjelenés érdekében.
- Oldaltörések: A táblázat olvashatóbbá tétele érdekében minden második sor új oldalon kezdődik.

## 6. lépés: Adja hozzá a láblécsort

A fejléchez hasonlóan a lábléc is rögzíti a táblázatot. Hozzunk létre egyet.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

Egyszerűen átugorunk három lábléccellán, és hozzáadunk egy kis szöveget. A lábléc alternatív szövege a „Foot Row”, hogy elérhető legyen.

## 7. lépés: Mentse el a PDF-dokumentumot

Most, hogy az asztal készen van, itt az ideje, hogy megmentse remekművét!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

Ugyanígy a PDF-fájl mentése az összes gyönyörű táblázatsorral együtt, amelyet most alakítottunk ki.

## 8. lépés: Érvényesítse a PDF/UA megfelelőséget

Annak érdekében, hogy PDF-ünk megfeleljen a kisegítő lehetőségek szabványainak, ellenőrizni fogjuk a PDF/UA megfelelőség szempontjából.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Ez biztosítja, hogy a PDF megfelel a PDF/UA szabványnak, így mindenki számára elérhetővé válik. Az akadálymentesítés a játék neve!

## Következtetés

És megvan! Néhány sornyi kóddal egy teljesen stílusos táblázatot hozott létre PDF-ben az Aspose.PDF for .NET használatával. A fejlécektől a láblécekig minden sort stílusosan alakítottunk, kisegítő elemeket adtunk hozzá, és még a dokumentum megfelelőségét is ellenőriztük. Akár vállalati jelentésekkel, prezentációkkal dolgozik, akár csak szórakozik a PDF-ekkel, ez az útmutató mindenre kiterjed. Most pedig kezdje el az asztalok stílusát profi módon!

## GYIK

### Módosíthatom a táblázat betűstílusát is?  
 Igen! A betűtípus stílusát a gombbal módosíthatja`TextState` objektum minden cellához, lehetővé téve a teljes testreszabást.

### Hogyan adhatok több oszlopot a táblázatomhoz?  
 Csak állítsa be a`colCount`változót, és adjon hozzá több cellát a ciklusokhoz a fejlécekhez, a törzshöz és a láblécekhez.

### Mi történik, ha nem állítom be a sormagasságot?  
Ha nem állítja be a sor magasságát, a táblázat automatikusan a tartalom alapján módosul.

### Használhatom ezt dinamikus számú sorhoz?  
Teljesen! Adatokat lekérhet adatbázisból vagy bármely más forrásból, és dinamikusan módosíthatja a sorok és oszlopok számát.

### Ingyenesen használható az Aspose.PDF for .NET?  
 Az Aspose.PDF for .NET egy licencelt termék, de kipróbálhatja a[ingyenes próbaverzió](https://releases.aspose.com/) vagy kap a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/).