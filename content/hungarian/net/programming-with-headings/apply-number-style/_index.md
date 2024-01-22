---
title: Számstílus alkalmazása PDF-fájlban
linktitle: Számstílus alkalmazása PDF-fájlban
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan alkalmazhat számozási stílust a PDF-fájlok címsoraira az Aspose.PDF for .NET segítségével. Lépésről lépésre útmutató.
type: docs
weight: 10
url: /hu/net/programming-with-headings/apply-number-style/
---
Ebben az oktatóanyagban lépésről lépésre végigvezetjük a következő C#-forráskódon a számozási stílus alkalmazásához PDF-fájlban az Aspose.PDF for .NET segítségével.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette az Aspose.PDF könyvtárat, és beállította a fejlesztői környezetet. C# programozási alapismeretekkel is rendelkezel.

### 1. lépés: Dokumentumkönyvtár beállítása

A megadott forráskódban meg kell adnia azt a könyvtárat, ahová a generált PDF fájlt menteni szeretné. Módosítsa a "dataDir" változót a kívánt könyvtárra.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2. lépés: A PDF-dokumentum létrehozása

Létrehozunk egy új PDF dokumentumot meghatározott méretekkel és margókkal.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### 3. lépés: Oldal és lebegő tároló létrehozása

Hozzáadunk egy oldalt a dokumentumhoz, és létrehozunk egy lebegő tárolót a tartalom rendszerezéséhez.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### 4. lépés: Adjon hozzá címsorokat számozással

Adott számozású fejléceket készítünk, és hozzáadjuk a lebegő tárolóhoz.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### 5. lépés: Mentse el a PDF-dokumentumot

A létrehozott PDF dokumentumot a megadott könyvtárba mentjük.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Minta forráskód az Apply Number Style programhoz az Aspose.PDF for .NET használatával 
```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Következtetés

Ebben az oktatóanyagban elmagyaráztuk, hogyan lehet számozási stílust alkalmazni egy PDF-dokumentum címsoraira az Aspose.PDF for .NET használatával. Mostantól ezt a tudást felhasználhatja PDF-dokumentumok létrehozására egyéni címsorszámozással.

### GYIK a számstílus alkalmazásához PDF-fájlban

#### K: Mi az a számozási stílus egy PDF-dokumentumban?

V: A számozási stílus arra a formátumra utal, amelyben a fejlécek vagy szakaszok számozásra kerülnek a PDF-dokumentumban. Tartalmazhat számokat, betűket vagy más karaktereket, amelyek hierarchikus szerkezetet biztosítanak.

#### K: Miért kell számozási stílust alkalmaznom a PDF-dokumentumok címsoraira?

V: A címsorok számozási stílusának alkalmazása javítja a PDF-dokumentum olvashatóságát és rendszerezését. Segít az olvasóknak könnyen eligazodni és megérteni a tartalom hierarchikus szerkezetét.

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PDF-fájlokkal .NET-alkalmazásokban. Funkciók széles skáláját kínálja PDF dokumentumok létrehozásához, szerkesztéséhez, konvertálásához és kezeléséhez.

#### K: Hogyan importálhatom a szükséges könyvtárakat a C# projektemhez?

V: A C#-projekthez szükséges könyvtárak importálásához adja meg a következő importálási direktívákat:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ezek az utasítások lehetővé teszik a PDF-dokumentumok kezeléséhez és a számozási stílusok alkalmazásához szükséges osztályok és módszerek elérését.

#### K: Hogyan adhatom meg a létrehozott PDF fájl mentési könyvtárát?

V: A megadott forráskódban módosítsa a "dataDir" változót, és adja meg azt a könyvtárat, ahová menteni szeretné a létrehozott PDF-fájlt.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a tényleges könyvtár elérési útjával.

#### K: Hogyan hozhatok létre PDF-dokumentumot meghatározott méretekkel és margókkal?

V: Adott méretekkel és margókkal rendelkező PDF-dokumentum létrehozásához használja a következő kódot:

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### K: Hogyan adhatok hozzá számozási stílusú címsorokat a PDF-dokumentumhoz?

V: Ha számozási stílusú címsorokat szeretne hozzáadni a PDF-dokumentumhoz, használja a mellékelt kódmintákat a címsorok létrehozásához és a számozási stílusok testreszabásához. Szükség szerint állítsa be a tulajdonságokat, például a szöveget, a számozási stílust, a kezdőszámot és az automatikus sorrendet.

#### K: Hogyan menthetem el a létrehozott PDF dokumentumot?

 V: A létrehozott PDF dokumentum mentéséhez használja a`Save` módszere a`pdfDoc` tárgy:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### K: Hogyan erősíthetem meg, hogy a számozási stílust alkalmazták?

V: Nyissa meg a létrehozott PDF-fájlt, és ellenőrizze, hogy a megadott számozási stílust alkalmazta-e a címsorokhoz.

#### K: Tovább szabhatom a számozási stílust?

 V: Igen, tovább szabhatja a számozási stílust a tulajdonságok beállításával`Heading` objektumok, például számozási stílus típusa, kezdőszám és automatikus sorozat.

#### K: Alkalmazhatok különböző számozási stílusokat a dokumentum különböző szakaszaira?

V: Igen, többféle számozási stílust is alkalmazhat a dokumentum különböző szakaszaira, ha több példányt hoz létre`Heading` különböző stílusú és sorozatú objektumok.