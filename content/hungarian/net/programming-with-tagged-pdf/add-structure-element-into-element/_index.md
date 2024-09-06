---
title: Struktúraelem hozzáadása az elemhez
linktitle: Struktúraelem hozzáadása az elemhez
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre, hogyan adhat hozzá szerkezeti elemet a PDF-dokumentum eleméhez az Aspose.PDF for .NET használatával.
type: docs
weight: 20
url: /hu/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan adhat hozzá szerkezeti elemet egy PDF-dokumentum eleméhez az Aspose.PDF for .NET használatával. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi PDF-dokumentumok programozott létrehozását, kezelését és konvertálását. Az Aspose.PDF megjelölt tartalomszerkezeti funkcióival hierarchikus struktúrát hozhat létre a PDF-dokumentumban.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Visual Studio .NET keretrendszerrel telepítve.
2. Az Aspose.PDF könyvtár a .NET-hez.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új projektet a Visual Studióban, és adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz. Letöltheti a könyvtárat az Aspose hivatalos webhelyéről, és telepítheti a gépére.

## 2. lépés: Importálja a szükséges névtereket

A C# kódfájlba importálja az Aspose.PDF által biztosított osztályok és metódusok eléréséhez szükséges névtereket:

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3. lépés: A PDF dokumentum létrehozása és a strukturált elemek meghatározása

Használja a következő kódot PDF-dokumentum létrehozásához és a strukturált elemek meghatározásához:

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Ez a kód üres PDF-dokumentumot hoz létre, és strukturált elemeket, például bekezdéseket és szakaszokat ad hozzá. Minden szerkezeti elem az Aspose.PDF által biztosított módszerekkel jön létre.

## 4. lépés: Mentse el a PDF-dokumentumot

A PDF dokumentum mentéséhez használja a következő kódot:

```csharp
document. Save(outFile);
```

Ez a kód elmenti a PDF dokumentumot a strukturált elemekkel egy megadott fájlba.

### Minta forráskód a Struktúraelem hozzáadása elemhez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
// Dokumentum létrehozása és címkézett PDF tartalom beszerzése
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// A dokumentum címének és természetének nyelvének beállítása
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Gyökérstruktúra elem lekérése (Dokumentumstruktúra elem)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Címkézett PDF dokumentum mentése
document.Save(outFile);
// PDF/UA megfelelőség ellenőrzése
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan adhat hozzá szerkezeti elemet egy PDF-dokumentum eleméhez az Aspose.PDF for .NET használatával. Az Aspose.PDF megjelölt tartalomszerkezeti funkcióival hierarchikus struktúrát hozhat létre PDF-dokumentumában, amely megkönnyíti a tartalom kezelését és navigálását.

### GYIK

#### K: Mi a célja egy struktúraelem hozzáadásának egy PDF-dokumentum eleméhez az Aspose.PDF for .NET használatával?

V: Ha egy PDF-dokumentum eleméhez hozzáad egy szerkezeti elemet az Aspose.PDF for .NET használatával, akkor hierarchikus struktúra hozható létre a dokumentum tartalmán belül. Ez a hierarchikus felépítés javítja a tartalom szervezését és navigálását, megkönnyítve az egyes elemek kezelését és elérését.

#### K: Hogyan segíti az Aspose.PDF könyvtár szerkezeti elemek hozzáadását egy PDF dokumentumhoz?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi PDF-dokumentumok programozott létrehozását, kezelését és konvertálását. Ebben az oktatóanyagban a könyvtár megjelölt tartalomszerkezeti funkcióit kihasználva szerkezeti elemeket hozhatunk létre és hozzáfűzhetünk a PDF-dokumentum tartalmához.

#### K: Milyen előfeltételei vannak annak, hogy az Aspose.PDF for .NET használatával szerkezeti elemeket adjon a PDF-dokumentumhoz?

V: Mielőtt elkezdené, győződjön meg arról, hogy a Visual Studio telepítve van a .NET-keretrendszerrel, és hivatkozott-e a projektben a .NET-hez készült Aspose.PDF könyvtárra.

#### K: Hogyan hoz létre és fűz hozzá szerkezeti elemeket a PDF dokumentum tartalmához a megadott C# kód?

V: A kód bemutatja, hogyan hozhat létre PDF-dokumentumot, hogyan definiálhat gyökérstruktúra-elemet, és hogyan fűzhet hozzá különféle strukturált elemeket, például bekezdéseket és szakaszokat. Minden strukturált elem az Aspose.PDF által biztosított módszerekkel jön létre, lehetővé téve a hierarchikus struktúra felépítését.

#### K: Testreszabhatom a PDF-dokumentumhoz csatolandó szerkezeti elemek típusait?

V: Igen, testreszabhatja a szerkezeti elemek típusait az Aspose.PDF könyvtár által biztosított különböző módszerek felfedezésével. A kód példaként bemutatja a bekezdéseket és az íveket, de szükség szerint más típusú strukturált elemeket is létrehozhat és hozzáfűzhet.

#### K: Hogyan határozhatom meg a hierarchikus kapcsolatot a hozzáadott szerkezeti elemek között?

 V: A szerkezetelemek közötti hierarchikus kapcsolatot az határozza meg, hogy milyen sorrendben hozzáfűzi őket a szülőelemekhez. A kódban a szülő-gyermek kapcsolatok a következővel jönnek létre`AppendChild` módszer.

#### K: Milyen előnyökkel jár a hierarchikus struktúra létrehozása egy PDF-dokumentumban?

V: Hierarchikus struktúra létrehozása PDF-dokumentumban javítja a hozzáférhetőséget, a navigációt és a rendszerezést. Lehetővé teszi a kisegítő technológiák számára a dokumentum tartalmának jobb értelmezését és közvetítését, így a fogyatékkal élők számára is felhasználóbarátabbá válik.

#### K: Hogyan ellenőrizhetem a PDF/UA megfelelőséget a szerkezeti elemek hozzáadása után?

 V: Az oktatóanyagban található kód bemutatja, hogyan ellenőrizhető a PDF/UA megfelelőség a`Validate` módszer. A dokumentum PDF/UA szabvány szerinti érvényesítésével biztosíthatja, hogy a hozzáadott szerkezeti elemek megfeleljenek az akadálymentesítési irányelveknek.

#### K: Használhatom ezt a megközelítést szerkezeti elemek hozzáadására egy meglévő PDF-dokumentumhoz?

V: Igen, módosíthatja a megadott megközelítést, hogy szerkezeti elemeket adjon hozzá egy meglévő PDF-dokumentumhoz. Új dokumentum létrehozása helyett töltse be a meglévő dokumentumot az Aspose.PDF használatával, majd kövesse a hasonló lépéseket a szerkezeti elemek hozzáfűzéséhez.