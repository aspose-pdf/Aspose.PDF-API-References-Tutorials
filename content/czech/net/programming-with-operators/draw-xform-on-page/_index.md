---
title: Nakreslete XForm na stránku
linktitle: Nakreslete XForm na stránku
second_title: Aspose.PDF pro .NET API Reference
description: Podrobný průvodce kreslením formuláře XForm na stránku PDF pomocí Aspose.PDF pro .NET. Přidejte a umístěte formulář na stránku.
type: docs
weight: 10
url: /cs/net/programming-with-operators/draw-xform-on-page/
---
V tomto tutoriálu vám poskytneme průvodce krok za krokem, jak nakreslit XForm na stránku pomocí Aspose.PDF pro .NET. Aspose.PDF je výkonná knihovna, která vám umožňuje programově vytvářet, manipulovat a převádět dokumenty PDF. Pomocí operátorů poskytovaných Aspose.PDF můžete přidat a umístit formulář XForm na existující stránku PDF.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio nainstalované s .NET frameworkem.
2. Knihovna Aspose.PDF pro .NET.

## Krok 1: Nastavení projektu

Chcete-li začít, vytvořte nový projekt v sadě Visual Studio a přidejte odkaz na knihovnu Aspose.PDF for .NET. Knihovnu si můžete stáhnout z oficiálních stránek Aspose a nainstalovat ji do svého počítače.

## Krok 2: Importujte potřebné jmenné prostory

Do souboru s kódem C# importujte jmenné prostory potřebné pro přístup ke třídám a metodám poskytovaným Aspose.PDF:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## Krok 3: Nastavení cest k souboru

Definujte cesty k souboru pro obrázek na pozadí, vstupní soubor PDF a výstupní soubor PDF:

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

Nezapomeňte zadat skutečné cesty k souborům na vašem počítači.

## Krok 4: Načtení vstupního souboru PDF

Pro načtení vstupního souboru PDF použijte následující kód:

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
// Následující kód používá operátory GSave/GRestore
// Kód používá k umístění XForm operátor ContatenateMatrix
// Kód používá operátor Do k nakreslení XFormu na stránku
// Operátoři GSave/GRestore obalují stávající obsah
// to se provádí za účelem získání počátečního grafického stavu na konci existujícího obsahu
// jinak mohou na konci řetězce stávajících operátorů zůstat nechtěné transformace
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
// Přidejte operátor GSave pro správné resetování stavu grafiky po nových příkazech
pageContents. Add(new GSave());

// Vytvořte XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
// Nastavte šířku a výšku obrázku
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
// Načtěte obrázek do streamu
Stream imageStream = new FileStream(imageFile, FileMode.Open);
// Přidejte obrázek do kolekce obrázků prostředků XForm
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
// Použití operátoru Do: tento operátor nakreslí obrázek
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//Umístěte XForm na souřadnice x=100 a y=500
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
// Nakreslete XForm pomocí operátoru Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
// Umístěte XForm na souřadnice x=100 a y=300
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
// Nakreslete XForm pomocí operátoru Do
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

// Obnovte stav grafiky pomocí GRestore po GSave
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

Ujistěte se, že jste specifikovali skutečné cesty k souboru a podle potřeby upravte číslo stránky a pozice XForm.

### Ukázkový zdrojový kód pro Draw XForm On Page pomocí Aspose.PDF pro .NET
 
```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	// Ukázka ukazuje
	// Využití operátorů GSave/GRestore
	// Použití operátoru ContatenateMatrix k umístění xForm
	// Pomocí operátora nakreslete xForm na stránku
	// Zabalte existující obsah pomocí dvojice operátorů GSave/GRestore
	// toto je získat počáteční grafický stav na a existujícího obsahu
	// jinak by na konci řetězce stávajících operátorů mohly zůstat některé nežádoucí transformace
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Přidejte operátor uložení stavu grafiky, abyste správně vymazali stav grafiky po nových příkazech
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	// Vytvořte xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	// Definujte šířku a výšku obrázku
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	// Načíst obrázek do streamu
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//Přidejte obrázek do kolekce Images v XForm Resources
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	// Použití operátoru Do: tento operátor kreslí obrázek
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Umístěte formulář na souřadnice x=100 y=500
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	// Nakreslete formulář pomocí operátoru Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	// Umístěte formulář na souřadnice x=100 y=300
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	// Nakreslete formulář pomocí operátoru Do
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	// Obnovte stav grafiky pomocí GRestore po GSave
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## Závěr

V tomto tutoriálu jste se naučili, jak nakreslit formulář XForm na stránku PDF pomocí Aspose.PDF for .NET. Podle popsaných kroků budete moci přidat a umístit formulář XForm na existující stránku, čímž poskytnete vašim dokumentům PDF větší flexibilitu.

### Často kladené otázky pro draw XForm na stránce

#### Otázka: Co je XForm v Aspose.PDF?

Odpověď: XForm je opakovaně použitelný grafický objekt v dokumentu PDF. Umožňuje definovat a kreslit komplexní grafiku, obrázky nebo text, které lze opakovaně použít na různých stránkách.

#### Otázka: Jak naimportuji potřebné jmenné prostory pro Aspose.PDF?

 Odpověď: V souboru kódu C# použijte soubor`using` direktiva pro import požadovaných jmenných prostorů pro přístup ke třídám a metodám poskytovaným Aspose.PDF:
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### Otázka: Jaký je účel operátorů GSave a GRestore?

 A:`GSave` a`GRestore`operátory v Aspose.PDF se používají k uložení a obnovení stavu grafiky. Pomáhají zajistit, aby transformace a nastavení aplikované na jednu část obsahu neovlivnily následující části.

#### Otázka: Jak mohu definovat XForm pomocí Aspose.PDF?

 A: Chcete-li vytvořit XForm, použijte`XForm.CreateNewForm` metodu a přidejte ji do`Resources.Forms` kolekce konkrétní stránky. Poté můžete přidat obsah do XFormu`Contents` vlastnictví.

#### Otázka: Jak mohu nakreslit obrázek v XFormu?

 Odpověď: Načtěte obrázek do streamu a přidejte jej do`Resources.Images` kolekce XFormu. Použijte`Do` operátor v rámci XFormu`Contents` nakreslit obrázek.

#### Otázka: Jak umístím XFormulář na stránku PDF?

 A: Chcete-li umístit XForm na stránku, použijte`ConcatenateMatrix` operátor v rámci stránky`Contents`. Upravte parametry matice, abyste určili posun (pozici) a měřítko XFormu.

#### Otázka: Mohu nakreslit více XFormů na stejnou stránku?

 Odpověď: Ano, můžete nakreslit více XFormů na stejnou stránku úpravou`ConcatenateMatrix`parametry pro umístění každého XFormu na jiné souřadnice.

#### Otázka: Mohu upravit obsah XFormu po jeho vytvoření?

 Odpověď: Ano, po vytvoření můžete upravit obsah XForm přidáním dalších operátorů`Contents` vlastnictví.

#### Otázka: Co se stane, když vynechám operátory GSave a GRestore?

Odpověď: Vynechání operátorů GSave a GRestore může vést k nechtěným transformacím nebo nastavením, která budou aplikována na následný obsah. Jejich používání pomáhá udržovat čistý grafický stav.

#### Otázka: Mohu znovu použít XForms na různých stránkách dokumentu PDF?

 Odpověď: Ano, můžete znovu použít XForms na více stránkách přidáním stejného XFormu do`Resources.Forms` sbírka různých stránek.

#### Otázka: Existuje nějaký limit na počet XForms, které mohu vytvořit?

Odpověď: I když neexistuje žádný přísný limit na počet XForms, které můžete vytvořit, mějte na paměti, že příliš mnoho XFormů může ovlivnit výkon a využití paměti. Používejte je uvážlivě.

#### Otázka: Mohu otočit XForm nebo použít jiné transformace?

 Odpověď: Ano, můžete použít`ConcatenateMatrix`operátor pro použití transformací, jako je rotace, změna měřítka a posunutí na XForm.
