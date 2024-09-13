---
title: Szöveg keresése és hiperhivatkozás hozzáadása
linktitle: Szöveg keresése és hiperhivatkozás hozzáadása
second_title: Aspose.PDF for .NET API Reference
description: Tanulja meg, hogyan kereshet szöveget PDF-ben, hogyan adhat hiperhivatkozásokat a talált szöveghez, és hogyan mentheti el a módosított dokumentumot az Aspose.PDF for .NET segítségével.
type: docs
weight: 450
url: /hu/net/programming-with-text/search-text-and-add-hyperlink/
---
Ez az oktatóanyag elmagyarázza, hogyan használhatja az Aspose.PDF for .NET fájlt egy adott szöveg megkereséséhez egy PDF-dokumentumban, hiperhivatkozás hozzáadásához a talált szöveghez, és a módosított dokumentum mentéséhez. A mellékelt C# forráskód lépésről lépésre mutatja be a folyamatot.

## Előfeltételek

Mielőtt folytatná az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következőkkel:

- C# programozási nyelv alapismerete.
- Aspose.PDF for .NET könyvtár telepítve. Beszerezheti az Aspose webhelyéről, vagy a NuGet segítségével telepítheti a projektbe.

## 1. lépés: Állítsa be a projektet

Kezdje azzal, hogy hozzon létre egy új C# projektet a kívánt integrált fejlesztői környezetben (IDE), és adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket

Adja hozzá a következőket direktívák használatával a C# fájl elejéhez a szükséges névterek importálásához:

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 3. lépés: Állítsa be a dokumentumkönyvtár elérési útját

 Állítsa be a dokumentumkönyvtár elérési útját a`dataDir` változó:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 4. lépés: Hozzon létre egy TextFragmentAbsorber-t

 Hozzon létre a`TextFragmentAbsorber` objektumot a bemeneti keresési kifejezés összes példányának megtalálásához:

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Cserélje ki`"\\d{4}-\\d{4}"` a kívánt reguláris kifejezésmintával.

## 5. lépés: Engedélyezze a reguláris kifejezések keresését

 A reguláris kifejezések keresésének engedélyezése a`TextSearchOptions` az abszorber tulajdonságai:

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 6. lépés: Nyissa meg és kösse össze a PDF-dokumentumot

 Hozzon létre a`PdfContentEditor` objektumot, és kösd a forrás PDF-fájlhoz:

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Cserélje ki`"SearchRegularExpressionPage.pdf"` a PDF-fájl tényleges nevével.

## 7. lépés: Fogadja el az oldal elnyelőjét

Fogadja el az elnyelőt a dokumentum kívánt oldalához:

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Cserélje ki`1` a kívánt oldalszámmal.

## 8. lépés: Adjon hozzá hiperhivatkozásokat a talált szöveghez

Lapozzon át a letöltött szövegrészleteken, és adjon hozzá hivatkozásokat:

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Hozzon létre egy téglalapot a szövegrészlet helyzete alapján
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Adjon hozzá egy webes hivatkozást a téglalaphoz
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Cserélje ki`"http://www.aspose.com"` a kívánt hiperhivatkozás URL-jével.

## 9. lépés: Mentse el és zárja be a módosított dokumentumot

Mentse el a módosított dokumentumot, és zárja be a szerkesztőt:

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Ügyeljen arra, hogy cserélje ki`"SearchTextAndAddHyperlink_out.pdf"` a kívánt kimeneti fájlnévvel.

### Minta forráskód a keresési szöveghez és a hiperhivatkozás hozzáadásához az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Hozzon létre abszorber objektumot a bemeneti keresési kifejezés összes példányának megtalálásához
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Reguláris kifejezés keresés engedélyezése
absorber.TextSearchOptions = new TextSearchOptions(true);
// Nyissa meg a dokumentumot
PdfContentEditor editor = new PdfContentEditor();
// Forrás PDF-fájl kötése
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Fogadja el az oldal elnyelőjét
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Hurok át a töredékeken
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, kék, akciónév);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Következtetés

Gratulálok! Sikeresen megtanulta, hogyan kereshet meghatározott szöveget egy PDF-dokumentumban, hogyan adhat hiperhivatkozásokat a talált szöveghez, és hogyan mentheti el a módosított dokumentumot az Aspose.PDF for .NET segítségével. Ez az oktatóanyag lépésről lépésre nyújt útmutatót a projekt beállításától a szükséges műveletek végrehajtásáig. Most már beépítheti ezt a kódot saját C#-projektjeibe, hogy szöveget manipuláljon és hiperhivatkozásokat adjon hozzá PDF-fájlokhoz.

### GYIK

#### K: Mi a "Szöveg keresése és hiperhivatkozás hozzáadása" oktatóanyag célja?

V: A "Szöveg keresése és hiperhivatkozás hozzáadása" című oktatóanyag célja, hogy bemutassa, hogyan használható az Aspose.PDF könyvtár a .NET-hez, hogy konkrét szöveget keressen egy PDF-dokumentumban, hiperhivatkozásokat adjon hozzá a talált szöveghez, majd mentse el a módosított dokumentumot. Az oktatóanyag átfogó útmutatót és C# kódmintákat tartalmaz a folyamat lépésről lépésre történő bemutatására.

#### K: Hogyan segít ez az oktatóanyag hiperhivatkozások hozzáadásához egy PDF-dokumentum adott szövegéhez?

V: Ez az oktatóanyag végigvezeti Önt az Aspose.PDF könyvtár használatán a PDF-dokumentum adott szövegének megkereséséhez, az azonosított szövegre mutató hiperhivatkozás alkalmazásához és a módosított PDF mentéséhez. Olyan alapvető lépéseket tartalmaz, mint a projekt beállítása, a dokumentum betöltése, a reguláris kifejezések keresésének engedélyezése és a hiperhivatkozások hozzáadása a talált szöveghez.

#### K: Milyen előfeltételek szükségesek az oktatóanyag követéséhez?

V: Mielőtt elkezdené, ismernie kell a C# programozási nyelvet. Ezenkívül telepítenie kell az Aspose.PDF for .NET könyvtárat, amely beszerezhető az Aspose webhelyéről, vagy a NuGet segítségével telepíthető a projektben.

#### K: Hogyan állíthatom be a projektemet, hogy kövesse ezt az oktatóanyagot?

V: Kezdje egy új C# projekt létrehozásával a preferált integrált fejlesztői környezetben (IDE). Ezután adjon hozzá egy hivatkozást az Aspose.PDF for .NET könyvtárhoz, amely lehetővé teszi a könyvtár képességeinek a projektben való felhasználását.

#### K: Adhatok hiperhivatkozásokat adott szöveghez ezzel az oktatóanyaggal?

V: Igen, ez az oktatóanyag kifejezetten a hiperhivatkozások hozzáadására összpontosít egy PDF-dokumentum adott szövegéhez. Bemutatja, hogyan találhatja meg és bonthatja ki a kívánt szöveget reguláris kifejezések segítségével, hogyan hozhat létre hivatkozásokat a szövegrészletekhez, és hogyan mentheti el a módosított PDF-fájlt.

#### K: Hogyan határozhatom meg azt a szöveget, amelyre keresni szeretnék, és amelyhez hiperhivatkozást szeretnék hozzáadni?

 V: A keresni kívánt szöveg megadásához és hiperhivatkozás hozzáadásához hozzon létre a`TextFragmentAbsorber` objektumot, és állítsa be a mintáját a segítségével`Text` paraméter. Cserélje ki az alapértelmezett mintát`"\\d{4}-\\d{4}"` az oktatóprogram kódjában a kívánt reguláris kifejezésmintával.

#### K: Hogyan engedélyezhetem a reguláris kifejezések keresését a szövegben?

 V: A reguláris kifejezések keresése az a. létrehozásával engedélyezhető`TextSearchOptions` objektumot, és állítsa be az értékét`true` . Rendelje hozzá ezt az objektumot a`TextSearchOptions` tulajdona a`TextFragmentAbsorber` példa. Ez biztosítja, hogy a rendszer a reguláris kifejezésmintát alkalmazza a szöveges keresés során.

#### K: Hogyan adhatok hiperhivatkozásokat a talált szöveghez?

 V: Miután azonosította a szövegrészleteket a`TextFragmentAbsorber` , az oktatóanyag egy hurkot biztosít ezeken a töredékeken való iterációhoz. Az oktatóanyag minden szövegrészlet esetében bemutatja, hogyan állíthatja be a szöveg színét kékre, és hogyan hozhat létre hiperhivatkozást a segítségével`CreateWebLink` módszer.

#### K: Milyen lépésekkel mentheti a módosított PDF-et hiperhivatkozásokkal?

 V: Miután hiperhivatkozásokat adott a kívánt szövegrészletekhez, használja a`PdfContentEditor` osztályba a módosított dokumentum mentéséhez. Az oktatóanyag mintakódja bemutatja, hogyan kell menteni a szerkesztett PDF-fájlt, bezárni a szerkesztőt, és megjeleníteni a sikerüzenetet.