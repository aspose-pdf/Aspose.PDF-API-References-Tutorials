---
title: Html-ből való konvertálás után távolítsa el a hiperhivatkozásokat
linktitle: Html-ből való konvertálás után távolítsa el a hiperhivatkozásokat
second_title: Aspose.PDF for .NET API Reference
description: Ebből a lépésenkénti útmutatóból megtudhatja, hogyan távolíthat el hiperhivatkozásokat HTML-dokumentumokból, miután az Aspose.PDF for .NET segítségével PDF-formátumba konvertálta.
type: docs
weight: 250
url: /hu/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## Bevezetés

A digitális korban gyakori feladat a HTML-dokumentumok PDF-be konvertálása. Előfordulhat azonban, hogy különféle okokból – például az olvashatóság javítása vagy a nem kívánt navigáció megakadályozása miatt – el szeretné távolítani a hiperhivatkozásokat a konvertált PDF-fájlból. Ebben az oktatóanyagban megvizsgáljuk, hogyan érhetjük el ezt az Aspose.PDF for .NET használatával. 

## Előfeltételek

Mielőtt belemerülne a kódba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Visual Studio: Győződjön meg arról, hogy a Visual Studio telepítve van a gépen. Ez lesz az Ön fejlesztési környezete.
2.  Aspose.PDF .NET-hez: rendelkeznie kell az Aspose.PDF könyvtárral. Letöltheti innen[itt](https://releases.aspose.com/pdf/net/).
3. Alapvető C# ismerete: A C# programozás ismerete segít a kód jobb megértésében.

## Csomagok importálása

A kezdéshez importálnia kell a szükséges csomagokat a C# projektbe. A következőképpen teheti meg:

1. Nyissa meg a Visual Studio projektet.
2. Kattintson a jobb gombbal a projektre a Solution Explorerben, és válassza a "NuGet-csomagok kezelése" lehetőséget.
3.  Keressen rá`Aspose.PDF` és telepítse.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

Most, hogy mindent beállított, részletezzük a hiperhivatkozások eltávolításának folyamatát egy HTML-fájlból, miután PDF formátumba konvertálta.

## 1. lépés: Állítsa be a dokumentumkönyvtárat

Először is meg kell adnia a dokumentumkönyvtár elérési útját. Itt található a HTML-fájl, és a kimeneti PDF mentésre kerül.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a HTML-fájl tárolási útvonalával.

## 2. lépés: Töltse be a HTML-dokumentumot

 Ezután töltse be a HTML dokumentumot a`Document` osztály az Aspose.PDF-ből. Ez az osztály lehetővé teszi a PDF dokumentumok egyszerű kezelését.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 Itt betöltjük a nevű HTML-fájlt`SampleHtmlFile.html`. Győződjön meg arról, hogy ez a fájl létezik a megadott könyvtárban.

## 3. lépés: Mentse el a dokumentumot a memóriafolyamba

Mielőtt elkezdené a megjegyzések feldolgozását, el kell mentenünk a dokumentumot egy memóriafolyamba. Ez a lépés kulcsfontosságú, mivel előkészíti a dokumentumot a további manipulációkhoz.

```csharp
doc.Save(new MemoryStream());
```

Ez a sor a memóriába menti a dokumentumot, így anélkül dolgozhatunk vele, hogy még lemezre írnánk.

## 4. lépés: Ismétlés megjegyzésekkel

Most ismételjük a dokumentum megjegyzéseit. A kommentárok olyan elemek, mint a linkek, megjegyzések és kiemelések. Kifejezetten a link-annotációk érdekelnek bennünket.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // A link megjegyzés feldolgozása
    }
}
```

Ebben a ciklusban ellenőrizzük, hogy a megjegyzés típusa hivatkozás. Ha igen, akkor folytassa a következő lépésekkel.

## 5. lépés: Távolítsa el a hiperhivatkozási műveletet

Minden hivatkozás megjegyzésénél ellenőriznünk kell, hogy van-e benne hiperhivatkozási művelet. Ha igen, akkor eltávolítjuk a hiperhivatkozást úgy, hogy az URI-jét üres karakterláncra állítjuk.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

Ez a kódrészlet biztosítja a hiperhivatkozási művelet hatékony eltávolítását.

## 6. lépés: Szövegtöredékek felszívása

Ezután felvesszük a hivatkozás megjegyzéséhez kapcsolódó szövegrészleteket. Ez lehetővé teszi számunkra, hogy módosítsuk a szöveg megjelenését.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 Itt létrehozunk a`TextFragmentAbsorber` és állítsa be a keresési beállításait a megjegyzés téglalapjára. Ez segít megtalálni a linkelt szöveget.

## 7. lépés: Módosítsa a szöveg megjelenését

Ha megvannak a szövegrészletek, módosíthatjuk a megjelenésüket. Ebben az esetben eltávolítjuk az aláhúzást, és a szöveg színét feketére változtatjuk.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

Ez a lépés javítja a szöveg olvashatóságát azáltal, hogy eltávolítja a hiperhivatkozás stílusát.

## 8. lépés: Törölje a megjegyzést

A szöveg módosítása után nyugodtan törölhetjük a hivatkozási megjegyzést a dokumentumból.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

Ez a sor eltávolítja a hiperhivatkozást a PDF-ből, biztosítva, hogy az már ne szerepeljen a végső kimenetben.

## 9. lépés: Mentse el a módosított dokumentumot

Végül el kell mentenünk a módosított dokumentumot egy új PDF fájlba. Ez folyamatunk utolsó lépése.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 Ez a sor menti a dokumentumot a hiperhivatkozások eltávolításával, és létrehoz egy új nevű PDF-fájlt`RemoveHyperlinksFromText_out.pdf`.

## Következtetés

És megvan! Sikeresen eltávolította a hiperhivatkozásokat egy HTML-dokumentumból, miután PDF-be konvertálta az Aspose.PDF for .NET segítségével. Ez a folyamat nemcsak a PDF olvashatóságát javítja, hanem a megjelenített tartalom felett is irányítani tudja. 

## GYIK

### Eltávolíthatom a hiperhivatkozásokat bármely PDF-dokumentumból?
Igen, az Aspose.PDF for .NET használatával eltávolíthat hivatkozásokat bármely PDF-dokumentumból.

### Ingyenesen használható az Aspose.PDF?
 Az Aspose.PDF ingyenes próbaverziót kínál, de a teljes funkciók használatához licencet kell vásárolnia. Ellenőrizze a[oldal vásárlása](https://purchase.aspose.com/buy).

### Mi a teendő, ha problémákat tapasztalok az Aspose.PDF használata közben?
 Segítséget kérhetsz a[támogatási fórum](https://forum.aspose.com/c/pdf/10).

### Átalakíthatok más fájlformátumokat PDF-be az Aspose segítségével?
Igen, az Aspose különféle fájlformátumokat támogat a PDF-be való konvertáláshoz.

### Honnan tölthetem le az Aspose.PDF-et .NET-hez?
 Letöltheti a[letöltési link](https://releases.aspose.com/pdf/net/).