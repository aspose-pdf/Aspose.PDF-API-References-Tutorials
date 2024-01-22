---
title: Eszköztipp hozzáadása a PDF-fájl szövegéhez
linktitle: Eszköztipp hozzáadása a PDF-fájl szövegéhez
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan adhat eszköztippeket PDF-fájl szövegéhez az Aspose.PDF for .NET segítségével.
type: docs
weight: 90
url: /hu/net/programming-with-text/add-tooltip-to-text/
---
Ez az oktatóanyag végigvezeti Önt az Aspose.PDF for .NET segítségével eszköztippek hozzáadásának folyamatán PDF-fájlban. A mellékelt C# forráskód bemutatja a szükséges lépéseket.

## Követelmények
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Visual Studio vagy bármely más C# fordító telepítve a gépedre.
- Aspose.PDF .NET könyvtárhoz. Letöltheti az Aspose hivatalos webhelyéről, vagy használhat csomagkezelőt, például a NuGetet a telepítéséhez.

## 1. lépés: Állítsa be a projektet
1. Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben.
2. Adjon hozzá hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
Abban a kódfájlban, amelyhez eszköztippeket szeretne hozzáadni a szöveghez, adja hozzá a következőket a fájl tetején található direktívák használatával:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtárat
 A kódban keresse meg azt a sort, amely ezt mondja`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` annak a könyvtárnak az elérési útjával, ahol a dokumentumokat tárolják.

## 4. lépés: Hozzon létre egy mintadokumentumot szöveggel
 Újat csinálni`Document` objektumot, és adjon hozzá oldalakat szövegtöredékekkel. A megadott kódban két szövegrészletet adunk a dokumentumhoz a megfelelő eszköztipp szöveggel.

```csharp
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

## 5. lépés: Nyissa meg a dokumentumot, és keresse meg a szövegrészleteket
 Töltse be a létrehozott dokumentumot a`Document` konstruktort, és segítségével keresse meg azokat a szövegrészleteket, amelyekhez eszköztippekre van szükség`TextFragmentAbsorber`.

```csharp
Document document = new Document(outputFile);
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
```

## 6. lépés: Eszköztippek hozzáadása a szövegrészletekhez
 Lapozzon át a kivont szövegrészleteken, és hozzon létre láthatatlan gombokat a helyükön. Rendelje hozzá a kívánt eszköztipp szöveget a`AlternateName` tulajdona a`ButtonField`. Adja hozzá a gombmezőket a dokumentum űrlapjához.

```csharp
foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Tooltip for text.";
     document.Form.Add(field);
}
```

## 7. lépés: Ismételje meg a további szövegtöredékekhez, hosszú eszköztippekkel
Ismételje meg az 5. és 6. lépést a hosszú eszköztippeket tartalmazó szövegrészleteknél. Módosítsa ennek megfelelően a keresési feltételeket és az eszköztipp szövegét.

```csharp
absorb = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorb);
textFragments = absorb.TextFragments;

foreach(TextFragment fragment in textFragments)
{
     ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
     field. AlternateName = "Long tooltip text goes here...";
     document.Form.Add(field);
}
```

## 8. lépés: Mentse el a módosított dokumentumot
 Mentse el a módosított PDF dokumentumot a`Save` módszere a`Document` tárgy.

```csharp
document. Save(outputFile);
```

### Forráskód minta az Eszköztipp hozzáadása szöveghez az Aspose.PDF for .NET használatával programhoz 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
// Készítsen mintadokumentumot szöveggel
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
// Nyissa meg a dokumentumot szöveggel
Document document = new Document(outputFile);
// Hozzon létre TextAbsorber objektumot a reguláris kifejezésnek megfelelő kifejezések megtalálásához
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
// Fogadja el az elnyelőt a dokumentumoldalakhoz
document.Pages.Accept(absorber);
// Szerezze be a kivont szövegrészleteket
TextFragmentCollection textFragments = absorber.TextFragments;
// Hurok át a töredékeken
foreach (TextFragment fragment in textFragments)
{
	// Láthatatlan gomb létrehozása a szövegrészlet pozíciójában
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Az AlternateName értéket eszközleírásként jeleníti meg egy megjelenítő alkalmazás
	field.AlternateName = "Tooltip for text.";
	// Gombmező hozzáadása a dokumentumhoz
	document.Form.Add(field);
}
// Következő lesz egy nagyon hosszú eszköztipp
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Állítson be nagyon hosszú szöveget
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
// Dokumentum mentése
document.Save(outputFile);
```

## Következtetés
Sikeresen eszköztippeket adott hozzá egy PDF-dokumentum szövegéhez az Aspose.PDF for .NET segítségével. Az eredményül kapott PDF-fájl most már megtalálható a megadott kimeneti fájl elérési útján.

## GYIK

#### K: Mi áll ennek az oktatóanyagnak a középpontjában?

V: Ez az oktatóanyag az Aspose.PDF for .NET könyvtár használatával eszköztippek hozzáadására összpontosít egy PDF-fájlban található szöveghez. A mellékelt C# forráskód bemutatja az ehhez szükséges lépéseket.

#### K: Mely névtereket kell importálni ehhez az oktatóanyaghoz?

V: Abban a kódfájlban, amelyhez eszköztippeket szeretne hozzáadni a szöveghez, importálja a következő névtereket a fájl elejére:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

#### K: Hogyan adhatom meg a dokumentumkönyvtárat?

 V: A kódban keresse meg a sort`string dataDir = "YOUR DOCUMENT DIRECTORY";` és cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

#### K: Hogyan hozhatok létre szöveges mintadokumentumot?

 V: A 4. lépésben újat hoz létre`Document` objektumot, és adjon hozzá oldalakat szövegtöredékekkel. A megadott kód két szövegrészletet ad hozzá a megfelelő eszköztipp szöveggel.

#### K: Hogyan nyithatom meg a dokumentumot és kereshetem meg a szövegrészleteket?

 V: Az 5. lépésben töltse be a létrehozott dokumentumot a`Document` konstruktort, és keresse meg az eszköztippeket igénylő szövegrészleteket a segítségével`TextFragmentAbsorber`.

#### K: Hogyan adhatok eszköztippeket a szövegrészletekhez?

 V: A 6. lépésben végigpörgeti a kibontott szövegrészleteket, és a helyükön láthatatlan gombokat hoz létre. Az eszköztipp szövege hozzá van rendelve a`AlternateName` tulajdona a`ButtonField`amely hozzáadódik a dokumentum űrlapjához.

#### K: Hogyan ismételhetem meg a folyamatot további szövegtöredékek esetén, hosszú eszköztippekkel?

V: Hosszú elemleírású szövegtöredékek esetén ismételje meg az 5. és 6. lépést. Módosítsa ennek megfelelően a keresési feltételeket és az eszköztipp szövegét.

#### K: Hogyan menthetem el a módosított dokumentumot?

 V: A 8. lépésben a módosított PDF-dokumentumot a`Save` módszere a`Document` tárgy.

#### K: Mi a fő kivonat ebből az oktatóanyagból?

V: Az oktatóanyag követésével megtanulta, hogyan javíthatja PDF-dokumentumát az Aspose.PDF for .NET segítségével eszköztippek hozzáadásával a szöveghez. Ez értékes további információkkal szolgálhat az olvasók számára, amikor kapcsolatba lépnek a PDF-tartalommal.