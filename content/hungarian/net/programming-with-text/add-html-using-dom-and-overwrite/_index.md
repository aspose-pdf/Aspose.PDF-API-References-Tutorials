---
title: HTML hozzáadása DOM és PDF felülírás segítségével
linktitle: Adjon hozzá HTML-t a DOM használatával és írja felül
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat hozzá HTML-tartalmat DOM-mal és PDF-felülírással az Aspose.PDF for .NET fájlban.
type: docs
weight: 50
url: /hu/net/programming-with-text/add-html-using-dom-and-overwrite/
---
Ez az oktatóanyag végigvezeti a HTML-tartalom hozzáadásának folyamatán a DOM (Document Object Model) használatával az Aspose.PDF for .NET-ben. Ezenkívül megtanulhatja, hogyan írhatja felül a HTML-tartalom stílusait. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyhez hozzá szeretné adni a HTML-tartalmat, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat és a kimeneti fájl elérési útját
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. lépés: Hozzon létre egy új dokumentum objektumot
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Document doc = new Document();
```

## 5. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Új oldal hozzáadása a dokumentumhoz a gombbal`Add` módszere a`Pages`gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6. lépés: Hozzon létre egy HTML-töredéket a HTML-tartalommal
 Példányosítása an`HtmlFragment` objektumot, és biztosítsa a kívánt HTML-tartalmat. A megadott kódban a HTML-tartalom hozzá van rendelve a változóhoz`title`. A HTML tartalmat szükség szerint módosíthatja.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## 7. lépés: Írja felül a HTML-tartalom stílusait
 A HTML-tartalom stílusainak felülírásához módosíthatja a`TextState` tulajdonságai a`HtmlFragment` objektum. A megadott kódban a betűcsalád „Arial”-ra változik, a betűméret pedig 20-ra van állítva.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## 8. lépés: Állítsa be a margóinformációkat
Ha szükséges, állítsa be a HTML-részlet alsó és felső margóját. A megadott kódban az alsó margó 10, a felső margó pedig 400.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## 9. lépés: Adja hozzá a HtmlFragmentet az oldalhoz
 Add hozzá a`HtmlFragment` tiltakozik az oldal bekezdésgyűjteményével szemben.

```csharp
page.Paragraphs.Add(title);
```

## 10. lépés: Mentse el a PDF dokumentumot
 Mentse el a PDF dokumentumot a`Save` módszere a`Document` objektum. Adja meg a kimeneti fájl elérési útját, amelyet a 3. lépésben állított be.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### Minta forráskód a HTML hozzáadása DOMA használatával és felülírás Aspose.PDF segítségével .NET-hez 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Dokumentum objektum példányosítása
Document doc = new Document();
// Oldal hozzáadása a PDF-fájl oldalgyűjteményéhez
Page page = doc.Pages.Add();
// HtmlFragment példányosítása HTML-kontnetekkel
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//A „Verdana” betűtípuscsaládja vissza lesz állítva „Arial”-ra
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// Állítsa be az alsó margó információit
title.Margin.Bottom = 10;
// Állítsa be a felső margó információit
title.Margin.Top = 400;
// HTML-töredék hozzáadása az oldal bekezdésgyűjteményéhez
page.Paragraphs.Add(title);
// PDF fájl mentése
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF fájl mentése
doc.Save(dataDir);
```

## Következtetés
Sikeresen hozzáadott HTML-tartalmat a DOM használatával az Aspose.PDF for .NET-hez, és felülírta a HTML-tartalom stílusait. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

### GYIK

#### K: Mi áll ennek az oktatóanyagnak a középpontjában?

V: Ez az oktatóanyag végigvezeti Önt a HTML-tartalom PDF-dokumentumokhoz való hozzáadásának folyamatán az Aspose.PDF for .NET-ben található Document Object Model (DOM) segítségével. Ezenkívül megtanulhatja, hogyan írhatja felül a HTML-tartalom stílusait, így testreszabhatja a megjelenését. Az oktatóanyag C# forráskódrészleteket tartalmaz a szükséges lépések bemutatásához.

#### K: Milyen névtereket kell importálnom ehhez az oktatóanyaghoz?

V: Abba a kódfájlba, amelybe HTML-tartalmat kíván hozzáadni, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat és a kimeneti fájl elérési útját?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre egy dokumentum objektumot?

 V: A 4. lépésben egy új példányt fog létrehozni`Document` objektum a következő kódsor használatával:

```csharp
Document doc = new Document();
```

#### K: Hogyan adhatok hozzá oldalt a dokumentumhoz?

 V: Az 5. lépésben új oldalt ad hozzá a dokumentumhoz a`Add` módszere a`Pages` gyűjtemény:

```csharp
Page page = doc.Pages.Add();
```

#### K: Hogyan állíthatok be HTML tartalmat a DOM segítségével?

 V: A 6. lépésben létrehoz egy`HtmlFragment` objektumot, és rendelje hozzá a kívánt HTML-tartalmat. A HTML-tartalom hozzá van rendelve a változóhoz`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### K: Hogyan írhatom felül a HTML-tartalom stílusait?

 V: A 7. lépésben felülírja a HTML-tartalom stílusát a`TextState` tulajdonságai a`HtmlFragment` objektum. Például módosíthatja a betűcsaládot "Arial"-ra, és beállíthatja a betűméretet 20-ra:

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### K: Beállíthatom a HTML-tartalom margóját?

V: Igen, a 8. lépésben szükség szerint módosíthatja a HTML-részlet alsó és felső margóját:

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### K: Hogyan adhatom hozzá a HTML-töredéket a PDF-dokumentumhoz?

 V: A 9. lépésben hozzáadja a`HtmlFragment` tárgy (`title`) az oldal bekezdésgyűjteményéhez:

```csharp
page.Paragraphs.Add(title);
```

#### K: Hogyan menthetem el az eredményül kapott PDF-dokumentumot?

 V: A HTML-tartalom hozzáadása és a stílusok testreszabása után használja a`Save` módszere a`Document` objektum a PDF dokumentum mentéséhez:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### K: Mi a legfontosabb kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével sikeresen megtanulta, hogyan építhet be HTML-tartalmat a Document Object Model (DOM) segítségével az Aspose.PDF for .NET-ben. Ezenkívül lehetőséget kapott a stílusok felülírására, hogy személyre szabhassa a HTML-tartalom megjelenését az eredményül kapott PDF-dokumentumban.