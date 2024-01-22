---
title: Szöveg kivonat a bélyegző megjegyzéséből
linktitle: Szöveg kivonat a bélyegző megjegyzéséből
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan vonhat ki egyszerűen szöveget a PDF-dokumentumokban lévő bélyegző megjegyzéseiből az Aspose.PDF for .NET segítségével.
type: docs
weight: 80
url: /hu/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
Ebben az oktatóanyagban lépésről lépésre bemutatjuk, hogyan lehet szöveget kivonni egy PDF-dokumentum bélyegzőjegyzetéből az Aspose.PDF for .NET használatával. Megmutatjuk, hogyan használhatja a megadott C# forráskódot a szöveg kinyerésére egy adott bélyegző megjegyzéséből a PDF dokumentum adott oldalán.

## 1. lépés: A környezet beállítása

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Telepített .NET fejlesztői környezet.
- A projektben letöltött és hivatkozott Aspose.PDF könyvtár a .NET-hez.

## 2. lépés: A PDF dokumentum betöltése

Az első lépés a meglévő PDF dokumentum betöltése a projektbe. Itt van, hogyan:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "test.pdf");
```

Feltétlenül cserélje ki a „DOKUMENTUMKÖNYVTÁR” elemet a PDF-dokumentum könyvtárának tényleges elérési útjára.

## 3. lépés: Szöveg kibontása a bélyegző megjegyzéséből

Most, hogy betöltötte a PDF dokumentumot, kivonhatja a szöveget az adott bélyegző megjegyzéséből. Itt van, hogyan:

```csharp
// Puffer annotáció lekérése
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

// Hozzon létre egy szövegelnyelőt
TextAbsorber ta = new TextAbsorber();

// Tekintse meg a kommentár megjelenését
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

// A kivont szöveg megjelenítése
Console.WriteLine(ta.Text);
```

fenti kód lekéri a bélyegző megjegyzést a PDF-dokumentum megadott oldaláról, majd egy szövegelnyelő segítségével kiemeli a szöveget a megjegyzés megjelenéséből. A kivont szöveg ezután megjelenik a kimenetben.

### Minta forráskód a bélyegjegyzet szövegének kivonásához az Aspose.PDF for .NET használatával 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## Következtetés

Gratulálok ! Megtanulta, hogyan lehet szöveget kivonni egy PDF-dokumentum bélyegző megjegyzéséből az Aspose.PDF for .NET használatával. Most már használhatja ezt a módszert a PDF-dokumentumok más megjegyzéseiből való szöveg kivonására.

### GYIK a bélyegjegyzet szövegének kivonásához

#### K: Mi az a bélyegző megjegyzés egy PDF-dokumentumban, és miért kell szöveget kivonnom belőle?

V: A PDF-dokumentumban található bélyegző megjegyzés olyan grafikus elem, amely további információk, például vízjel vagy gumibélyegző biztosítására használható. Szöveg kinyerése egy bélyegző megjegyzésből akkor hasznos, ha szövegalapú tartalmat szeretne lekérni ezekből a megjegyzésekből, amelyek tartalmazhatnak megjegyzéseket, címkéket vagy egyéb szöveges információkat.

#### K: Hogyan bontja ki a megadott C#-forráskód a szöveget a bélyegző megjegyzéséből?

 V: A mellékelt forráskód bemutatja, hogyan lehet szöveget kivonni egy adott bélyegző megjegyzésből a PDF-dokumentum adott oldalán. Az Aspose.PDF könyvtárat használja a bélyegző megjegyzésének lekéréséhez, a megjelenés meglátogatásához egy`TextAbsorber`, majd megjeleníti a kivont szöveget a kimenetben.

#### K: Kivonhatok-e szöveget különböző típusú megjegyzésekből hasonló megközelítéssel?

V: Igen, hasonló megközelítést használhat más típusú megjegyzésekből, például szöveges megjegyzésekből vagy felugró megjegyzésekből szöveg kinyerésére. Módosítania kell a kódot, hogy megcélozza azt a konkrét típusú megjegyzést, amelyből szöveget szeretne kivonni.

####  K: Mi a célja a`TextAbsorber` class in the code?

 V: A`TextAbsorber` osztály a PDF-dokumentum különböző részeinek szövegének kinyerésére szolgál, beleértve a bélyegző megjegyzéseket is. "Elnyeli" vagy rögzíti a PDF meghatározott területén vagy elemében található szöveges tartalmat.

#### K: Hogyan azonosíthatom be azt a bélyegző megjegyzést, amelyből szöveget szeretnék kivonni?

 V: A megadott kódban a bélyegző annotáció azonosítása a`Annotations` egy adott oldal gyűjteménye, és az index segítségével lekérheti a kívánt megjegyzést. Módosíthatja az indexet, vagy más kritériumok segítségével azonosíthatja a célfeljegyzést.

#### K: Kivonhatok szöveget több bélyegző megjegyzésből ugyanazon az oldalon?

 V: Igen, módosíthatja a kódot, hogy végigfusson a`Annotations`egy oldal gyűjteménye, szűrje ki a bélyegző megjegyzéseket, és mindegyikből kinyerje ki a szöveget.

#### K: Mi a teendő, ha a bélyegző megjegyzésének nincs szöveges tartalma? Működni fog még a kód?

V: A kód továbbra is működik, de kibontja és üres karakterláncot jelenít meg, ha a bélyegző megjegyzés megjelenése nem tartalmaz szöveges tartalmat.

#### K: Hogyan menthetem el a kicsomagolt szöveget fájlba ahelyett, hogy a kimenetben jelenítené meg?

 V: Módosíthatja a kódot, hogy a kibontott szöveget fájlba mentse, ahelyett, hogy a konzolon jelenítené meg. Egyszerűen cserélje ki a`Console.WriteLine` utasítás kóddal a szöveg fájlba írásához.

#### K: Hogyan használhatom a kivont szöveget további feldolgozáshoz vagy elemzéshez?

V: Miután a megadott módszerrel kibontotta a szöveget, eltárolhatja azt egy változóban, módosíthatja, elemezheti, vagy szükség szerint integrálhatja az alkalmazás más részeibe.