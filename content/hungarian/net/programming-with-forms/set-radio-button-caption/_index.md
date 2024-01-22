---
title: Állítsa be a rádiógomb feliratát
linktitle: Állítsa be a rádiógomb feliratát
second_title: Aspose.PDF for .NET API Reference
description: Ismerje meg, hogyan használhatja az Aspose.PDF for .NET fájlt a választógomb feliratának beállításához PDF-formátumban.
type: docs
weight: 280
url: /hu/net/programming-with-forms/set-radio-button-caption/
---
Ebben az útmutatóban lépésről lépésre elmagyarázzuk, hogyan használhatjuk az Aspose.PDF könyvtárat .NET-hez egy választógomb feliratának meghatározásához PDF-formátumban. Megmutatjuk, hogyan érheti el a választógomb mezőt, hogyan hozhat létre új választógomb-beállítást, és hogyan szabhatja testre a gomb feliratát.

## 1. lépés: A dokumentumkönyvtár konfigurálása

 Az első lépés annak a dokumentumkönyvtárnak a konfigurálása, amelyben a dolgozni kívánt PDF-űrlap található. Használhatja a`dataDir` változót a könyvtár elérési útjának megadásához.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Feltétlenül cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

## 2. lépés: Töltse be a forrás PDF űrlapot

 Ebben a lépésben betöltjük a forrás PDF űrlapot a`Aspose.Pdf.Facades.Form` osztályú Aspose.PDF.

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

Győződjön meg arról, hogy az űrlapot tartalmazó PDF-fájl megtalálható a megadott dokumentumok könyvtárában.

## 3. lépés: A választógomb feliratának szerkesztése

Végignézzük az űrlapmezők nevét, és megkeressük a választógomb mezőket. Ha talál egyező mezőt, létrehozunk egy új választógombot egyéni felirattal, és hozzáadjuk a meglévő mezőhöz.

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
// Hozzon létre egy TextParagraph objektumot
TextParagraph par = new TextParagraph();
// Állítsa be a bekezdés pozícióját
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
// Adja meg a tördelési módot
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
// Adja hozzá az új szövegtöredéket a bekezdéshez
par.AppendLine(updatedFragment);
// Adja hozzá a TextParagraph-ot a TextBuilder segítségével
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

Szükség szerint testreszabhatja a felirat rádiógombot és az egyéb beállításokat.

## 4. lépés: Az eredményül kapott PDF mentése

 Most, hogy befejeztük a választógomb feliratának módosítását, elmenthetjük a kapott PDF-et a`Save` módszere a`Document` osztály.

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

Feltétlenül adja meg a kapott PDF teljes elérési útját és fájlnevét.

### Minta forráskód a Set Radio Button Caption funkcióhoz az Aspose.PDF for .NET használatával 
```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Forrás PDF űrlap betöltése
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
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
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## Következtetés

Ebben az útmutatóban megtanultuk, hogyan használhatjuk az Aspose.PDF könyvtárat a .NET-hez egy választógomb feliratának beállításához PDF-formátumban. A leírt lépéseket követve testreszabhatja a választógomb beállításait, és szükség szerint módosíthatja a feliratot. Nyugodtan fedezze fel az Aspose.PDF for .NET szolgáltatásait a PDF-fájlok kezelésének lehetőségeinek bővítése érdekében.

### GYIK

#### K: Használhatom az Aspose.PDF for .NET fájlt a választógombok feliratainak beállításához PDF-formátumban?

V: Igen, az Aspose.PDF for .NET segítségével beállíthatja a választógombok feliratait PDF-formátumban. A mellékelt mintaforráskód bemutatja, hogyan lehet elérni a választógomb mezőt, létrehozni egy új választógomb opciót egyéni felirattal, és frissíteni a meglévő mezőt.

#### K: Hogyan szabhatom testre a választógomb feliratának megjelenését, például a betűméretet és a színt?

 V: Testreszabhatja a választógomb feliratának megjelenését a tulajdonságainak módosításával`TextFragment` felirathoz használták. Beállíthatja például a betűtípust, a betűméretet, a színt, a sorközt és más szövegformázási beállításokat.

#### K: Lehetséges-e több választógomb-beállítást hozzáadni különböző feliratokkal egyetlen választógomb-csoporthoz?

V: Igen, egyetlen választógomb-csoporthoz több választógomb opciót is hozzáadhat különböző feliratokkal. Mindegyik opció más választást jelent, és a felhasználók csak egy lehetőséget választhatnak a csoportból.

#### K: Használhatom az Aspose.PDF for .NET fájlt a PDF-dokumentum egyéb űrlapmezőinek módosítására?

V: Igen, az Aspose.PDF for .NET szolgáltatások átfogó készletét kínálja a PDF-dokumentum különböző űrlapmezőinek, például szövegmezőknek, jelölőnégyzeteknek, legördülő listáknak és egyebeknek a kezeléséhez. A könyvtár segítségével értékeket állíthat be, módosíthatja a megjelenést, és interaktivitást adhat az űrlapmezőkhöz.

#### K: Az Aspose.PDF for .NET támogatja a más forrásokból előállított PDF-ekkel, például beolvasott dokumentumokkal való munkát?

V: Igen, az Aspose.PDF for .NET támogatja a különféle forrásokból előállított PDF-ekkel, beleértve a beszkennelt dokumentumokat is. A könyvtár OCR (Optical Character Recognition) funkciót biztosít a beolvasott PDF-fájlok szövegének kinyeréséhez és a tartalom programozott kezeléséhez.