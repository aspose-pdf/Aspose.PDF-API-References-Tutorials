---
title: Szavak kihúzása
linktitle: Szavak kihúzása
second_title: Aspose.PDF for .NET API Reference
description: Ez a cikk lépésről lépésre ismerteti az Aspose.PDF fájl használatát a .NET áthúzott szavak funkciójához, beleértve a lépésről lépésre szóló útmutatót és magyarázatokat
type: docs
weight: 150
url: /hu/net/annotations/strikeoutwords/
---
Az Aspose.PDF for .NET egy PDF-dokumentum-manipulációs és -feldolgozási könyvtár, amely különféle funkciókat kínál PDF-fájlok létrehozásához, módosításához és konvertálásához. Az Aspose.PDF egyik hasznos funkciója a szavak vagy kifejezések kihúzása a PDF-dokumentumból C# forráskóddal. Ebben a cikkben lépésről lépésre bemutatjuk, hogyan lehet szavakat kihúzni az Aspose.PDF for .NET használatával.

## 1. lépés: A PDF dokumentum betöltése
Az első lépés a módosítani kívánt PDF dokumentum betöltése. Ebben az oktatóanyagban egy „input.pdf” nevű PDF dokumentumot töltünk be a „DOKUMENTUMKÖNYVTÁR” mappából. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## 2. lépés: Szövegtöredékek keresése
Ha konkrét szavakat vagy kifejezéseket szeretne kihúzni a PDF-dokumentumból, először meg kell keresnie őket. Az Aspose.PDF egy TextFragmentAbsorber osztályt biztosít, amely egy adott szövegrészlet megkeresésére használható a PDF dokumentumban.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

fenti kódban az "Estoque" szövegrészletet keressük a PDF dokumentumban. Módosíthatja, hogy bármilyen más szót vagy kifejezést keressen, amelyet ki szeretne húzni.

## 3. lépés: A szövegrészletek kihúzása
A szövegrészletek megtalálása után a következő lépés az, hogy áthúzzuk őket. Az Aspose.PDF egy StrikeOutAnnotation osztályt biztosít, amellyel áthúzható annotációt lehet létrehozni a szövegrészlethez. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

A fenti kódban minden talált szövegrészlethez áthúzható megjegyzést hozunk létre. Beállítjuk az áthúzható annotáció átlátszatlanságát, szegélyét és színét is.

## 4. lépés: Mentse el a módosított PDF dokumentumot
A szövegrészletek kihúzása után mentse el a módosított dokumentumot.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Példa forráskódra az Áthúzott szavakhoz az Aspose.PDF for .NET használatával


```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Nyissa meg a dokumentumot
Document document = new Document(dataDir + "input.pdf");

// Hozzon létre TextFragment Absorber példányt egy adott szövegrészlet kereséséhez
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Iteráljon a PDF-dokumentum oldalain keresztül
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Töltse le a PDF dokumentum első oldalát
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Hozzon létre egy gyűjteményt az elnyelt szövegekből
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Ismételje meg a fenti gyűjteményt
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Szerezze be a TextFragment objektum téglalap alakú méreteit
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// A StrikeOut Annotation példány példányosítása
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Állítsa be a kommentár átlátszatlanságát
	strikeOut.Opacity = .80f;
	// Állítsa be a szegélyt a megjegyzéspéldányhoz
	strikeOut.Border = new Border(strikeOut);
	// Állítsa be a megjegyzés színét
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Megjegyzés hozzáadása a TextFragment megjegyzésgyűjteményéhez
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan használhatja az Aspose.PDF for .NET fájlt bizonyos szavak kihúzására egy PDF-dokumentumban. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával könnyedén betölthet PDF-dokumentumot, kereshet adott szövegrészleteket, és áthúzható megjegyzéseket hozhat létre, amelyekkel vizuálisan megjelölheti és kihúzhatja ezeket a szavakat. Az Aspose.PDF for .NET egyszerű és hatékony módot kínál a PDF-dokumentumok programozott kezelésére, így értékes eszközzé válik a .NET-alkalmazásokban PDF-fájlokkal dolgozó fejlesztők számára.

### GYIK

#### K: Mi az Aspose.PDF for .NET?

V: Az Aspose.PDF for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára PDF-dokumentumok programozott létrehozását, szerkesztését és kezelését .NET-alkalmazásokban. Funkciók széles skáláját kínálja a PDF-fájlokkal való munkavégzéshez, beleértve a szövegkivonást, a megjegyzések kezelését, az űrlapok kitöltését és még sok mást.

#### K: Használhatom az Aspose.PDF for .NET fájlt bizonyos szavak kihúzására egy PDF-dokumentumban?

V: Igen, az Aspose.PDF for .NET lehetőséget biztosít adott szövegrészletek megkeresésére egy PDF-dokumentumban, majd áthúzható megjegyzések létrehozására a szavak vizuális megjelölésére és áthúzására.

#### K: Hogyan adhatom meg a PDF-dokumentumban áthúzni kívánt szöveget?

 V: A kihúzni kívánt szöveg megadásához használja a`TextFragmentAbsorber` osztályt az Aspose.PDF biztosítja a .NET számára. Lehetővé teszi, hogy egy adott szövegrészletet keressen a PDF-dokumentumban a kívánt kritériumok alapján.

#### K: Testreszabhatom az áthúzott kommentár megjelenését?

V: Igen, testreszabhatja az áthúzott megjegyzés különféle tulajdonságait, például az átlátszatlanságot, a keret stílusát és a színét. Ez lehetővé teszi, hogy az áthúzott megjegyzés megjelenését az Ön egyedi igényeihez igazítsa.