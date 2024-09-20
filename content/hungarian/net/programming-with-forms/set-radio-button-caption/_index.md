---
title: Állítsa be a rádiógomb feliratát
linktitle: Állítsa be a rádiógomb feliratát
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan állíthat be választógomb feliratokat PDF-fájlokban az Aspose.PDF for .NET használatával. Ez a lépésenkénti útmutató végigvezeti Önt a PDF-űrlapok betöltése, módosítása és mentése során.
type: docs
weight: 280
url: /hu/net/programming-with-forms/set-radio-button-caption/
---
## Bevezetés

Ha belevág a PDF-manipulációba az Aspose.PDF for .NET segítségével, akkor ez a csemege! Ma egy praktikus funkcióra összpontosítunk: a választógomb feliratainak beállítására a PDF-űrlapokon. A választógombok nélkülözhetetlenek azoknál a felhasználói űrlapoknál, ahol több lehetőség közül kell választani. Képzelje el őket feleletválasztós kérdésként, ahol csak egy válasz megengedett. Ez az oktatóanyag végigvezeti a választógombok feliratainak PDF-formátumban történő frissítésének folyamatán, hogy a dokumentumok interaktívak és felhasználóbarátak legyenek. 

## Előfeltételek

Mielőtt belemerülne a kódba, meg kell bizonyosodnia néhány dologról:

1. Aspose.PDF for .NET: Győződjön meg arról, hogy telepítve van az Aspose.PDF könyvtár. Ez a könyvtár segít a PDF-fájlok programozott kezelésében.
2. Fejlesztői környezet: Be kell állítania egy .NET fejlesztői környezetet, például a Visual Studio-t.
3. Minta PDF-űrlap: Ehhez az oktatóanyaghoz szüksége lesz egy minta PDF-űrlapra választógombokkal. Használhat bármilyen meglévő PDF űrlapot, vagy létrehozhat egy újat a választógombokkal.
4. Alapvető C# ismerete: Ez az útmutató feltételezi, hogy rendelkezik a C# és a .NET programozási fogalmak alapvető ismereteivel.

 Ha még nem telepítette az Aspose.PDF for .NET fájlt, vagy ideiglenes licencre van szüksége,[töltse le itt](https://releases.aspose.com/pdf/net/) vagy[ideiglenes engedélyt szerezni](https://purchase.aspose.com/temporary-license/).

## Csomagok importálása

A kezdéshez importálnia kell a szükséges csomagokat a C# projektbe. A következőképpen veheti fel az Aspose.PDF könyvtárat:

```csharp
using System;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
using Aspose.Pdf.Text;
```

Győződjön meg arról, hogy ezeket a csomagokat hozzáadta a projekthez a NuGet segítségével vagy a választott módszerrel.

## 1. lépés: Töltse be a PDF űrlapot

 Először is be kell töltenie a választógombokat tartalmazó PDF űrlapot. A`Aspose.Pdf.Facades.Form`osztályt használják erre a célra. Íme, hogyan kell csinálni:

```csharp
// Határozza meg a dokumentumkönyvtár elérési útját
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Töltse be a forrás PDF űrlapot
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
```

Ebben a kódrészletben:
- `dataDir` megadja az elérési utat, ahol a PDF található.
- `Form` osztály a PDF-en belüli űrlapmezőkkel való interakcióra szolgál.
- `Document` osztály hozzáférést biztosít a PDF dokumentum oldalaihoz.

## 2. lépés: Ismétlés a rádiógombmezőkön keresztül

Ezután ismételje meg az űrlap mezőit a választógomb mezőinek azonosításához és kezeléséhez:

```csharp
foreach (var item in form1.FieldNames)
{
    Console.WriteLine(item.ToString());
    Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
```

Ebben a körben:
- `FieldNames` a PDF-ben található összes mezőnév listáját tartalmazza.
- `GetButtonOptionValues(item)` lekéri az egyes választógombokhoz elérhető opciókat.

## 3. lépés: Módosítsa a rádiógomb opcióit

 Miután azonosította a választógomb mezőit, módosíthatja a beállításokat. Ehhez ki kell dobnia a mezőt`RadioButtonField` és frissítse a lehetőségeit:

```csharp
    if (item.Contains("radio1"))
    {
        Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
        Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
        fieldoption.OptionName = "Yes";
        fieldoption.PartialName = "Yesname";
```

Itt:
- Ellenőrizzük, hogy a mező neve tartalmazza-e a „radio1”-et, hogy azonosítsuk a módosítani kívánt rádiógomb-mezőt.
- `RadioButtonField`az űrlapmezőkből adható ki, hogy konkrét módosításokat hajtson végre.

## 4. lépés: Állítsa be a rádiógomb feliratát

 A választógomb feliratának beállításához vagy frissítéséhez létre kell hoznia a`TextFragment` és használja`TextBuilder` hogy a kívánt helyre helyezze:

```csharp
        var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
        updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
        updatedFragment.TextState.FontSize = 10;
        updatedFragment.TextState.LineSpacing = 6.32f;

        // TextParagraph objektum létrehozása
        TextParagraph par = new TextParagraph();
        // Állítsa be a bekezdés pozícióját
        par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
        // Adja meg a tördelési módot
        par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
        // Új szövegrészlet hozzáadása a bekezdéshez
        par.AppendLine(updatedFragment);
        // Adja hozzá a TextParagraph-ot a TextBuilder segítségével
        TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
        textBuilder.AppendParagraph(par);
```

Ebben a részben:
- `TextFragment` a szöveg és megjelenésének meghatározására szolgál.
- `TextParagraph` segíti a szöveg elhelyezését és formázását.
- `TextBuilder` hozzáadja a szöveget a PDF megadott oldalához.

## 5. lépés: Mentse el a frissített PDF-fájlt

Végül mentse a frissített PDF-fájlt egy új fájlba:

```csharp
        field0.DeleteOption("item1");
    }
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Ez biztosítja, hogy:
- A módosítások a PDF-re vonatkoznak.
- Az eredeti választógomb opció a megadott módon eltávolítva.

## Következtetés

választógombok feliratainak módosítása PDF-formátumban az Aspose.PDF for .NET használatával nagymértékben növelheti a dokumentumok interaktivitását és használhatóságát. Az oktatóanyagban ismertetett lépésekkel könnyedén betölthet PDF-fájlt, frissítheti a választógomb beállításait, és mentheti a módosításokat. Ez a megközelítés praktikus az űrlapkezeléshez, és biztosítja, hogy a PDF-fájlok pontosan megfeleljenek a felhasználók igényeinek. Merüljön el az Aspose.PDF-ben, és fedezze fel lehetőségeit más PDF-manipulációkhoz!

## GYIK

### Frissíthetek több választógomb mezőt egyszerre?
Igen, ismételheti az összes választógomb mezőt, és szükség szerint alkalmazhatja a módosításokat.

### Szükségem van engedélyre az Aspose.PDF használatához?
 Kezdheti egy ingyenes próbaverzióval, de a hosszabb használathoz licenc szükséges.[Szerezzen jogosítványt itt](https://purchase.aspose.com/buy).

### Hogyan tesztelhetem a változtatásokat a PDF mentése előtt?
Megtekintheti a PDF előnézetét a fejlesztői környezetben, vagy PDF-nézegetővel ellenőrizheti a módosításokat.

### Az Aspose.PDF kompatibilis a .NET összes verziójával?
Az Aspose.PDF a .NET különféle verzióit támogatja. Győződjön meg róla, hogy ellenőrizze a kompatibilitást az adott .NET-verzióval.

### Hasonló módon kezelhetek más űrlapmezőket?
Igen, hasonló technikák alkalmazhatók a PDF dokumentumok más típusú űrlapmezőire is.