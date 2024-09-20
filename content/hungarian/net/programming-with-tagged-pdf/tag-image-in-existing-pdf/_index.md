---
title: Kép címkézése a meglévő PDF-ben
linktitle: Kép címkézése a meglévő PDF-ben
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan lehet képeket címkézni a meglévő PDF-fájlokban az Aspose.PDF for .NET használatával. Útmutató lépésről lépésre a PDF/UA-megfelelőséggel történő kisegítő lehetőségek javításához.
type: docs
weight: 210
url: /hu/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
## Bevezetés

Ebben az oktatóanyagban végigvezetjük, hogyan címkézhet meg egy képet egy meglévő PDF-fájlban az Aspose.PDF for .NET használatával. Ennek az útmutatónak a végére beállíthat alternatív szöveget a képekhez, beállíthatja az elrendezési attribútumokat, és gondoskodhat arról, hogy PDF-je megfeleljen a kisegítő lehetőségek szabványainak.

## Előfeltételek

Mielőtt belemerülnénk, nézzük meg, mire lesz szüksége az induláshoz:

-  Aspose.PDF for .NET: Győződjön meg arról, hogy letöltötte és telepítette az Aspose.PDF for .NET legújabb verzióját.[Töltse le itt](https://releases.aspose.com/pdf/net/).
- .NET-keretrendszer: Győződjön meg arról, hogy be van állítva egy .NET-fejlesztői környezet, például a Visual Studio.
- A PDF szerkezetének alapvető ismerete: Ismerje meg a PDF szerkezeti elemeit, például bekezdéseket, szakaszokat, táblázatokat és képeket.
-  Érvényes licenc: licencet vásárolhat[itt](https://purchase.aspose.com/buy) vagy használjon ideiglenest[itt](https://purchase.aspose.com/temporary-license/).

## Csomagok importálása

A kódolás megkezdéséhez importálnia kell az alapvető névtereket az Aspose.PDF for .NET fájlból. Ezek hozzáférést biztosítanak a PDF-dokumentum kezeléséhez szükséges osztályokhoz és módszerekhez.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Most, hogy készen állunk, bontsuk fel a kép címkézésének folyamatát több lépésre.

## 1. lépés: Töltse be a meglévő PDF-dokumentumot

Az első lépés a PDF-fájl betöltése, amellyel dolgozni szeretne. Ez lehet bármilyen PDF-fájl, amelyen egy képet szeretne megjelölni.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Nyissa meg a dokumentumot
Document document = new Document(inFile);
```

-  Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a fájl tényleges elérési útjával.
-  A`Document` osztály lehetővé teszi egy meglévő PDF betöltését. A kép címkézéséhez módosítani fogja ezt a PDF-fájlt.

## 2. lépés: Hozzáférés a címkézett tartalomhoz és a gyökérstruktúra elemhez

A PDF megnyitása után a következő lépés a címkézett tartalom elérése és a gyökérstruktúra elem azonosítása. Ez kulcsfontosságú, mivel lehetővé teszi a PDF elemei közötti navigálást és a módosítások végrehajtását.

```csharp
// Szerezzen be címkézett tartalmat és gyökérszerkezeti elemet
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

- `TaggedContent` hozzáférést biztosít a PDF strukturált elemeihez.
-  A`RootElement` a legfelső szerkezeti elem, ahonnan átléphet más elemekre, például bekezdésekre, táblázatokra és képekre.

## 3. lépés: Állítsa be a címkézett PDF-dokumentum címét

Ha címet ad a címkézett PDF-dokumentumhoz, akkor a dokumentum megfelelő címkével rendelkezik, ami segíti a kisegítő lehetőségeket és a PDF/UA megfelelőséget.

```csharp
// Adja meg a címkézett PDF-dokumentum címét
taggedContent.SetTitle("Document with images");
```

- A címkézett PDF-fájl címének megadása javítja a képernyőolvasók és a kisegítő technológiák hozzáférhetőségét, és javítja a dokumentumok átláthatóságát.

## 4. lépés: Keresse meg és címkézze meg a képet

 Most keressük meg a képelemet (a továbbiakban: a`FigureElement` az Aspose.PDF-ben), állítson be egy alternatív szöveget, és állítsa be az elrendezési attribútumait.

```csharp
// Lapozzon át az összes ábraelemen (képen), és állítson be alternatív szöveg- és elrendezési attribútumokat
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
    // Állítson be alternatív szöveget az ábrához
    figureElement.AlternativeText = "Figure alternative text (technique 2)";
    
    // BBox attribútum létrehozása és beállítása (határoló doboz)
    StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
    bboxAttribute.SetRectangleValue(new Aspose.Pdf.Rectangle(0.0, 0.0, 100.0, 100.0));
    
    // Állítsa be az ábra elrendezési attribútumait
    StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
    figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

-  Ez a kód végigfut az összesen`FigureElement` a gyökérstruktúrában lévő objektumok, amelyek képeket reprezentálnak.
- Beállítja a kisegítő lehetőségek alternatív szövegét (a képernyőolvasók ezt fogják használni a kép leírására).
- A határoló doboz (`BBox`megadja a kép elrendezésének koordinátáit, biztosítva, hogy az megfelelően jelenjen meg a dokumentumban.

## 5. lépés: Módosítsa a feszítőelemeket a táblázatban

 Bizonyos esetekben előfordulhat, hogy módosítania kell a táblázaton belüli span elemeket. Itt bemutatjuk, hogyan lehet megtalálni a`SpanElement` és helyezze át egy bekezdésbe.

```csharp
// Keresse meg a táblázat-, span- és bekezdéselemeket
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Helyezze át a span elemet a bekezdésbe
spanElement.ChangeParentElement(paragraph);
```

-  Itt megtaláljuk a`TableElement`, `SpanElement` , és`ParagraphElement` a PDF-ben.
-  A`ChangeParentElement` módszerrel áthelyezzük a szakaszt a bekezdésbe, hogy biztosítsuk a megfelelő címkézést és szerkezetet.

## 6. lépés: Mentse el a dokumentumot, és ellenőrizze a PDF/UA megfelelőséget

Az összes módosítás után az utolsó lépés a frissített PDF mentése, és annak ellenőrzése, hogy az megfelel-e a PDF/UA szabványoknak.

```csharp
// Mentse el a frissített PDF dokumentumot
document.Save(outFile);

// Érvényesítse a PDF/UA megfelelőséget
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

-  A`Validate` metódus ellenőrzi a PDF dokumentumot a PDF/UA szabványoknak megfelelően, és naplózza az eredményeket.
- A megfelelőség biztosítása elősegíti a hozzáférhetőség javítását és a dokumentumok közzétételére vonatkozó szabályozási követelmények teljesítését.

## Következtetés

Ebben az oktatóanyagban megmutattuk, hogyan címkézhet meg képeket egy meglévő PDF-ben az Aspose.PDF for .NET használatával. Alternatív szöveg beállításával, az elrendezési attribútumok módosításával és a dokumentum PDF/UA-megfelelőségének ellenőrzésével biztosíthatja, hogy PDF-fájljai elérhetőek legyenek, és megfeleljenek a modern szabványoknak. Az Aspose.PDF megkönnyíti a strukturált elemekkel való munkát, így Ön szabályozhatja a dokumentum elrendezését és hozzáférhetőségét.

## GYIK

### Mire használható az Aspose.PDF for .NET?
Az Aspose.PDF for .NET egy hatékony könyvtár, amely PDF-dokumentumok programozott létrehozására, szerkesztésére és manipulálására szolgál .NET környezetben.

### Hogyan biztosíthatom a PDF/UA megfelelőséget?
 Használhatja az Aspose.PDF-et`Validate` módszer a PDF/UA megfelelőség ellenőrzésére a dokumentum módosítása után.

### Mi az alternatív szöveg a PDF-ekben?
Az alternatív szöveg a PDF-fájlokban található képekhez hozzáadott leírás a hozzáférhetőség javítása érdekében, különösen a képernyőolvasókat használó felhasználók számára.

### Az Aspose.PDF segítségével manipulálhatom a táblázatokat és a terjedelmeket PDF-ben?
Igen, az Aspose.PDF lehetővé teszi a táblázatok, ívek és egyéb strukturált elemek kezelését egy PDF-dokumentumban.

### Honnan tölthetem le az Aspose.PDF-et .NET-hez?
 Letöltheti az Aspose.PDF legújabb verzióját .NET-hez[itt](https://releases.aspose.com/pdf/net/).