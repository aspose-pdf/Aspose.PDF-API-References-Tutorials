---
title: Címke kép a meglévő PDF-ben
linktitle: Címke kép a meglévő PDF-ben
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan jelölhet meg egy képet egy meglévő PDF-ben az Aspose.PDF for .NET segítségével. Útmutató lépésről lépésre a képekhez címkék hozzáadásához.
type: docs
weight: 210
url: /hu/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Ebben a részletes oktatóanyagban lépésről lépésre végigvezetjük a megadott C# forráskódon, hogy megjelölhessen egy képet egy meglévő PDF-ben az Aspose.PDF for .NET használatával. Kövesse az alábbi utasításokat, hogy megértse, hogyan lehet címkéket hozzáadni egy PDF-fájlhoz.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy a fejlesztői környezetet úgy konfigurálta, hogy az Aspose.PDF for .NET fájlt használja. Ez magában foglalja az Aspose.PDF könyvtár telepítését és a projekt konfigurálását, hogy hivatkozzon rá.

## 2. lépés: Nyissa meg a meglévő PDF-dokumentumot

Ebben a lépésben megnyitunk egy meglévő PDF dokumentumot az Aspose.PDF használatával.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Bemeneti és kimeneti fájl elérési útja
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Nyissa meg a dokumentumot
Document document = new Document(inFile);
```

A meglévő PDF dokumentumot az Aspose.PDF segítségével nyitottuk meg.

## 3. lépés: Szerezze be a címkézett tartalmat és a gyökérstruktúra elemet

Most megkapjuk a PDF dokumentum címkézett tartalmát és a hozzá tartozó gyökérstruktúra elemet.

```csharp
// Szerezzen be címkézett tartalmat és gyökérszerkezeti elemet
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Megkaptuk a PDF dokumentum címkézett tartalmát és a hozzá tartozó gyökérstruktúra elemet.

## 4. lépés: A címkézett PDF-dokumentum címének beállítása

Most állítsuk be a címkézett PDF-dokumentum címét.

```csharp
// Adja meg a címkézett PDF-dokumentum címét
taggedContent.SetTitle("Document with images");
```

Beállítottuk a címkézett PDF dokumentum címét.

## 5. lépés: Rendeljen alternatív szövegeket és határolókeretet a képhez

Most minden képelemhez alternatív szöveget és határolókeretet rendelünk.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Alternatív szöveg hozzárendelése a képhez
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // A határolókeret (bbox) létrehozása és hozzárendelése
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

PDF dokumentumban minden képelemhez alternatív szöveget és határolókeretet rendeltünk.

## 6. lépés: A Span elem áthelyezése a bekezdésbe

Most helyezzük át a Span elemet a bekezdésbe.

```csharp
// A Span elem áthelyezése a bekezdésbe (helytelen terjedelem és bekezdés keresése az első TD-ben)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Mozgassa a Span elemet a bekezdésben
spanElement.ChangeParentElement(paragraph);
```

A Span elemet áthelyeztük a megadott bekezdésbe.

## 7. lépés: Mentse el a módosított PDF dokumentumot

Most, hogy elvégeztük a szükséges változtatásokat, elmentjük a módosított PDF dokumentumot.

```csharp
// Mentse el a PDF dokumentumot
document. Save(outFile);
```

A módosított PDF dokumentumot a megadott könyvtárba mentettük.

### Minta forráskód a Tag Image In Existing PDF-ben az Aspose.PDF for .NET használatával 

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Nyissa meg a dokumentumot
Document document = new Document(inFile);

// Lekéri a címkézett tartalmat és a gyökérstruktúra elemet
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Cím beállítása a címkézett pdf-dokumentumhoz
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Állítsa be az ábra alternatív szövegét
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// BBox attribútum létrehozása és beállítása
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Feszítőelem áthelyezése a bekezdésbe (rossz terjedelem és bekezdés keresése az első TD-ben)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// A Span elem áthelyezése a bekezdésbe
spanElement.ChangeParentElement(paragraph);

// Dokumentum mentése
document.Save(outFile);

// PDF/UA megfelelőség ellenőrzése a kiadott dokumentumhoz
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan jelölhet meg egy képet egy meglévő PDF-ben az Aspose.PDF for .NET használatával. Az Aspose.PDF segítségével címkéket adhat hozzá, és szerkesztheti a PDF-dokumentumokban lévő képeket.

### GYIK

#### K: Mi a fő célja ennek az oktatóanyagnak a meglévő PDF-ben lévő képek Aspose.PDF for .NET használatával címkézésével kapcsolatban?

V: Ennek az oktatóanyagnak az elsődleges célja, hogy végigvezesse a kép megjelölésének folyamatán egy meglévő PDF-dokumentumban az Aspose.PDF for .NET használatával. Az oktatóanyag lépésenkénti utasításokat és C# forráskód példákat tartalmaz, amelyek segítenek megérteni, hogyan rendelhet hozzá alternatív szöveget és határolókereteket a képekhez, hogyan helyezhet át elemeket a dokumentumon belül, és hogyan adhat hozzá címkéket a képekhez.

#### K: Milyen előfeltételei vannak ennek az oktatóanyagnak a PDF-ben található képek Aspose.PDF for .NET használatával történő címkézésével kapcsolatban?

V: Mielőtt elkezdené, győződjön meg arról, hogy a fejlesztői környezetet az Aspose.PDF for .NET használatára állította be. Ez magában foglalja az Aspose.PDF könyvtár telepítését és a projekt konfigurálását, hogy hivatkozzon rá.

#### K: Hogyan nyithatok meg egy meglévő PDF-dokumentumot, és érhetem el a címkézett tartalmát az Aspose.PDF for .NET használatával?

V: Az oktatóanyag C#-forráskód példákat mutat be, amelyek bemutatják, hogyan lehet megnyitni egy meglévő PDF-dokumentumot az Aspose.PDF for .NET használatával, és hogyan lehet hozzáférni a címkézett tartalmához további kezelés céljából.

#### K: Mi a célja alternatív szövegek és határolókeretek hozzárendelésének a PDF-dokumentum képeihez?

V: Alternatív szövegek és határolókeretek hozzárendelése a képekhez javítja a hozzáférhetőséget azáltal, hogy leíró szöveget biztosít a képekhez, és meghatározza azok elrendezését és elhelyezkedését a dokumentumban. Ez az információ döntő fontosságú a képernyőolvasók és más segítő technológiák számára.

#### K: Hogyan állíthatom be egy címkézett PDF-dokumentum címét az Aspose.PDF for .NET használatával?

V: Az oktatóanyag C#-forráskód-példákat tartalmaz, amelyek bemutatják, hogyan lehet beállítani egy címkézett PDF-dokumentum címét az Aspose.PDF for .NET használatával.

#### K: Mit foglal magában az elemek mozgatása egy PDF dokumentumon belül?

V: A PDF dokumentumon belüli elemek áthelyezése egy adott elem szülőelemének megváltoztatását jelenti. Ebből az oktatóanyagból megtudhatja, hogyan helyezhet át egy Span elemet egy táblázatban megadott bekezdéselembe.

#### K: Hogyan menthetem el a módosított PDF-dokumentumot a címkék hozzáadása és a képek szerkesztése után?

 V: Miután hozzáadta a címkéket, hozzárendelt alternatív szöveget, beállította a határolókereteket, és szerkesztette a PDF-dokumentumot, a mellékelt C#-forráskód-példák segítségével elmentheti a módosított PDF-dokumentumot a`Save()` módszer.

#### K: Mi a célja az oktatóanyagban található mintaforráskódnak?

V: A mintaforráskód gyakorlati referenciaként szolgál a képek címkézéséhez és manipulálásához az Aspose.PDF for .NET használatával. Ezt a kódot használhatja kiindulási pontként, és módosíthatja sajátos igényei szerint.

#### K: Alkalmazhatom ezeket a technikákat egy PDF-dokumentum más típusú elemeire is, nem csak képekre?

V: Igen, az ebben az oktatóanyagban bemutatott technikák adaptálhatók a PDF-dokumentum különféle elemeinek kezelésére. Hasonló elveket alkalmazhat más elemek, például szöveg, táblázatok és egyebek címkézésére és manipulálására.

#### K: Hogyan ellenőrizhetem a módosított PDF dokumentum PDF/UA megfelelőségét?

 V: Az oktatóanyag C# forráskód példákat tartalmaz, amelyek bemutatják, hogyan ellenőrizhető a módosított PDF-dokumentum PDF/UA megfelelősége a`Validate()` módszert és XML jelentést generál.

#### K: Milyen egyéb funkciókat kínál az Aspose.PDF for .NET a PDF-dokumentumok kezeléséhez?

V: Az Aspose.PDF for .NET szolgáltatások széles skáláját kínálja a PDF-dokumentumokkal való munkavégzéshez, beleértve a szövegkezelést, a képbeszúrást, a táblázatkészítést, az űrlapmezők kezelését, a digitális aláírásokat, a megjegyzéseket stb. A további feltáráshoz tekintse meg a hivatalos dokumentációt és forrásokat.