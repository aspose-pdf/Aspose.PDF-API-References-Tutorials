---
title: Přidat vrstvy do souboru PDF
linktitle: Přidat vrstvy do souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat vrstvy do souborů PDF pomocí Aspose.PDF pro .NET. Podrobný průvodce s výukovým programem kódu pro vytváření a ukládání vrstvených PDF.
type: docs
weight: 20
url: /cs/net/programming-with-document/addlayers/
---
Chcete-li přidat vrstvy do souboru PDF, použijeme Aspose.PDF pro .NET. Tato knihovna nám umožňuje efektivně pracovat se soubory PDF v aplikacích .NET. Chcete-li přidat vrstvy pomocí Aspose.PDF pro .NET, postupujte podle níže uvedených pokynů krok za krokem.

## Krok 1: Vytvořte nový dokument PDF

 Začněte vytvořením nové instance souboru`Document` třídy poskytované Aspose.PDF pro .NET. To bude sloužit jako dokument PDF, kam přidáme vrstvy.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## Krok 2: Přidejte stránku do dokumentu

 Dále přidejte stránku do dokumentu pomocí`Add` metoda`Pages` sbírka v`Document` třída.

```csharp
Page page = doc.Pages.Add();
```

## Krok 3: Vytvořte a přidejte vrstvy na stránku

 Vytvořte instance`Layer` třídy pro každou vrstvu, kterou chcete přidat do souboru PDF. Zadejte jedinečný identifikátor a název pro každou vrstvu.

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

V tomto tutoriálu jsme na stránku přidali tři vrstvy s různými barvami a názvy.

## Krok 4: Uložte soubor PDF

 Uložte upravený soubor PDF pomocí`Save` metoda`Document` třída.

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

Tento kód uloží upravený soubor PDF do určeného adresáře.

### Příklad zdrojového kódu pro přidávání vrstev na stránky PDF pomocí Aspose.PDF pro .NET

```csharp            
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## Závěr

V tomto článku jsme poskytli podrobného průvodce přidáváním vrstev do souborů PDF pomocí Aspose.PDF pro .NET. Podle pokynů a pomocí poskytnutých výukových programů kódu můžete do dokumentů PDF snadno začlenit vrstvy. Vrstvy vám umožňují organizovat a řídit viditelnost obsahu, což vašim uživatelům poskytuje interaktivnější a přizpůsobitelnější prostředí.


### Časté dotazy pro přidání vrstev do souboru PDF

#### Otázka: Co je Aspose.PDF pro .NET?

A: Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům efektivně pracovat se soubory PDF v aplikacích .NET. Poskytuje širokou škálu funkcí pro vytváření, úpravy a manipulaci s dokumenty PDF.

#### Otázka: Co jsou vrstvy PDF?

Odpověď: Vrstvy PDF, známé také jako volitelné skupiny obsahu (OCG), vám umožňují řídit viditelnost a vzhled určitého obsahu v souboru PDF. Jsou užitečné pro organizaci obsahu a vytváření interaktivních dokumentů.

#### Otázka: Mohu přidat více vrstev do souboru PDF pomocí Aspose.PDF pro .NET?

Odpověď: Ano, do souboru PDF můžete přidat více vrstev pomocí Aspose.PDF pro .NET. Každá vrstva může mít svůj jedinečný identifikátor a název, jak je ukázáno v tutoriálu.

#### Otázka: Jak mohu přizpůsobit vzhled vrstev?

Odpověď: Vzhled vrstev můžete přizpůsobit zadáním různých vlastností, jako je barva, krytí a viditelnost. Aspose.PDF pro .NET poskytuje různé možnosti, jak toho dosáhnout.

#### Otázka: Je Aspose.PDF pro .NET vhodný pro profesionální projekty?

Odpověď: Ano, Aspose.PDF for .NET je spolehlivá a široce používaná knihovna pro manipulaci s PDF v profesionálních projektech. Nabízí rozsáhlou funkčnost a vynikající výkon pro práci se soubory PDF v aplikacích .NET.