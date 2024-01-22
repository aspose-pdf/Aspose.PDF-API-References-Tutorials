---
title: Přidat anotaci lnk
linktitle: Přidat anotaci lnk
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak přidat funkci Ink Annotation do PDF dokumentů v C# pomocí Aspose.PDF for .NET s podrobným průvodcem a úplným zdrojovým kódem.
type: docs
weight: 20
url: /cs/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům provádět různé operace s PDF. Jednou z takových operací je přidání inkoustové anotace do dokumentů PDF. V tomto článku poskytneme podrobného průvodce vysvětlujícího zdrojový kód C# pro přidávání inkoustové anotace pomocí Aspose.PDF pro .NET. Začněme!

## Pochopení funkce inkoustové anotace Aspose.PDF pro .NET

Než se ponoříme do zdrojového kódu C#, nejprve si ujasněme, co je to Ink Annotation a jak se používá.

Ink Annotation je způsob, jak kreslit volné poznámky inkoustem na dokumenty PDF. Umožňuje vytvářet poznámky pomocí stylusu nebo myši. Tato funkce je užitečná v situacích, kdy potřebujete kreslit diagramy, náčrty nebo jiné typy poznámek.

## Krok 1: Vytvoření nového dokumentu

Prvním krokem při přidávání inkoustové anotace do dokumentu PDF je vytvoření nové instance třídy Dokument. Toho je dosaženo pomocí následujícího fragmentu kódu:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Zde vytvoříme novou instanci třídy Document a přidáme do ní novou stránku.

## Krok 2: Vytvoření inkoustové anotace

Dalším krokem je vytvoření instance třídy InkAnnotation. To se provádí pomocí následujícího fragmentu kódu:

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Zde nejprve vytvoříme obdélník pomocí třídy System.Drawing.Rectangle a převedeme jej na Aspose.Pdf.Rectangle pomocí metody FromRect. Poté vytvoříme instanci třídy InkAnnotation pomocí obdélníku, seznamu bodů a stránky, kam je přidána anotace.

Poté nastavíme různé vlastnosti InkAnnotation, jako je nadpis, barva, styl čepice, ohraničení a krytí. Nakonec přidáme anotaci na stránku pomocí metody Annotations.Add.

## Krok 3: Uložení dokumentu

Posledním krokem je uložení dokumentu PDF s přidanou Ink Annotation. Toho je dosaženo pomocí následujícího fragmentu kódu:

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Zde zřetězíme název výstupního souboru do datového adresáře a dokument uložíme pomocí metody Save.

### Příklad zdrojového kódu pro přidávání inkoustové anotace pomocí Aspose.PDF pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Uložit výstupní soubor
doc.Save(dataDir);
```

## Závěr

tomto tutoriálu jsme prozkoumali, jak přidat inkoustové anotace do dokumentu PDF pomocí Aspose.PDF pro .NET. Pomocí podrobného průvodce a poskytnutého zdrojového kódu C# mohou vývojáři snadno implementovat funkci Ink Annotation do svých aplikací pro zpracování PDF.

### FAQ

#### Otázka: Co je to inkoustová anotace v dokumentu PDF?

Odpověď: Inkoustová anotace v dokumentu PDF umožňuje uživatelům kreslit volné inkoustové anotace pomocí stylusu nebo myši. Běžně se používá k přidávání ručně kreslených náčrtů, diagramů nebo jiných poznámek od ruky do PDF.

#### Otázka: Mohu přizpůsobit vzhled poznámky inkoustu?

Odpověď: Ano, Aspose.PDF for .NET poskytuje různé vlastnosti pro přizpůsobení vzhledu inkoustové anotace, jako je barva, neprůhlednost, styl čepice, šířka ohraničení a další. Vývojáři mohou tyto vlastnosti upravit tak, aby splňovaly jejich specifické požadavky.

#### Otázka: Je možné přidat více inkoustových anotací na jednu stránku PDF?

Odpověď: Ano, pomocí Aspose.PDF for .NET můžete na jednu stránku PDF přidat více inkoustových anotací. Každá anotace inkoustu může mít vlastní sadu bodů a přizpůsobený vzhled.

#### Otázka: Mohu přidat inkoustové anotace ke stávajícím dokumentům PDF?

Odpověď: Ano, Aspose.PDF for .NET vám umožňuje přidávat inkoustové anotace jak do nově vytvořených dokumentů PDF, tak do stávajících souborů PDF. Můžete otevřít existující PDF, přidat inkoustové anotace a uložit aktualizovaný dokument.

#### Otázka: Jaké jsou některé běžné případy použití inkoustových anotací v dokumentech PDF?

Odpověď: Inkoustové anotace jsou užitečné pro širokou škálu aplikací, včetně přidávání podpisů nebo ručně psaných poznámek do formulářů PDF, anotování architektonických plánů nebo technických výkresů a označování dokumentů pro společnou kontrolu.