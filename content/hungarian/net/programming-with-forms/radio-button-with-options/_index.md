---
title: Rádiógomb Opciókkal
linktitle: Rádiógomb Opciókkal
second_title: Aspose.PDF for .NET API Reference
description: Az Aspose.PDF for .NET segítségével egyszerűen adjon hozzá opciókat tartalmazó választógombot egy PDF-dokumentumhoz.
type: docs
weight: 230
url: /hu/net/programming-with-forms/radio-button-with-options/
---

Ebben az oktatóanyagban bemutatjuk, hogyan adhat hozzá opciókat tartalmazó választógombot egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Lépésről lépésre elmagyarázzuk a C# forráskódot, hogy végigvezetjük Önt ezen a folyamaton.

## 1. lépés: Előkészítés

Győződjön meg arról, hogy importálta a szükséges könyvtárakat, és beállította a dokumentumkönyvtár elérési útját:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Példányosítson egy dokumentumobjektumot

Példányosítson egy dokumentumobjektumot új PDF-dokumentum létrehozásához:

```csharp
Document doc = new Document();
```

## 3. lépés: Adjon hozzá oldalt és táblázatot

Adjon hozzá egy oldalt a dokumentumhoz, és hozzon létre egy táblázatot a választógomb opcióinak tárolására:

```csharp
Page page = doc.Pages.Add();
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "120 120 120";
page.Paragraphs.Add(table);
```

## 4. lépés: Példányosítson egy RadioButtonField objektumot

Példányosítsa a rádiógombot reprezentáló RadioButtonField objektumot:

```csharp
RadioButtonField rf = new RadioButtonField(page);
rf. PartialName = "radio";
doc.Form.Add(rf, 1);
```

## 5. lépés: Adja hozzá a választógomb opcióit

Adja hozzá a rádiógomb-beállításokat a RadioButtonField objektumhoz:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
RadioButtonOptionField opt2 = new RadioButtonOptionField();
RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt1.OptionName = "Item1";
opt2.OptionName = "Item2";
opt3.OptionName = "Item3";
opt1.Width = 15;
opt1. Height = 15;
opt2.Width = 15;
opt2. Height = 15;
opt3.Width = 15;
opt3. Height = 15;
rf.Add(opt1);
rf.Add(opt2);
rf.Add(opt3);
```

## 6. lépés: A választógomb opcióinak testreszabása

Testreszabhatja a választógomb beállításait olyan attribútumok beállításával, mint a keret, a szöveg színe és a felirat szövege:

```csharp
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Border.Style = BorderStyle.Solid;
opt1.Characteristics.Border = System.Drawing.Color.Black;
opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
opt1.Caption = new TextFragment("Item1");

// Ismételje meg ugyanezeket a lépéseket az opt2 és opt3 esetében

```

## 7. lépés: Adja hozzá a választógomb opcióit a táblázathoz

Adja hozzá a választógomb opcióit a táblázathoz, hogy megjelenjenek:

```csharp
Cell c1 = table.Rows.Add().Cells.Add();
Cell c2 = table.Rows[table.Rows.Count].Cells.Add();
Cell c3 = table.Rows[table.Rows.Count].Cells.Add();

c1.Paragraphs.Add(opt1);
c2.Paragraphs.Add(opt2);
c3.Paragraphs.Add(opt3);
```

## 8. lépés: Mentse el a PDF-dokumentumot

Mentse el a létrehozott PDF dokumentumot:

```csharp
dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
doc.Save(dataDir);
```

### Minta forráskód a Radio Button With Options számára az Aspose.PDF for .NET használatával 
```csharp
try
{
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	Page page = doc.Pages.Add();
	Aspose.Pdf.Table table = new Aspose.Pdf.Table();
	table.ColumnWidths = "120 120 120";
	page.Paragraphs.Add(table);
	Row r1 = table.Rows.Add();
	Cell c1 = r1.Cells.Add();
	Cell c2 = r1.Cells.Add();
	Cell c3 = r1.Cells.Add();
	RadioButtonField rf = new RadioButtonField(page);
	rf.PartialName = "radio";
	doc.Form.Add(rf, 1);
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt1.OptionName = "Item1";
	opt2.OptionName = "Item2";
	opt3.OptionName = "Item3";
	opt1.Width = 15;
	opt1.Height = 15;
	opt2.Width = 15;
	opt2.Height = 15;
	opt3.Width = 15;
	opt3.Height = 15;
	rf.Add(opt1);
	rf.Add(opt2);
	rf.Add(opt3);
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt1.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt1.Caption = new TextFragment("Item1");
	opt2.Border = new Border(opt1);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	opt2.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt2.Caption = new TextFragment("Item2");
	opt3.Border = new Border(opt1);
	opt3.Border.Width = 1;
	opt3.Border.Style = BorderStyle.Solid;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	opt3.DefaultAppearance.TextColor = System.Drawing.Color.Red;
	opt3.Caption = new TextFragment("Item3");
	c1.Paragraphs.Add(opt1);
	c2.Paragraphs.Add(opt2);
	c3.Paragraphs.Add(opt3);
	dataDir = dataDir + "RadioButtonWithOptions_out.pdf";
	// Mentse el a PDF fájlt
	doc.Save(dataDir);
	Console.WriteLine("\nRadio button field with three options added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Következtetés

Gratulálok ! Sikeresen hozzáadott egy opciókat tartalmazó választógombot egy PDF-dokumentumhoz az Aspose.PDF for .NET használatával. Most már használhatja ezt a módszert interaktív űrlapok létrehozására a PDF-dokumentumokban.