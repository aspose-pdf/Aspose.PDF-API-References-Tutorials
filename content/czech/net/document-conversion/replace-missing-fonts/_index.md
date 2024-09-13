---
title: Nahradit chybějící písma
linktitle: Nahradit chybějící písma
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nahradit chybějící písma v dokumentech PDF pomocí Aspose.PDF for .NET, pomocí tohoto podrobného průvodce.
type: docs
weight: 260
url: /cs/net/document-conversion/replace-missing-fonts/
---
## Zavedení

Stalo se vám někdy, že jste otevřeli dokument PDF, abyste zjistili, že některá písma chybí? Může to být frustrující, že? Chybějící písma mohou vést k tomu, že dokument vypadá úplně jinak, než zamýšlel tvůrce. Naštěstí s Aspose.PDF for .NET můžete snadno nahradit chybějící písma a zajistit, aby si vaše dokumenty PDF zachovaly svůj zamýšlený vzhled. V tomto tutoriálu vás provedeme procesem krok za krokem, aby byl jednoduchý a přímočarý.

## Předpoklady

Než začneme, je potřeba mít připraveno několik věcí:

1.  Aspose.PDF pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.PDF. Můžete si jej stáhnout z[zde](https://releases.aspose.com/pdf/net/).
2. Visual Studio: Vývojové prostředí, kde můžete psát a testovat svůj kód.
3. Základní znalost C#: Znalost programování v C# vám pomůže lépe porozumět úryvkům kódu.

## Importujte balíčky

Chcete-li začít, budete muset importovat potřebné balíčky do svého projektu C#. Můžete to udělat takto:

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte zadat cestu k adresáři dokumentů. Zde je umístěn váš vstupní soubor PDF a kde bude uložen výstupní soubor.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Inicializujte původní písmo

Dále budete chtít zkusit najít původní písmo, které by mohlo chybět. V tomto případě hledáme "AgencyFB."

```csharp
Aspose.Pdf.Text.Font originalFont = null;
try
{
    originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
    //Na cílovém počítači chybí písmo
    FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

Zde se pokusíme najít písmo. Pokud není nalezen, zachytíme výjimku a nahradíme ji běžnějším písmem „Arial“. Tím zajistíte, že váš dokument bude stále vypadat dobře, i když původní písmo nebude k dispozici.

## Krok 3: Načtěte dokument PDF

Nyní načteme dokument PDF, který chcete zpracovat. Budete muset zadat cestu ke vstupnímu souboru.

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
```

 V tomto kroku vytvoříme nový`FileInfo` objekt pro výstupní soubor a načtěte vstupní dokument PDF do nového`Document` objekt.

## Krok 4: Převeďte dokument PDF

Před uložením dokumentu je dobré jej převést do konkrétního formátu PDF. V tomto případě jej převedeme do formátu PDF/A-1B, což je standard pro dlouhodobou archivaci elektronických dokumentů.

```csharp
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

Tento řádek převede PDF a zaprotokoluje všechny chyby do určeného souboru XML. Pokud se během převodu vyskytnou nějaké problémy, budou zaznamenány v „log.xml“.

## Krok 5: Uložte aktualizovaný dokument PDF

Konečně je čas uložit aktualizovaný dokument PDF s nahrazenými fonty.

```csharp
pdf.Save(fileNew.FullName);
```

Tento řádek uloží upravené PDF do zadané cesty k výstupnímu souboru. A právě tak jste úspěšně nahradili chybějící písma v dokumentu PDF!

## Závěr

Nahrazení chybějících písem v dokumentech PDF nemusí být skličující úkol. S Aspose.PDF for .NET můžete snadno spravovat náhrady písem a zajistit, aby vaše dokumenty vypadaly tak, jak mají. Podle kroků uvedených v tomto kurzu můžete zachovat integritu souborů PDF, i když některá písma nejsou k dispozici. Takže až příště narazíte na problém s chybějícím písmem, budete přesně vědět, co dělat!

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF programově.

### Mohu používat Aspose.PDF zdarma?
 Ano, Aspose nabízí bezplatnou zkušební verzi, kterou můžete použít k hodnocení knihovny. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Co mám dělat, když písmo, které potřebuji, není k dispozici?
Chybějící písmo můžete nahradit běžnějším pomocí funkce nahrazování písem v Aspose.PDF.

### Je možné převést PDF do jiných formátů?
Absolutně! Aspose.PDF podporuje převod do různých formátů, včetně PDF/A, DOCX a dalších.

### Kde najdu podporu pro Aspose.PDF?
 Podporu a dotazy můžete najít na fóru Aspose[zde](https://forum.aspose.com/c/pdf/10).