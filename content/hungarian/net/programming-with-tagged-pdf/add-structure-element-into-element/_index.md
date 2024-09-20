---
title: Struktúraelem hozzáadása az elemhez
linktitle: Struktúraelem hozzáadása az elemhez
second_title: Aspose.PDF for .NET API Reference
description: Ebből az átfogó, lépésenkénti oktatóanyagból megtudhatja, hogyan adhat hozzá akadálymentesítési struktúra elemeket PDF-fájlokhoz az Aspose.PDF for .NET használatával.
type: docs
weight: 20
url: /hu/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## Bevezetés

A mai digitális világban a hozzáférhetőség kulcsfontosságú. Mindenkinek egyenlő hozzáféréssel kell rendelkeznie az információkhoz, és kulcsfontosságú, hogy azokat olyan formátumban biztosítsák, amelyben mindenki könnyen eligazodhat. Ebben az oktatóanyagban belemerülünk abba, hogyan javíthatja a PDF-hozzáférést az Aspose.PDF for .NET használatával szerkezeti elemek hozzáadásával. Ez a nagy teljesítményű könyvtár lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen dolgozzanak a PDF-dokumentumokkal, lehetővé téve számukra, hogy címkézett PDF-fájlokat hozzanak létre, amelyek megfelelnek a kisegítő lehetőségek szabványainak.

## Előfeltételek

Mielőtt elkezdenénk utazásunkat a PDF szerkezeti elemek világába, győződjünk meg arról, hogy mindennel rendelkezünk, amire szükségünk van:

1.  Visual Studio: Ez az IDE, ahol írhatja és futtathatja a C# kódot. Letöltheti innen[Visual Studio](https://visualstudio.microsoft.com/) ha még nem tetted meg.
2.  Aspose.PDF for .NET Library: A PDF-fájlok kezeléséhez szüksége lesz a könyvtárra. Töltse le a legújabb verziót a[Aspose honlapja](https://releases.aspose.com/pdf/net/). Ez a könyvtár kulcsfontosságú projektünk számára.
3. Alapvető C# ismerete: A C# szintaxis és az objektumorientált programozás ismerete előnyt jelent. Ha boldogan tudsz írni néhány sort C#-ból, akkor kész!
4. PDF-dokumentumkönyvtár: Hozzon létre egy könyvtárat a rendszeren, ahol tárolja az oktatóanyag bemeneti és kimeneti PDF-fájljait.

Most, hogy összeszedtük az eszközeinket és a tudásunkat, hozzuk be a szükséges csomagokat az induláshoz!

## Csomagok importálása

Először is importáljuk a szükséges névtereket. Győződjön meg arról, hogy a C# fájl tetején a következők szerepelnek:

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

Ezek a névterek hozzáférést biztosítanak a PDF-dokumentumok kezeléséhez és a címkézett tartalom létrehozásához szükséges osztályokhoz és módszerekhez. Most lépjünk a dolog lényegébe, és kezdjük el a kódolást!

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Mielőtt bármilyen kódolás megtörténne, meg kell határoznunk, hogy hova mentjük a fájljainkat. Ez kulcsfontosságú a szkriptünk zökkenőmentes futtatásához.

```csharp
// Határozza meg a dokumentumok könyvtárának elérési útját.
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a tényleges elérési úttal, ahol a PDF-fájlokat tárolni szeretné. Ez valami ilyesmi lehet`C:\\PDFs\\`.

## 2. lépés: Hozzon létre egy új PDF-dokumentumot

Most, hogy beállítottuk a könyvtárunkat, hozzunk létre egy PDF-dokumentumot, amelybe hozzáadjuk a szerkezeti elemeinket.

```csharp
Document document = new Document();
```

 Ez a sor inicializálja a`Document` osztályba, így elkezdhetünk dolgozni PDF-tartalmunkkal.

## 3. lépés: A címkézett tartalom elérése és beállítása

Ha a dokumentum elkészült, ideje beállítani a címkézett tartalmat, ami elengedhetetlen a kisegítő lehetőségekhez.

### A címkézett tartalom inicializálása

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Ez a sor hozzáférést biztosít a PDF címkézett tartalmához. A címkézett tartalom szükséges ahhoz, hogy a képernyőolvasók pontosan értelmezhessék a dokumentumot.

### Dokumentum metaadatainak beállítása

A dokumentumnak megfelelő címet kell adnia, és meg kell határoznia a nyelvet.

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

Ez javítja a dokumentum metaadatait és javítja a hozzáférhetőségét.

## 4. lépés: Struktúraelemek létrehozása és hozzáfűzése

Adjunk hozzá egy kis szerkezetet! Ez magában foglalja a bekezdések és a span elemek létrehozását a megfelelően formázott és címkézett dokumentum létrehozása érdekében.

### Hozzon létre gyökérszerkezeti elemet

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

Most létrehozzuk az első bekezdésekből és span elemekből álló készletünket.

### Első bekezdés elem létrehozása

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

Itt inicializálunk egy új bekezdéselemet, és hozzáfűzzük a gyökérstruktúra elemhez. Ez a tartalmad kiindulópontja!

### Adjon hozzá feszítőelemeket a bekezdéshez

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

 A`span` az elemek olyanok, mint a kis bekezdések a nagyobb bekezdésünkön belül. Lehetővé teszik a szöveg formázásának finomabb szabályozását.

### Kombinálja mindezt

Most készítsük el a teljes bekezdést az összes elemmel együtt:

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### Ismételje meg a további bekezdésekhez

Ezt a folyamatot meg kell ismételni további bekezdéseknél:

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

 Csak alkoss tovább`ParagraphElement` s és`SpanElement` s, hozzáfűzve őket a`rootElement` a fentebb látható módon`p1`.

## 5. lépés: Mentse el a dokumentumot

Ha az összes szerkezeti elem a helyén van, ideje elmenteni PDF-dokumentumát.

### Adja meg a kimeneti fájl elérési útját

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### Mentse el a dokumentumot

```csharp
document.Save(outFile);
```

Itt történik a varázslat! A dokumentum a megadott kimeneti fájl elérési útjára kerül mentésre.

## 6. lépés: Érvényesítse a PDF/UA megfelelőséget

Az utolsó lépés annak ellenőrzése, hogy a dokumentum megfelel-e a PDF/UA akadálymentesítési szabványainak.

A megfelelőség ellenőrzéséhez használja a következő kódot:

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

Ez kiírja, hogy a dokumentum megfelel-e a PDF/UA szabványoknak, ami elengedhetetlen a hozzáférhetőséghez.

## Következtetés

És megvan! Most tanulta meg, hogyan adhat hozzá szerkezeti elemeket egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Az alábbi lépések követésével bármilyen PDF-et átalakíthat olyan hozzáférhető formátumba, amely megfelel a szabványoknak, így mindenki egyenlő hozzáférést biztosít az információkhoz. 

## GYIK

### Mi az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok programozott létrehozását, kezelését és konvertálását.

### Hogyan ellenőrizhetem, hogy a PDF-em elérhető-e?
Az Aspose.PDF könyvtár használatával ellenőrizheti PDF-fájlját a PDF/UA szabványok szerint, hogy megbizonyosodjon a kisegítő lehetőségekről szóló irányelveknek.

### Használhatom ingyenesen az Aspose.PDF-et?
 Igen, az Aspose ingyenes próbaverziót kínál, amely lehetővé teszi a funkciók ingyenes felfedezését. Letöltheti[itt](https://releases.aspose.com/).

### Hol találom az Aspose.PDF dokumentációját?
Az Aspose.PDF átfogó dokumentációja megtalálható[itt](https://reference.aspose.com/pdf/net/).

### Hogyan vásárolhatok licencet az Aspose.PDF fájlhoz?
 Licenceket közvetlenül az Aspose webhelyéről vásárolhat[itt](https://purchase.aspose.com/buy).