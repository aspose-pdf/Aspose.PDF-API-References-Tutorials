---
title: Egyéni tabulátorok a PDF-fájlban
linktitle: Egyéni tabulátorok a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan hozhat létre egyéni tabulátorokat PDF-fájlban az Aspose.PDF for .NET segítségével.
type: docs
weight: 120
url: /hu/net/programming-with-text/custom-tab-stops/
---

Ez az oktatóanyag végigvezeti az egyéni tabulátorok létrehozásának folyamatán PDF-fájlban az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyben egyéni tabulátorokat szeretne létrehozni, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Hozzon létre egy új dokumentumpéldányt
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Document _pdfdocument = new Document();
```

## 5. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Új oldal hozzáadása a dokumentumhoz a gombbal`Add` módszere a`Pages`gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`page`.

```csharp
Page page = _pdfdocument.Pages.Add();
```

## 6. lépés: Hozzon létre egyéni tabulátorokat
 Hozzon létre a`TabStops` objektumot, és adjunk hozzá egyéni tabulátorokat. Állítsa be az igazítás típusát és a vezető típusát minden tabulátorhoz.

```csharp
TabStops ts = new TabStops();
TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;

TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;

TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
```

## 7. lépés: Hozzon létre szövegrészleteket tabulátorokkal
 Teremt`TextFragment` objektumokat, és adja át nekik az egyéni tabulátorokat. Használja a speciális karaktereket`#$TAB` a szövegen belüli tabulátorok jelzésére.

```csharp
TextFragment header = new TextFragment("This is an example of forming a table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));

page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
```

## 8. lépés: Mentse el a PDF dokumentumot
 Mentse el a PDF dokumentumot a`Save` módszere a`Document` objektum.

```csharp
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

### Minta forráskód az egyéni tabulátorokhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document _pdfdocument = new Document();
Page page = _pdfdocument.Pages.Add();
Aspose.Pdf.Text.TabStops ts = new Aspose.Pdf.Text.TabStops();
Aspose.Pdf.Text.TabStop ts1 = ts.Add(100);
ts1.AlignmentType = TabAlignmentType.Right;
ts1.LeaderType = TabLeaderType.Solid;
Aspose.Pdf.Text.TabStop ts2 = ts.Add(200);
ts2.AlignmentType = TabAlignmentType.Center;
ts2.LeaderType = TabLeaderType.Dash;
Aspose.Pdf.Text.TabStop ts3 = ts.Add(300);
ts3.AlignmentType = TabAlignmentType.Left;
ts3.LeaderType = TabLeaderType.Dot;
TextFragment header = new TextFragment("This is a example of forming table with TAB stops", ts);
TextFragment text0 = new TextFragment("#$TABHead1 #$TABHead2 #$TABHead3", ts);
TextFragment text1 = new TextFragment("#$TABdata11 #$TABdata12 #$TABdata13", ts);
TextFragment text2 = new TextFragment("#$TABdata21 ", ts);
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data22 "));
text2.Segments.Add(new TextSegment("#$TAB"));
text2.Segments.Add(new TextSegment("data23"));
page.Paragraphs.Add(header);
page.Paragraphs.Add(text0);
page.Paragraphs.Add(text1);
page.Paragraphs.Add(text2);
dataDir = dataDir + "CustomTabStops_out.pdf";
_pdfdocument.Save(dataDir);
Console.WriteLine("\nCustom tab stops setup successfully.\nFile saved at " + dataDir);
```

## Következtetés
Sikeresen létrehozott egy PDF-dokumentumot egyéni tabulátorokkal az Aspose.PDF for .NET használatával. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

### GYIK

#### K: Mi áll ennek az oktatóanyagnak a középpontjában?

V: Ez az oktatóanyag az Aspose.PDF for .NET könyvtár használatával történő egyéni tabulátorok létrehozásának folyamatán segíti Önt. A mellékelt C# forráskód bemutatja az ehhez szükséges lépéseket.

#### K: Milyen névtereket importáljak ehhez az oktatóanyaghoz?

V: Abban a kódfájlban, amelyben egyéni tabulátorokat szeretne létrehozni, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre új dokumentumpéldányt?

 V: A 4. lépésben egy új példányt fog létrehozni`Document` objektumot a megadott kód segítségével.

#### K: Hogyan adhatok hozzá oldalt a dokumentumhoz?

 V: Az 5. lépésben új oldalt ad hozzá a dokumentumhoz a`Add` módszere a`Pages` gyűjtemény.

#### K: Hogyan hozhatok létre egyéni tabulátorokat?

 V: A 6. lépésben létrehoz egy`TabStops` objektumot, és adjunk hozzá egyéni tabulátorokat. Az egyes tabulátorokhoz igazítási és vezetőtípusokat is beállíthat.

#### K: Hogyan hozhatok létre szövegrészleteket tabulátorokkal?

 V: A 7. lépésben létre kell hozni`TextFragment` objektumokat, és adja át nekik az egyéni tabulátorokat. Használja a speciális karaktereket`#$TAB` a szövegen belüli tabulátorok jelzésére.

#### K: Hogyan menthetem el a PDF dokumentumot?

 V: A 8. lépésben a PDF-dokumentumot a`Save` módszere a`Document` objektum.

#### K: Mi a fő kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan hozhat létre egyéni tabulátorokkal rendelkező PDF-dokumentumot az Aspose.PDF for .NET használatával. Ez hasznos lehet a szöveg strukturált rendezéséhez és igazításához.