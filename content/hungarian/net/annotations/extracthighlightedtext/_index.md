---
title: Kiemelt szöveg kibontása PDF-fájlból
linktitle: Kiemelt szöveg kibontása PDF-fájlból
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan bonthat ki kiemelt szöveget PDF-fájlból az Aspose.PDF for .NET használatával.
type: docs
weight: 60
url: /hu/net/annotations/extracthighlightedtext/
---
A kiemelt szöveg PDF-fájlból való kivonásához használja az Aspose.PDF for .NET API-t. Ez az API egyszerű módot biztosít a dokumentumban kiemelt szövegek lekérésére.

## 1. lépés: Töltse be a PDF dokumentumot

 A kiemelt szöveg PDF-fájlból való kibontásának első lépése a dokumentum betöltése az Aspose.PDF for .NET API használatával. Ezt úgy teheti meg, hogy létrehoz egy új példányt a`Document` osztályt, és paraméterként adja át a PDF dokumentum elérési útját. 

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 2. lépés: Végezze el az összes megjegyzést

 A következő lépés a PDF-dokumentumban található összes megjegyzés végigjátszása. Ezt megteheti az a`foreach` hurok, így:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// A kód ide kerül
}
```

## 3. lépés: Szűrje ki a szövegjelölő megjegyzéseket

 Benne`foreach` hurkot, ki kell szűrnie az összes olyan megjegyzést, amely nem szöveges jelölés. Ezt úgy teheti meg, hogy ellenőrzi, hogy a megjegyzés példánya-e a`TextMarkupAnnotation` osztály.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// A kód ide kerül
}
```

## 4. lépés: A kiemelt szövegrészletek lekérése

 Miután kiszűrte az összes szövegjelölő megjegyzést, lekérheti az egyes megjegyzések kiemelt szövegrészleteit. Ezt megteheti a`GetMarkedTextFragments()` módszer a`TextMarkupAnnotation` tárgy.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 5. lépés: Jelenítse meg a kiemelt szöveget

 Végül a kiemelt szöveget megjelenítheti a felhasználó számára. Ezt úgy teheti meg, hogy mindegyiket végignézi`TextFragment` objektum a`TextFragmentCollection` és felhívja a`Text` ingatlan.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Példa forráskódra a kiemelt szöveg kibontásához az Aspose.PDF for .NET használatával

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan lehet kiemelt szöveget kivonni egy PDF-dokumentumból az Aspose.PDF for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt C# forráskód használatával a fejlesztők könnyedén kivonhatják és kezelhetik a kiemelt szövegeket PDF-dokumentumaikból.

### GYIK a kiemelt szöveg PDF-fájlból való kivonásához

#### K: Mik azok a szövegjelölő megjegyzések egy PDF-dokumentumban?

V: A szövegjelölő megjegyzések olyan megjegyzések, amelyek kiemelnek vagy megjelölnek egy adott szöveget a PDF-dokumentumban. A szövegjelölő megjegyzésekre példák a kiemelések, aláhúzások és áthúzások.

#### K: Kivonhatok szöveget más típusú megjegyzésekből az Aspose.PDF for .NET használatával?

V: Igen, az Aspose.PDF for .NET különféle módszereket biztosít a szöveg kinyerésére a különböző típusú megjegyzésekből, beleértve a szövegjelölő megjegyzéseket, a szabad szöveges megjegyzéseket és egyebeket.

#### K: Az Aspose.PDF for .NET támogatja a szövegek kibontását jelszóval védett PDF-fájlokból?

 V: Igen, az Aspose.PDF for .NET támogatja a szöveg kinyerését a jelszóval védett PDF-fájlokból. Meg kell adnia a helyes jelszót, amikor a PDF dokumentumot a`Document` osztály.

#### K: Szűrhetem a kiemelt szöveget más kritériumok, például szín vagy szerző alapján?

V: Igen, a kiemelt szöveget más kritériumok alapján is szűrheti, például szín, szerző vagy létrehozási dátum alapján. Az Aspose.PDF for .NET módszereket biztosít a megjegyzések eléréséhez és szűréséhez azok tulajdonságai alapján.

#### K: Lehetséges-e a kibontott kiemelt szöveget külön fájlba menteni?

V: Igen, a kibontott kiemelt szöveget elmentheti egy külön fájlba, vagy tárolhatja adatstruktúrában további feldolgozás vagy elemzés céljából.
