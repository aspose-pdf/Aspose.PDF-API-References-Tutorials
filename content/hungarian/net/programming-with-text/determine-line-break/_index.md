---
title: Határozza meg a sortörést a PDF-fájlban
linktitle: Határozza meg a sortörést a PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan határozhatja meg a sortöréseket PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 130
url: /hu/net/programming-with-text/determine-line-break/
---
Ez az oktatóanyag végigvezeti Önt a sortörések meghatározásán a PDF-fájlban az Aspose.PDF for .NET használatával. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyben meg szeretné határozni a sortöréseket, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Hozzon létre egy új dokumentumpéldányt
 Példányosítson egy újat`Document` objektumot a következő kódsor hozzáadásával:

```csharp
Document doc = new Document();
```

## 5. lépés: Adjon hozzá egy oldalt a dokumentumhoz
 Adjon hozzá egy új oldalt a dokumentumhoz a`Add` módszere a`Pages` gyűjtemény. A megadott kódban az új oldal hozzá van rendelve a változóhoz`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6. lépés: Adjon hozzá szövegrészleteket sortöréssel
Hozzon létre egy hurkot több szövegrészlet hozzáadásához az oldalhoz, amelyek mindegyike tartalmaz egy-egy bekezdést sortöréssel.

```csharp
for (int i = 0; i < 4; i++)
{
     TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
     text.TextState.FontSize = 20;
     page.Paragraphs.Add(text);
}
```

## 7. lépés: Mentse el a PDF-dokumentumot, és bontsa ki a sortörési információkat
 Mentse el a PDF dokumentumot a`Save` módszere a`Document` objektum. Ezután bontsa ki a sortörés információit a`GetNotifications` a kívánt oldal módszerét.

```csharp
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

### Forráskód minta a sortörés meghatározásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextFragment text = new TextFragment("Lorem ipsum \r\ndolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
	text.TextState.FontSize = 20;
	page.Paragraphs.Add(text);
}
doc.Save(dataDir + "DetermineLineBreak_out.pdf");
string notifications = doc.Pages[1].GetNotifications();
File.WriteAllText(dataDir + "notifications_out.txt", notifications);
```

## Következtetés
Sikeresen meghatározta a sortöréseket egy PDF-dokumentumban az Aspose.PDF for .NET használatával. A sortörés információi ki lettek bontva és elmentve egy szöveges fájlba.

### GYIK

#### K: Mi a fő hangsúly ebben az oktatóanyagban?

V: Ez az oktatóanyag arra összpontosít, hogy végigvezeti Önt a sortörések meghatározásán egy PDF-fájlban az Aspose.PDF for .NET könyvtár használatával. A mellékelt C# forráskód bemutatja az ehhez szükséges lépéseket.

#### K: Mely névtereket kell importálnom ehhez az oktatóanyaghoz?

V: Abban a kódfájlban, amelyben sortörést szeretne meghatározni, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre új dokumentumpéldányt?

 V: A 4. lépésben egy új példányt fog létrehozni`Document` objektumot a megadott kód segítségével.

#### K: Hogyan adhatok hozzá oldalt a dokumentumhoz?

 V: Az 5. lépésben új oldalt ad hozzá a dokumentumhoz a`Add` módszere a`Pages` gyűjtemény.

#### K: Hogyan adhatok hozzá szövegrészleteket sortöréssel?

V: A 6. lépésben létrehoz egy hurkot, amellyel több szövegrészletet ad hozzá az oldalhoz, amelyek mindegyike tartalmaz egy-egy bekezdést sortöréssel.

#### K: Hogyan menthetem el a PDF-dokumentumot és bonthatom ki a sortörési információkat?

 V: A 7. lépésben a PDF-dokumentumot a`Save` módszere a`Document` objektum. Ezután a sortörés információit a`GetNotifications` módszerét, és mentse el egy szöveges fájlba.

#### K: Mi a kinyert sortörési információ célja?

V: A kivont sortörés-információ részleteket ad a PDF-dokumentumban található sortörésekről és értesítésekről. Ez hasznos lehet a szöveg és a bekezdések dokumentumon belüli felépítésének elemzéséhez és megértéséhez.

#### K: Mi a fő kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan határozhat meg sortöréseket egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Ezt a tudást felhasználhatja a PDF-fájlok sortörési információinak programozottan történő kinyerésére és elemzésére.