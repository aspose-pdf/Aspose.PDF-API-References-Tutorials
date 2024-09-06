---
title: Jegyzetszerkezeti elem létrehozása
linktitle: Jegyzetszerkezeti elem létrehozása
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre strukturált jegyzetelemek létrehozásához PDF-dokumentumban az Aspose.PDF for .NET használatával.
type: docs
weight: 30
url: /hu/net/programming-with-tagged-pdf/create-note-structure-element/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan hozhat létre jegyzetszerkezeti elemet PDF-dokumentumban az Aspose.PDF for .NET használatával. Az Aspose.PDF egy hatékony könyvtár, amely lehetővé teszi PDF-dokumentumok programozott létrehozását, kezelését és konvertálását. Az Aspose.PDF megjelölt tartalomszerkezeti funkcióival strukturált jegyzeteket adhat hozzá PDF-dokumentumához.

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

## 3. lépés: A PDF-dokumentum és a megjegyzés strukturált elemeinek létrehozása

Használja a következő kódot PDF-dokumentum létrehozásához, és jegyzetstrukturált elemek hozzáadásához:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Ez a kód üres PDF-dokumentumot hoz létre, és strukturált jegyzetelemeket ad egy bekezdéshez. Minden jegyzet az Aspose.PDF által biztosított módszerekkel készül.

## 4. lépés: Mentse el a PDF-dokumentumot

A PDF dokumentum mentéséhez használja a következő kódot:

```csharp
document. Save(outFile);
```

Ez a kód elmenti a PDF-dokumentumot a megjegyzés strukturált elemeivel egy megadott fájlba.

### Minta forráskód a Create Note Structure Elementhez az Aspose.PDF for .NET használatával 

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Pdf dokumentum létrehozása
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Bekezdéselem hozzáadása
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// NoteElement hozzáadása
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// NoteElement hozzáadása
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// NoteElement hozzáadása
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
// Kivételt kell dobni – Aspose.Pdf.Tagged.TaggedException : A(z) 'note_002' azonosítójú szerkezetelem már létezik
//note3.SetId("note_002");
// Az eredményül kapott dokumentum nem felel meg a PDF/UA szabványnak, ha a ClearId() függvényt a jegyzetszerkezeti elemhez használja
//note3.ClearId();
// Címkézett PDF dokumentum mentése
document.Save(outFile);
// PDF/UA megfelelőség ellenőrzése
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan hozhat létre jegyzetszerkezeti elemeket PDF-dokumentumban az Aspose.PDF for .NET használatával. A strukturált jegyzetelemek lehetővé teszik további, strukturált információk hozzáadását a PDF-dokumentumhoz.

### GYIK

#### K: Mi a célja a jegyzetszerkezeti elemek létrehozásának egy PDF-dokumentumban az Aspose.PDF for .NET használatával?

V: Ha PDF-dokumentumban jegyzetszerkezeti elemeket hoz létre az Aspose.PDF for .NET használatával, strukturált jegyzeteket adhat hozzá a dokumentum tartalmához. Ezek a megjegyzések további kontextust, magyarázatokat vagy hivatkozásokat adhatnak a tartalom bizonyos részeire.

#### K: Hogyan segít az Aspose.PDF könyvtár a jegyzetszerkezeti elemek létrehozásában egy PDF-dokumentumban?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely funkciókat biztosít PDF-dokumentumok programozott létrehozásához, kezeléséhez és konvertálásához. Ebben az oktatóanyagban a könyvtár megjelölt tartalomszerkezeti funkciói a PDF-dokumentum tartalmán belüli strukturált jegyzetelemek létrehozására szolgálnak.

#### K: Milyen előfeltételei vannak a jegyzetszerkezeti elemek létrehozásának egy PDF-dokumentumban az Aspose.PDF for .NET használatával?

V: Mielőtt elkezdené, győződjön meg arról, hogy a Visual Studio telepítve van a .NET-keretrendszerrel, és hivatkozott-e a projektben a .NET-hez készült Aspose.PDF könyvtárra.

#### K: Hogyan hoz létre a megadott C# kód jegyzetszerkezeti elemeket a PDF dokumentum tartalmában?

V: A kód bemutatja, hogyan hozhat létre PDF-dokumentumot, hogyan határozhat meg jegyzetszerkezeti elemeket, és hogyan adhatja hozzá őket egy bekezdéshez. Minden jegyzet az Aspose.PDF által biztosított módszerekkel készül, lehetővé téve strukturált jegyzetek beépítését a tartalomba.

#### K: Testreszabhatom az általam létrehozott jegyzetszerkezeti elemek tartalmát és tulajdonságait?

V: Igen, testreszabhatja a jegyzetszerkezet elemeinek tartalmát és tulajdonságait az Aspose.PDF könyvtár által biztosított módszerek és tulajdonságok használatával. A kód bemutatja, hogyan állíthatja be a jegyzetelemek szövegét és azonosítóját, de szükség szerint tovább testreszabhatja azokat.

#### K: Hogyan jön létre a hierarchikus kapcsolat a jegyzetszerkezet elemei és a dokumentum tartalma között?

 V: A hierarchikus kapcsolat úgy jön létre, hogy jegyzetszerkezeti elemeket adunk hozzá más strukturált elemekhez, például bekezdésekhez. A kódban a jegyzetelemek a bekezdéselemhez fűződnek a`AppendChild` módszer.

#### K: Hozzárendelhetek egyedi azonosítókat a jegyzetszerkezet elemeihez?

V: Igen, egyedi azonosítókat rendelhet a jegyzetszerkezet elemeihez a segítségével`SetId` módszer. A kód bemutatja, hogyan állíthatja be a jegyzetelemek azonosítóit egyedi értékekre.

#### K: Mi történik, ha megpróbálok ismétlődő azonosítót rendelni egy jegyzetszerkezet elemhez?

V: Ha ismétlődő azonosítót próbál hozzárendelni egy jegyzetszerkezet elemhez, az kivételt eredményez. Az oktatóanyagban található kód tartalmaz egy megjegyzést, amely ezt a forgatókönyvet illusztrálja.

#### K: Hogyan biztosíthatom a PDF/UA megfelelőséget a jegyzetszerkezeti elemek létrehozásakor?

 V: Az oktatóanyagban található kód bemutatja, hogyan ellenőrizhető a PDF/UA megfelelőség a`Validate` módszer. A dokumentum PDF/UA szabvány szerinti érvényesítésével biztosíthatja, hogy a hozzáadott jegyzetszerkezeti elemek megfeleljenek a kisegítő lehetőségeknek.

#### K: Használhatom ezt a megközelítést jegyzetszerkezeti elemek hozzáadására egy meglévő PDF-dokumentumhoz?

V: Igen, módosíthatja a megadott megközelítést, hogy jegyzetszerkezeti elemeket adjon hozzá egy meglévő PDF-dokumentumhoz. Új dokumentum létrehozása helyett töltse be a meglévő dokumentumot az Aspose.PDF használatával, majd kövesse a hasonló lépéseket a jegyzetelemek hozzáfűzéséhez.
