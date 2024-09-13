---
title: Nastavte datum vypršení platnosti v souboru PDF
linktitle: Nastavte datum vypršení platnosti v souboru PDF
second_title: Aspose.PDF pro .NET API Reference
description: Naučte se, jak nastavit datum vypršení platnosti v souborech PDF pomocí Aspose.PDF pro .NET. Vylepšete zabezpečení dokumentů pomocí tohoto podrobného průvodce.
type: docs
weight: 300
url: /cs/net/programming-with-document/setexpirydate/
---
## Zavedení

dnešní digitální době je správa a zabezpečení dokumentů důležitější než kdy jindy. Představte si, že posíláte PDF, které se po určitém datu automaticky stane nepřístupným. Zní to jako kouzlo, že? S Aspose.PDF pro .NET můžete snadno nastavit datum vypršení platnosti souborů PDF. Tato funkce je užitečná zejména pro citlivé dokumenty, které je třeba po určité době omezit. V tomto tutoriálu vás krok za krokem provedeme procesem nastavení data vypršení platnosti v souboru PDF. Takže popadněte svůj kódovací klobouk a pojďme se ponořit!

## Předpoklady

Než začneme, je třeba mít připraveno několik věcí:

1. Vývojové prostředí: Ujistěte se, že máte nastavené vývojové prostředí .NET. Může to být Visual Studio nebo jakékoli jiné IDE, které podporuje .NET.
2.  Aspose.PDF for .NET: Musíte mít nainstalovanou knihovnu Aspose.PDF. Pokud jste to ještě neudělali, můžete si to stáhnout z[zde](https://releases.aspose.com/pdf/net/).
3. Základní znalost C#: Tento tutoriál předpokládá, že máte základní znalosti o programování v C#. Pokud jste v C# noví, nebojte se! Zachováme to jednoduché a přímočaré.

## Importujte balíčky

Chcete-li začít s Aspose.PDF, musíte do svého projektu C# importovat potřebné jmenné prostory. Můžete to udělat takto:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Tyto jmenné prostory vám poskytují přístup k základním funkcím potřebným pro práci s dokumenty PDF v Aspose.PDF.

## Krok 1: Nastavte adresář dokumentů

Nejprve musíte zadat cestu k adresáři dokumentů. Zde se uloží vaše výstupní PDF. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou, kam chcete soubor PDF uložit. Je to, jako byste svému programu řekli: "Hej, tady si uchovávám své soubory!"

## Krok 2: Vytvořte instanci objektu dokumentu

 Dále musíte vytvořit novou instanci souboru`Document` třída. Toto je vaše plátno, na kterém vytvoříte PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Myslete na`Document` objekt jako prázdný list papíru. Můžete do něj přidávat obsah, jak chcete!

## Krok 3: Přidejte stránku do PDF

Nyní, když máte dokument nastavený, je čas přidat do něj stránku. Tady bude váš obsah.

```csharp
doc.Pages.Add();
```

Právě jste vytvořili novou stránku ve svém PDF. Je to jako přidat do poznámkového bloku novou stránku, kam si můžete zapisovat své myšlenky.

## Krok 4: Přidejte text na stránku

Pojďme udělat tuto stránku trochu zajímavější přidáním nějakého textu. Přidáme jednoduchou zprávu „Ahoj světe“.

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Tento řádek kódu přidá textový fragment na první stránku vašeho PDF. Je to jako napsat nadpis v horní části stránky!

## Krok 5: Vytvořte JavaScript pro datum vypršení platnosti

Nyní přichází ta zábavná část! Vytvoříte akci JavaScriptu, která zkontroluje datum vypršení platnosti PDF. Pokud aktuální datum překročí datum vypršení platnosti, upozorní uživatele zpráva.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Zde je to, co se děje:
- Definujete rok a měsíc platnosti.
- Dostanete dnešní datum.
- Porovnáte dnešní datum s datem vypršení platnosti.
- Pokud je dnešní datum po datu vypršení platnosti, objeví se zpráva!

## Krok 6: Nastavte JavaScript jako PDF Open Action

Nyní musíte nastavit akci JavaScript jako akci otevření pro váš dokument PDF. To znamená, že JavaScript se spustí, jakmile se PDF otevře.

```csharp
doc.OpenAction = javaScript;
```

Tento řádek říká PDF, aby spustil JavaScript, když jej někdo otevře. Je to jako nastavit připomenutí, které se spustí, jakmile otevřete kalendář!

## Krok 7: Uložte dokument PDF

Konečně je čas uložit dokument PDF pomocí funkce data vypršení platnosti. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Tento řádek uloží vaše PDF do zadaného adresáře s názvem "SetExpiryDate_out.pdf". Je to jako vložit hotové umělecké dílo do rámu!

## Závěr

A tady to máte! Úspěšně jste vytvořili soubor PDF s datem vypršení platnosti pomocí Aspose.PDF pro .NET. Tato funkce nejen zvyšuje zabezpečení, ale také zajišťuje, že citlivé informace budou udržovány pod kontrolou. Ať už posíláte smlouvy, zprávy nebo jiné důležité dokumenty, nastavení data vypršení může změnit hru.

## FAQ

### Co je Aspose.PDF pro .NET?
Aspose.PDF for .NET je výkonná knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět dokumenty PDF v aplikacích .NET.

### Mohu používat Aspose.PDF zdarma?
 Ano, můžete použít bezplatnou zkušební verzi Aspose.PDF. Můžete si jej stáhnout[zde](https://releases.aspose.com/).

### Jak koupím Aspose.PDF?
Aspose.PDF si můžete zakoupit na adrese[nákupní stránku](https://purchase.aspose.com/buy).

### Co když potřebuji podporu?
Pokud máte nějaké dotazy nebo potřebujete pomoc, můžete navštívit stránku[Aspose fórum podpory](https://forum.aspose.com/c/pdf/10).

### Mohu získat dočasnou licenci pro Aspose.PDF?
 Ano, můžete požádat o dočasnou licenci[zde](https://purchase.aspose.com/temporary-license/).