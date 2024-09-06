---
title: Soron belüli szerkezeti elemek
linktitle: Soron belüli szerkezeti elemek
second_title: Aspose.PDF for .NET API Reference
description: Lépésről lépésre az online szerkezeti elemek használatához az Aspose.PDF for .NET-hez. Rendezze PDF-fájljait címsorokkal és bekezdésekkel.
type: docs
weight: 110
url: /hu/net/programming-with-tagged-pdf/inline-structure-elements/
---
Ebben a lépésről lépésre bemutatjuk, hogyan használhatja a soron belüli szerkezeti elemeket az Aspose.PDF for .NET-hez. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi a PDF-dokumentumok programozott kezelését. A beágyazott szerkezeti elemek lehetővé teszik, hogy hierarchikus struktúrát hozzon létre a PDF-dokumentumban különböző szintű címsorok és bekezdések használatával.

Merüljünk el a kódban, és tanuljuk meg a soron belüli szerkezeti elemek használatát az Aspose.PDF for .NET segítségével.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Aspose.PDF könyvtár a .NET-hez telepítve.
2. Alapszintű C# programozási nyelv ismerete.

## 1. lépés: A környezet beállítása

A kezdéshez nyissa meg a C# fejlesztői környezetet, és hozzon létre egy új projektet. Győződjön meg arról, hogy a projektben hozzáadott egy hivatkozást a .NET Aspose.PDF könyvtárára.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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

Most már beállíthatjuk a dokumentum címét és nyelvét.

```csharp
// Határozza meg a dokumentum címét és nyelvét
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## 5. lépés: Szerkezeti elemek online hozzáadása

Most soron belüli szerkezeti elemeket, például különböző szintű címsorokat és bekezdéseket fogunk hozzáadni a dokumentumunkhoz.

```csharp
// Szerezd meg a gyökérstruktúra elemet
StructureElement rootElement = taggedContent.RootElement;

// Adjon hozzá különböző szintű fejléceket
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Adjon hozzá tartalmat minden fejléchez
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Adjon hozzá egy bekezdést
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Adjon hozzá tartalmat a bekezdéshez
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Itt sorközi szerkezeti elemeket hozunk létre, például különböző szintű címsorokat és egy bekezdést, és tartalommal egészítjük ki őket.

## 6. lépés: Mentse el a címkézett PDF-dokumentumot

Végül elmentjük a címkézett PDF dokumentumot.

```csharp
// Mentse el a címkézett PDF dokumentumot
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Minta forráskód az Inline Structure Elements számára az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Pdf dokumentum létrehozása
Document document = new Document();

// Szerezzen tartalmat munkához a TaggedPdf segítségével
ITaggedContent taggedContent = document.TaggedContent;

// Állítsa be a Documnet címét és nyelvét
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Szerezze be a gyökérszerkezeti elemet
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Címkézett PDF dokumentum mentése
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Következtetés

Gratulálok ! Megtanulta a soron belüli szerkezeti elemek használatát az Aspose.PDF for .NET fájlban. Mostantól hierarchikus struktúrát hozhat létre a PDF-dokumentumban különböző szintű címsorok és bekezdések használatával. Fedezze fel az Aspose.PDF további funkcióit, hogy felfedezze a benne rejlő lehetőségeket.

### GYIK

#### K: Mik azok a beépített szerkezeti elemek egy PDF-dokumentumban, és hogyan járulnak hozzá a hierarchikus struktúra létrehozásához?

V: A PDF-dokumentum soron belüli szerkezeti elemei, például a különböző szintű címsorok és bekezdések, hierarchikus struktúra létrehozására szolgálnak, amely strukturált módon szervezi és mutatja be a tartalmat. Ezek az elemek lehetővé teszik egyértelmű hierarchia és információáramlás kialakítását a dokumentumon belül.

#### K: Hogyan javíthatják a beágyazott szerkezeti elemek a PDF-dokumentumok olvashatóságát és rendszerezését?

V: A soron belüli struktúraelemek, különösen a címsorok és bekezdések, logikai struktúrával segítik a PDF-dokumentumok olvashatóságát és rendszerezését. A címsorok különböző fontossági szinteket jeleznek, és segítik az olvasókat a tartalomban való eligazodásban, míg a bekezdések a kapcsolódó információkat csoportosítják.

#### K: Hogyan segíti elő az Aspose.PDF for .NET a beágyazott szerkezeti elemek használatát?

V: Az Aspose.PDF for .NET osztályokat és módszereket kínál a soron belüli struktúraelemek, például címsorok és bekezdések létrehozásához és kezeléséhez. Ezek az elemek testreszabhatók, hierarchikusan rendezhetők, és tartalommal gazdagíthatók a dokumentum vizuális megjelenítésének és hozzáférhetőségének javítása érdekében.

####  K: Mi a célja a`taggedContent` object in relation to inline structure elements?

 V: A`taggedContent` tárgy, kapott a`TaggedContent` tulajdona a`Document`, lehetővé teszi a strukturált elemekkel való munkát, beleértve a beépített szerkezeti elemeket is. Lehetővé teszi fejlécek és bekezdések létrehozását, testreszabását és rendszerezését a dokumentumon belül.

#### K: Hogyan segítik a soron belüli szerkezeti elemek az egyértelmű dokumentumhierarchia létrehozását?

V: A soron belüli szerkezeti elemek, például a különböző szintű címsorok hozzájárulnak egy világos és jól meghatározott hierarchia kialakításához a dokumentumban. Az olvasók gyorsan azonosíthatják a fő témákat, altémákat és a kapcsolódó tartalmakat, így könnyebben eligazodhatnak és megérthetők a dokumentumban.

#### K: Testreszabhatom a soron belüli szerkezeti elemek megjelenését és formázását az Aspose.PDF for .NET használatával?

V: Igen, testreszabhatja a soron belüli szerkezeti elemek megjelenését és formázását. Beállíthat olyan tulajdonságokat, mint a betűstílusok, méretek, színek, igazítás, behúzás és térköz, hogy elérje a címsorok és bekezdések kívánt vizuális megjelenítését.

#### K: Hogyan hozhatok létre és adhatok hozzá különböző szintű fejléceket egy PDF-dokumentumhoz az Aspose.PDF for .NET-hez soron belüli szerkezeti elemeivel?

 V: Különböző szintű címsorokat hozhat létre a`CreateHeaderElement` módszert, majd hozzáfűzi őket a gyökérstruktúra elemhez. Ezt követően az egyes címsorelemekhez tartalmat adhat hozzá a`CreateSpanElement` szövegszakasz létrehozásának módszere.

#### K: Használhatok soron belüli szerkezeti elemeket listák, felsoroláspontok vagy más típusú tartalomszervezés létrehozására egy PDF-dokumentumban?

V: Míg magukat a beágyazott szerkezeti elemeket elsősorban címsorokhoz és bekezdésekhez használják, használhatja őket az Aspose.PDF for .NET által kínált egyéb funkciókkal kombinálva listák, felsoroláspontok, táblázatok és egyéb tartalomszervezési típusok létrehozásához az átfogó tartalomszervezés érdekében. dokumentum szerkezet.

#### K: Hogyan járulnak hozzá a beépített szerkezeti elemek a dokumentumok hozzáférhetőségéhez?

V: A beágyazott szerkezeti elemek döntő szerepet játszanak a dokumentumok hozzáférhetőségének javításában. A megfelelően strukturált címsorok és bekezdések egyértelmű dokumentumhierarchiát biztosítanak, amely segíti a képernyőolvasókat és más segítő technológiákat a tartalom pontos értelmezésében és továbbításában a fogyatékkal élő felhasználók számára.

#### K: Fedezhetem a soron belüli szerkezeti elemek fejlettebb felhasználási lehetőségeit, például interaktív elemek létrehozását vagy multimédia beágyazását?

V: Abszolút! Míg ez az oktatóanyag a címsorok és bekezdések létrehozására összpontosít, az Aspose.PDF for .NET fejlett funkciókat kínál interaktív elemek létrehozásához, multimédia beágyazásához, hiperhivatkozások hozzáadásához stb. Tekintse meg a könyvtár dokumentációját és példáit, hogy elmélyüljön ezekben a fejlett képességekben.