---
title: Přidat anotaci PDF
linktitle: Přidat anotaci
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se přidávat textové anotace PDF pomocí Aspose.PDF pro .NET pomocí tohoto zdrojového kódu C#. Přizpůsobte si poznámky pomocí konkrétních podrobností a ikon.
type: docs
weight: 10
url: /cs/net/annotations/addannotation/
---
Přidávání anotací do dokumentů PDF je výkonná funkce, která může zlepšit spolupráci a recenzní procesy. Aspose.PDF for .NET usnadňuje programové přidávání anotací do dokumentů PDF pomocí C#. V této příručce vám krok za krokem vysvětlíme, jak používat Aspose.PDF for .NET k přidávání anotací do dokumentu PDF.

## Krok 1: Vytvořte nový projekt a nainstalujte Aspose.PDF pro .NET

Než začneme psát kód pro přidávání anotací, musíme vytvořit nový projekt a nainstalovat Aspose.PDF for .NET. Chcete-li nainstalovat Aspose.PDF pro .NET, postupujte takto:

1. Otevřete Visual Studio a vytvořte nový projekt C#.
2. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a vyberte „Spravovat balíčky NuGet“.
3. Vyhledejte „Aspose.PDF“ a vyberte „Instalovat“.

Po dokončení instalace můžeme začít psát kód.

## Krok 2: Otevřete dokument PDF

Prvním krokem při přidávání anotací je otevření dokumentu PDF. K otevření dokumentu můžeme použít následující kód:

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

V tomto kódu určíme cestu k PDF dokumentu, který chceme otevřít. Nezapomeňte nahradit „VÁŠ DATOVÝ ADRESÁŘ“ skutečnou cestou k vašemu datovému adresáři.

## Krok 3: Vytvořte anotaci

 Chcete-li přidat anotaci, musíme vytvořit novou instanci souboru`TextAnnotation` třída. K vytvoření nové textové anotace můžeme použít následující kód:

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

V tomto kódu vytvoříme novou textovou anotaci na druhé stránce dokumentu PDF. Také nastavujeme vlastnosti názvu, předmětu, stavu, obsahu, otevření a ikony.

## Krok 4: Přizpůsobte anotaci

 Vzhled anotace můžeme upravit pomocí`Border` třída. K přizpůsobení ohraničení anotace můžeme použít následující kód:

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 V tomto kódu vytvoříme nový`Border`objekt a nastavte jeho vlastnosti šířka a pomlčka. Poté nastavíme`Border` vlastnost anotace k novému`Border` objekt. Nakonec nastavíme`Rect` vlastnost anotace určit její polohu a velikost.

## Krok 5: Přidejte anotaci do dokumentu PDF

Jakmile jsme vytvořili a upravili anotaci, musíme ji přidat do dokumentu PDF. K přidání anotace do dokumentu PDF můžeme použít následující kód:

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

V tomto kódu přidáme anotaci do kolekce anotací na druhé stránce dokumentu PDF.

## Krok 6: Uložte výstupní soubor

Nakonec musíme uložit PDF dokument s přidanou anotací. K uložení výstupního souboru můžeme použít následující kód:

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Příklad zdrojového kódu pro přidání anotace pomocí Aspose.PDF pro .NET


```csharp   
 // Cesta k adresáři dokumentů.
string dataDir = "YOUR DATA DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Vytvořte anotaci
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Přidejte anotaci do kolekce anotací na stránce
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Uložit výstupní soubor
pdfDocument.Save(dataDir);
```
Tento kód ukazuje, jak přidat textovou anotaci se specifickým názvem, předmětem, stavem, obsahem a ikonou na stránku PDF pomocí Aspose.PDF for .NET. Tento kód můžete upravit podle svých požadavků na přidávání anotací do dokumentů PDF. Jen nezapomeňte nahradit VÁŠ DATOVÝ ADRESÁŘ skutečnou cestou k adresáři, kde se nachází váš soubor PDF a kam chcete uložit výstupní soubor.

## Závěr

Přidávání anotací do dokumentů PDF pomocí Aspose.PDF for .NET nabízí cenný nástroj pro zlepšení spolupráce na dokumentech a procesů recenzování. Podle podrobného průvodce v tomto článku mohou vývojáři bez problémů integrovat možnosti anotací do svých aplikací v jazyce C#.

### FAQ

#### Otázka: Jaké typy anotací lze přidat pomocí Aspose.PDF pro .NET?

A: Aspose.PDF for .NET podporuje různé typy anotací, včetně textových anotací, razítek, odkazů, tvarů a dalších. Vývojáři mohou upravit vzhled a vlastnosti těchto poznámek tak, aby vyhovovaly jejich specifickým potřebám.

#### Otázka: Mohu přidat anotace ke konkrétním stránkám ve vícestránkovém dokumentu PDF?

Odpověď: Ano, Aspose.PDF pro .NET vám umožňuje určit stránku, kam chcete přidat anotaci. Podle potřeby můžete vybrat konkrétní stránku nebo přidat poznámky na více stránek.

#### Otázka: Jak přizpůsobím vzhled anotací?

Odpověď: Poznámky lze přizpůsobit pomocí vlastností, jako je šířka okraje, barva, styl čárky, styl textu a další. Aspose.PDF for .NET poskytuje bohatou sadu možností pro přizpůsobení vzhledu anotací.

#### Otázka: Je možné přidávat hypertextové odkazy jako anotace pomocí Aspose.PDF pro .NET?

Odpověď: Ano, pomocí Aspose.PDF pro .NET můžete přidávat hypertextové odkazy jako anotace k dokumentům PDF. Anotace hypertextových odkazů lze použít k propojení na externí adresy URL nebo konkrétní umístění v rámci stejného dokumentu.

#### Otázka: Lze do existujících dokumentů PDF přidávat anotace, aniž by se změnil původní obsah?

Odpověď: Ano, Aspose.PDF pro .NET přidává anotace jako další prvky, aniž by měnil původní obsah dokumentu PDF. Původní obsah PDF zůstane nedotčen.