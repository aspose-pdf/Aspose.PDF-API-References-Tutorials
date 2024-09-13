---
title: Link szerkezeti elemek
linktitle: Link szerkezeti elemek
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre a hivatkozásszerkezet elemeinek használatához az Aspose.PDF for .NET-hez. Hozzon létre hiperhivatkozásokat PDF-dokumentumaiban.
type: docs
weight: 120
url: /hu/net/programming-with-tagged-pdf/link-structure-elements/
---
Ebben a lépésenkénti útmutatóban bemutatjuk, hogyan használhatja a hivatkozásszerkezet elemeit az Aspose.PDF for .NET-hez. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi PDF-dokumentumok programozott létrehozását és kezelését. A hivatkozásszerkezet elemei lehetővé teszik hiperhivatkozások hozzáadását a PDF-dokumentumhoz, így a felhasználók rákattinthatnak a hivatkozásokra, és az online forrásokhoz navigálhatnak.

Merüljünk el a kódban, és tanuljuk meg, hogyan használhatjuk a hivatkozásszerkezet elemeit az Aspose.PDF for .NET-hez.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Aspose.PDF könyvtár a .NET-hez telepítve.
2. Alapszintű C# programozási nyelv ismerete.

## 1. lépés: A környezet beállítása

A kezdéshez nyissa meg a C# fejlesztői környezetet, és hozzon létre egy új projektet. Győződjön meg arról, hogy a projektben hozzáadott egy hivatkozást a .NET Aspose.PDF könyvtárára.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## 2. lépés: A dokumentum létrehozása

 Az első lépés egy új PDF dokumentum létrehozása a`Document` osztály.

```csharp
// Hozza létre a PDF dokumentumot
Document document = new Document();
```

## 3. lépés: Dolgozzon a címkézett tartalommal

Ezután megkapjuk a dokumentum címkézett tartalmát, amellyel dolgozhatunk.

```csharp
// Szerezze be a dokumentum címkézett tartalmát
ITaggedContent taggedContent = document.TaggedContent;
```

## 4. lépés: Állítsa be a dokumentum címét és nyelvét

Most beállíthatjuk a dokumentum címét és nyelvét.

```csharp
// Határozza meg a dokumentum címét és nyelvét
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## 5. lépés: Adjon hozzá hivatkozásszerkezeti elemeket

Most adjunk hivatkozásszerkezeti elemeket a dokumentumunkhoz. Különféle hivatkozásokat fogunk létrehozni, beleértve az egyszerű szöveges hivatkozásokat, a képi hivatkozásokat és a többsoros hivatkozásokat.
```csharp
// A gyökérstruktúra elem beszerzése (dokumentumstruktúra elem)
StructureElement rootElement = taggedContent.RootElement;

// Adjon hozzá egy bekezdést hiperhivatkozással
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Adjon hozzá egy bekezdést formázott szöveget tartalmazó hiperhivatkozással
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Adjon hozzá egy bekezdést egy részben formázott szöveget tartalmazó hiperhivatkozással
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Adjon hozzá egy bekezdést többsoros hiperhivatkozással
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Adjon hozzá egy bekezdést egy képet tartalmazó hiperhivatkozással
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## 6. lépés: Mentse el a címkézett PDF-dokumentumot

Végül elmentjük a címkézett PDF dokumentumot.

```csharp
// Mentse el a címkézett PDF dokumentumot
document. Save(outFile);
```

## 7. lépés: Ellenőrizze a PDF/UA megfelelőséget

 A dokumentum PDF/UA megfelelőségét is ellenőrizhetjük a`Validate` módszere a`Document` osztály.

```csharp
// Ellenőrizze a PDF/UA megfelelőséget
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Minta forráskód a Link Structure Elements számára az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//Dokumentum létrehozása és címkézett PDF tartalom beszerzése
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// A dokumentum címének és természetének nyelvének beállítása
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Gyökérstruktúra elem lekérése (Dokumentumstruktúra elem)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Címkézett PDF dokumentum mentése
document.Save(outFile);

// PDF/UA megfelelőség ellenőrzése
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Következtetés

Gratulálok ! Megtanulta, hogyan kell használni a hivatkozásszerkezet elemeit az Aspose.PDF for .NET-hez. Mostantól hiperhivatkozásokat hozhat létre PDF-dokumentumaiban, lehetővé téve a felhasználók számára az online forrásokhoz való navigálást. Kísérletezzen és fedezzen fel az Aspose.PDF további funkcióit interaktív és gazdagított PDF dokumentumok létrehozásához.

### GYIK

#### K: Mik azok a linkstruktúra elemei egy PDF-dokumentumban, és hogyan javítják a dokumentumok interaktivitását?

V: A PDF-dokumentumban található hivatkozásszerkezet elemei hiperhivatkozások létrehozására szolgálnak, amelyek lehetővé teszik a felhasználók számára, hogy online forrásokhoz vagy a dokumentumon belüli meghatározott helyekhez navigáljanak. Ezek az elemek fokozzák az interaktivitást azáltal, hogy kattintható hivatkozásokat biztosítanak, amelyek lehetővé teszik a felhasználók számára, hogy hozzáférjenek a kapcsolódó tartalmakhoz vagy külső webhelyekhez.

#### K: Hogyan lehetnek előnyösek a linkszerkezet elemei egy PDF-dokumentumban?

V: A hivatkozásszerkezet elemei a PDF-dokumentum interaktívvá tételével javítják a felhasználói élményt. Gyors hozzáférést biztosítanak a további információkhoz, kapcsolódó tartalmakhoz, külső webhelyekhez vagy a dokumentum egyes szakaszaihoz, javítva a navigációt és megkönnyítve az információkeresést.

#### K: Létrehozhatok különböző típusú hiperhivatkozásokat az Aspose.PDF for .NET hivatkozásszerkezetének elemeivel?

V: Igen, különféle típusú hiperhivatkozásokat hozhat létre hivatkozásstruktúra elemekkel. Az Aspose.PDF for .NET lehetővé teszi, hogy sima szöveget, formázott szöveget, képeket és többsoros leírásokat tartalmazó hiperhivatkozásokat hozzon létre, sokoldalúságot biztosítva a dokumentumon belüli külső tartalomra vagy helyekre mutató hivatkozásokban.

#### K: Hogyan állíthatok be és inicializálhatom a hivatkozásszerkezet elemeit egy PDF-dokumentumban az Aspose.PDF for .NET használatával?

 V: A hivatkozásszerkezet elemeinek használatához először létre kell hoznia egy új PDF dokumentumot a`Document` osztály. Ezután szerezze be a címkézett tartalmat a`TaggedContent` dokumentum tulajdonsága. Innen létrehozhat és testreszabhat hivatkozásszerkezeti elemeket, és hozzáadhatja őket a gyökérstruktúra elemhez.

#### K: Hogyan hozhatok létre egyszerű szöveges hiperhivatkozást hivatkozásszerkezeti elemek használatával?
 V: Létrehozhat egy egyszerű szöveges hiperhivatkozást az a`LinkElement` és annak beállítása`Hyperlink` ingatlan a`WebHyperlink` azzal az URL-lel, amelyre hivatkozni szeretne. A hivatkozás megjelenítési szövegét a gombbal is beállíthatja`SetText` módszer.

#### K: Lehetséges-e hiperhivatkozásokat létrehozni képekkel linkszerkezeti elemek használatával?

 V: Igen, létrehozhat hiperhivatkozásokat képekkel a hivatkozásszerkezet elemeinek használatával. Létrehozna a`LinkElement` majd fűzze hozzá a`FigureElement` képpel hozzá. Ez lehetővé teszi egy kép alapú hiperhivatkozás létrehozását.

#### K: Hogyan biztosíthatom, hogy a hiperhivatkozásokat tartalmazó PDF-dokumentumom megfeleljen a PDF/UA akadálymentesítési szabványának?

 V: Az Aspose.PDF for .NET lehetővé teszi a PDF-dokumentum PDF/UA szabványnak való megfelelőségének ellenőrzését a`Validate` módszere a`Document`osztály. Ez biztosítja, hogy a dokumentum hiperhivatkozásai elérhetőek legyenek a fogyatékkal élő felhasználók számára.

#### K: Mik a hivatkozásszerkezet elemeinek alternatív leírásai, és miért fontosak?

V: A hivatkozásszerkezet elemeinek alternatív leírásai (alt szöveg) szöveges leírást adnak a hiperhivatkozásokról. Ezek a leírások elengedhetetlenek az akadálymentesítéshez, lehetővé téve a látássérült felhasználók számára, hogy megértsék a link célját és célját.

#### K: Testreszabhatom a hivatkozásszerkezet elemeivel létrehozott hiperhivatkozások megjelenését és viselkedését?

V: Míg a hivatkozásszerkezet elemei elsősorban a hiperhivatkozások létrehozására összpontosítanak, a hivatkozások megjelenését és viselkedését az Aspose.PDF for .NET által kínált egyéb szolgáltatások segítségével tovább testreszabhatja. Ez magában foglalja a színek, stílusok és hivatkozási műveletek megadását.

#### K: Hogyan járulnak hozzá a linkszerkezet elemei a PDF-dokumentumok interaktívabbá és felhasználóbarátabbá tételéhez?

V: A hivatkozásszerkezet elemei kattintható hiperhivatkozások hozzáadásával a statikus PDF-dokumentumokat interaktív élményekké alakítják. Ez az interaktivitás javítja a felhasználók elkötelezettségét, zökkenőmentes navigációt tesz lehetővé a kapcsolódó tartalmak között, és javítja a dokumentum általános használhatóságát.