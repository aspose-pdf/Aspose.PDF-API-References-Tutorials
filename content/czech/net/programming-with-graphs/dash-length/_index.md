---
title: Délka pomlčky
linktitle: Délka pomlčky
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit délku pomlček pomocí Aspose.PDF pro .NET. Krok za krokem průvodce přizpůsobením vzorů čárek.
type: docs
weight: 70
url: /cs/net/programming-with-graphs/dash-length/
---
tomto tutoriálu vás krok za krokem provedeme následujícím zdrojovým kódem C#, jak nastavit délku pomlček pomocí Aspose.PDF pro .NET.

Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili své vývojové prostředí. Také mít základní znalosti programování v C#.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém zdrojovém kódu musíte určit adresář, kam chcete uložit výsledný soubor PDF. Změňte proměnnou "dataDir" na požadovaný adresář.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření instance objektu dokumentu a přidání stránky

Vytvoříme instanci třídy Document a do tohoto dokumentu přidáme stránku.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Krok 3: Vytvoření objektu Graph a jeho přidání na stránku

Vytvoříme objekt Graph se zadanými rozměry a přidáme jej do kolekce odstavců stránky.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Krok 4: Vytvoření čárového objektu a konfigurace

Vytvoříme objekt Line se zadanými souřadnicemi a nakonfigurujeme barvu a délku čárek.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Krok 5: Přidání čáry do objektu Graph

Čáru přidáme do kolekce tvarů objektu Graph.

```csharp
canvas.Shapes.Add(line);
```

## Krok 6: Uložení výsledného souboru PDF

Nakonec výsledný soubor PDF s názvem „DashLength_out.pdf“ uložíme do zadaného adresáře.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Ukázkový zdrojový kód pro Dash Length pomocí Aspose.PDF pro .NET 

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancia dokumentu instance
Document doc = new Document();
// Přidat stránku do kolekce stránek objektu Document
Page page = doc.Pages.Add();
// Vytvořte nakreslený objekt s určitými rozměry
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Přidejte nakreslený objekt do kolekce odstavců instance stránky
page.Paragraphs.Add(canvas);
// Vytvořit objekt Line
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Nastavte barvu pro objekt Line
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Zadejte pole čárek pro objekt line
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Nastavte fázi pomlčky pro instanci Line
line.GraphInfo.DashPhase = 1;
// Přidejte čáru do kolekce tvarů nakresleného objektu
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Uložit dokument PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Závěr

tomto tutoriálu jsme vysvětlili, jak nastavit délku pomlček pomocí Aspose.PDF pro .NET. Nyní můžete tyto znalosti využít k vytváření čar s vlastními čárkovanými vzory v souborech PDF.

## Nejčastější dotazy

#### Otázka: Jaký je účel tohoto tutoriálu?

Odpověď: Účelem tohoto tutoriálu je provést vás procesem nastavení délky pomlček pro čáry pomocí Aspose.PDF pro .NET. Dozvíte se, jak vytvořit čáry s vlastními čárkovanými vzory v souborech PDF.

#### Otázka: Jaké předpoklady jsou vyžadovány před zahájením?

A: Než začnete, ujistěte se, že jste nainstalovali knihovnu Aspose.PDF a nastavili vaše vývojové prostředí. Doporučuje se také základní znalost programování v C#.

#### Otázka: Jak určím adresář pro uložení souboru PDF?

Odpověď: Upravte proměnnou "dataDir" v poskytnutém zdrojovém kódu tak, aby označovala adresář, kam chcete uložit výsledný soubor PDF.

#### Otázka: Jak vytvořím čáru s vlastními čárkovanými vzory?

 Odpověď: Výukový program demonstruje vytvoření objektu Line a konfiguraci jeho barvy, pole čárek a fáze čárky pomocí`GraphInfo` objekt. Upravte tato nastavení, abyste dosáhli požadovaného vzoru čárek.

#### Otázka: Mohu přizpůsobit barvu čáry?

 Odpověď: Ano, můžete upravit barvu čáry nastavením`Color` majetek z`GraphInfo` objekt spojený s linií.

#### Otázka: Jak uložím dokument PDF po nastavení délky pomlčky?

 Odpověď: Po konfiguraci objektu Line s požadovaným vzorem čárky můžete výsledný dokument PDF uložit pomocí`doc.Save(dataDir + "DashLength_out.pdf");` řádek v poskytnutém zdrojovém kódu.