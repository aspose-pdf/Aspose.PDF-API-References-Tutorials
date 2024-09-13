---
title: Seskupená zaškrtávací políčka v dokumentu PDF
linktitle: Seskupená zaškrtávací políčka v dokumentu PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet seskupená zaškrtávací políčka (přepínače) v dokumentu PDF pomocí Aspose.PDF for .NET pomocí tohoto podrobného návodu.
type: docs
weight: 170
url: /cs/net/programming-with-forms/grouped-check-boxes/
---
## Zavedení

Vytváření interaktivních PDF není tak obtížné, jak by se mohlo zdát, zvláště když máte k dispozici výkonné nástroje jako Aspose.PDF for .NET. Jedním z interaktivních prvků, které možná budete muset přidat do svých dokumentů PDF, jsou seskupená zaškrtávací políčka, nebo konkrétněji přepínače, které uživatelům umožňují vybrat jednu možnost ze sady. Tento tutoriál vás provede procesem přidávání seskupených zaškrtávacích políček (přepínačů) do dokumentu PDF pomocí Aspose.PDF pro .NET. Ať už jste začátečník nebo ostřílený vývojář, tento průvodce shledáte poutavým, podrobným a snadno sledovatelným.

## Předpoklady

Než se ponoříme do podrobného průvodce, pojďme si pokrýt některé základní předpoklady:

1.  Aspose.PDF pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF. Pokud ne, můžete[stáhněte si jej zde](https://releases.aspose.com/pdf/net/).
2. IDE: Měli byste mít nastavené vývojové prostředí, jako je Visual Studio.
3. .NET Framework: Projekt by měl cílit na verzi rozhraní .NET Framework kompatibilní s Aspose.PDF.
4. Základní znalost C#: Pro bezproblémové pokračování je nutná znalost C# a manipulace s PDF.
5.  Licence: Aspose.PDF vyžaduje licenci pro plnou funkčnost. Můžete[získat dočasnou licenci](https://purchase.aspose.com/temporary-license/) v případě potřeby.

## Importujte balíčky

Než začnete, ujistěte se, že jste do projektu importovali potřebné jmenné prostory:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Tyto balíčky vám umožní přístup ke všem třídám a metodám potřebným pro manipulaci s dokumenty PDF, včetně vytváření přepínačů a definování jejich vlastností.

V této části rozdělíme proces vytváření seskupených zaškrtávacích políček (přepínačů) do jasných a snadno pochopitelných kroků.

## Krok 1: Vytvořte nový dokument PDF

 Prvním krokem je vytvoření instance souboru`Document` objekt, který bude reprezentovat váš soubor PDF. Poté do dokumentu přidejte prázdnou stránku, kam umístíte seskupená zaškrtávací políčka.

```csharp
// Objekt okamžitého dokumentu
Document pdfDocument = new Document();

// Přidejte stránku do souboru PDF
Page page = pdfDocument.Pages.Add();
```

Tím se nastaví základ pro přidávání jakýchkoli prvků, jako jsou přepínače, do PDF.

## Krok 2: Inicializujte pole přepínače

Dále musíme vytvořit a`RadioButtonField` objekt, který bude obsahovat seskupená zaškrtávací políčka (přepínače). Toto pole se přidá na konkrétní stránku, kde se objeví zaškrtávací políčka.

```csharp
// Vytvořte instanci objektu RadioButtonField a přiřaďte jej na první stránku
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Představte si to jako kontejner, který bude seskupovat jednotlivé možnosti přepínače.

## Krok 3: Přidejte možnosti přepínače

 Nyní do pole přidáme jednotlivé možnosti přepínače. V tomto příkladu přidáme dva přepínače a určíme jejich pozice pomocí`Rectangle` objekt.

```csharp
// Přidejte první možnost přepínače a určete jeho polohu pomocí Obdélník
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Nastavte názvy možností pro identifikaci
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Tady,`Rectangle` objekt definuje souřadnice a velikost každého přepínače na stránce.

## Krok 4: Přizpůsobte styl přepínacích tlačítek

 Vzhled přepínacích tlačítek můžete upravit jejich nastavením`Style` vlastnictví. Můžete například chtít zaškrtávací políčka ve tvaru čtverce nebo kříže.

```csharp
// Nastavte styl přepínacích tlačítek
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

To vám umožňuje ovládat vzhled a chování zaškrtávacích políček, díky čemuž jsou uživatelsky přívětivější a vizuálně přitažlivější.

## Krok 5: Konfigurace vlastností ohraničení

Hranice hrají zásadní roli při snadné identifikaci zaškrtávacích políček. Zde přidáme pevné okraje kolem každé možnosti přepínače a definujeme jejich šířku a barvu.

```csharp
// Nakonfigurujte ohraničení prvního přepínače
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Nakonfigurujte ohraničení druhého přepínače
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Tento krok zajistí, že každý přepínač bude mít dobře definovaný okraj, čímž se zlepší čitelnost dokumentu.

## Krok 6: Přidejte možnosti přepínacího tlačítka do formuláře

Nyní přidáme přepínače do formuláře dokumentu. Toto je poslední krok při seskupování zaškrtávacích políček do jednoho pole.

```csharp
// Přidejte pole přepínače do objektu formuláře dokumentu
pdfDocument.Form.Add(radio);
```

Objekt formuláře funguje jako kontejner pro všechny interaktivní prvky, včetně našich seskupených zaškrtávacích políček.

## Krok 7: Uložte dokument PDF

Nakonec, jakmile je vše nastaveno, můžete uložit dokument PDF na požadované místo.

```csharp
// Definujte cestu k výstupnímu souboru
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Uložte dokument PDF
pdfDocument.Save(dataDir);

// Potvrďte úspěšné vytvoření
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

A je to! Úspěšně jste vytvořili PDF se seskupenými zaškrtávacími políčky pomocí Aspose.PDF pro .NET.

## Závěr

Přidávání interaktivních prvků, jako jsou seskupená zaškrtávací políčka, do dokumentů PDF se může zpočátku zdát složité, ale s Aspose.PDF pro .NET se to stane hračkou. Podle tohoto podrobného průvodce jste se naučili, jak nastavit základní dokument PDF, přidat seskupená přepínače, upravit jejich vzhled a uložit konečný výsledek. Ať už vytváříte formuláře, průzkumy nebo jakýkoli jiný typ interaktivního PDF, tato příručka vám poskytne pevný základ, se kterým můžete začít.

## FAQ

### Mohu do skupiny přidat více než dva přepínače?
 Absolutně! Jednoduše vytvořte další instanci`RadioButtonOptionField` objekty a přidejte je do`RadioButtonField` jak je uvedeno v tutoriálu.

### Jak zpracuji více skupin zaškrtávacích políček v jednom dokumentu?
Chcete-li vytvořit více skupin, vytvořte samostatnou instanci`RadioButtonField` objekty pro každou skupinu.

### Existuje nějaký limit na počet zaškrtávacích políček, která mohu přidat?
Ne, Aspose.PDF for .NET neukládá žádná omezení na počet zaškrtávacích políček, která můžete přidat do PDF.

### Mohu změnit vzhled zaškrtávacích políček po jejich přidání?
Ano, po přidání zaškrtávacích políček můžete upravit vlastnosti, jako je styl ohraničení, šířka a barva.

### Je možné použít obrázky jako přepínače?
 Ano, Aspose.PDF vám umožňuje používat vlastní obrázky jako přepínače nastavením`Appearance` vlastnost každé možnosti přepínače.