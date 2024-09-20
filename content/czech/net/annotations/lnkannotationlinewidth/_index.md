---
title: lnk Šířka čáry anotace
linktitle: lnk Šířka čáry anotace
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit šířku čáry inkoustové anotace v PDF pomocí Aspose.PDF pro .NET. Tento podrobný návod vás provede každým krokem a zajistí vysoce kvalitní výstup.
type: docs
weight: 110
url: /cs/net/annotations/lnkannotationlinewidth/
---
## Zavedení

Při práci s dokumenty PDF může být přidávání anotací účinným způsobem, jak zvýraznit informace nebo přidat do souborů interaktivní prvky. Jednou z takových anotací je inkoustová anotace, která umožňuje kreslit do PDF čáry volného tvaru. Co když ale potřebujete upravit vzhled těchto čar, zejména šířku čáry? V tomto tutoriálu vás provedeme procesem nastavení šířky čáry inkoustové anotace pomocí Aspose.PDF pro .NET.

## Předpoklady

Než se ponoříte do kódu, ujistěte se, že máte vše nastaveno, abyste mohli hladce sledovat tento tutoriál:

1.  Aspose.PDF for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF for .NET. Můžete si jej stáhnout z[stránka ke stažení](https://releases.aspose.com/pdf/net/) nebo jej nainstalujte prostřednictvím NuGet Package Manager ve Visual Studiu.
2. Vývojové prostředí: Tento kurz předpokládá, že pracujete ve vývojovém prostředí .NET, jako je Visual Studio.
3. Základní znalost C#: Základní znalost C# vám pomůže dodržet kroky kódování.
4. Dokument PDF: Použijte existující dokument PDF nebo vytvořte nový pro tento výukový program.

## Import nezbytných jmenných prostorů

Než začnete kódovat, nezapomeňte do projektu importovat potřebné jmenné prostory:

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Tyto jmenné prostory poskytují třídy a metody potřebné pro manipulaci s dokumenty PDF, práci s anotacemi a zpracování grafických prvků.

Nyní, když máme připraveny naše předpoklady, pojďme si rozdělit proces nastavení šířky čáry inkoustové anotace do jasných, zvládnutelných kroků.

## Krok 1: Inicializujte dokument PDF

Nejprve musíme vytvořit nebo otevřít dokument PDF. Pro tento tutoriál vytvoříme nový dokument PDF od začátku.

```csharp
// Inicializujte dokument PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Zadejte adresář dokumentů
Document doc = new Document();
doc.Pages.Add(); // Přidejte do dokumentu prázdnou stránku
```

 Zde inicializujeme nový`Document` objekt, který představuje náš soubor PDF. K tomuto dokumentu pak přidáme prázdnou stránku, se kterou budeme pracovat.

## Krok 2: Vytvořte poznámku inkoustem

Dále vytvoříme samotnou poznámku inkoustem. To zahrnuje definování bodů, které tvoří tahy inkoustem.

```csharp
// Vytvořte inkoustovou anotaci
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 V tomto kroku definujeme`LineInfo` objekt, který obsahuje souřadnice tahů inkoustem, jejich viditelnost, barvu a počáteční šířku čáry. The`VerticeCoordinate` pole obsahuje souřadnice X a Y každého bodu v tahu.

## Krok 3: Převeďte souřadnice na body

Nyní potřebujeme tyto souřadnice převést na body, které lze použít v Ink Annotation.

```csharp
// Převést souřadnice na body
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Tato smyčka zpracovává pole souřadnic a převádí každou dvojici souřadnic na a`Point` objekt, který se pak přidá k našemu`inkList`.

## Krok 4: Přidejte inkoustovou anotaci na stránku PDF

S připravenými body můžeme nyní vytvořit poznámku inkoustem a přidat ji na stránku PDF.

```csharp
// Přidejte poznámku inkoustem na stránku PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 V tomto kroku inicializujeme an`InkAnnotation`objekt, specifikující stránku, ohraničující obdélník a náš seznam bodů. Nastavíme také předmět, název a barvu anotace.

## Krok 5: Přizpůsobte ohraničení anotace

Abychom dále přizpůsobili vzhled naší anotace, upravíme její vlastnosti ohraničení.

```csharp
// Přizpůsobte ohraničení anotace
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Zde vytvoříme a`Border` objekt pro naši anotaci, nastavení jeho šířky, efektu, vzoru čárek a stylu. Tento krok zajistí, že anotace na stránce PDF vizuálně vynikne.

## Krok 6: Uložte dokument PDF

Nakonec, po provedení všech nezbytných změn, je čas dokument uložit.

```csharp
// Uložte dokument PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Tento kód uloží upravený dokument PDF s inkoustovou anotací do určeného adresáře. The`Console.WriteLine` výpis potvrzuje úspěšné provedení kódu.

## Závěr

Gratuluji! Úspěšně jste vytvořili a upravili inkoustovou anotaci v dokumentu PDF pomocí Aspose.PDF pro .NET. Tento tutoriál pokryl celý proces, od inicializace dokumentu až po uložení konečného souboru. S těmito znalostmi můžete dále prozkoumat rozsáhlé možnosti Aspose.PDF pro .NET a aplikovat podobné techniky na jiné typy anotací nebo manipulací s PDF.

## FAQ

### Mohu použít různé barvy pro různé části poznámky inkoustem?  
 Ano, můžete vytvořit více`InkAnnotation` objekty s různými barvami a přidejte je na stejné nebo různé stránky vašeho PDF.

### Jak dynamicky změním šířku čáry?  
 Můžete upravit`LineWidth` vlastnictvím`LineInfo` objekt před převodem souřadnic na body.

### Je možné zprůhlednit poznámku inkoustem?  
 Ano, můžete upravit`Opacity` vlastnictvím`InkAnnotation` objekt, aby byl průhledný.

### Mohu přidat více inkoustových poznámek na stejnou stránku?  
Absolutně! Opakováním postupu můžete na jednu stránku přidat libovolný počet inkoustových anotací.

### Jak odstraním inkoustovou anotaci z PDF?  
 Anotace můžete odstranit pomocí`doc.Pages[1].Annotations.Delete(a1)` metoda, kde`a1` je objekt vaší anotace.