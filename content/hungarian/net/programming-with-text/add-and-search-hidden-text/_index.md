---
title: Rejtett szöveg hozzáadása és keresése PDF fájlban
linktitle: Rejtett szöveg hozzáadása és keresése PDF fájlban
second_title: Aspose.PDF for .NET API Reference
description: Útmutató lépésről lépésre rejtett szöveg hozzáadásához és kereséséhez PDF-fájlban az Aspose.PDF for .NET használatával.
type: docs
weight: 20
url: /hu/net/programming-with-text/add-and-search-hidden-text/
---
Ebben az oktatóanyagban végigvezetjük, hogyan adhat hozzá rejtett szöveget, és hogyan kereshet PDF-fájlban az Aspose.PDF for .NET használatával. Kövesse ezeket a lépéseket a művelet egyszerű végrehajtásához.

## 1. Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más fejlesztői környezet telepítve és konfigurálva.
- Alapszintű C# programozási nyelv ismerete.
- Aspose.PDF könyvtár a .NET-hez telepítve. Letöltheti az Aspose hivatalos webhelyéről.

## 2. PDF dokumentum létrehozása rejtett szöveggel

A kezdéshez használja a következő kódot egy új, rejtett szöveget tartalmazó PDF dokumentum létrehozásához:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Hozzon létre egy dokumentumot
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
// Szövegtulajdonság beállítása - láthatatlan
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

Feltétlenül adja meg a PDF-dokumentum kívánt elérési útját és fájlnevét.

## 3. Keressen szöveget a dokumentumban

Ezután keresni fogunk a rejtett szövegben a PDF dokumentumban. Használja a következő kódot:

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
// Csinálj valamit a töredékekkel
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

Ez megkeresi a rejtett szöveget a PDF dokumentum második oldalán, és megjeleníti a vonatkozó információkat.

### Minta forráskód a Rejtett szöveg hozzáadása és kereséshez az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Dokumentum létrehozása rejtett szöveggel
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//Szövegtulajdonság beállítása - láthatatlan
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//Szöveg keresése a dokumentumban
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//Csinálj valamit a töredékekkel
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## Következtetés

Gratulálok ! Sikeresen hozzáadott és rejtett szöveget talált egy PDF-dokumentumban az Aspose.PDF for .NET használatával. Most már alkalmazhatja ezt a módszert saját projektjeire, hogy manipuláljon és keressen rejtett szöveget PDF-fájlokban.

### GYIK

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy robusztus könyvtár, amely felhatalmazza a fejlesztőket PDF dokumentumok létrehozására, kezelésére és átalakítására .NET alkalmazásokon belül.

#### K: Használható a rejtett szöveg vízjelezési célokra?

V: Abszolút! A rejtett szöveg hatékony eszközként szolgálhat a PDF-dokumentumok vízjelezésére, ami további biztonsági réteget jelent.

#### K: Felfedhető a rejtett szöveg egy PDF dokumentumban?

V: Igen, a rejtett szöveg keresése és felfedése egy PDF-dokumentumban megvalósítható az ebben az oktatóanyagban felvázolt technikákkal.

#### K: Milyen egyéb funkciókat kínál az Aspose.PDF for .NET?

V: A rejtett szövegkezelésen túl az Aspose.PDF for .NET funkciók széles skáláját kínálja, beleértve a PDF-generálást, a konvertálást, a titkosítást és egyebeket.