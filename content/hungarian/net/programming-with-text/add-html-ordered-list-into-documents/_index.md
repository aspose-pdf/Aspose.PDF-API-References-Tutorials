---
title: HTML rendezett lista hozzáadása a dokumentumokhoz
linktitle: Adjon hozzá HTMLRendezett listát a dokumentumokhoz
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá rendezett HTML-listát egy dokumentumhoz az Aspose.PDF for .NET használatával.
type: docs
weight: 30
url: /hu/net/programming-with-text/add-html-ordered-list-into-documents/
---
Ebből az oktatóanyagból megtudhatja, hogyan használhatja az Aspose.PDF for .NET könyvtárat HTML rendezett lista hozzáadásához a dokumentumhoz. A mellékelt kód bemutatja a feladat végrehajtásához szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyhez hozzá szeretné adni a HTML rendezett listát, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat és a kimeneti fájl elérési útját
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

 Ezután keresse meg azt a sort, amely ezt mondja`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` és cserélje ki`"AddHTMLOrderedListIntoDocuments_out.pdf"` a kimeneti PDF-fájl kívánt nevével.

## 4. lépés: Hozzon létre egy új dokumentum objektumot
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Document doc = new Document();
```

## 5. lépés: Hozzon létre egy HtmlFragment objektumot a HTML-tartalommal
 Példányosítása an`HtmlFragment` objektumot a dokumentumhoz hozzáadni kívánt HTML-tartalommal. A megadott kódban a HTML-tartalom hozzá van rendelve a változóhoz`t`. A HTML tartalmat szükség szerint módosíthatja.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## 6. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Új oldal hozzáadása a dokumentumhoz a gombbal`Add` módszere a`Pages`gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`page`.

```csharp
Page page = doc.Pages.Add();
```

## 7. lépés: Adja hozzá a HtmlFragmentet az oldalhoz
 Add hozzá a`HtmlFragment` objektumot az oldalra a`Add` módszere a`Paragraphs` gyűjtemény.

```csharp
page.Paragraphs.Add(t);
```

## 8. lépés: Mentse el a PDF dokumentumot
 Mentse el a kapott PDF-fájlt a`Save` módszere a`Document` objektum. Adja meg a kimeneti fájl elérési útját, amelyet a 3. lépésben állított be.

```csharp
doc.Save(outFile);
```

### Minta forráskód a HTMLRendezett lista dokumentumokhoz való hozzáadásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// A kimeneti dokumentum elérési útja.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Dokumentum objektum példányosítása
Document doc = new Document();
// Példányosítsa a HtmlFragment objektumot a megfelelő HTML-részlettel
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// Oldal hozzáadása az Oldalgyűjteményhez
Page page = doc.Pages.Add();
// HtmlFragment hozzáadása az oldalhoz
page.Paragraphs.Add(t);
// Az eredményül kapott PDF fájl mentése
doc.Save(outFile);
```

## Következtetés
Sikeresen hozzáadott egy HTML rendezett listát egy dokumentumhoz az Aspose.PDF for .NET használatával. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

Ne felejtse el személyre szabni a HTML-tartalmat, és módosítsa a kódot az Ön egyedi igényei szerint.

### GYIK

#### K: Mi a célja ennek az oktatóanyagnak?

V: Ennek az oktatóanyagnak az a célja, hogy végigvezeti Önt egy HTML-sorrendezett lista dokumentumhoz való hozzáadásának folyamatán az Aspose.PDF for .NET könyvtár használatával. Részletes utasításokat és kódrészleteket tartalmaz, amelyek segítenek elérni ezt a feladatot.

#### K: Milyen névtereket kell importálnom ehhez az oktatóanyaghoz?

V: Importálnia kell a következő névtereket a kódfájl tetején:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat és a kimeneti fájl elérési útját?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával. Ezenkívül keresse meg a vonalat`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` és cserélje ki`"AddHTMLOrderedListIntoDocuments_out.pdf"` a kívánt kimeneti PDF fájlnévvel.

#### K: Testreszabhatom a dokumentumhoz hozzáadandó HTML-tartalmat?

 V: Abszolút! Az 5. lépésben létrehoz egy`HtmlFragment` nevű objektum`t` amely a HTML-tartalmat tartalmazza. Módosíthatja a HTML-tartalmat a backticken belül, hogy megfeleljen az igényeinek.

#### K: Hogyan adhatom hozzá a HTML rendezett listát a dokumentum egy oldalához?

 V: A 7. lépésben hozzáadja a`HtmlFragment` tárgy (`t` ) az oldalra a`Add` módszere a`Paragraphs`gyűjtemény. Ez zökkenőmentesen integrálja a HTML rendezett listát a dokumentumba.

#### K: Hogyan menthetem el az eredményül kapott PDF-dokumentumot?

 V: A HTML-tartalom hozzáadása és egy oldalon való elrendezése után a PDF-dokumentumot a következővel mentheti el`Save` módszere a`Document` objektum. Ügyeljen arra, hogy a korábban beállított helyes kimeneti fájl elérési utat adja meg.

#### K: Meg tudná adni a mintaforráskód összefoglalását referenciaként?

V: Természetesen! Íme az oktatóanyagban található minta forráskód összefoglaló változata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Ennek az oktatóanyagnak a követésével sikeresen megtanulta, hogyan használhatja fel az Aspose.PDF for .NET könyvtárat, hogy HTML formátumban rendezett listát építsen be egy dokumentumba. Ez az új tudás felhasználható a dokumentumkészítési és -manipulációs folyamatok javítására.