---
title: Vodorovně a svisle Přepínače
linktitle: Vodorovně a svisle Přepínače
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se vytvářet vodorovně a svisle zarovnaná přepínací tlačítka v PDF pomocí Aspose.PDF pro .NET pomocí tohoto podrobného návodu.
type: docs
weight: 180
url: /cs/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Zavedení

Vytváření interaktivních formulářů PDF může výrazně zlepšit uživatelskou zkušenost, zejména pokud jde o shromažďování informací. Jedním z nejběžnějších prvků formuláře je přepínač, který uživatelům umožňuje vybrat jednu možnost ze sady. V tomto tutoriálu prozkoumáme, jak vytvořit vodorovně a svisle zarovnaná přepínací tlačítka pomocí Aspose.PDF pro .NET. Ať už jste zkušený vývojář nebo teprve začínáte, tento průvodce vás provede procesem krok za krokem a zajistí vám jasné pochopení každé části.

## Předpoklady

Než se ponoříte do kódu, musíte mít splněno několik předpokladů:

1.  Aspose.PDF for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF. Můžete si jej stáhnout z[místo](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Vývojové prostředí, kde můžete psát a testovat svůj kód.
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.

## Importujte balíčky

Chcete-li začít, musíte do svého projektu C# importovat potřebné balíčky. Můžete to udělat takto:

### Vytvořit nový projekt

Otevřete Visual Studio a vytvořte nový projekt C#. Pro jednoduchost si můžete vybrat konzolovou aplikaci.

### Přidejte odkaz Aspose.PDF

1. Klepněte pravým tlačítkem myši na svůj projekt v Průzkumníku řešení.
2. Vyberte „Spravovat balíčky NuGet“.
3. Vyhledejte „Aspose.PDF“ a nainstalujte nejnovější verzi.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Nyní, když máte vše nastaveno, pojďme rozdělit kód a vytvořit vodorovně a svisle zarovnaná přepínací tlačítka.

## Krok 1: Nastavte adresář dokumentů

V tomto kroku definujeme cestu k adresáři, kde budou uloženy vaše PDF dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kam chcete soubor PDF uložit. To je zásadní, protože říká programu, kde má hledat vstupní soubory a kam uložit výstup.

## Krok 2: Načtěte existující dokument PDF

 Dále musíme načíst PDF dokument, se kterým budeme pracovat. To se provádí pomocí`FormEditor` třída.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Zde vytvoříme instanci`FormEditor` a svázat jej s existujícím souborem PDF s názvem`input.pdf`. Ujistěte se, že tento soubor existuje ve vašem zadaném adresáři.

## Krok 3: Konfigurace vlastností přepínacího tlačítka

Nyní nastavíme některé vlastnosti pro naše přepínače. To zahrnuje mezeru mezi tlačítky, jejich orientaci a velikost.

```csharp
formEditor.RadioGap = 4; // Vzdálenost mezi možnostmi přepínače
formEditor.RadioHoriz = true; // Nastavte na hodnotu true pro horizontální zarovnání
formEditor.RadioButtonItemSize = 20; // Velikost přepínače
formEditor.Facade.BorderWidth = 1; // Šířka okraje
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Barva ohraničení
```

 Tyto vlastnosti pomohou definovat, jak se přepínací tlačítka zobrazí v PDF. The`RadioGap` vlastnost ovládá mezeru mezi tlačítky, zatímco`RadioHoriz` určuje jejich rozložení.

## Krok 4: Přidejte horizontální přepínače

Nyní do PDF přidáme horizontální přepínače.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 V tomto kódu definujeme položky pro přepínače a přidáme je do PDF. The`AddField`metoda přebírá několik parametrů, včetně typu pole, názvu pole a souřadnic pro umístění.

## Krok 5: Přidejte vertikální přepínače

Dále přidáme vertikální přepínače. K tomu musíme změnit orientaci zpět na vertikální.

```csharp
formEditor.RadioHoriz = false; // Pro vertikální zarovnání nastavte na false
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Stejně jako předtím definujeme položky a přidáme je do PDF, ale tentokrát budou zarovnány svisle.

## Krok 6: Uložte dokument PDF

Nakonec musíme upravený PDF dokument uložit.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Tento kód uloží PDF s nově přidanými přepínači. Nezapomeňte zkontrolovat zadaný adresář pro výstupní soubor.

## Závěr

Vytváření přepínačů v PDF pomocí Aspose.PDF pro .NET je jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete do formulářů PDF snadno přidat vodorovně i svisle zarovnané přepínače. To nejen zlepšuje interaktivitu vašich dokumentů, ale také zlepšuje celkovou uživatelskou zkušenost. Takže do toho a vyzkoušejte to!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k hodnocení knihovny. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Jak získám podporu pro Aspose.PDF?
 Podporu můžete získat návštěvou stránky[Aspose fórum](https://forum.aspose.com/c/pdf/10).

### Je možné pomocí Aspose.PDF vytvořit další prvky formuláře?
Absolutně! Aspose.PDF podporuje různé prvky formuláře, včetně textových polí, zaškrtávacích políček a rozevíracích seznamů.

### Kde si mohu zakoupit Aspose.PDF pro .NET?
 Můžete si koupit Aspose.PDF pro .NET z[nákupní stránku](https://purchase.aspose.com/buy).