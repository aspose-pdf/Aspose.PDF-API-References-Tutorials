---
title: Získejte rozměry stránky PDF
linktitle: Získejte rozměry stránky PDF
second_title: Aspose.PDF pro .NET API Reference
description: V tomto tutoriálu vysvětlíme, jak získat rozměry stránky PDF a provádět manipulace pomocí Aspose.PDF for .NET. Jsou uvedeny podrobné kroky, které vás provedou celým procesem.
type: docs
weight: 60
url: /cs/net/programming-with-pdf-pages/get-dimensions/
---
## Zavedení

Potřebovali jste někdy upravit rozměry stránky dokumentu PDF? Možná jste chtěli změnit velikost stránky nebo ji otočit, aby vyhovovala vašim potřebám? Pokud ano, jste na správném místě! V tomto tutoriálu vás provedeme načítáním a úpravou rozměrů stránky PDF pomocí Aspose.PDF pro .NET. Ať už jste začátečník nebo ostřílený vývojář, tato příručka je pro vás jednoduchá a snadno se s ní budete řídit.

Aspose.PDF for .NET je výkonná knihovna, která vám umožní snadno vytvářet, manipulovat a transformovat soubory PDF. Je to jako mít švýcarský armádní nůž na PDF – můžete vyladit každý malý detail, aby přesně odpovídal vašim požadavkům. Pojďme se tedy ponořit přímo do toho a naučit se, jak načíst a aktualizovat rozměry stránky PDF pomocí tohoto úžasného nástroje!

## Předpoklady

Než začnete, budete potřebovat několik věcí, abyste mohli hladce postupovat podle tohoto návodu:

1.  Aspose.PDF pro .NET: Můžete[stáhněte si nejnovější verzi zde](https://releases.aspose.com/pdf/net/) . Pokud nemáte licenci, nebojte se! Můžete požádat a[zkušební verze zdarma](https://releases.aspose.com/) , nebo se rozhodnout pro a[dočasná licence](https://purchase.aspose.com/temporary-license/).
2. Visual Studio: Vývojové prostředí, které budete používat k psaní a spouštění kódu.
3. Základní znalost C#: I když budeme mít věci jednoduché, určitá znalost C# proces usnadní.
4. Soubor PDF, se kterým můžete pracovat: Vezměte si jakýkoli vzorový soubor PDF nebo vytvořte nový k otestování.

## Importujte balíčky

Chcete-li pracovat s Aspose.PDF pro .NET, musíte importovat několik základních jmenných prostorů. To vytváří podmínky pro interakci s dokumenty PDF. Jak na to:

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Tyto importy zajišťují, že máte přístup k základním třídám potřebným pro manipulaci se soubory PDF, zejména pro správu stránek a načítání jejich rozměrů.

Nyní, když máme vše na svém místě, pojďme si celý proces rozdělit do snadno srozumitelných kroků.

## Krok 1: Definujte cestu k souboru a načtěte dokument

Prvním krokem je zadat cestu k vašemu PDF dokumentu a načíst jej pomocí Aspose.PDF. To vám umožní pracovat se stránkami v souboru PDF.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Otevřete dokument
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

V tomto kroku v podstatě otevíráte soubor PDF, se kterým chcete pracovat. Pokud jste někdy otevřeli knihu na konkrétní stránce, je to docela podobné – ale místo toho otevíráte dokument PDF, abyste získali přístup k jeho stránkám.

## Krok 2: Pokud neexistují žádné stránky, přidejte prázdnou stránku

Co když váš dokument nemá žádné stránky? Nebojte se! Do dokumentu můžeme přidat prázdnou stránku a pracovat s ní. Zde je návod, jak zkontrolovat, zda stránka existuje, a v případě potřeby přidat novou:

```csharp
// Přidá prázdnou stránku do dokumentu pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Tento řádek kódu zkontroluje, zda již v dokumentu existuje stránka. Pokud ano, vybere první stránku (`Pages[1]`). V opačném případě vytvoří prázdnou stránku a přidá ji do PDF.

Představte si to jako otevřít prázdný sešit a napsat na první stránku, pokud tam nic není – snadné, že?

## Krok 3: Získejte informace o výšce a šířce stránky

 Nyní, když máme stránku, se kterou můžeme pracovat, načteme rozměry stránky. Použijeme`GetPageRect()` způsob, jak získat výšku a šířku.

```csharp
// Získejte informace o výšce a šířce stránky
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Zde,`GetPageRect(true)` vrátí obdélník, který zahrnuje výšku a šířku stránky. Je to jako měřit kus papíru pravítkem. Výstup se zobrazí v konzole a poskytne vám aktuální rozměry stránky.

## Krok 4: Otočte stránku o 90 stupňů

Chcete otočit stránku? Žádný problém! Pomocí jednoduché vlastnosti můžete otočit stránku o 90 stupňů.

```csharp
// Otočte stránku v úhlu 90 stupňů
page.Rotate = Rotation.on90;
```

Tento krok otočí stránku ve směru hodinových ručiček o 90 stupňů. Představte si, že otáčíte vytištěný list na stole – nyní je v režimu na šířku!

## Krok 5: Znovu zkontrolujte rozměry stránky po otočení

Po otočení stránky je dobré znovu zkontrolovat rozměry. Proč? Protože rotace může ovlivnit, jak interpretujete výšku a šířku.

```csharp
// Získejte informace o výšce a šířce stránky
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Nyní budou rozměry stránky aktualizovány na základě nové orientace. Je to jako otáčení fotografie na telefonu – ze šířky se najednou stane výška a naopak.


## Závěr

Gratuluji! Úspěšně jste se naučili, jak načíst a upravit rozměry stránky PDF pomocí Aspose.PDF for .NET. Nyní byste měli být schopni načíst PDF, zkontrolovat rozměry jeho stránky a v případě potřeby stránku dokonce otočit.

Manipulace s PDF nemusí být složitá. S Aspose.PDF je to tak jednoduché, jak následovat několik kroků a používat intuitivní metody. Takže až budete příště potřebovat zvládnout rozměry stránky PDF, budete přesně vědět, co máte dělat!

## FAQ

### Mohu stránku otočit o jiné úhly kromě 90 stupňů?
 Ano, Aspose.PDF vám umožňuje otáčet stránky o 0, 90, 180 nebo 270 stupňů pomocí`Rotation` vlastnictví.

### Co se stane, když můj PDF nemá žádné stránky?
 Pokud váš PDF nemá žádné stránky, můžete přidat prázdnou stránku pomocí`Pages.Add()` metodou, jak je uvedeno v tomto návodu.

### Mohu manipulovat s více stránkami najednou?
Ano, můžete procházet více stránkami a na všechny aplikovat transformace, jako je změna velikosti nebo otočení.

### Ovlivňují rozměry stránky obsah uvnitř PDF?
Rozměry stránky mění pouze velikost plátna, nikoli obsah. Změna velikosti však může změnit vzhled obsahu na stránce.

### Kde najdu další informace o Aspose.PDF pro .NET?
 Můžete navštívit[dokumentace zde](https://reference.aspose.com/pdf/net/) pro podrobnější informace a pokročilé případy použití.